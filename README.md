# :octocat: workflow

## 1. Conflict가 최소로 발생하는 Flow
feature develop release main

## 2. Rollback 정책

## 3. hotpix 정책
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

### 3. 핫픽스 테스트
핫픽스가 제대로 작동하는지 테스트합니다. 충분히 테스트가 완료되면 변경 사항을 원격 저장소에 푸시합니다.

```
git push origin hotfix/<hotfix-name>
```
### 4. 핫픽스 배포
테스트가 완료된 후, 핫픽스를 배포합니다. CI/CD 파이프라인을 통해 자동화될 수도 있습니다.

### 5. 핫픽스 병합
핫픽스가 배포된 후, 변경 사항을 main 브랜치와 develop 브랜치(또는 다른 관련 브랜치)로 병합합니다.<br><br>

먼저 main 브랜치로 병합합니다:

```
git checkout main
git pull origin main
git merge hotfix/<hotfix-name>
git push origin main
```
그 다음, `develop` 브랜치로 병합합니다:

```
git checkout develop
git pull origin develop
git merge hotfix/<hotfix-name>
git push origin develop

```
### 6. 핫픽스 브랜치 삭제
모든 병합이 완료된 후, 핫픽스 브랜치를 삭제합니다:

```
git branch -d hotfix/<hotfix-name>
git push origin --delete hotfix/<hotfix-name>
```


## 5. PR 정책
reviewer 선정 기준


## 6. 최소 reviewer 
