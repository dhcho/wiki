## 📦 What is Webpack?
* 웹팩은 모듈 번들러(Module Bundler)입니다. 코딩할 때 편의를 위해 여러 개의 모듈로 나눠서 작업하는 경우가 많습니다. 하지만 브라우저에서 파일 단위 모듈 시스템을 이용하는 것은 많은 네트워크 비용 낭비를 유발할 수 있습니다. 이러한 문제 때문에 여러 개의 모듈을 하나의 파일로 묶어서 보낼 모듈 번들러가 필요합니다. 여기서 웹팩이 등장합니다. 웹팩에서는 자바스크립트, 스타일시트, 이미지 등 모든 것을 모듈로 봅니다. 이런 웹팩에는 중요한 속성이 4가지 있습니다.

1. Entry:
    entry 는 웹팩에서 웹 자원을 변환하기 위해 필요한 최초 진입점 이자 자바스크립트 파일 경로 입니다. 웹팩은 entry 를 통해서 모듈을 로딩하고 하나의 파일로 묶습니다.
2. Output:
    웹팩에서 entry 로 찾은 모듈을 하나로 묶은 결과물을 반환할 위치입니다.
3. Loader:
    웹팩은 기본적으로 자바스크립트와 JSON 만 빌드할 수 있습니다. 자바스크립트가 아닌 다른 자원 (HTML, CSS, Image)를 빌드할 수 있도록 도와주는 속성입니다.
4. Plugin:
    plugin 은 웹팩의 기본적인 동작 외 추가적인 기능을 제공하는 속성입니다. loader 는 파일을 해석하고 변환하는 과정에 관여하고, plugin 은 결과물의 형태를 바꾸는 역할을 합니다.

## 🔍 About Babel
* 바벨은 자바스크립트 es6 문법을 es5로 변환해주는 트렌스파일러(transpiler) 입니다. 이것을 통해 React를 일반 브라우저에서 실행시킬 수 있습니다. babel 공식 사이트에서 간단하게 es6 문법으로 변환된 자바스크립트 코드를 확인할 수 있습니다.

# Functional Component vs. Class Components

## 클래스형
1. state, lifeCycle 관련 기능을 사용가능하다.
2. 메모리 자원을 함수형 컴포넌트보다 조금 더 사용한다.
3. 임의 메서드를 정의할 수 있다.

## 함수형
1. state, lifeCycle 관련 기능사용 불가능 [Hook을 통해 해결 됨]
2. 메모리 자원을 함수형 컴포넌트보다 덜 사용한다.
3. 컴포넌트 선언이 편하다.


# Recoil - 또 다른 React 상태 관리 라이브러리
<img src="https://github.com/dhcho/document/blob/main/images/recoil.jpeg">
Recoil은 무엇이 다를까?
우선 첫번째, Recoil은 배우기 쉽다. API가 단순하고 이미 hook을 사용하고 있는 사람들에게 익숙할 것이다. Recoil을 시작하기 위해서는 어플리케이션을 RecoilRoot로 감싸고, 데이터를 atom이라는 단위로 선언하여 useState를 Recoil의 useRecoilState로 대체해야 한다.

두번째, 컴포넌트가 사용하는 데이터 조각만 사용할 수 있고, 계산된 selector를 선언할 수 있으며, 비동기 데이터 흐름을 위한 내장 솔루션까지 제공한다.

동적 키로 atom을 만들고, selector에 인자를 보내는 등 모두 간단하게 할 수 있다.

그리고 앞에서 말한 바와 같이 곧 React 동시성 모드에 대한 지원도 될 것이다.

Recoil의 기본부터 시작해보자
Atom — atom은 하나의 상태의라고 볼 수 있다. 컴포넌트가 구독할 수 있는 React state라고 생각하면 된다. atom의 값을 변경하면 그것을 구독하고 있는 컴포넌트들이 모두 다시 렌더링된다. atom을 생성하기 위해 어플리케이션에서 고유한 키 값과 디폴트 값을 설정해야한다. 디폴트 값은 정적인 값, 함수 또는 심지어 비동기 함수(나중에 지원 예정)가 될 수 있다.
```
export const nameState = atom({
  key: 'nameState',
  default: 'Jane Doe'
});
```
useRecoilState — atom의 값을 구독하여 업데이트할 수 있는 hook. useState와 동일한 방식으로 사용할 수 있다.

useRecoilValue — setter 함수 없이 atom의 값을 반환만 한다.

