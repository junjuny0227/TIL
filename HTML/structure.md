# HTML 문서의 기본 구조

## `<!DOCTYPE>`

문서의 유형을 정의한다.

```html
<!DOCTYPE html>
```

## `<html>`

HTML 문서의 루트 요소로, 모든 HTML 코드는 `<html>` 태그로 감싸져야 하며, 이 태그 내에 `<head>`와 `<body>`가 포함된다.

```html
<html lang="ko">
  <!-- 문서의 언어를 한글(Korean)로 설정 -->
  ...
</html>
```

## `<head>`

문서에 대한 메타데이터를 포함하는 태그로, 페이지의 스타일, 스크립트, 메타 정보 등을 담는다.

```html
<head>
  ...
</head>
```

## `<meta>`

웹페이지 자체의 정보를 명시한다.

```html
<meta charset="UTF-8" />
<!-- 문서의 문자 인코딩 방식을 UTF-8로 설정 -->
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<!-- 모바일 장치에서 페이지가 올바르게 표시되도록 뷰포트를 설정 -->
```

## `<title>`

웹 브라우저 탭에 표시되는 제목을 설정한다.

```html
<title>제목</title>
```

## `<body>`

실제로 웹 페이지에 표시되는 모든 콘텐츠(텍스트, 이미지, 링크 등)를 포함하는 태그이다.

```html
<body>
  ...
</body>
```
