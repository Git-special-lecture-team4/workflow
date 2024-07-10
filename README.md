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

## 3. hotplix 정책


## 4. hotpix 정책


## 5. PR 정책
reviewer 선정 기준


## 6. 최소 reviewer 
1. feature 브랜치 : 1명 -> 자기 코드 아닌 것
2. develop 브랜치 : 2명 -> 고정