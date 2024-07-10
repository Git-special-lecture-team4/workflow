# :octocat: workflow

## 1. Conflict가 최소로 발생하는 Flow
feature develop release main

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
