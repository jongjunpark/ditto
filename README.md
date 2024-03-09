# ditto

따라하고 싶은 UI를 흉내냅니다. ditto는 상동이라는 뜻으로 메타몽의 영문표기법을 참조하였습니다.

## typescript

- 별도의 library(react, ...)없이 vanilla js + typescript로 코드를 구성합니다.
  - 사실상 typescript가 있는 이상 vanilla라고 할 수 없지만 그래도 type을 제외하고 vanilla를 추구합니다.

## nextjs

> 대부분의 코드는 nextjs에서 만들어질 예정입니다.

- nextjs를 이용하여 코드를 구성합니다.
  - nextjs는 14버전으로 app router를 사용합니다.
  - 현재 fetch가 굳이 필요하지 않으나 사용하게 된다면 suspense를 이용합니다.
- 다음과 같은 라이브러리 및 기술스택이 적용되어 있습니다.
  - fetch: axios
  - server-state: react-query
  - client-global-state: zustand + (react context API)
  - style: sass, emotion (주로 styled)
  - 날짜 format: date-fns, dayjs
  - form: react-hook-form
  - design pattern: atomic design (비적극적 활용)
- directory 구조 (적극적인 활용은 아님)
  - 각 page는 layout과 error, suspense를 가질 수 있음
  - 구조
  ```
  ditto app
  ├── (common)          // 공통 사용 요소들
  │   ├── api               // api 함수 정리 (사용시에)
  │   ├── components        // 공통 컴포넌트
  │   │   ├── icons               // custom icon 컴포넌트
  │   │   ├── atoms               // atomic design의 atom
  │   │   └── molecules           // atomic design의 molecules
  │   ├── hooks             // 공통 hooks
  │   ├── assets            // 에셋 모음
  │   │   ├── images              // image 파일
  │   │   └── svgs                // svg 파일
  │   ├── state             // client, server state
  │   │   ├── client        // client global state (zustand)
  │   │   └── server        // server state (react-query)
  │   ├── styles            // 공통 스타일
  │   ├── types             // 공통 타입
  │   │   ├── global.d.ts         // global type
  │   │   └── type.d.ts           // common type
  │   └── utils             // 공통 유틸리티
  ├── (pages)           // 각 UI별 페이징
  │   └── creative-carousel          // (예) creative-carousel UI
  ├── layout.tsx        // 전체 layout
  ├── page.tsx          // main page
  └── providers.tsx     // 전체 provider
  ```
