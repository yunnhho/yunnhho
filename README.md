# 김윤호 (백엔드 웹개발)

Java/Spring Boot 기반 백엔드 개발자입니다.
고동시성 환경에서의 데이터 정합성 확보와 성능 최적화에 집중하여 프로젝트를 수행해 왔고, REST API, Redis, Apache Kafka 등을 활용한 대용량 처리 경험을 갖추고 있습니다.

자기 주도적으로 학습 계획과 요구사항 분석을 수행하며, 문제 발생 시 논리적인 해결 방안을 모색합니다.
도메인을 이해한 뒤 그에 맞는 기술을 선택하는 것이 좋은 설계의 시작이라고 생각합니다.

> `동시성 제어` · `분산 락` · `이벤트 기반 아키텍처` · `데이터 정합성` · `성능 최적화`

[![Email](https://img.shields.io/badge/Email-rladbsgh27@gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:rladbsgh27@gmail.com)

---

## 기술 스택 / Skill Set

**Languages**
![Java](https://img.shields.io/badge/Java-21-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)

**Framework / Library**
![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.4-6DB33F?style=flat-square&logo=spring-boot&logoColor=white)
![Spring Security](https://img.shields.io/badge/Spring_Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white)
![Spring Data JPA](https://img.shields.io/badge/Spring_Data_JPA-6DB33F?style=flat-square&logo=spring&logoColor=white)
![QueryDSL](https://img.shields.io/badge/QueryDSL-5.0-0769AD?style=flat-square)
![MyBatis](https://img.shields.io/badge/MyBatis-000000?style=flat-square)
![React](https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react&logoColor=black)
![Resilience4j](https://img.shields.io/badge/Resilience4j-000000?style=flat-square)
![JUnit5](https://img.shields.io/badge/JUnit-5-25A162?style=flat-square&logo=junit5&logoColor=white)
![Bucket4j](https://img.shields.io/badge/Bucket4j-blue?style=flat-square)

**Infra**
![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=flat-square&logo=mysql&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Apache Kafka](https://img.shields.io/badge/Apache_Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white)
![Kafka Streams](https://img.shields.io/badge/Kafka_Streams-231F20?style=flat-square&logo=apachekafka&logoColor=white)
![MinIO](https://img.shields.io/badge/MinIO-C72E49?style=flat-square&logo=minio&logoColor=white)

**DevOps / Monitoring**
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white)
![JMeter](https://img.shields.io/badge/JMeter-D22128?style=flat-square&logo=apachejmeter&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)

**ETC**
![REST API](https://img.shields.io/badge/REST_API-005571?style=flat-square)
![JWT](https://img.shields.io/badge/JWT-000000?style=flat-square&logo=jsonwebtokens&logoColor=white)
![OAuth2](https://img.shields.io/badge/OAuth2-EB5424?style=flat-square)
![WebSocket](https://img.shields.io/badge/WebSocket_(STOMP)-010101?style=flat-square)

---

## 프로젝트 / Projects

### 1. 산업 안전 관제 플랫폼

> 중대재해처벌법 대응을 위한 실시간 산업 안전 모니터링 시스템

**기간**: 2026.02 ~ 2026.03 (약 4주) · 개인 프로젝트
**GitHub**: [yunnhho/platform](https://github.com/yunnhho/platform)

법적 요건을 기술로 해결하는 과정에서, 도메인 이해가 기술 선택에 직접적인 영향을 준다는 걸 체감했습니다. 3단계 불변성 방어 체계와 Event Sourcing을 적용하면서 데이터의 신뢰성과 추적 가능성을 보장하는 아키텍처를 설계해 볼 수 있었습니다.

**주요 성과**
- Application(@PreUpdate 차단) + DB TRIGGER(SQL 차단 + 감사 로그) + SHA-256 해시 체이닝 3단계 방어 체계로 법적 증거 능력을 갖춘 변조 방지 구축
- dblink 자율 트랜잭션으로 감사 로그 독립 커밋 처리, 어떤 상황에서도 감사 로그 100% 보존 달성
- Outbox Pattern으로 도메인 데이터와 이벤트 발행의 트랜잭션 일관성 확보
- Kafka Streams 30분 텀블링 윈도우 실시간 집계 + CQRS 패턴으로 읽기/쓰기 모델 분리하여 조회 성능 최적화
- 월별 RANGE 파티셔닝 + Hot-Warm-Cold 계층형 스토리지(PostgreSQL → MinIO) 전략 적용
- Resilience4j Circuit Breaker 적용하여 실패율 50% 초과 시 자동 차단, Cascading Failure 방지
- JUnit 5 + TestContainers로 실제 PostgreSQL/Redis/Kafka 컨테이너 기반 통합 테스트 수행

`Spring Boot 3.4` `Java 21` `PostgreSQL 15` `Apache Kafka` `Kafka Streams` `Redis` `MinIO` `Resilience4j` `React 18` `STOMP.js` `Docker Compose` `Prometheus` `Grafana` `JUnit 5` `TestContainers`

---

### 2. XRail — 열차 예매 시스템

> 고동시성에 대비한 열차 예매 플랫폼

**기간**: 2026.01 ~ 2026.02 (약 4주) · 개인 프로젝트
**GitHub**: [yunnhho/xrail](https://github.com/yunnhho/xrail)

비트마스킹을 이용한 구간 예매와 Redis Lua Script를 이용한 원자적 점유를 설계하면서, 비즈니스 로직을 적절한 자료구조와 알고리즘으로 풀어내는 경험을 했습니다. 특히 Redis-DB 간 데이터 불일치를 다층 보상 전략으로 해결하는 과정에서 분산 시스템의 동시성 제어에 대한 이해를 넓힐 수 있었습니다.

**주요 성과**
- Redis Lua Script로 좌석 상태 확인→점유를 단일 원자적 연산으로 처리하여 Race Condition 원천 차단, 좌석 중복 예매 0건 달성
- Bitwise AND 연산 한 번(O(1))으로 구간 겹침을 판단, 동일 좌석의 비겹침 구간 재사용으로 좌석 활용률 극대화
- Lua Script(1차 점유) → 비관적 락 DB 2차 검증 → 보상 트랜잭션 → Reconciliation Scheduler(야간 정리) 4중 안전망 설계로 데이터 정합성 100% 확보
- JWT + OAuth2(카카오/네이버) + 비회원(accessCode + PIN) + @Honeypot 봇 차단을 하나의 Spring Security 필터 체인으로 통합
- Bucket4j + Redis 기반 IP별 요청 제한(10 req/sec, 100 req/min) 적용하여 비정상 트래픽 API 진입 전 차단
- Modular Monolith 패턴으로 도메인별 모듈 분리, 모놀리스의 단순함과 MSA 전환 용이성 동시에 확보

`Spring Boot 3.4` `Spring Security` `Spring Data JPA` `QueryDSL 5.0` `Java 21` `React 19` `TypeScript` `MySQL 8.0` `Redis` `Apache Kafka` `JWT` `OAuth2` `Bucket4j` `Docker Compose` `JMeter`

---

### 3. 콘서트 티켓팅 시스템

> 수만 명 동시 접속 환경에서도 서버가 견디는 티켓팅 시스템

**기간**: 2026.01 (약 3주) · 개인 프로젝트
**GitHub**: [yunnhho/ticketing-system](https://github.com/yunnhho/ticketing-system)

Redis 대기열과 분산 락을 통해 동시성 문제를 직접 해결하고, 대규모 트래픽 상황에서의 안정성과 데이터 정합성을 보장하는 시스템을 설계해 볼 수 있었습니다. 처음으로 동시성 제어를 본격적으로 다뤄본 프로젝트였고, 이후 프로젝트들의 기반이 된 경험입니다.

**주요 성과**
- Redis Sorted Set 대기열을 도입하여 3초마다 100명씩 배치 승격, DB CPU 사용률 40% 미만 안정화
- Redisson 분산 락을 tryLock(waitTime=0) Fast-Fail 전략으로 적용, 1,000명 동시 테스트에서 오버부킹 0건
- Kafka 기반 비동기 이벤트 발행(Write-Behind 패턴)으로 결제 응답 시간 100ms 미만 달성
- Redis 기반 멱등성 키(Idempotency Key) 도입으로 정확히 1회만 결제 처리 보장
- DLQ(Dead Letter Queue) 구현하여 1초 간격 2회 재시도 후 실패 메시지 격리, 장애 전파 차단
- CAPTCHA + Redisson RRateLimiter(분당 10,000건) + 대기열 토큰 검증 3계층 봇/매크로 방어
- JMeter 1,000명 동시 부하 테스트 수행하여 500석 전석 정확 배정, HTTP 500 에러 0% 검증

`Spring Boot 3.4` `Java 21` `MySQL 8.0` `JPA` `MyBatis` `Thymeleaf` `Redis` `Apache Kafka` `Docker` `Grafana` `Prometheus` `JMeter`

---

## 진행 중인 프로젝트 

### 집체크(ZipCheck)
**기간**: 2026.03 ~ 진행중
**개요**: 이사 또는 자취 시작 시 방을 보러갈 때 잘 고르기 위한 체크리스트 앱

## 학력 / Education

- **인하공업전문대학교** 컴퓨터정보공학과 졸업 (2020.03 ~ 2025.02)

## 자격증 / Certificate

- **정보처리산업기사** (2025.09 취득)
