# 속성(attributes)

요소는 아래와 같이 **속성**(attributes)을 가질 수 있다.

```html
<p class="title">HTML is Awesome!</p>
```

속성(attributes)은 요소에 화면에는 직접 나타나지 않지만 추가적인 정보를 제공하고 싶을 때 사용한다.

## 규칙

1. 요소 이름과 속성 사이, 그리고 속성과 속성 사이에는 공백이 있어야 한다.
2. 속성 뒤에는 =(등호)가 붙어야 한다.
3. 속성 값은 반드시 따옴표로 감싸야 한다.

## 예시

```html
<a href="https://velog.io/@junjuny0227" title="velog" target="_blank">anchor</a>
```

- `href`: 연결하고자 하는 웹 주소를 지정한다.
- `title`: 링크에 대한 추가 정보를 나타낸다. 링크 위로 마우스를 옮기면 나타난다.
- `target`: 링크가 어떻게 열릴 것인지 지정한다. `target="_blank"`는 새 탭에서 링크를 열며, `target="_self"`는 현재 탭에서 링크된 웹 페이지를 연다.
