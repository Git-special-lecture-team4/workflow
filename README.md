# workflow

## 1. Conflict가 최소로 발생하는 Flow
feature develop release main

## 2. Rollback 정책


## 3. hotplix 정책


## 4. hotpix 정책
Hotfix Workflow는 보통 다음과 같은 단계로 이루어집니다.

1. 문제 식별 및 핫픽스 브랜치 생성
2. 핫픽스 개발
3. 핫픽스 테스트
4. 핫픽스 배포
5. 핫픽스 병합
6. 핫픽스 브랜치 삭제

### 1. 문제 식별 및 핫픽스 브랜치 생성
문제가 발생하면, 해당 문제를 해결하기 위한 핫픽스 브랜치를 생성합니다. 일반적으로 `main` 브랜치 또는 `master` 브랜치에서 시작합니다.

```
git checkout main
git pull origin main
git checkout -b hotfix/<hotfix-name>

```

### 2. 핫픽스 개발
핫픽스 브랜치에서 문제를 해결하고 코드를 커밋합니다.

```
# 파일 수정
git add .
git commit -m "Fix critical issue: <description>"

```



## 5. PR 정책
reviewer 선정 기준

## 6. 최소 reviewer 
