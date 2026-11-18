# 임재린 | Java / Spring Backend Developer

## 2026-11 포트폴리오 개편 기록

- **목적과 범위:** 첫 방문자가 경력과 대표 업무 사례를 먼저 이해하도록 소개와 사례 진입 경로를 정리하고, 근무계획·마감 사례의 업무 흐름을 시각화한다. 기존 상세 페이지와 주소는 유지한다.
- **선택:** 전체를 새 사이트로 교체하는 대신 기존 Astro 사이트와 사례 자료를 재사용했다. 소개 다음에 대표 사례를 배치하고 상세 페이지에는 업무 흐름을 추가했다. 개별 운영 성과나 확인되지 않은 수치는 새로 주장하지 않는다.
- **트레이드오프:** 기존 상세 페이지의 내용과 구성은 대부분 유지하므로 모든 사례가 같은 깊이나 시각 형식을 갖추지는 않는다. 회사 내부 코드와 고객 데이터는 포함하지 않는다.
- **완료 조건:** 사진과 경력 소개, 대표 사례, 상세 페이지 이동과 모바일 메뉴가 작동하고, 빌드와 데스크톱·모바일 화면 점검이 완료되어야 한다.
- **기여:** 사용자는 참고 방향과 사진을 제공하고 표현을 결정했다. Codex는 기존 공개 사이트와 자료를 바탕으로 구성·화면을 수정하고 검증했다.
- **검증:** `npm run build`에서 9개 정적 페이지 생성 확인. 로컬 브라우저에서 첫 화면, 대표 사례 진입, 모바일 배치와 메뉴를 확인했다. 배포 후 공개 URL과 각 사례의 실제 내용·링크는 추가 확인이 필요하다.

