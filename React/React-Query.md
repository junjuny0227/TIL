# React Query

**React Query**는 서버 상태를 페칭(fetching), 캐싱(caching), 동기화(synchronization), 업데이트(updating)하는 작업을 쉽게 처리할 수 있도록 도와주는 라이브러리이다.

> React Query는 원래 이 이름으로 시작했지만, v4부터 Vue나 Svelte 등 다른 프레임워크에서도 활용할 수 있도록 기능이 확장되면서 TanStack Query라는 이름으로 변경되었다. 하지만 React Query라는 이름에 더 익숙한 사람이 많을 것이라고 생각하여, React Query로 표기하였다.

## 용어

- **페칭**(fetching): 웹 애플리케이션에서 서버로부터 데이터를 요청하고 가져오는 과정.

- **캐싱**(caching): 자주 사용되는 데이터나 값을 임시로 저장하여, 동일한 요청 시 서버에 다시 요청하지 않고 빠르게 불러오는 방식.

- **동기화**(synchronization): 클라이언트의 데이터 상태와 서버의 데이터 상태를 일치시키는 과정.

- **업데이트**(updating): 기존 데이터를 수정하거나 새로운 데이터로 교체하는 과정.

## 언제 사용해야 하나

React Query는 다음과 같은 상황에서 특히 유용하다.

- **서버 상태 관리가 필요한 경우**: useState, useEffect로 관리하기 어려운 서버 데이터를 보다 효율적으로 관리할 수 있다.

- **자주 갱신되는 데이터를 자동으로 동기화해야 할 때**: 실시간 피드, 대시보드, 알림 기능 등을 쉽게 구현할 수 있다.

- **캐싱을 활용해 불필요한 요청을 줄이고 싶을 때**: 같은 데이터를 여러 곳에서 사용할 때 동일한 요청을 최소화할 수 있다.

- **로딩 및 에러 상태 관리를 간편하게 하고 싶을 때**: isLoading, isError 등의 내장 상태를 활용하면 로딩과 에러 상태를 손쉽게 처리할 수 있다.

## 핵심 기능

### QueryClient

`QueryClient`는 모든 `query`와 `mutation`에 대한 상태와 캐시를 관리하는 객체이다.

```jsx
const queryClient = new QueryClient();
```

### QueryClientProvider

`QueryClientProvider`는 하위 컴포넌트들이 `QueryClient`에 접근할 수 있도록 도와주는 컴포넌트이다.

```jsx
import { QueryClient, QueryClientProvider } from "@tanstack/react-query";

const queryClient = new QueryClient();

createRoot(document.getElementById("root")!).render(
  <QueryClientProvider client={queryClient}>
    <App />
  </QueryClientProvider>
);
```

`QueryClientProvider`는 `client`라는 prop을 받으며, 이 `client`에는 `QueryClient`의 인스턴스를 전달해야 한다. `QueryClientProvider`로 앱을 감싸면 하위 컴포넌트들에서 `QueryClient`를 통해 `query`와 `mutation`을 사용할 수 있게 된다.

### useQuery

`useQuery`는 React Query에서 가장 기본적인 쿼리 훅으로, 컴포넌트에서 서버로부터 데이터를 가져올 때 사용되며 객체를 인자로 받는다.

> 쿼리란 데이터베이스나 서버에서 원하는 정보를 검색하거나 요청하는 것을 의미한다.

```jsx
const 반환값 = useQuery(옵션);
```

#### 반환값

`useQuery`의 반환값에는 보통 다음과 같은 상태 값과 함수가 포함된다.

- `data`: 쿼리로 가져온 데이터
- `isLoading`: 데이터가 로드 중인지 여부
- `error`: 데이터 요청 중 발생한 에러
- `refetch`: 수동으로 데이터를 다시 가져오는 함수

#### 옵션

`useQuery`에서 자주 사용되는 옵션은 아래와 같다.

| **옵션**                 | **설명**                                                 | **기본값**     |
| ------------------------ | -------------------------------------------------------- | -------------- |
| **queryKey**             | 쿼리를 고유하게 식별하는 키(식별자)                      | (필수)         |
| **queryFn**              | 데이터를 가져오는 함수 (API 호출 등)                     | (필수)         |
| **enabled**              | 쿼리 자동 실행 여부. false로 설정하면 수동으로 실행 가능 | `true`         |
| **staleTime**            | 데이터가 신선한 상태로 유지되는 시간(ms).                | `0`            |
| **gcTime**               | 쿼리 데이터가 캐시에 유지되는 시간(ms).                  | `300000` (5분) |
| **refetchOnWindowFocus** | 브라우저 창에 다시 포커스될 때 자동으로 데이터 갱신 여부 | `true`         |
| **retry**                | 쿼리 실패 시 자동 재시도 횟수                            | `3`            |
| **select**               | 가져온 데이터를 변형하거나 가공하는 함수                 | 없음           |
| **initialData**          | 쿼리가 생성되거나 캐시되기 전에 사용할 초기 데이터       | 없음           |

### useMutation

`useMutation`은 React Query에서 데이터 변경 작업(생성, 수정, 삭제 등)을 처리하기 위한 훅이다. 이를 사용하면 데이터 변경 요청을 쉽게 관리할 수 있으며, 요청의 성공, 실패, 로딩 상태 등을 편리하게 추적할 수 있다.

```jsx
const 반환값 = useMutation(옵션);
```

#### 반환값

`useMutation`의 반환값에는 보통 다음과 같은 상태 값과 함수가 포함된다.

- `mutate`: 변이 요청을 실행하는 함수
- `data`: 변이가 성공했을 때 반환된 데이터
- `isLoading`: 변이 요청이 진행 중인지 여부
- `error`: 변이 요청 중 발생한 에러

#### 옵션

`useMutation`에서 자주 사용되는 옵션은 아래와 같다.

| **옵션**       | **설명**                                      | **기본값** |
| -------------- | --------------------------------------------- | ---------- |
| **mutationFn** | 실행할 비동기 변이 함수                       | (필수)     |
| **onSuccess**  | 변이가 성공했을 때 호출되는 함수              | 없음       |
| **onError**    | 변이 중 오류가 발생했을 때 호출되는 함수      | 없음       |
| **onSettled**  | 변이가 성공하거나 실패해도 항상 호출되는 함수 | 없음       |
| **onMutate**   | 변이 함수가 실행되기 전에 호출되는 함수       | 없음       |
| **retry**      | 변이 실패 시 재시도 횟수                      | `0`        |
| **retryDelay** | 재시도 시 딜레이 시간(ms)                     | 자동 설정  |

## 사용

### 설치

#### NPM

```bash
npm i @tanstack/react-query
```

#### Yarn

```bash
yarn add @tanstack/react-query
```

#### PNPM

```bash
pnpm add @tanstack/react-query
```

### 예제 코드

```jsx
import axios from "axios";
import { useQuery } from "@tanstack/react-query";

const App = () => {
  const { data, isLoading, error } = useQuery({
    queryKey: ["userData"],
    queryFn: () => axios.get("/api/user").then((res) => res.data),
    staleTime: 10000, // 10초 동안 데이터 신선하게 유지
    gcTime: 300000, // 5분 동안 캐시 유지
    refetchOnWindowFocus: false, // 창 포커스 시 자동 갱신 비활성화
  });

  if (isLoading) return <div>로딩 중...</div>;
  if (error) return <div>에러 발생: {error.message}</div>;

  return (
    <div>
      <h1>사용자 정보</h1>
      <p>이름: {data.name}</p>
      <p>이메일: {data.email}</p>
    </div>
  );
};

export default App;
```
