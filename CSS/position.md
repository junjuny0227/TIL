# position

`position` 속성은 문서에서 요소의 배치 방법을 지정하는 속성이다. `top`, `right`, `bottom`, `left` 속성은 요소의 최종 위치를 결정한다.

## 종류

`position` 속성은 아래와 같은 속성값을 가질 수 있다.

### static

`position` 속성의 기본값으로, 요소를 일반적인 문서 흐름에 따라 배치한다. 이 경우, `top`, `right`, `bottom`, `left`, `z-index` 속성은 영향을 미치지 않는다.

```css
position: static;
```

### relative

`static`과 같이 일반적인 문서 흐름에 따라 배치되지만, 자식 요소에게 자기 자신을 기준으로 `top`, `right`, `bottom`, `left`의 값에 따라 오프셋을 적용한다.

```css
position: relative;
```

### absolute

요소를 일반적인 문서 흐름에서 제거하고, 페이지의 레이아웃 공간도 할당하지 않는다. 대신 가장 가까운 위치 지정 조상 요소를 기준으로 상대적으로 배치한다. 만약 위치 지정된 조상이 없다면 초기 컨테이닝 블록을 기준으로 삼고, 최종 위치는 `top`, `right`, `bottom`, `left` 값을 통해 설정한다.

**컨테이닝 블록**(containing block)은 CSS에서 위치를 지정하는 요소가 배치될 기준이 되는 블록이다. 초기 컨테이닝 블록은 일반적으로 문서의 뿌리 요소인 `<html>`이나 `<body>`이다.

```css
position: absolute;
```

### fixed

요소를 일반적인 문서 흐름에서 제거하고, 페이지의 레이아웃 공간도 할당하지 않는다. 대신, **뷰포트**(viewport)의 초기 컨테이닝 블록을 기준으로 배치한다. 다만, 요소의 조상 중 하나라도 `transform`, `perspective`, `filter` 속성 중 하나가 설정되어 있으면, 뷰포트 대신 그 조상 요소를 컨테이닝 블록으로 사용한다. 최종 위치는 `top`, `right`, `bottom`, `left` 값을 통해 설정된다.

```css
position: fixed;
```

### sticky

`static`과 같이 일반적인 문서 흐름에 따라 배치되며, 테이블 관련 요소를 포함해 가장 가까운 스크롤 가능한 조상 요소와, 표 관련 요소를 포함한 컨테이닝 블록(가장 가까운 블록 레벨 조상)을 기준으로 `top`, `right`, `bottom`, `left` 값에 따라 오프셋이 적용된다.

```css
position: sticky;
```
