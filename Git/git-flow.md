# Git flow

**Git flow**는 Git을 활용한 다양한 브랜치 관리 방법 중 하나로, 대규모 프로젝트에서 코드를 효율적으로 관리할 수 있도록 도와준다. Git flow는 **주요 브랜치**와 **보조 브랜치**로 크게 두 가지로 나눠진다.

## 주요 브랜치

- **main**: 정식 배포가 이루어지는 브랜치

- **develop**: 개발된 내용이 통합되는 브랜치

## 보조 브랜치

- **feature**: 새로운 기능을 개발하는 브랜치

- **release**: 배포 준비 및 테스트를 하는 브랜치

- **hotfix**: main 브랜치에서 긴급한 버그가 발생했을 때 수정을 위한 브랜치

## 흐름

### 개발

feature -> develop -> release -> main

### 핫픽스

hotfix -> main

<img src="https://goo-gy.github.io/static/5e2b0ac473ed6ea7282bb1188dcfea43/65d79/git-flow.png" />
