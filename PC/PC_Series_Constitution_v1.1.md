# PC Series Constitution v1.1

**Series**: PC (Presentation & Communication)
**Status**: Frozen (v1.1 Lock)
**Governs**: PC01–PC07

---

## Hero Message

> **좋은 컨설턴트는 많이 말하는 사람이 아니라, 복잡한 내용을 쉽게 이해시키는 사람이다.**
> A great consultant is not remembered for speaking well, but for making complex ideas easy to understand.

---

## 1. Purpose

### 1.1 왜 PC 시리즈를 만드는가
기존 BC/GR/SAC 시리즈는 "무엇을 아는가"(기술 지식)를 다룬다. PC 시리즈는 "아는 것을 어떻게 고객이 이해하도록 전달하는가"(설명 역량)를 다룬다. 이는 별도의 메타 스킬이며, 기술 시리즈와 독립적으로 존재하되 모든 기술 시리즈의 전달력을 뒷받침한다.

### 1.2 대상 독자
BAC 소속 주니어~시니어 SAP 컨설턴트. 특히 발표 경험이 적어 고객 앞에서 시스템/업무를 설명하는 데 어려움을 겪는 주니어 컨설턴트를 1차 대상으로 한다.

### 1.3 범위 (In-Scope)
- 고객 대상 설명/발표의 구조화, 전달, Q&A 대응, 상황별 전략, 훈련법
- SAP 기능을 예시로 활용한 설명 패턴 (SAC Allocation, Data Action, Universal Journal 등)
- Facilitation의 기본기 (워크숍/회의 운영에 필요한 최소 범위)

### 1.4 범위 밖 (Out-of-Scope)
- 일반적인 대중 강연/TED형 발표 스킬 (동기부여, 스토리텔링 중심 발표)
- SAP 기능 자체에 대한 심화 학습 (이는 GR/SAC/REF 시리즈가 담당)
- 프로젝트 관리, 협상, 세일즈 스킬

---

## 2. Core Principles

1. **Customer Understanding First** — 발표의 성공 기준은 발표자의 유창함이 아니라 고객의 이해다.
2. **Explanation over Presentation** — 컨설턴트는 감동시키는 사람이 아니라 이해시키고 의사결정을 돕는 사람이다.
3. **Audience First** — "무엇을 설명할 것인가"보다 "누구에게 설명하는가"를 먼저 결정한다.
4. **Business Context First** — 모든 설명은 SAP 기능을 소개하기 전에 그 기능이 필요한 비즈니스 문제에서 시작한다.
   - ❌ "Data Action은 데이터를 복사합니다."
   - ✅ "계획 수립에서는 이전 버전을 재사용해야 하는 경우가 많습니다. 이를 위해 SAC는 Data Action의 Copy Step을 제공합니다."
5. **One Slide, One Message** — 슬라이드 한 장은 하나의 결론만 전달한다.
6. **Slide is Visual Aid, Speech is Primary** — 슬라이드는 보조 수단이며, 설명의 본체는 말이다.
7. **Every Framework Needs a Before/After** — 새로운 프레임워크나 규칙을 소개할 때는, 가능한 한 Before/After 예시로 그 효과를 직접 보여준다. 설명보다 변화를 보여줄 때 학습 효과가 크다 (예: Pyramid → 나열형 vs 구조형, Action Title → 주제어 vs 완전한 문장, Support Evidence → 5개 나열 vs 3개 압축).

---

## 3. Standard Explanation Pattern (시리즈 대표 자산)

모든 SAP 기능/개념 설명은 다음 4단계를 따른다:

```
Concept          → 이것은 무엇인가 (정의)
Mechanism        → 어떻게 작동하는가 (동작 방식)
Business Value   → ERP/기존 방식과 비교했을 때 무엇이 다른가 (의미)
Customer Impact  → 고객의 업무/의사결정에 실제로 무엇이 바뀌는가
[Optional] Recommendation / Next Action → (제안서·Steering Committee 설명 시에만 추가) 이 내용을 바탕으로 무엇을 결정/실행해야 하는가
```

**적용 예시 (SAC Allocation)**
- Concept: Allocation은 Driver를 기준으로 Source 데이터를 Target으로 재분배하는 Planning Engine이다.
- Mechanism: Data Action 내 Allocation Step으로 실행되며, Driver/Source/Target을 사전 정의한다.
- Business Value: ERP CO Allocation과 달리 회계전표를 생성하지 않고 Planning Version의 데이터만 변경한다.
- Customer Impact: 실제 회계 마감에 영향을 주지 않으면서 시나리오별 배부 결과를 자유롭게 시뮬레이션할 수 있다.
- (Optional) Recommendation: 다수 시나리오 비교가 필요하다면 Driver를 Version 파라미터로 분리하는 설계를 권장.

