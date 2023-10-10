## switch문을 object로 바꾸기
- switch문의 case가 많은 경우 object로 표현하는 것이 코드가 훨씬 깔끔해진다! 

- switch case
    
    ```jsx
    background-color: ${({ region }) => {
      switch (region) {
        case "서울":
          return "#ff8285";
        case "부산":
          return "#FF9D7E";
        case "대구":
          return "#FFC289";
        case "인천":
          return "#FFDE88";
        case "광주":
          return "#AEE775";
        case "제주":
        default:
          return "#FA82A7";
      }
    }};
    ```
    
- object
    
    ```jsx
    background-color: ${({ region }) => {
      return {
        서울: "#FF8285",
        부산: "#FF9D7E",
        대구: "#FFC289",
        인천: "#FFD467",
        광주: "#AEE775",
        제주: "#FA82A7",
      }[region ?? "제주"];
    }};
    ```
