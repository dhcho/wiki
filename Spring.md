# Spring Batch

배치 어플리케이션이란
간단하게 배치 어플리케이션이 무엇인지 정리해봅니다. 배치(batch) 는 일괄처리 라는 뜻을 갖고 있습니다. 즉, 요청이 들어오는 대로 응답을 보내주는 일반 웹 어플리케이션과 달리, 배치를 사용하면 큰 데이터를 한번에 처리하고, 해당 결과를 저장하거나 사용할 수 있습니다.

데이터에 손댈 일이 있으면 API 를 만들어서 계속 호출해서 사용하면 되는 거 아냐?

5만건, 10만건이 되는 데이터에 대해서 매번 API를 호출해서 처리를 한다면 실 서비스에 영향이 가게 됩니다. 클라이언트에서 사용자가 사용해야할 I/O 를 차지하게 되고, 서버에 부하를 유발하게 되죠.

이럴 때 배치 어플리케이션을 사용하게 됩니다.

## 본론 : Tasklet
간단하게 생각하면, Spring Batch에서는 Job이 있습니다. Job은 여러개의 Step으로 구성되고, Step 은 Tasklet(기능) 으로 구성됩니다. 배치 작업 하나가 Job에 해당 됩니다. 즉 다음과 같은 그림입니다.
<img src="https://github.com/dhcho/document/blob/main/images/springbatch%231.png"/>

그런데 저는 실행 전후에 하고 싶은 일이 있습니다. 이를 위해서 StepExecutionListener 를 함께 구현합니다. 이를 구현하면 beforeStep과 afterStep을 사용해서 Step 전후에 원하는 일을 할 수 있습니다.

차례대로 beforeStep, execute, afterStep 순으로 실행됩니다.

배치 어플리케이션은 기본적으로 1. 읽어서 2. 작업하고 3. 그 결과를 다시 저장하는 것이 대부분이기 때문에 제가 본 코드들은 대부분 item reader - processor - writer의 과정을 거칩니다.

다만 가볍고 몇줄되지 않는 작업이며, writer 가 불필요한 경우 tasklet으로 처리하는 것도 좋은 선택인 것 같습니다.

# Spring Scheduler
Spring Scheduler는 별도의 추가적인 의존성이 필요하지 않습니다. Spring Boot starter에 기본적인 의존성으로 제공됩니다. 사용하기 위해서는 @EnableScheduling 어노테이션을 붙여주면 됩니다.

```
@EnableScheduling
@SpringBootApplication
public class Application() {
    public static void main(String[] args) {
        SpringApplication.run(Application.class, args);
    }
}
```
이런 설정을 잡아 준 후 실제 사용은 아래와 같이 사용할 수 있습니다. @Scheduled 어노테이션 메서드에 붙여 주기만 하면 됩니다. 해당 어노테이션의 내부 값으로 scheduler가 실행 될 타이밍을 정할 수 있습니다. scheduling을 할 메서드는 2개의 조건을 가집니다.

method는 void의 return 타입을 가져야합니다.
method는 파라미터를 가질 수 없습니다.
그리고 아래처럼 사용할 수 있습니다. 내용은 각 주석을 봐 주시기 바랍니다.


```
public class Scheculer() {

    @Scheduled(fixedDelay = 1000) // scheduler 끝나는 시간 기준으로 1000 간격으로 실행
    public void scheduleFixedDelayTask() {
        System.out.println(
        "Fixed delay task - " + System.currentTimeMillis() / 1000);
    }

    @Scheduled(fixedRate = 1000) // scheduler 시작하는 시간 기준으로 1000 간격으로 실행
    public void scheduleFixedRateTask() {
        System.out.println(
        "Fixed rate task - " + System.currentTimeMillis() / 1000);
    }

    @Scheduled(cron = "0 15 10 15 * ?") // cron에 따라 실행
    public void scheduleTaskUsingCronExpression() {
        long now = System.currentTimeMillis() / 1000;
        System.out.println(
        "schedule tasks using cron jobs - " + now);
    }

    @Scheduled(cron = "0 15 10 15 * ?", zone = "Europe/Paris") // cron에 TimeZone 설정 추가
}
```

Scheduler는 기본적으로 thread 1개를 이용하여 동기 형식으로 진행됩니다. 즉 1번 스케줄이 끝나지 않으면 2번 스케줄이 시작시간이 되었다고 하더라도 시작되지 않습니다. 비동기 형식으로 진행하시고 싶으시다면 @EnableAsync 어노테이션을 이용할 수 있습니다.
