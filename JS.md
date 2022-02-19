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
