### enumerate: 인덱스와 원소로 이루어진 tuple을 만들

넘버링 필요할 때 유용

- 사용하기
  ```python
  for i in enumerate(['A', 'B', 'C']):
      print(i)
  ```
- 인덱스와 원소를 다른 변수에 할당하고 싶으면
  ```python
  for i, letter in enumerate(['A', 'B', 'C']):
      print(i, letter)
  ```
- 시작 인덱스 변경
  ```python
  for i, letter in enumerate(['A', 'B', 'C'], start=1):
      print(i, letter)
  ```

참고 링크

- [링크](https://www.daleseo.com/python-enumerate/)