useSetRecoilState — setter 함수만 반환한다.
```
import {nameState} from './someplace'
// useRecoilState
const NameInput = () => {
  const [name, setName] = useRecoilState(nameState);
  const onChange = (event) => {
   setName(event.target.value);
  };
  return <>
   <input type="text" value={name} onChange={onChange} />
   <div>Name: {name}</div>
  </>;
}
// useRecoilValue
const SomeOtherComponentWithName = () => {
  const name = useRecoilValue(nameState);
  return <div>{name}</div>;
}
// useSetRecoilState  
const SomeOtherComponentThatSetsName = () => {
  const setName = useSetRecoilState(nameState);
  return <button onClick={() => setName('Jon Doe')}>Set Name</button>;
}
```
selector — seletor는 상태에서 파생된 데이터로, 다른 atom에 의존하는 동적인 데이터를 만들 수 있게 해준다. Recoil의 selector는 기존에 우리가 알던 selector의 개념과는 조금 다르다. Redux의 reselect와 MobX의 @computed처럼 동작하는 "get" 함수를 가지고 있다. 하지만 하나 이상의 atom을 업데이트 할 수 있는 "set" 함수를 옵션으로 받을 수 있다. 이 부분은 나중에 다룰 테니, 일단 "selector" 부분만 살펴보자.
```
// 동물 목록 상태
const animalsState = atom({
  key: 'animalsState',
  default: [{
    name: 'Rexy',
    type: 'Dog'
  }, {
    name: 'Oscar',
    type: 'Cat'
  }],
});
// 필터링 동물 상태
const animalFilterState = atom({
 key: 'animalFilterState',
 default: 'dog',
});
// 파생된 동물 필터링 목록
const filteredAnimalsState = selector({
 key: 'animalListState',
 get: ({get}) => {
   const filter = get(animalFilterState);
   const animals = get(animalsState);
   
   return animals.filter(animal => animal.type === filter);
 }
});
// 필터링된 동물 목록을 사용하는 컴포넌트
const Animals = () => {
  const animals = useRecoilValue(filteredAnimalsState);
  return animals.map(animal => (<div>{ animal.name }, { animal.type    }</div>));
}
```

# React에서 div contentEditable 사용하기

contentEditable은 HTML 요소를 수정 가능하게 만들어주는 속성이다. 예를 들어, div에 contenteditable 속성을 true로 설정해주면 div 요소도 input처럼 입력을 할 수 있게 된다.
contentEditable을 사용하는 이유는 웹 에디터를 쉽게 만들기 위함이다. 
contentEditable을 사용하면 브라우저가 자체적으로 클립보드, 드래그&드롭, 실행 취소, 서식과 같은 기능을 전부 제공해준다. 
또한, 특정 내용을 편집 모드로 수정하기 쉽다는 장점이 있다. 
편집 모드 변경 시 input이나 textarea로 수정할 필요없이 간단하게 contentEditable=true 속성만 추가해줘도 편집 모드로 변경할 수 있다. 
때문에 div를 input으로 바꿨을 때 발생할 수 있는 스타일 변경을 신경쓰지 않아도 되어 편리하다.

### div element
<img src="https://github.com/dhcho/wiki/blob/main/images/React/1.png?raw=true">

### div contentEditable={true}
<img src="https://github.com/dhcho/wiki/blob/main/images/React/2.png?raw=true">

하지만 contentEditable은 React에서 사용할 때 꽤나 문제가 많았다. 
input과 동작 방식이 다르기 때문이다. 
먼저, 입력 시 change event가 아니라 input event가 동작한다. 
또한, input이 아니기 때문에 value 값이 없다. 
이 때문에 제어 컴포넌트처럼 리액트가 DOM을 제어할 수가 없다.

따라서 비제어 컴포넌트 방식으로 contentEditable을 관리해줘야 한다.

```
export const useContentEditable = (initialContent: string) => {
  const $contentEditable = useRef<HTMLDivElement | null>(null);
  const [content, _setContent] = useState(initialContent);
 
  const onInput = (event: ChangeEvent<HTMLDivElement>) => {
    _setContent(event.target.innerText);
  };
 
  const setContent = (newContent: string) => {
    if ($contentEditable.current) {
      $contentEditable.current.innerText = newContent;
      _setContent(newContent);
    }
  };
 
  useEffect(() => {
    setContent(initialContent);
  }, []);
 
  return { content, setContent, onInput, $contentEditable };
};
```

contentEditable DOM에 접근하기 위한 ref와 상태를 저장하기 위한 useState를 추가한다. 상태에는 contentEditable의 innerText가 저장된다. 
비제어 컴포넌트이기 때문에 상태 값을 저장할 필요가 없다고 생각될 수 있지만 입력값을 즉각적으로 validation 하기 위해 추가하였다.
contentEditable은 input은 아니지만 element.focus() 메서드를 사용하여 포커스를 줄 수 있다. 
하지만 이렇게 포커스를 주게 되는 경우, contentEditable에 작성된 내용이 있어도 포커스가 맨 앞쪽에 위치하게 된다. 
일반적으로 input에 포커스를 주면 작성된 내용의 가장 뒤로 가는 것과는 대조적이다. 
따라서 별도의 focus 함수를 만들어 사용해야 한다.

```
export const focusContentEditableTextToEnd = (element: HTMLElement) => {
  if (element.innerText.length === 0) {
    element.focus();
 
    return;
  }
 
  const selection = window.getSelection();
  const newRange = document.createRange();
  newRange.selectNodeContents(element);
  newRange.collapse(false);
  selection?.removeAllRanges();
  selection?.addRange(newRange);
};
```

만약 contentEditable의 innerText의 길이가 0이라면 작성된 내용이 없다는 것이므로 focus를 사용해도 된다. 
하지만 작성된 내용이 있는 경우에는 포커스를 가장 뒤쪽에 붙이기 위해 현재 Caret(커서)의 위치를 변경해줘야 한다. 
caret의 위치를 찾고 contentEditable의 range(드래그 된 영역)를 맨 끝으로 이동시킨다. 
마지막으로 기존 range를 삭제하고 새로운 range를 추가함으로써 contentEditable 내용 끝에 커서를 위치 시킬 수 있다.

origin link : https://yung-developer.tistory.com/109

# 리액트 코딩 컨벤션
- https://3-stack.tistory.com/53
- - https://velog.io/@welloff_jj/React-Design-Pattern-Presentational-and-Container-Atomic-Design
