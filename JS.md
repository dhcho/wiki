# 자바스크립트 object 2개 비교하기(ES6, Lodash)

개발 도중에 JSON으로 된 Object 또는 일반 object에 특정 값이 변경 되었을 경우 비교하여 조건문을 걸고 싶은 경우
생각하지 못했던 결과를 얻게 되어서 정리를 해보겠습니다.
```
const k1 = {fruit: '🥝'};
const k2 = {fruit: '🥝'};

// Using JavaScript
JSON.stringify(k1) === JSON.stringify(k2); // true

// Using Lodash
_.isEqual(k1, k2); // true
```
- Deep Nested 비교
- 조금더 복잡하고 중첩되어진 Object를 비교하여도 제대로된 결과를 얻을수 있습니다.
```
const one = {
  fruit: '🥝',
  nutrients: {
    energy: '255kJ',
    minerals: {
      name: 'calcium'
    }
  }
};

const two = {
  fruit: '🥝',
  nutrients: {
    energy: '255kJ',
    minerals: {
      name: 'calcium'
    }
  }
};

// Using JavaScript
JSON.stringify(one) === JSON.stringify(two); // true

// Using Lodash
_.isEqual(one, two); // true
``` 

-결론
 1. 간단하고 Object 깊이가 깊지 않은 경우는 JSON.stringify()함수를 쓰고
 2. 깊고 복잡한 비교를 했을경우는 Lodash 방식인 isEqual함수를 쓰는것이 좋은것 같다.

- 결론 보충내용
  - JSON.stringify : string 비교를 하므로 Object 전체를 비교.
  - Lodash : Object 전체 비교하지 않고 비교 중 다른 부분이 있으면 함수 종료

 부록 내용: ES6 방법으로 entries를 이용하여서 비교 할 수도 있음
```
const k1 = {fruit: '🥝'};
const k2 = {fruit: '🥝'};

Object.entries(k1).toString() === Object.entries(k2).toString();
```
- ref: https://slee2540.tistory.com/49

# div contenteditable cursor focus
- https://akashicseer.com/web-development/javascript-and-contenteditable-how-to-move-the-cursor-to-the-end-of-user-input/

# JS 주석
/**
 * @description 전화번호를 입력하면 적합한 전화번호 형태로 변경해준다.
 * @param  {string} telNo ( 예 : 01000000000 )
 * @return {string} 010-0000-0000 형태의 전화번호
 * @example ( param: 01000000000 => return: "010-0000-0000" )
 */
export function commonTelNoFormat(telNo: string) {
  function isNumeric(val) {
    return /^-?\d+$/.test(val);
  }

  if (isNumeric(telNo.replace(/\-/g, ''))) {
    return telNo
      .replace(/[^0-9]/g, '')
      .replace(/(^02|^0505|^1[0-9]{3}|^0[0-9]{2})([0-9]+)?([0-9]{4})$/, '$1-$2-$3')
      .replace('--', '-');
  } else {
    return telNo;
  }
}

