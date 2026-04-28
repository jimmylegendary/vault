# Docker stack에서 D만 추가하고 A/C는 건드리지 않는 방법

## 핵심 결론
### 1) D만 추가하고 B는 당장 지우지 않을 때
```bash
docker stack deploy -c stack.yml <stack_name>
```

이 경우:
- `D`는 새로 생성됨
- `A`, `C`는 compose 정의가 바뀌지 않았다면 그대로 유지됨
- `B`는 compose 파일에서 빠졌더라도 **자동 삭제되지 않음**
  - `--prune`를 안 썼기 때문

즉, **가장 간단하게 D만 추가하고 싶으면 이게 맞음**.

---

### 2) D 추가 + B 제거까지 같이 하고 싶을 때
```bash
docker stack deploy --prune -c stack.yml <stack_name>
```

이 경우:
- `D` 추가
- `B` 제거
- `A`, `C`는 스펙이 안 바뀌면 재시작 없이 유지되는 게 일반적

---

## A/C를 안 건드리려면 중요한 조건
`docker stack deploy`는 **스택의 desired state를 reconcile**하는 명령이라,
A/C 정의가 조금이라도 달라지면 rolling update가 걸릴 수 있음.

그래서 A/C를 진짜 안 건드리고 싶으면 다음을 지켜야 함:
- A/C의 image tag 변경 금지
- env 변경 금지
- command/args 변경 금지
- network/volume/mount 변경 금지
- replicas/update_config/resources 변경 금지

즉 **stack.yml에서 A/C 관련 줄이 완전히 동일해야 함**.

---

## 추천 운영 순서
### 보수적으로 가는 순서
1. 먼저 D만 추가
```bash
docker stack deploy -c stack.yml <stack_name>
```

2. 확인
```bash
docker service ls
docker service ps <stack_name>_d
```

3. D가 정상 동작하면 그때 B 제거
```bash
docker stack deploy --prune -c stack.yml <stack_name>
```

이게 제일 안전함.

---

## 확인 명령
### stack 전체 서비스 확인
```bash
docker stack services <stack_name>
```

### 특정 서비스 상태 확인
```bash
docker service ps <stack_name>_d
```

### A/C가 업데이트 안 먹었는지 확인
```bash
docker service ps <stack_name>_a
docker service ps <stack_name>_c
```

### compose diff를 보기 어렵다면 최소한 inspect 비교
```bash
docker service inspect <stack_name>_a
docker service inspect <stack_name>_c
```

---

## 실무적으로 한 줄 추천
- **D만 일단 추가:** `docker stack deploy -c stack.yml <stack_name>`
- **B까지 정리:** `docker stack deploy --prune -c stack.yml <stack_name>`

네 질문 기준으로는,
**A/C 중단 없이 D를 간단히 추가 배포하고 싶다**면
우선은 **`--prune 없이 stack deploy`**가 제일 맞다.
