# :octocat: workflow

## 1. Conflict가 최소로 발생하는 Flow
### feature (기능계)
  - 기능별 브랜치 분기
    - feature/1
    - feature/2
    - feature/3
    - feature/4 ...

### develop (개발계)
  - feature 에서 QA 를 거쳐 종합되는 브랜치
  - feature/1 + feature/2 + feature/3 + feature/4 ...

### release (개발계)
  - develop 에서 QA 를 거친 브랜치

### hotfix (개발계)
  - 사소한 오류를 조치하는 브랜치
  - 조치 완료 시, develop 브랜치로 merge

### main (운영계)
  - 서비스 출시 가능 브랜치

### rollback (개발계)
  - 백업 브랜치
  - 큰 버전을 백업 : 1.xx, 2.xx ... 

## 2. Rollback 정책
2-1. tag 정책
    - 각 버전에 특정 버전 번호로 태그 지정 
        ex) 1.0, 1.1, 2.0 ... 
    - 문제가 발생 할 경우 전 버전 번호로 rollback
    - 현재 버전에서 latest 태그를 사용
        - rollback할 경우 latest 태그를 이전번호로 지정

2.2. 커밋내역을 되돌릴 때는 revert
    reset은 삭제된 커밋을 복구 할 수 없어 치명적인 단점!


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
reviewer 선정 기준:
1. 코드베이스 전문성 ->특정 모듈이나 기능 경험 순
2. 기술 스택
3. 프로젝트 경험
4. 주요 기능 관련 : 주요 기능 담당자
5. 협업 경험 및 피드백 능력
6. 리뷰 경험

- 리뷰어 수
ㄴ feature - (1명) -> dev - (2명) -> release - main
-- 개발 속도감 확보 가능
-- 리뷰로 인한 시간 소요를 최소화
-- 다른 기능 파악 수월

## 6. 최소 reviewer 

1. feature 브랜치 : 1명 -> 자기 코드 아닌 것
2. develop 브랜치 : 2명 -> 고정


