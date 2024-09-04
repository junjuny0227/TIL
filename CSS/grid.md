# Grid

Grid는 두 방향(가로,세로) 레이아웃 시스템이다.

```css
display: grid;
```

1. 기본 설명

   1. 용어 정리

      1. row : 가로줄(행)
      2. column \*\*\*\*: 세로줄(열)
      3. Grid container : display: grid를 적용하는 Grid의 전체 영역
      4. Grid item : Grid 컨테이너의 자식 요소
      5. Grid cell : Grid의 한 칸을 가리키는 말
      6. Grid line : Grid 셀을 구분하는 선
      7. Grid number : Grid 라인의 각 번호
      8. Grid gap : Grid 셀 사이의 간격
      9. Grid area : Grid 라인으로 둘러싸인 사각형 영역, grid 셀의 집합

      > 출처 : 1분코딩
      >
      > <img src="https://studiomeal.com/wp-content/uploads/2020/01/03-2.jpg" width="70%" height="70%"/>

   2. 추가 설명
      1. 크롬 개발자 도구를 이용하면 grid를 확인할 수 있다.
      2. 컨테이너가 Grid의 영향을 받는 전체 공간이고, 설정된 속성에 따라 각각의 아이템들이 어떤 형태로 배치되는 것이다.

2. 속성들

   1. 기본 속성

      1. grid-template-columns / grid-template-rows

         Grid의 행과 열을 정의하는 핵심 속성이다. 이 둘을 지정하면 Grid cell이 생성된다.

         ```css
         .container {
         	grid-template-columns: 100px 100px 100px
         	grid-template-rows: 100px 100px 100px
         ```

         위와 같이 작성하면 100px 크기의 3행 \* 3열의 Grid가 생성된다.

         ```css
         .container {
         	grid-template-columns: repeat(3, 100px)
         	grid-template-rows: repeat(3, 100px)
         ```

         위와 같이 repeat를 사용하면 더욱 간편하게 Grid를 생성할 수 있다.

      2. grid-column-gap / grid-row-gap

         ```css
         .container {
           grid-column-gap: 10px;
           grid-row-gap: 10px;
         }
         ```

         위와 같이 작성하면 cell의 간격이 행과 행, 열과 열의 간격이 10px이 된다.

      3. grid-template-areas

         ```css
         .container {
           grid-template-areas:
             "header header header"
             "nav main main"
             "footer footer footer";
         }

         .header {
           grid-area: header;
         }
         .nav {
           grid-area: nav;
         }
         .main {
           grid-area: main;
         }
         .footer {
           grid-area: footer;
         }
         ```

         위와 같이 작성하면 Grid의 레이아웃의 이름을 붙이고, 그 이름을 이용하여 배치가 가능하다.

      4. grid-auto-rows / grid-auto-columns

         ```css
         .container {
           grid-auto-rows: 100px;
           grid-auto-columns: 200px;
         }
         ```

         auto는 자동으로 생성되는 행과 열의 크기를 정의한다.

      5. grid-auto-flow

         ```css
         .container {
           grid-auto-flow: row; /* 기본값, 행 우선 배치 */
           grid-auto-flow: column; /* 열 우선 배치 */
           grid-auto-flow: dense; /* 촘촘하게 배치 */
         }
         ```

         auto-flow는 자동으로 배치되는 아이템의 흐름을 설정한다.

   2. 정렬속성

      1. justify / align-items (가로/세로 방향 정렬)

         아이템들을 세로/가로 (row축/column축) 방향으로 정렬하며 컨테이너에 적용한다.

         ```css
         .container {
           justify-items: stretch / start / center / end;
           align-items: stretch / start / center / end;
         }
         ```

         - stretch : 항목들을 채우도록 크기를 조정
         - start : 항목들을 시작 위치로 정렬
         - center : 항목들을 중앙에 정렬
         - end : 항목들을 끝 위치로 정렬

      2. justify / align-self (개별 아이템 가로/세로 정렬)

         해당 아이템을 세로/가로 (row축/column축) 방향으로 정렬하며 아이템에 적용한다.

         ```css
         .item {
           align-self: stretch / start / center / end;
           justify-self: stretch / start / center / end;
         }
         ```

         - stretch : 항목을 채우도록 크기를 조정
         - start : 항목을 시작 위치로 정렬
         - center : 항목을 중앙에 정렬
         - end : 항목을 끝 위치로 정렬

      3. justify / align-content (아이템 그룹 가로/세로 정렬)

         Grid 아이템들의 너비/높이를 모두 합한 값이 Grid 컨테이너의 너비보다 작을 때 Grid 아이템들을 통째로 정렬한다.

         ```css
         .container {
           justify-content: stretch / start / center / end / space-between /
             space-around / space-evenly;
           align-content: stretch / start / center / end / space-between /
             space-around / space-evenly;
         }
         ```

         - start : Grid를 시작 위치로 정렬
         - end : Grid를 끝 위치로 정렬
         - center : Grid를 중앙에 정렬
         - stretch : Grid가 컨테이너를 채우도록 크기를 조정
         - space-around : 항목들 사이에 동일한 간격을 둠
         - space-between : 항목들 사이에 동일한 간격을 둠 (첫 항목과 마지막 항목은 컨테이너에 붙음)
         - space-evenly : 항목들 사이와 항목과 컨테이너 사이에 동일한 간격을 둠

   3. 자식 요소 속성

      1. grid-column / grid-row

         아이템이 Grid 내에서 차지하는 열과 행을 정의한다.

         ```css
         .item {
           grid-column: 1 / 3; /* 1열부터 3열까지 차지 */
           grid-row: 2 / 4; /* 2행부터 4행까지 차지 */
         }
         ```

      2. grid-column-start / grid-column-end 및 grid-row-start / grid-row-end

         Grid 아이템의 시작과 끝을 정의한다.

         ```css
         .item {
           grid-column-start: 1;
           grid-column-end: 3;
           grid-row-start: 2;
           grid-row-end: 4;
         }
         ```

      3. grid-area

         Grid 아이템이 배치될 영역을 정의합니다.

         ```css
         .item {
           grid-area: 2 / 1 / 4 / 3;
           /* grid-row-start / grid-column-start / grid-row-end / grid-column-end */
         }
         ```
