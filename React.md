## π¦ What is Webpack?
* μΉν©μ λͺ¨λ λ²λ€λ¬(Module Bundler)μλλ€. μ½λ©ν  λ νΈμλ₯Ό μν΄ μ¬λ¬ κ°μ λͺ¨λλ‘ λλ μ μμνλ κ²½μ°κ° λ§μ΅λλ€. νμ§λ§ λΈλΌμ°μ μμ νμΌ λ¨μ λͺ¨λ μμ€νμ μ΄μ©νλ κ²μ λ§μ λ€νΈμν¬ λΉμ© λ­λΉλ₯Ό μ λ°ν  μ μμ΅λλ€. μ΄λ¬ν λ¬Έμ  λλ¬Έμ μ¬λ¬ κ°μ λͺ¨λμ νλμ νμΌλ‘ λ¬Άμ΄μ λ³΄λΌ λͺ¨λ λ²λ€λ¬κ° νμν©λλ€. μ¬κΈ°μ μΉν©μ΄ λ±μ₯ν©λλ€. μΉν©μμλ μλ°μ€ν¬λ¦½νΈ, μ€νμΌμνΈ, μ΄λ―Έμ§ λ± λͺ¨λ  κ²μ λͺ¨λλ‘ λ΄λλ€. μ΄λ° μΉν©μλ μ€μν μμ±μ΄ 4κ°μ§ μμ΅λλ€.

1. Entry:
    entry λ μΉν©μμ μΉ μμμ λ³ννκΈ° μν΄ νμν μ΅μ΄ μ§μμ  μ΄μ μλ°μ€ν¬λ¦½νΈ νμΌ κ²½λ‘ μλλ€. μΉν©μ entry λ₯Ό ν΅ν΄μ λͺ¨λμ λ‘λ©νκ³  νλμ νμΌλ‘ λ¬Άμ΅λλ€.
2. Output:
    μΉν©μμ entry λ‘ μ°Ύμ λͺ¨λμ νλλ‘ λ¬Άμ κ²°κ³Όλ¬Όμ λ°νν  μμΉμλλ€.
3. Loader:
    μΉν©μ κΈ°λ³Έμ μΌλ‘ μλ°μ€ν¬λ¦½νΈμ JSON λ§ λΉλν  μ μμ΅λλ€. μλ°μ€ν¬λ¦½νΈκ° μλ λ€λ₯Έ μμ (HTML, CSS, Image)λ₯Ό λΉλν  μ μλλ‘ λμμ£Όλ μμ±μλλ€.
4. Plugin:
    plugin μ μΉν©μ κΈ°λ³Έμ μΈ λμ μΈ μΆκ°μ μΈ κΈ°λ₯μ μ κ³΅νλ μμ±μλλ€. loader λ νμΌμ ν΄μνκ³  λ³ννλ κ³Όμ μ κ΄μ¬νκ³ , plugin μ κ²°κ³Όλ¬Όμ ννλ₯Ό λ°κΎΈλ μ­ν μ ν©λλ€.

## π About Babel
* λ°λ²¨μ μλ°μ€ν¬λ¦½νΈ es6 λ¬Έλ²μ es5λ‘ λ³νν΄μ£Όλ νΈλ μ€νμΌλ¬(transpiler) μλλ€. μ΄κ²μ ν΅ν΄ Reactλ₯Ό μΌλ° λΈλΌμ°μ μμ μ€νμν¬ μ μμ΅λλ€. babel κ³΅μ μ¬μ΄νΈμμ κ°λ¨νκ² es6 λ¬Έλ²μΌλ‘ λ³νλ μλ°μ€ν¬λ¦½νΈ μ½λλ₯Ό νμΈν  μ μμ΅λλ€.

# Functional Component vs. Class Components

## ν΄λμ€ν
1. state, lifeCycle κ΄λ ¨ κΈ°λ₯μ μ¬μ©κ°λ₯νλ€.
2. λ©λͺ¨λ¦¬ μμμ ν¨μν μ»΄ν¬λνΈλ³΄λ€ μ‘°κΈ λ μ¬μ©νλ€.
3. μμ λ©μλλ₯Ό μ μν  μ μλ€.

