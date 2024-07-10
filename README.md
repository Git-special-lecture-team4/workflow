# workflow

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

- ### rollback (개발계)
  - 백업 브랜치
  - 큰 버전을 백업 : 1.xx, 2.xx ... 

## 2. Rollback 정책


## 3. hotplix 정책


## 4. hotpix 정책


## 5. PR 정책
reviewer 선정 기준

## 6. 최소 reviewer 