이 패턴은 PC04를 중심으로 학습되며, 이후 모든 챕터의 예시 작성 시 기본 템플릿으로 사용한다. Recommendation 단계는 일반 기능 설명(Ch1~Ch4 수준)에는 불필요하며, 제안/의사결정을 요청하는 상황(PC06 임원 대상 설명 등)에서만 선택적으로 추가한다. 다른 시리즈(GR/SAC)의 콘텐츠 제작 시에도 참고 프레임워크로 활용할 수 있다.

**PC04와의 관계**: 본 패턴은 "무엇을 설명할지"를 정하는 설명의 논리 구조(Explanation Logic)다. PC04는 이를 변경하지 않고, 이 패턴을 실제 발표에서 감싸는 전달 순서 — Explanation Delivery Sequence(Audience Context → Why This Matters → Standard Explanation Pattern 적용 → Business Decision) — 를 별도로 소유한다. 두 개념은 서로 다른 레이어이며 하나가 다른 하나를 대체하지 않는다.

---

## 4. Chapter Ownership

| Chapter | 역할 | 비고 |
|---|---|---|
| PC01 | 발표의 본질 정의 | 발표=설명이라는 관점 전환 |
| PC02 | 메시지 구조화 | Audience Analysis, Pyramid, MECE |
| PC03 | 슬라이드/화면 활용 | 슬라이드는 보조 수단, 애니메이션 포함 |
| PC04 | 설명과 전달의 기술 | **시리즈 핵심**, Explanation Delivery Sequence(신규) 소유. Standard Explanation Pattern(§3)은 참조만 하며 변경하지 않음 |
| PC05 | Q&A와 토론 | Question Handling Pattern(신규) 소유. Explanation Delivery Sequence(PC04)와 반대 방향(청중→발표자)으로 작동하는 별도 레이어 |
| PC06 | 상황별 전략 & Facilitation | Presentation Facilitation Pattern(신규) 소유. 대상/상황별 사전 조정(6.3)은 기존 범위 유지, 세션 전체 운영은 PC04·PC05와 다른 단위(세션 전체 vs 설명/질문 단위)에서 작동 |
| PC07 | 연습 방법 | Presentation Learning Loop(신규) 소유 — 신규 Pattern이 아니라 PC01~PC06을 반복 훈련으로 전환하는 회수(Closure) 절차. Capstone에서 전 챕터를 재사용만 함 |

**중복 금지 원칙**: Standard Explanation Pattern은 PC04에서만 정의하고, 다른 챕터는 이를 참조만 한다. Signposting 문장은 PC04에서만 다루며 PC02(구조화)와 혼동하지 않는다. Facilitation은 PC06에서만 다루며 Q&A(PC05)와 구분한다 — Q&A는 "질문에 답하는 것", Facilitation은 "논의를 운영하는 것"으로 경계를 명확히 한다.

**예시 소유권 원칙**: 하나의 비즈니스 예시(예: SAC Allocation)에는 하나의 Primary Owning Chapter를 지정한다. 다른 챕터에서 동일 예시를 재사용할 경우, 반드시 학습 목적(Learning Objective)이 달라야 한다 — 예를 들어 PC04는 "설명 패턴 학습"을, PC02가 같은 예시를 쓴다면 "청중별 구조화 학습"을 목적으로 해야 하며, 단순 반복은 금지한다. 각 챕터 제작 시 예시 목록과 소유 챕터를 별도 표로 관리한다(§7 참조).

---

## 5. Design Standards

HTML 모듈의 컴포넌트별 필수/권장/선택 구분, Ownership Badge 표기 방식, Learning Rhythm Rule 등 세부 레이아웃 규격은 별도 문서 **PC_Series_HTML_Template_v1.0**에서 관리한다. Constitution은 "왜"(원칙)를, Template은 "어떻게"(컴포넌트 규격)를 다루며, Template 변경은 Freeze Rule 1의 적용을 받지 않고 Template 자체 버전(v1.1, v1.2…)으로 독립 관리한다.

각 절(section)의 기본 구성 요소(참고용 — 상세 Mandatory/Optional 구분은 Template 문서 참조):
1. Action Title (완전한 문장 결론)
2. Hero Message (핵심 한 문장)
3. Misconception → Correction
4. Key Takeaways (3개)
5. 실제 SAP 프로젝트 예시 (SAC/GR 중심, K100 스토리 재사용 가능)
6. Quick Check (판단형 자가 점검)
7. Chapter Summary
8. QA Gate

디자인 스탠다드는 기존 포털 Interactive Web Education Design Standard(폰트/색상/컴포넌트)를 그대로 따른다.

---

## 6. Quality Gates

