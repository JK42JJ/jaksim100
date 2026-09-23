<!-- 사람말검사 제외 -->
# 미션 — 09-23(수) · Day 2 · 발화 2/49

> 어제 사건 1 문서가 저장소에 없어서 오늘 아침에 제가 만들었다. `prep/cases/01.md` 를 열면 된다.
> 원장과 경력기술서와 발화 코퍼스에서 뽑았고 줄마다 출처를 달았다. `[James]` 두 곳은 출처에 없어 James 가 채울 자리인데, 오늘은 비운 채로 말해도 된다.

## 발화 (20분) — 사건 1: 네트워크 재설계와 4,000대 WAS 이전
1. 어제 쓴 `prep/cases/01.md`를 연다. 한국어 문서를 보면서 영어로 90초 동안 말한다. 문장을 새로 짓지 말고 문서의 문장을 옮긴다. 항목 순서대로 말한다. 언제 어디서 일어난 일인지, 무엇이 걸려 있었는지, 내가 무엇을 결정했는지, 내 손으로 무엇을 했는지, 숫자는 무엇인지, 결과는 무엇인지.
2. 문서를 덮고 같은 사건을 60초 동안 다시 말한다. 사건과 결과만 말한다.
3. 녹음은 한 번에 이어서 한다. 콘솔 또는 `~/Downloads/eng-2026-09-23.m4a`에 남기고, 전사와 지표를 여기에 붙인다. 네 기준(결론이 30초 안에 나왔는가, 숫자가 하나 있는가, 자기를 낮추는 말이 없는가, 한국어가 나오지 않았는가)으로 채점하고 표현 세 개를 고쳐 준다. 고친 세 문장은 내일 미션의 0번이 된다.

## 영어로 옮길 때 막히는 말 (문장은 James 가 만든다)

문서의 한국어를 영어로 옮기다 막히면 여기 조각을 쓴다. 문장을 통째로 외우지 않는다.

- 단계별로 이전했다 — a staged migration · we moved it in stages
- 고객 영향 없이 — with no customer impact · no customer-visible downtime
- 시큐리티 그룹이 쌓여 있었다 — security groups were created and never cleaned up
- IP 가 고갈됐다 — we were running out of IP addresses
- 내가 발의했다 — I proposed it · I raised it with my group head
- 계획된 컷오버 — a planned cutover
- 의존성 맵 — a dependency map
- 주 1회 호출되는 API — an API that was called once a week
- 롤백하고 프로그램을 멈췄다 — we rolled back and paused the program
- 트래픽 분석기를 만들었다 — we built a traffic analyzer on VPC flow logs
- 실측 데이터로 재개했다 — we resumed with measured traffic data
- 전부 핸즈온을 하지는 않았다 — I led the design; I didn't do all the hands-on myself

막히면 멈춘 채로 이어 간다. 한국어로 돌아가지 않는다. 못 알아들은 질문에는 "Sorry, could you repeat that?" 이라고 묻는다.

## 글 (10분) — 내일 말할 사건 2: Self-Healing 자동 복구
출처를 열고 일곱 항목을 한국어로 채운다. 항목마다 어디에서 가져왔는지 적는다. 출처에 없는 내용은 [기억]이라고 표시한다. 10분 안에 다 채우지 못하면 채운 데까지 둔다. `prep/cases/02.md`로 저장하고 여기에 붙이면 출처와 대조해서 본다.

출처는 다음과 같다.
- `260331_김전호_이력사항.docx` 의 "AIOps 기반 장애 자동복구 시스템 구축" 항목. 저장소에는 없고 클로드웹 프로젝트에서 연다.
- `portfolio/sof-enrichment/SAMSUNG-CASE-A-SELFHEALING.md` — 클로드웹 프로젝트의 `14-case-selfhealing.md` 와 같은 자료다. 사례 원고에 500건 전수조사, 선정 논리, 승격 게이트, 파이프라인 5단, 분리의 이유, 피드백 루프, 40%의 정의가 있다.
- `portfolio/sof-enrichment/02-cloudops-original-deck.md` — 클로드웹 프로젝트의 `12-cloudops-original-deck.md` 와 같은 자료다. 2022년 ChatOps에서 2023년 Self-Healing 으로 이어지는 로드맵이 있다.
- `profile/resume-claims-ledger.md` 43행, 46행

| 항목 | 채울 내용 |
|---|---|
| 1. 언제, 어디서 일어난 일인가 | 2022년 1월부터 2023년 7월까지 한 일이다. 대상은 VM 5,000대와 WAS·Kafka·Cassandra 클러스터였다. |
| 2. 무엇이 걸려 있었나 | 야간과 휴일에 사람이 같은 절차를 반복했고, L3 엔지니어의 주간 시간이 줄었다. 그 전에는 어떻게 대응했는지 쓴다. |
| 3. 내가 무엇을 결정했나 | 전수조사로 대상을 고르기로 한 결정, 판단이 필요한 유형은 자동화하지 않기로 한 결정, 판정과 실행을 나눈 결정을 쓴다. |
| 4. 내 손으로 한 일은 무엇인가 | 조사와 분류를 내가 했는지, 판정 규칙을 내가 썼는지, 복구 서버 코드를 누가 썼는지 쓴다. |
| 5. 숫자는 무엇인가 | 장애 500건(2020.08~2023.01), Instance Down 120건, Connection Timeout 110건, EC2 호스트 계층 원인 120건, DBMS 재기동 조치 130건, 야간·휴일 대응 40% 감소(L3 야간 호출 빈도 기준의 내부 측정)를 쓴다. |
| 6. 결과는 무엇인가 | 40%의 정의를 정확히 쓴다. 야간 호출 빈도가 줄었고 그 시간이 주간 엔지니어링으로 돌아온 것이며, 인원 절감 수치가 아니다. |
| 7. 다시 한다면 무엇을 바꾸겠나 | 오판 사례가 있었는지, 자동화하지 않은 유형과 그 이유를 쓴다. |


## 기록
달리기를 기록하는 자리에 "발화 2/49"라고 적는다.