## ν¨μν
1. state, lifeCycle κ΄λ ¨ κΈ°λ₯μ¬μ© λΆκ°λ₯ [Hookμ ν΅ν΄ ν΄κ²° λ¨]
2. λ©λͺ¨λ¦¬ μμμ ν¨μν μ»΄ν¬λνΈλ³΄λ€ λ μ¬μ©νλ€.
3. μ»΄ν¬λνΈ μ μΈμ΄ νΈνλ€.


# Recoil - λ λ€λ₯Έ React μν κ΄λ¦¬ λΌμ΄λΈλ¬λ¦¬
<img src="https://github.com/dhcho/document/blob/main/images/recoil.jpeg">
Recoilμ λ¬΄μμ΄ λ€λ₯ΌκΉ?
μ°μ  μ²«λ²μ§Έ, Recoilμ λ°°μ°κΈ° μ½λ€. APIκ° λ¨μνκ³  μ΄λ―Έ hookμ μ¬μ©νκ³  μλ μ¬λλ€μκ² μ΅μν  κ²μ΄λ€. Recoilμ μμνκΈ° μν΄μλ μ΄νλ¦¬μΌμ΄μμ RecoilRootλ‘ κ°μΈκ³ , λ°μ΄ν°λ₯Ό atomμ΄λΌλ λ¨μλ‘ μ μΈνμ¬ useStateλ₯Ό Recoilμ useRecoilStateλ‘ λμ²΄ν΄μΌ νλ€.

λλ²μ§Έ, μ»΄ν¬λνΈκ° μ¬μ©νλ λ°μ΄ν° μ‘°κ°λ§ μ¬μ©ν  μ μκ³ , κ³μ°λ selectorλ₯Ό μ μΈν  μ μμΌλ©°, λΉλκΈ° λ°μ΄ν° νλ¦μ μν λ΄μ₯ μλ£¨μκΉμ§ μ κ³΅νλ€.

λμ  ν€λ‘ atomμ λ§λ€κ³ , selectorμ μΈμλ₯Ό λ³΄λ΄λ λ± λͺ¨λ κ°λ¨νκ² ν  μ μλ€.

κ·Έλ¦¬κ³  μμμ λ§ν λ°μ κ°μ΄ κ³§ React λμμ± λͺ¨λμ λν μ§μλ λ  κ²μ΄λ€.

Recoilμ κΈ°λ³ΈλΆν° μμν΄λ³΄μ
Atom β atomμ νλμ μνμλΌκ³  λ³Ό μ μλ€. μ»΄ν¬λνΈκ° κ΅¬λν  μ μλ React stateλΌκ³  μκ°νλ©΄ λλ€. atomμ κ°μ λ³κ²½νλ©΄ κ·Έκ²μ κ΅¬λνκ³  μλ μ»΄ν¬λνΈλ€μ΄ λͺ¨λ λ€μ λ λλ§λλ€. atomμ μμ±νκΈ° μν΄ μ΄νλ¦¬μΌμ΄μμμ κ³ μ ν ν€ κ°κ³Ό λν΄νΈ κ°μ μ€μ ν΄μΌνλ€. λν΄νΈ κ°μ μ μ μΈ κ°, ν¨μ λλ μ¬μ§μ΄ λΉλκΈ° ν¨μ(λμ€μ μ§μ μμ )κ° λ  μ μλ€.
```
export const nameState = atom({
  key: 'nameState',
  default: 'Jane Doe'
});
```
useRecoilState β atomμ κ°μ κ΅¬λνμ¬ μλ°μ΄νΈν  μ μλ hook. useStateμ λμΌν λ°©μμΌλ‘ μ¬μ©ν  μ μλ€.

useRecoilValue β setter ν¨μ μμ΄ atomμ κ°μ λ°νλ§ νλ€.

