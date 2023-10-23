# Array.reduce 함수

: 배열의 각 요소에 대해 주어진 리듀서 (reducer) 함수를 실행하고, 하나의 결과값을 반환

`arr.reduce(callback[, initialValue])`로 사용

`arr.reduce((acc, cur) => (acc + cur), 0)` 

<br />

### 매개변수
- 배열의 각 요소에 대해 실행할 리듀서 함수(callback)
    - 의 인수들
        1. 누적값, 누산기 (accumulator): 콜백 함수의 반환값의 누적.
        2. 현재 값 (currentValue): 현재 처리할 값. 
        3. 현재 인덱스 (currentIndex): (Optional). initialValue를 사용한 경우 0, 아니면 1부터 시작. (initialValue 없으면 첫 번째(0번) 인덱스 건너뜀
        4. 원본 배열 (array): (Optional). reduce()를 호출한 원본 배열
- 초기값(initialValue): (Optional). 첫 번째 인수에 제공하는 값. 빈 배열에서 초기값 없이 reduce() 호출 시 오류 발생

<br />

### 사용 예시
- 덧셈 연산
  
  ```jsx
  const total = array.reduce(
    (accumulator, currentValue) => accumulator + currentValue,
    0,
  );
  ```
  
  ```jsx
  const sumValues1 = (obj) => Object.values(obj).reduce((a, b) => a + b, 0);
  
  sumValues({a: 4, b: 6, c: -5, d: 0}); // gives 5
  ```
  
- 중첩 배열 펼치기
  
  ```jsx
  const array = [
      [0, 1],
      [2, 3],
      [4, 5],
    ]
  const flattenedArray = array.reduce((accumulator, currentValue) => accumulator.concat(currentValue), []);
  ```
  
- 속성으로 객체 분류하기
  
  ```jsx
  const people = [
    { name: "Alice", age: 21 },
    { name: "Max", age: 20 },
    { name: "Jane", age: 20 },
  ];
  
  function groupBy(objectArray, property) {
    return objectArray.reduce((acc, obj) => {
      const key = obj[property];
      const curGroup = acc[key] ?? [];
  
      return { ...acc, [key]: [...curGroup, obj] };
    }, {});
  }
  
  const groupedPeople = groupBy(people, "age");
  console.log(groupedPeople);
  // {
  //   20: [
  //     { name: 'Max', age: 20 },
  //     { name: 'Jane', age: 20 }
  //   ],
  //   21: [{ name: 'Alice', age: 21 }]
  // }
  ```
  
- 기타 사용했던 방법들
  
  ```jsx
  const checkedItems = 
    selectedItems.reduce(
      (acc, { itemCode }) => ({ ...acc, [itemCode]: true }),
      {}
    )
  );
  ```
  
  ```jsx
  const totalPrice = useMemo(
    () =>
      changedSelectedItems.reduce((sum, { itemPrice, isChecked }) => {
        if (isChecked) {
          return sum + itemPrice;
        } else {
          return sum;
        }
      }, 0),
    [changedSelectedItems]
  );
  ```
        
    

---
### 참고 링크
[mdn docs](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)   
[How to sum the values of a JavaScript object?](https://stackoverflow.com/questions/16449295/how-to-sum-the-values-of-a-javascript-object)