모든 챕터 발행 전 다음을 검증한다:
- **기술적 정확성**: SAP 공식 문서 기준 검증, 절제된 서술 원칙 준수
- **실무 적용 가능성**: 예시가 실제 프로젝트 상황에서 재현 가능한가
- **예시의 일관성**: SAC/GR 예시가 Standard Explanation Pattern을 정확히 따르는가
- **교육 밀도**: 절당 정보량이 과하거나 부족하지 않은가
- **용어 일관성**: 기존 GR/SAC Constitution의 용어 매핑과 충돌하지 않는가 (예: Allocation, Data Action 등 SAC 시리즈 정의를 그대로 참조)
- **Explainability Check**: 이 챕터를 읽은 주니어 컨설턴트가 고객에게 해당 개념을 실제로 설명할 수 있는가? (PC 시리즈의 존재 이유를 검증하는 핵심 게이트)

---

## 7. Example Ownership Registry (초기 배정)

| 예시 | Primary Owning Chapter | 재사용 가능 챕터 | 재사용 시 학습 목적 |
|---|---|---|---|
| SAC Allocation | PC04 (설명 패턴) | PC02, PC07 | PC02: 청중별 구조화 / PC07: 실습 케이스 |
| Data Action (Copy Step) | PC04 (Business Context First 예시) | PC01 | PC01: 설명 vs 발표 차이 예시 |
| K100 컨설팅 스토리 | PC07 (실습) | 전 챕터 배경 설정 | 배경 설정 목적으로만 인용, 신규 학습 포인트 추가 금지 |
| BPC Ownership Manager (지분율 변경) | PC01 (Hero Exercise · 인식 전환) | PC04 (가능) | PC04: Business Context First 패턴의 정식 설명 예시로 재사용 가능 |
| SAC Planning 4요소 (Model/Version/Data Action/Allocation) | PC02 (Hero Exercise · 구조화 효과 체험) | — | (현재 단독 배정) |
| SAC Allocation 3인 설명 (CFO/IT/Planner) | PC02 (Audience Analysis) | PC04, PC06 | PC04: 설명 패턴 심화 / PC06: 상황별 전략 예시 |
| 슬라이드 Before/After 4항목 대비 (읽기→보기, 청중 경험) | PC03 (Hero Before/After) | — | (현재 단독 배정) |
| Universal Journal 3단계 설명 비교 (A/B/C, Concept 단계별 확장) | PC04 (Hero Exercise) | — | (현재 단독 배정) |
| SAC Allocation ERP 비교 질문 A/B/C (Question Response Simulation) | PC05 (Hero Exercise) | — | (현재 단독 배정) |
| Executive Workshop Facilitation 시나리오 (CFO/IT/현업 동시 반응 관리) | PC06 (Hero Exercise) | — | (현재 단독 배정) |
| Presentation Learning Loop (Prepare→Practice→Present→Reflect→Improve) | PC07 (Primary Concept) | — | 신규 예시 아님, PC01~PC06 재사용 기반 Closure 개념 |

*신규 예시 추가 시 본 표를 갱신하고, Primary Owning Chapter를 먼저 지정한 뒤 제작을 시작한다.*

---

## 8. Version Policy

- v1.0 = Baseline (Freeze 2026-07-29)
- **v1.1= Core Principle #7 (Every Framework Needs a Before/After) 추가, Design Standards를 별도 Template 문서로 분리 (Freeze Rule 1 예외 — 전 챕터에 영향을 주는 원칙 추가로 판단)**
- v1.x = 챕터 추가/절 조정 등 구조적 업데이트
- v2.0 = 핵심 원칙 또는 Standard Explanation Pattern 자체의 재구성

---

## 9. Freeze Rules (v1.0 Lock 시점 선언)

**Freeze Rule 1 — Constitution Stability**
> Constitution changes only when multiple chapters are affected. A new idea discovered during a chapter implementation should be treated as a chapter-specific refinement unless it impacts the design principles of the entire series.

즉, 개별 챕터(예: PC01) 제작 중 발견된 아이디어는 우선 해당 챕터의 개선 사항으로 처리하며, 시리즈 전체 설계 원칙에 영향을 줄 때만 v1.1 발행을 검토한다.

**Freeze Rule 2 — Framework Reuse**
> The Standard Explanation Pattern is a reusable framework, not a mandatory script.

Business Context → Concept → Mechanism → Business Value → Customer Impact → Recommendation은 설명을 조직하는 프레임워크이며, 모든 발표에서 기계적으로 전 단계를 따라야 한다는 의미가 아니다. 상황에 따라 일부 단계를 생략하거나 순서를 조정할 수 있다.

---

*본 문서는 v1.0으로 Freeze되었다. PC01–PC03 제작 후 1차 QA를 수행하며, 이 기간 중 Constitution은 원칙적으로 변경하지 않는다.*