useSetRecoilState β setter ν¨μλ§ λ°ννλ€.
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
selector β seletorλ μνμμ νμλ λ°μ΄ν°λ‘, λ€λ₯Έ atomμ μμ‘΄νλ λμ μΈ λ°μ΄ν°λ₯Ό λ§λ€ μ μκ² ν΄μ€λ€. Recoilμ selectorλ κΈ°μ‘΄μ μ°λ¦¬κ° μλ selectorμ κ°λκ³Όλ μ‘°κΈ λ€λ₯΄λ€. Reduxμ reselectμ MobXμ @computedμ²λΌ λμνλ "get" ν¨μλ₯Ό κ°μ§κ³  μλ€. νμ§λ§ νλ μ΄μμ atomμ μλ°μ΄νΈ ν  μ μλ "set" ν¨μλ₯Ό μ΅μμΌλ‘ λ°μ μ μλ€. μ΄ λΆλΆμ λμ€μ λ€λ£° νλ, μΌλ¨ "selector" λΆλΆλ§ μ΄ν΄λ³΄μ.
```
// λλ¬Ό λͺ©λ‘ μν
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
// νν°λ§ λλ¬Ό μν
const animalFilterState = atom({
 key: 'animalFilterState',
 default: 'dog',
});
// νμλ λλ¬Ό νν°λ§ λͺ©λ‘
const filteredAnimalsState = selector({
 key: 'animalListState',
 get: ({get}) => {
   const filter = get(animalFilterState);
   const animals = get(animalsState);
   
   return animals.filter(animal => animal.type === filter);
 }
});
// νν°λ§λ λλ¬Ό λͺ©λ‘μ μ¬μ©νλ μ»΄ν¬λνΈ
const Animals = () => {
  const animals = useRecoilValue(filteredAnimalsState);
  return animals.map(animal => (<div>{ animal.name }, { animal.type    }</div>));
}
```

# Reactμμ div contentEditable μ¬μ©νκΈ°

contentEditableμ HTML μμλ₯Ό μμ  κ°λ₯νκ² λ§λ€μ΄μ£Όλ μμ±μ΄λ€. μλ₯Ό λ€μ΄, divμ contenteditable μμ±μ trueλ‘ μ€μ ν΄μ£Όλ©΄ div μμλ inputμ²λΌ μλ ₯μ ν  μ μκ² λλ€.
contentEditableμ μ¬μ©νλ μ΄μ λ μΉ μλν°λ₯Ό μ½κ² λ§λ€κΈ° μν¨μ΄λ€. 
contentEditableμ μ¬μ©νλ©΄ λΈλΌμ°μ κ° μμ²΄μ μΌλ‘ ν΄λ¦½λ³΄λ, λλκ·Έ&λλ‘­, μ€ν μ·¨μ, μμκ³Ό κ°μ κΈ°λ₯μ μ λΆ μ κ³΅ν΄μ€λ€. 
λν, νΉμ  λ΄μ©μ νΈμ§ λͺ¨λλ‘ μμ νκΈ° μ½λ€λ μ₯μ μ΄ μλ€. 
νΈμ§ λͺ¨λ λ³κ²½ μ inputμ΄λ textareaλ‘ μμ ν  νμμμ΄ κ°λ¨νκ² contentEditable=true μμ±λ§ μΆκ°ν΄μ€λ νΈμ§ λͺ¨λλ‘ λ³κ²½ν  μ μλ€. 
λλ¬Έμ divλ₯Ό inputμΌλ‘ λ°κΏ¨μ λ λ°μν  μ μλ μ€νμΌ λ³κ²½μ μ κ²½μ°μ§ μμλ λμ΄ νΈλ¦¬νλ€.

### div element
<img src="https://github.com/dhcho/wiki/blob/main/images/React/1.png?raw=true">

### div contentEditable={true}
<img src="https://github.com/dhcho/wiki/blob/main/images/React/2.png?raw=true">

