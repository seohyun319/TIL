### lambda로 n 번째 인덱스 기준 정렬하기

- 두 번째 원소, 오름차순
  ```python
  array.sort(key=lambda x: x[1])
  ```
- 두 번째 원소, 내림차순
  ```python
  array.sort(key=lambda x: -x[1])
  ```
- 첫 번째 원소로 오름차순, 첫 번째 원소 같으면 두 번째 원소로 오름차순
  ```python
  array.sort(key=lambda x: (x[0], x[1]))
  ```
- 첫 번째 원소로 내림차순, 첫 번째 원소 같으면 두 번째 원소로 오름차순
  ```python
  array.sort(key=lambda x: (-x[0], x[1]))
  ```

참고 링크

- [링크](https://leedakyeong.tistory.com/entry/python-%ED%8A%9C%ED%94%8C-%EC%A0%95%EB%A0%AC%ED%95%98%EA%B8%B0%EB%91%90-%EB%B2%88%EC%A7%B8-%EC%9B%90%EC%86%8C%EB%A1%9C-%EC%A0%95%EB%A0%AC%ED%95%98%EA%B8%B0-tuple-sorting-in-python)
