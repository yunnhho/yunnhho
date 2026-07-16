# 김윤호 (백엔드 웹개발)

Java/Spring Boot 기반 백엔드 개발자입니다.
고동시성 환경에서의 데이터 정합성 확보와 성능 최적화에 집중해 왔고, Spring Cloud 기반 MSA(Gateway · Service Discovery · Saga · Database per Service) 설계와 Redis, Apache Kafka를 활용한 대용량 처리 경험을 갖추고 있습니다. Python(FastAPI · Celery) 기반 비동기 API 서버와 AI 배치 파이프라인 구축도 가능합니다.

자기 주도적으로 학습 계획과 요구사항 분석을 수행하며, 문제 발생 시 논리적인 해결 방안을 모색합니다.
도메인을 이해한 뒤 그에 맞는 기술을 선택하는 것이 좋은 설계의 시작이라고 생각합니다.

> `동시성 제어` · `MSA` · `분산 트랜잭션(Saga)` · `이벤트 기반 아키텍처` · `데이터 정합성` · `성능 최적화`

[![Email](https://img.shields.io/badge/Email-rladbsgh27@gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:rladbsgh27@gmail.com)

---

## 기술 스택 / Skill Set

**Languages**
![Java](https://img.shields.io/badge/Java-21-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.12-3776AB?style=flat-square&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)

**Framework / Library**
![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.4-6DB33F?style=flat-square&logo=spring-boot&logoColor=white)
![Spring Cloud Gateway](https://img.shields.io/badge/Spring_Cloud_Gateway-6DB33F?style=flat-square&logo=spring&logoColor=white)
![Spring Security](https://img.shields.io/badge/Spring_Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white)
![Spring Data JPA](https://img.shields.io/badge/Spring_Data_JPA-6DB33F?style=flat-square&logo=spring&logoColor=white)
![QueryDSL](https://img.shields.io/badge/QueryDSL-5.1-0769AD?style=flat-square)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Celery](https://img.shields.io/badge/Celery-37814A?style=flat-square&logo=celery&logoColor=white)
![React](https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react&logoColor=black)
![Next.js](https://img.shields.io/badge/Next.js-15-000000?style=flat-square&logo=next.js&logoColor=white)
![Resilience4j](https://img.shields.io/badge/Resilience4j-000000?style=flat-square)
![JUnit5](https://img.shields.io/badge/JUnit-5-25A162?style=flat-square&logo=junit5&logoColor=white)

**Infra**
![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=flat-square&logo=mysql&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Apache Kafka](https://img.shields.io/badge/Apache_Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white)
![Elasticsearch](https://img.shields.io/badge/Elasticsearch-005571?style=flat-square&logo=elasticsearch&logoColor=white)
![Netflix Eureka](https://img.shields.io/badge/Netflix_Eureka-E50914?style=flat-square&logo=netflix&logoColor=white)

**DevOps / Monitoring**
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white)
![Zipkin](https://img.shields.io/badge/Zipkin-FF6B35?style=flat-square)
![JMeter](https://img.shields.io/badge/JMeter-D22128?style=flat-square&logo=apachejmeter&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)

**ETC**
![REST API](https://img.shields.io/badge/REST_API-005571?style=flat-square)
![MSA](https://img.shields.io/badge/MSA-1572B6?style=flat-square)
![Saga Pattern](https://img.shields.io/badge/Saga_Pattern-512BD4?style=flat-square)
![JWT](https://img.shields.io/badge/JWT-000000?style=flat-square&logo=jsonwebtokens&logoColor=white)
![OAuth2](https://img.shields.io/badge/OAuth2-EB5424?style=flat-square)

---

## 프로젝트 / Projects

### 1. XRail — 고동시성 열차 예매 MSA 플랫폼

> 5개 마이크로서비스 + Gateway + Discovery 구조의 단일 MSA로 통합 재설계한 고동시성 예매 플랫폼

- **기간**: 2026.05 ~ 2026.07 (약 2개월) · 개인 프로젝트
- **GitHub**: [yunnhho/xral-msa](https://github.com/yunnhho/xral-msa)
- **규모**: Gradle 멀티모듈 8 백엔드 + React 프론트엔드, 전 모듈 173개 테스트 통과

기차 예매 도메인을 5개 비즈니스 서비스 + Gateway + Discovery로 분리하면서, 서비스 경계를 나누고 분산 트랜잭션의 일관성을 보장하는 아키텍처를 직접 설계했습니다. 특히 비트마스크 좌석 점유와 Kafka Saga를 통해, 비즈니스 로직을 적절한 자료구조와 분산 패턴으로 풀어내는 경험을 했습니다.

**주요 성과**
- Redis Lua 비트마스크로 구간(segment) 단위 좌석 점유를 단일 원자적 연산으로 처리하고 Transactional 내 DB 존재 더블체크 + Reconciliation Scheduler 3중 안전망으로 JMeter 100 스레드 동시 경합에서 오버부킹 0건 달성
- Kafka Saga Choreography로 결제-좌석 확정 분산 트랜잭션을 처리하고 보상 책임을 train-service로 단일화하여 결제 실패/타임아웃/취소 등 5개 실패 시나리오 자동 복구
- 멱등 컨슈머(상태 전이 가드 · eventId 기반 correlation_id UNIQUE) + Transactional Outbox + DLT(1초 간격 2회 재시도 후 실패 메시지 격리) 조합으로 중복·순서 역전 이벤트에도 데이터 정합성 유지 및 장애 전파 차단
- Redis 기반 멱등성 키(Idempotency-Key, SETNX)로 예약·결제 중복 요청을 필터링하고 Redisson 락 + JPA @Version 낙관적 락 조합으로 정확히 1회만 결제 처리되도록 보장
- Gateway 단일 인증(JWT 검증 + X-User-* 헤더 주입, inbound 헤더 무조건 제거)으로 downstream 인증 로직 제거 및 헤더 스푸핑 차단
- JWT 발급·회전 + OAuth2(카카오/네이버) + 비회원(accessCode) 인증을 auth-service로 통합하고 Refresh 토큰 회전 체인 + Redis 블랙리스트 기반 강제 무효화 구현
- Database per Service 원칙으로 4개 스키마를 격리하고 크로스 서비스 FK 제거 + 스냅샷 비정규화로 독립 배포 가능한 구조 설계
- Redis Sorted Set 대기열을 자리 기반(concurrency) 입장 제어로 설계 — 동시 active 100명 상한에서 3초 주기 스케줄러가 빈 자리만큼만 Lua 원자 승급하고 예약 완료·이탈 시 슬롯 즉시 반환, SSE 실시간 순번 푸시 + Polling Fallback 이중 구성 및 평시 우회/포화 시 자동 대기 하이브리드 입장 제어 구현
- CAPTCHA + BruteForce 차단 + 봇 탐지(X-Suspicious 연동) + Redis 고정 윈도우 Rate Limit을 조합한 다층 Anti-Abuse 필터 체인 구축
- Prometheus 도메인 커스텀 메트릭 12종과 Micrometer Tracing 계측을 6개 서비스 전 구간에 적용, Zipkin으로 gateway→train 예약 동기 구간 trace 확보
- JMeter 1,000명 동시 접속 부하 테스트를 측정→진단→수정 5회 반복하여 에러율 56% → 0%, 예약 p95 14ms 달성 (bcrypt CPU 포화, Redis 왕복 폭증으로 인한 HikariCP 고갈, 소비된 큐 토큰 재발급 버그 규명·수정)

`Java 21` `Spring Boot 3.4` `Spring Cloud Gateway` `Netflix Eureka` `Spring Data JPA` `QueryDSL 5.1` `Flyway` `MySQL 8` `Redis (Redisson · Lua Script)` `Apache Kafka` `Resilience4j` `JWT` `OAuth2` `React 19` `TypeScript` `Docker Compose` `Prometheus` `Grafana` `Zipkin` `JMeter` `JUnit 5`

---

### 2. AI Pulse — AI 뉴스·기법 큐레이션 플랫폼

> AI/LLM 뉴스·기법을 자동 수집하고 Claude API로 요약·번역·분류해 카드 형태로 제공하는 풀스택 큐레이션 플랫폼

- **기간**: 2026.05 ~ 2026.07 (약 5주) · 개인 프로젝트
- **GitHub**: [yunnhho/AINews](https://github.com/yunnhho/AINews)
- **라이브 데모**: [AI Pulse](https://ai-pulse-demo-nu.vercel.app) · [관리자(읽기 전용)](https://ai-pulse-demo-nu.vercel.app/admin)

AI/LLM 뉴스·기법을 매일 4회 자동 수집하고 Claude API로 요약·번역·분류하여 카드로 제공하는 플랫폼입니다(웹 · 모바일 · 관리자 대시보드). LLM을 배치 파이프라인에 넣을 때의 비용 통제와 번역 품질 보증을, 무료 필터를 유료 단계 앞에 두는 원칙과 자동 품질 게이트로 풀어낸 경험을 했습니다.

**주요 성과**
- RSS · GitHub · 엔지니어링 블로그 · 뉴스레터 49개 소스를 Celery Beat 스케줄(KST 00/06/12/18시) 기반 배치 파이프라인으로 병렬 수집하고 카드 자동 발행
- URL SHA-256 완전 일치 + TF-IDF 제목 유사도(≥0.9) 2단계 디듀프를 AI 처리 앞단에 배치하여 중복분 토큰 비용 원천 차단
- 역번역(Back-translation) + 코사인 유사도 0.85 게이트로 LLM 번역 환각을 자동 차단하고 미달 카드는 수동 검토 큐로 격리하여 번역 품질 보증
- 카드 타입별 프롬프트 분리 + 입력 3,000자 절단 + 월 예산 하드 캡으로 AI 호출 비용 제어 (카드 1건 $0.0037 실측)
- 검색엔진을 Meilisearch에서 Elasticsearch로 전환하고, 배포 환경(Bonsai OpenSearch) 호환을 위해 opensearch-py 클라이언트 + cjk 바이그램 분석기로 재구성하여 한국어·영어 멀티필드 검색 구현
- implicit ALS 협업 필터링 + 상호작용 5건 미만 시 규칙 기반 자동 폴백 2단 추천 구조로 Cold Start 문제 해결
- 소스별 연속 실패 추적 및 3회 연속 실패 시 Slack/이메일 경보, 영구 소멸(404) 소스 자동 비활성화로 외부 소스 장애 격리
- 피드 응답 Redis 캐싱(TTL 5분, 필터 조합별 키) + 커서 페이지네이션으로 무한 스크롤 중 페이지 밀림(offset drift) 제거
- Playwright E2E(콘솔 에러 0 기준) + API 회귀 테스트 + 전면 리팩터 검증으로 만료 JWT 전 기능 401, Celery KST 시간대 버그, 검색 색인 클라이언트 불일치(프로덕션 색인 무음 실패) 등 실버그 16건 발견·수정
- 배포 전 보안 점검으로 취약점 8건 식별·7건 수정 — 웹 인증을 HttpOnly 쿠키 + CSRF 더블 서브밋 + Refresh 토큰 회전으로 개편, X-Forwarded-For 스푸핑 레이트리밋 우회 차단, 보안 회귀 테스트 7건 작성

`Python 3.12` `FastAPI` `SQLAlchemy 2.0` `PostgreSQL 16` `Redis 7` `Elasticsearch 8.17` `Celery 5.4` `Anthropic SDK` `sentence-transformers` `scikit-learn` `Next.js 15` `React 19` `React Native` `Docker Compose` `Railway · Vercel 배포` `pytest` `Playwright`

---

## 학력 / Education

- **인하공업전문대학교** 컴퓨터정보공학과 졸업 (2020.03 ~ 2025.02)

## 자격증 / Certificate

- **SQL 개발자(SQLD)** (2026.03 취득)
- **정보처리산업기사** (2025.09 취득)
