AWS 프리 티어를 사용하려면 계정을 우선 만들어야 합니다. 아래 링크에 접속합니다.

https://aws.amazon.com/free

 

“무료 계정 만들기”를 클릭합니다. 아래 웹페이지 화면은 추후 바뀔 가능성이 있습니다.

<img src="https://github.com/dhcho/document/blob/main/images/aws/%231.png"/>

로그인시 사용할 이메일 주소와 암호를 기입 후, 계속을 클릭하여 진행합니다.

<img src="https://github.com/dhcho/document/blob/main/images/aws/%232.png"/>

연락처 및 주소 정보를 기입 후, 계속을 클릭합니다.

<img src="https://github.com/dhcho/document/blob/main/images/aws/%233.png"/>

무료로 사용하는 것이지만 신용 카드 정보를 요구합니다.

<img src="https://github.com/dhcho/document/blob/main/images/aws/%234.png"/>

전화번호를 확인하는 절차가 필요합니다. 문자 메시지(SMS)를 사용했습니다.

<img src="https://github.com/dhcho/document/blob/main/images/aws/%235.png"/>

문자로 받은 코드를 입력합니다.

<img src="https://github.com/dhcho/document/blob/main/images/aws/%236.png"/>

“기본 지원 - 무료”가 선택된 상태에서 “가입 완료”를 클릭합니다.

<img src="https://github.com/dhcho/document/blob/main/images/aws/%237.png"/>

가입이 완료되었습니다. 

“AWS Management Console로 이동”을 클릭합니다.

<img src="https://github.com/dhcho/document/blob/main/images/aws/%238.png"/>

로그인이 필요합니다.

“루트 사용자”가 선택된 상태에서 가입시 사용한 이메일 주소를 입력하고 다음을 클릭합니다.

<img src="https://github.com/dhcho/document/blob/main/images/aws/%239.png"/>

오른쪽 상단에 보이는 리전을 서울로 변경합니다.

 

유료로 사용할 계획이 있는 경우, 선택한 지역 리전에 따라 가격이 다르다고하니 가격 정책을 확인하고 리전을 선택하세요.

<img src="https://github.com/dhcho/document/blob/main/images/aws/%2310.png"/>

“가상 머신 시작”을 클릭합니다.

<img src="https://github.com/dhcho/document/blob/main/images/aws/%2311.png"/>
          
          
왼쪽에 보이는 “프리 티어만”을 선택하면 무료로 사용 가능한 Amazon Machine Image만 보입니다. 

“Ubuntu Server 20.04 LTS”에 있는 선택을 클릭합니다. 다른 것을 선택해도 무방합니다.

<img src="https://github.com/dhcho/document/blob/main/images/aws/%2312.png"/>

“프리 티어 사용 가능”  이라고 표시된 t2.micro가 선택되어 있는 상태입니다. 

아쉽게도 1년동안 무료로 사용가능한 t2.micro는 GPU가 없다네요.

<img src="https://github.com/dhcho/document/blob/main/images/aws/%2313.png"/>

오른쪽 아래에 보이는 “검토 및 시작”을 클릭합니다.

<img src="https://github.com/dhcho/document/blob/main/images/aws/%2314.png"/>

“시작하기”를 클릭합니다.

<img src="https://github.com/dhcho/document/blob/main/images/aws/%2315.png"/>

“새 키 페어 생성”을 선택한 후, 아래 보이는 “키 페어 이름”에 적당한 이름을 적습니다. 

“키 페어 다운로드”를 클릭합니다. 이름이 “키 페어 이름”에 적은 것이고 확장자가 pem인 파일이 다운로드 됩니다.

<img src="https://github.com/dhcho/document/blob/main/images/aws/%2316.png"/>

“인스턴스 시작”을 클릭합니다.

<img src="https://github.com/dhcho/document/blob/main/images/aws/%2317.png"/>

인스턴스 생성이 완료되었습니다. 

“예상 요금 알림 받기” 항목에 있는 “결제 알림 생성”을 클릭하여 금액이 크게 결재되는 것을

 방지합니다.
 
<img src="https://github.com/dhcho/document/blob/main/images/aws/%2318.png"/>
 
 세가지 항목을 체크하고 이메일 주소를 적은 후, “기본 설정 저장”을 클릭하면 됩니다.
 
<img src="https://github.com/dhcho/document/blob/main/images/aws/%2319.png"/>
 
아래 웹페이지로 돌아와 “인스턴스 보기”를 클릭합니다.
 
<img src="https://github.com/dhcho/document/blob/main/images/aws/%2320.png"/>
 
인스턴스 상태가 “실행 중”입니다. 

사용하지 않을 때에는 인스턴스 상태를 중지로 바꾸는게 좋을 듯합니다.

<img src="https://github.com/dhcho/document/blob/main/images/aws/%2321.png"/>

고정 IP를 할당받아야 합니다. 왼쪽 메뉴에서 “탄력적 IP”를 선택합니다.

# 이 부분은 추가 요금이 할당되니 주의하세요.

<img src="https://github.com/dhcho/document/blob/main/images/aws/%2322.png"/>

“탄력적 IP 주소 할당”을 클릭합니다.

<img src="https://github.com/dhcho/document/blob/main/images/aws/%2323.png"/>

할당을 클릭합니다.

<img src="https://github.com/dhcho/document/blob/main/images/aws/%2324.png"/>

다음처럼 할당된 IPv4 주소를 확인할 수 있습니다.

<img src="https://github.com/dhcho/document/blob/main/images/aws/%2325.png"/>

작업에서 “탄력적 IP 주소 연결”을 선택합니다.

<img src="https://github.com/dhcho/document/blob/main/images/aws/%2326.png"/>

인스턴스와 프라이빗 IP 주소를 선택하고 연결을 클릭합니다.

<img src="https://github.com/dhcho/document/blob/main/images/aws/%2327.png"/>