**포트폴리오 사이트:** [GitHub Pages](https://limjaelin.github.io/portfolio/)

2024년 2월부터 Java 8/Spring Boot·MyBatis·Oracle 기반 인사·근태·급여 ERP의 백엔드와 업무 화면을 개발했습니다. 근무정책·마감/재집계·다중 DB 라우팅·배치 트랜잭션·외부 시스템 연동을 다루었고, 별도 Windows 근태 수집 앱(Electron/Node.js)의 외부 DB·시간대 처리도 개발·수정했습니다.

개인 프로젝트에서는 AWS ECS/Fargate·PostgreSQL 배포 및 장애 대응을 경험했고, 현재는 StratDock(연구·검증)과 별도 Java/Spring 관제 앱인 StratDock-Observatory를 개발하고 있습니다.

> **경계:** 회사 프로젝트의 Git 기반 구현 증거와 실제 배포·운영 성과는 구분합니다. 개인 프로젝트의 가상 주문 검증은 실제 주문·실계좌 운영 실적이 아닙니다. 고객·사내 코드·보안 정보는 공개하지 않습니다.

## Selected Company Work

| 사례 | 문제·개발 기여 | 상세 |
|---|---|---|
| **월근태 마감 변경 감지와 선택 재집계** | 마감 후 4종 원천 변경 시각 비교, 확인 기록, 잠금·선택 재집계 | [상세 페이지](https://limjaelin.github.io/portfolio/cases/month-close-rebuild/) |
| **Windows 근태 데이터 수집·연동** | PostgreSQL/SQLite 동기화, KST/UTC 변환, ODBC 진단, CALS↔ERP 데이터 계약 | [상세 페이지](https://limjaelin.github.io/portfolio/cases/attendance-integration/) |
| **근무정책 기반 계획 생성** | 5개 근무유형·3개 휴게시간 소스, 익일·휴일·퇴직일·수동 수정 보호 | [상세 페이지](https://limjaelin.github.io/portfolio/cases/work-schedule-policy/) |
| **Multi DataSource Routing** | 회사 코드 기준 3개 DB 환경, `LazyConnectionDataSourceProxy` / HikariCP | [상세 페이지](https://limjaelin.github.io/portfolio/cases/multi-datasource-routing/) |
| **배치 부분 실패 격리·재처리** | 처리 단위별 `REQUIRES_NEW`, 성공/실패 집계, 재처리 누락 조건 수정 | [상세 페이지](https://limjaelin.github.io/portfolio/cases/batch-partial-failure/) |
| **사원등록 초기 로딩 분석·개선** | 화면·API 호출 경로 분석과 지연 로딩 | [상세 페이지](https://limjaelin.github.io/portfolio/cases/employee-loading-performance/) |

그 외 전자계약 REST API 6종의 요청·외부 ID 매핑·상태/PDF 조회, 근무계획 변경 후 DB 재계산 연계, 조건검색 API 등 기능 개발 경험이 있습니다.

**주요 기술:** Java 8, Spring Boot 2.3.1, Spring MVC, Spring Transaction, MyBatis, Oracle, HikariCP, Spring Scheduler, REST API, AngularJS

## Personal Projects

### StratDock — 현재 개발·검증

Python·PostgreSQL·QuantConnect를 이용해 연구 신호·자료 시점·출처 정합성을 확인하고, 복원 가능한 오프라인 GHOST 가상 원장을 구현했습니다. 중복 이벤트·시간 역행·불일치 상태를 차단하는 검증 로직과 CI 테스트를 갖추고 있습니다.

- 단계: 연구 및 가상 실행 후보 검증
- **PAPER/LIVE 주문·브로커 연결 비활성**
- 실거래 수익이나 운영 성과를 주장하지 않음

### StratDock-Observatory — 개인 Java/Spring 관제 앱

Java 25·Spring Boot·PostgreSQL·React로 연구·상태 정보를 조회하는 관제 화면과 API를 개발했습니다. 별도 읽기 전용 JDBC 연결 및 응답 계약 검증, **합성 데이터**를 사용하는 PostgreSQL → Spring API → UI 통합 테스트를 갖췄습니다.

- 실제 StratDock 운영 DB·계좌 자료의 전체 연결 및 운영 배포는 검증되지 않음
- Java/Spring 구현 증거와 회사의 production JPA 경험을 구분

### Stock-manager — 이전 프로젝트 / 레거시 참고용

금융 데이터 프로젝트의 이전 구현입니다. 지금은 StratDock으로 활동 중심을 옮겼으며, **이전의 AWS/PostgreSQL 배포·운영 장애 대응 경험**을 설명하는 사례로 유지합니다.

- Docker·PostgreSQL → AWS ECS/Fargate·ECR·RDS 배포 및 GitHub Actions CI/CD
- ECS Task 기동 실패 분석, PostgreSQL deadlock·lock timeout 대응
- [클라우드 운영 사례](https://limjaelin.github.io/portfolio/cases/stock-manager-production/)
- [시간 데이터·전략 평가 검증](https://limjaelin.github.io/portfolio/cases/stock-manager-logic/)

### StockDataController — 팀 프로젝트

Python/FastAPI·PostgreSQL 기반 금융 데이터 수집 시스템에서 외부 API 호출 제한·거래 시간·실시간 수집 오류와 뉴스 파이프라인의 비동기 I/O/CPU 병목을 다뤘습니다. 팀 프로젝트 전체 설계 기여로 확대하지 않습니다.

### Backend Engineering Lab — 공개 학습·검증 저장소

Java 21·Spring Boot 4·Spring Data JPA·Hibernate·PostgreSQL로 영속성 컨텍스트, Dirty Checking, N+1/Fetch Join, 낙관적 락, 트랜잭션 전파를 작은 테스트로 재현했습니다.

[→ backend-engineering-lab](https://github.com/LIMJAELIN/backend-engineering-lab)

## Technical Approach

- 문제·데이터 정합성·트랜잭션 범위와 실패 조건을 먼저 정의합니다.
- 이력서에는 실제 구현·테스트·운영을 구분하고, 확인되지 않은 개선율·수익·처리량은 사용하지 않습니다.
- AI 코딩 도구를 작업에 활용하되, 범위 정의·코드 검토·테스트 결과·미확인 조건을 구분합니다.

## Links

- [Portfolio Website](https://limjaelin.github.io/portfolio/)
- [GitHub Profile](https://github.com/LIMJAELIN)
- [Backend Engineering Lab](https://github.com/LIMJAELIN/backend-engineering-lab)

_공개용 포트폴리오 요약: 2026-11-18. 회사 내부 데이터·접속 정보·상세 소스는 포함하지 않았습니다._