νμ§λ§ contentEditableμ Reactμμ μ¬μ©ν  λ κ½€λ λ¬Έμ κ° λ§μλ€. 
inputκ³Ό λμ λ°©μμ΄ λ€λ₯΄κΈ° λλ¬Έμ΄λ€. 
λ¨Όμ , μλ ₯ μ change eventκ° μλλΌ input eventκ° λμνλ€. 
λν, inputμ΄ μλκΈ° λλ¬Έμ value κ°μ΄ μλ€. 
μ΄ λλ¬Έμ μ μ΄ μ»΄ν¬λνΈμ²λΌ λ¦¬μ‘νΈκ° DOMμ μ μ΄ν  μκ° μλ€.

λ°λΌμ λΉμ μ΄ μ»΄ν¬λνΈ λ°©μμΌλ‘ contentEditableμ κ΄λ¦¬ν΄μ€μΌ νλ€.

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

contentEditable DOMμ μ κ·ΌνκΈ° μν refμ μνλ₯Ό μ μ₯νκΈ° μν useStateλ₯Ό μΆκ°νλ€. μνμλ contentEditableμ innerTextκ° μ μ₯λλ€. 
λΉμ μ΄ μ»΄ν¬λνΈμ΄κΈ° λλ¬Έμ μν κ°μ μ μ₯ν  νμκ° μλ€κ³  μκ°λ  μ μμ§λ§ μλ ₯κ°μ μ¦κ°μ μΌλ‘ validation νκΈ° μν΄ μΆκ°νμλ€.
contentEditableμ inputμ μλμ§λ§ element.focus() λ©μλλ₯Ό μ¬μ©νμ¬ ν¬μ»€μ€λ₯Ό μ€ μ μλ€. 
νμ§λ§ μ΄λ κ² ν¬μ»€μ€λ₯Ό μ£Όκ² λλ κ²½μ°, contentEditableμ μμ±λ λ΄μ©μ΄ μμ΄λ ν¬μ»€μ€κ° λ§¨ μμͺ½μ μμΉνκ² λλ€. 
μΌλ°μ μΌλ‘ inputμ ν¬μ»€μ€λ₯Ό μ£Όλ©΄ μμ±λ λ΄μ©μ κ°μ₯ λ€λ‘ κ°λ κ²κ³Όλ λμ‘°μ μ΄λ€. 
λ°λΌμ λ³λμ focus ν¨μλ₯Ό λ§λ€μ΄ μ¬μ©ν΄μΌ νλ€.

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

λ§μ½ contentEditableμ innerTextμ κΈΈμ΄κ° 0μ΄λΌλ©΄ μμ±λ λ΄μ©μ΄ μλ€λ κ²μ΄λ―λ‘ focusλ₯Ό μ¬μ©ν΄λ λλ€. 
νμ§λ§ μμ±λ λ΄μ©μ΄ μλ κ²½μ°μλ ν¬μ»€μ€λ₯Ό κ°μ₯ λ€μͺ½μ λΆμ΄κΈ° μν΄ νμ¬ Caret(μ»€μ)μ μμΉλ₯Ό λ³κ²½ν΄μ€μΌ νλ€. 
caretμ μμΉλ₯Ό μ°Ύκ³  contentEditableμ range(λλκ·Έ λ μμ­)λ₯Ό λ§¨ λμΌλ‘ μ΄λμν¨λ€. 
λ§μ§λ§μΌλ‘ κΈ°μ‘΄ rangeλ₯Ό μ­μ νκ³  μλ‘μ΄ rangeλ₯Ό μΆκ°ν¨μΌλ‘μ¨ contentEditable λ΄μ© λμ μ»€μλ₯Ό μμΉ μν¬ μ μλ€.

origin link : https://yung-developer.tistory.com/109

# λ¦¬μ‘νΈ μ½λ© μ»¨λ²€μ
- https://3-stack.tistory.com/53
- https://velog.io/@welloff_jj/React-Design-Pattern-Presentational-and-Container-Atomic-Design
