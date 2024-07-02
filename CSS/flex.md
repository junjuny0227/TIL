# Flex

Flex는 한 방향(가로/세로) 레이아웃 시스템이다.

```css
display: flex;
```

1.  기본 설명
    1. 용어 정리

       1. main axis: 메인축
       2. cross axis: 교차축
       3. Flex container: 부모 요소
       4. Flex item: 자식 요소

       > 출처: 1분코딩
       >
       > <img src="https://studiomeal.com/wp-content/uploads/2020/01/02.jpg" width="70%" height="70%"/>
       >
       > <img src="https://studiomeal.com/wp-content/uploads/2020/01/03.jpg" width="70%" height="70%"/>

    2. 추가 설명
       1. 크롬 개잘자 도구를 이용하면 Flex를 확인할 수 있다.
       2. 컨테이너가 Flex의 영향을 받는 전체 공간이고, 설정된 속성에 따라 각각의 아이템들이 어떤 형태로 배치되는 것이다.
2.  속성들
    1.  flex-direction

        아이템들이 배치되는 축의 방향을 결정하는 속성이다.

        ```css
        .container {
          flex-direction: row / column / row-reverse / column-reverse;
        }
        ```

        1. row: 기본값으로, 자식 요소들이 가로로 배치된다.
        2. row-reverse: 자식 요소들이 가로로 역순 배치된다.
        3. column: 자식 요소들이 세로로 배치된다.
        4. column-reverse: 자식 요소들이 세로로 역순 배치된다.

        > 출처 : 1분코딩
        >
        > <img src="https://studiomeal.com/wp-content/uploads/2020/01/05-1.jpg" width="70%" height="70%"/>

    2.  flex-wrap

        컨테이너가 더 이상 아이템들을 한 줄에 담을 여유 공간이 없을 때 아이템 줄바꿈을 어떻게 할지 결정하는 속성이다.

        ```css
        .container {
          flex-wrap: nowrap / wrap / wrap-reverse;
        }
        ```

        1. nowrap: 기본값으로, 자식 요소들이 한 줄에 배치된다.
        2. wrap: 자식 요소들이 여러 줄에 걸쳐서 배치됩니다.
        3. wrap-reverse: 자식 요소들이 여러 줄에 걸쳐 역순으로 배치됩니다.

    3.  justify-content

        메인축 방향으로 아이템을들 정렬하는 속성이다

        ```css
        .container {
          justify-content: flex-start / flex-end / center / space-between /
            space-around / space-evenly;
        }
        ```

        1. flex-start: 기본값으로, 자식 요소들이 컨테이너의 시작점에 배치된다.
        2. flex-end: 자식 요소들이 컨테이너의 끝점에 배치된다.
        3. center: 자식 요소들이 컨테이너의 중앙에 배치된다.
        4. space-between: 자식 요소들 사이에 균등한 간격이 생긴다.
        5. space-around: 자식 요소들 주위에 균등한 간격이 생긴다.
        6. space-evenly: 자식 요소들 사이와 가장자리에 균등한 간격이 생긴다.

        > 출처: 1분코딩
        >
        > <img src="https://studiomeal.com/wp-content/uploads/2020/01/10-1.jpg" width="70%" height="70%"/>

    4.  align-items
        수직축 방향으로 아이템을들 정렬하는 속성이다. justify-content와 수직 방향의 정렬이라고 생각하면 된다.
        
        ```css
        .container {
            align-items: stretch / flex-start / flex-end / center / baseline;
        }
        ```


        1. stretch: 기본값으로, 자식 요소들이 컨테이너의 높이에 맞게 늘어된다.
        2. flex-start: 자식 요소들이 컨테이너의 시작점에 정렬된다.
        3. flex-end: 자식 요소들이 컨테이너의 끝점에 정렬된다.
        4. center: 자식 요소들이 컨테이너의 중앙에 정렬된다.
        5. baseline: 자식 요소들이 텍스트 베이스라인에 맞춰 정렬된다.
    5.  align-content

        flex-wrap: wrap;이 설정된 상태에서, 아이템들의 행이 2줄 이상 되었을 때의 수직축 방향 정렬을 결정하는 속성이다.

        ```css
        .container {
          flex-wrap: wrap;
          align-content: stretch / flex-strat / flex-end / center /
            space-between / space-around / space-evenly;
        }
        ```

        1. flex-start: 기본값으로, 자식 요소들이 컨테이너의 시작점에 배치된다.
        2. flex-end: 자식 요소들이 컨테이너의 끝점에 배치된다.
        3. center: 자식 요소들이 컨테이너의 중앙에 배치된다.
        4. space-between: 자식 요소들 사이에 균등한 간격이 생긴다.
        5. space-around: 자식 요소들 주위에 균등한 간격이 생긴다.
        6. space-evenly: 자식 요소들 사이와 가장자리에 균등한 간격이 생긴다.

    6.  align-self

        flex 아이템의 교차 축 정렬을 조정한다.

        ```css
        .item {
          align-self: stretch / flex-start / flex-end / center / baseline;
        }
        ```

        1. stretch: 기본값으로, 자식 요소들이 컨테이너의 높이에 맞게 늘어된다.
        2. flex-start: 자식 요소들이 컨테이너의 시작점에 정렬된다.
        3. flex-end: 자식 요소들이 컨테이너의 끝점에 정렬된다.
        4. center: 자식 요소들이 컨테이너의 중앙에 정렬된다.
        5. baseline: 자식 요소들이 텍스트 베이스라인에 맞춰 정렬된다.
