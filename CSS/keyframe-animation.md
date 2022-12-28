### 키프레임 애니메이션 속성

| 속성 | 설명 | 속성 값 |
| --- | --- | --- |
| animation-name | 키프레임 애니메이션 이름 |  |
| animation-duration | 애니메이션 재생 시간, 또는 반복 루프 1회를 도는 시간 | 기본 값 0은 애니메이션 재생되지 않음. <br />"s"(초), "ms"(밀리초) 단위로 표현 가능. |
| animation-timing-function | 애니메이션 진행 속도, 또는 가속 방식을 지정. 미리 설정된 속도 커브 중 한가지를 선택. | linear | ease | ease-in | ease-out | ease-in-out | step-start | step-end | steps(int,start|end) | cubic-bezier(n,n,n,n) 중 한가지 선택 가능. |
| animation-delay | 애니메이션 시작 지연 시간. | 0s, 0ms, 미지정: 지연 없이 즉시 애니메이션 시작.<br />"s"(초), "ms"(밀리초) 2가지 단위 사용 가능 |
| animation-direction | 애니메이션 재생 방향 | normal: 정방향 재생<br />reverse: 역방향 재생<br />alternate: 정방향과 역방향으로 한 번씩 번갈아 재생(정 방향 시작)<br />alternate-reverse: 역방향과 정방향으로 한 번씩 번갈아 재생(역방향 시작) |
| animation-iteration-count | 애니메이션 반복 횟수 지정 | 양수: 정수로 횟수 표기. 횟수만큼 애니메이션 반복 실행 후 정지.<br />infinite: 무한 반복. |
| animation-fill-mode | 애니메이션 시작 전, 종료 후 적용할 CSS 스타일을 지정. "none"은 요소의 CSS 스타일을 유지하며, 그 외에는 키프레임 애니메이션의 CSS 스타일을 유지함. | none: 기본 값. 애니메이션 중이 아닌 경우, 요소의 CSS 스타일을 유지함.<br />forwards: 애니메이션 중이 아닌 경우, 애니메이션 마지막 키프레임의 CSS 스타일을 유지 함.<br />backwards: 애니메이션 중이 아닌 경우, 첫 번째 애니메이션 키프레임의 CSS 스타일을 유지 함.(지연 시간 포함)<br />both: 애니메이션 시작 전에는 첫 번째 애니메이션 키프레임을 유지하며, 종료 후에는 마지막 키프레임 애니메이션의 CSS 스타일을 유지함. "none" 과는 다름.<br />"none" 과 "backwards" 속성 값은 애니메이션 중이 아닌 경우 다른 화면을 표시할 수 있으므로 주의해야 함. |
| animation-play-state | 애니메이션의 초기 실행 상태를 결정.<br />웹페이지 로딩 후 애니메이션을 자동 실행할지 여부를 선택할 수 있음. | paused: 애니메이션이 일시 중지된 상태 유지<br />running: 애니메이션이 재생중인 상태. |


<br />

위 속성들은 animation 속성 하나로 표현 가능
- animation: name duration iteration-count timing-function  

다중 애니메이션 사용 시 쉼표로 구분해 나열
- animation: rotate 2s linear, scale 1s ease;
    - 위와 동일        
        animation-name: rotate, scale;       
        animation-duration: 2s, 1s;        
        animation-timing-function: linear, ease;        
- 같은 애니메이션 속성을 2개의 키프레임 애니메이션에 동시 적용한 경우, 애니메이션 채우기 모드("animation-fill-mode") 속성 값에 따라서 순서상 뒤쪽에 오는 키프레임 애니메이션의 것만 실행될 수도 있고, 2개의 키프레임 애니메이션 속성이 동시에 적용될 수도 있음 → 같은 속성이 중복되지 않도록 키프레임 애니메이션을 분할하거나, 시간 지연을 이용해 순차적으로 실행되도록 애니메이션을 작성하는 것이 좋음.

---

[CSS 애니메이션(animation) 속성 이해하기](https://blogpack.tistory.com/882#top)
