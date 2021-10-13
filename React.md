# Functional Component vs. Class Components

## Functional Component
함수형 컴포넌트가 가지는 특징(혹은 클래스형 컴포넌트와의 차이점)은 아래와 같이 나열할 수 있습니다.

함수형 컴포넌트는 기본적으로 클래스형 컴포넌트의 render함수입니다.
Functional components are just the render function of a class component.

Props에 접근하고 사용할 수 있지만, state를 가질 수는 없습니다.
You can use props in funtioncal components, but they can't have states.

lifecycle method를 사용할 수 없습니다. 따라서 UI에 집중하게 되고 app의 행동에는 크게 관여하지 않습니다.
You can't use lifecycle methods with functional components. Instead, they solely focus on the UI, no the behavior of the app.

this 키워드를 사용할 수 없습니다.
With functional component, you don't have a this keyword to use.

## Class Component
클래스형 함수는 ES6문법을 사용할 수 있습니다.
Class components make use of the ES6 class syntax.

따라서 componentWillMount 혹은 componentDidMount와 같은lifecycle 메소드를 사용할 수 있습니다.
Therefore, they can make use of lifecycle methods.

Class components는 React.Component에서 확장됩니다.
Class components extedn from React-Component.

props와 state 모두를 가지고 사용할 수 있으며, this 키워드를 사용해서 그들과 해당 컴포넌트 내에서 선언한 함수에 접근할 수 있다.
You have to use the this keyword to access props (and also other functions you declare inside the component).
