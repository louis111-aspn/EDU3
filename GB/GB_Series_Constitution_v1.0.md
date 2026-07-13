# GB Series Constitution v1.0

**ASPN BAC사업부 내부 표준 문서 — GB(GloBE & SAP Add-on Discovery) 시리즈의 설계 원칙을 고정한다**

Status: Frozen (GB01~07 기준)
관련 문서: G0(GloBE Solution Landscape & Product Strategy) · RN-001(SAP Enterprise Calculation Platform Strategy)

---

## 1. 시리즈 정체성

**GB 시리즈란 무엇인가**
GB는 GloBE(OECD Pillar Two, 글로벌 최저한세)를 SAP Group Reporting(GR) 고객 관점에서 이해하고, 이를 바탕으로 ASPN의 GloBE Add-on 제품 전략을 논리적으로 도출하는 교육 및 방법론 시리즈다. GloBE 세법 교육이 아니라 **Enterprise Architecture Methodology**로 기능하는 것을 의도적으로 지향한다.

**3층 문서 체계에서의 위치**

| 문서군 | 역할 | 질문 |
|---|---|---|
| G0 | 제품 전략 (Product Strategy) | 무엇을 만들 것인가? |
| RN-001 | 기술 전략 (Technology Strategy) | 왜 이 아키텍처인가? |
| **GB01~07** | **교육 및 방법론 (Education & Methodology)** | **어떻게 이해하고 구현하는가?** |

GB 시리즈는 G0가 도출한 제품 기회와 RN-001이 제시한 "Enterprise Calculation Platform" 가설을, 실제로 이해 가능한 논리 단계로 풀어낸 결과물이다. GB07의 결론(Reference Architecture)은 다시 G0/RN-001로 피드백되어야 한다.

**GR 시리즈와의 관계**
GB는 GR(Group Reporting Foundation/Advanced Lifecycle Series)과 별도 트랙이며, GR03~10에서 확립된 개념(ACDOCA, Release Universal Journal, ACDOCU, Consolidation Unit 등)을 전제로 인용하되 반복 설명하지 않는다. Running Case도 GR의 K100과 독립된 별도 케이스(Nova Global Holdings)를 사용한다.

**Part 구조**

| Part | 모듈 | 성격 |
|---|---|---|
| Part I — Foundation | GB01(Why) · GB02(Flow) · GB03(Structure) · GB04(Mapping) | 개념·계산·데이터모델·구현 원칙 학습 |
| Part II — Strategy | GB05(Capability) · GB06(Assessment) · GB07(Architecture) | 제품을 배제하고 역량→평가→아키텍처 도출 |

Part 경계가 결정된 시점(GB05 승인 시)에 GB01~04에도 Part 배지와 Learning Path 구분선을 **소급 적용**했다. 향후 새로운 Part 경계가 생기면 동일한 소급 원칙을 적용한다.

---

## 2. 모듈 공통 문법 (Common Grammar)

모든 GB 모듈은 다음 순서를 따른다.

1. **Hero**: GB SERIES 배지 + Part 배지 + 모듈 제목(영문) + 핵심 문장(부제)
2. **Sticky Nav Tabs**: 인트로 + Ch1~N + Wrap-up, 스크롤 연동 active 표시
3. **인트로**: Think Question + (필요 시) Running Case 배너
4. **각 챕터**: Section Kicker → Section Title → **Action Title**(챕터 결론을 완전한 문장으로) → 본문 → 해당 챕터의 고정 컴포넌트
5. **Wrap-up**: Conclusion Box(모듈 결론 + Bridge) → Calculation Platform Insight → (모듈별 신규/누적 컴포넌트) → Checklist → Learning Path(Part 구분선 포함 Roadmap Grid)

**Action Title 원칙**: 반드시 완전한 문장으로, 그 챕터를 다 읽지 않아도 결론을 알 수 있어야 한다.

---

## 3. 공통 컴포넌트 인벤토리

| 컴포넌트 | 도입 모듈 | 용도 | 재사용 규칙 |
|---|---|---|---|
| Business vs System | GB01 | Business 언어 ↔ SAP 언어 짝짓기 | GB01 Ch4에서 확립. 이후 필요한 모듈에서 개념별로 재사용 |
| B/D/R/S/O Template | GB02 | 핵심 개념을 Business/Data/Rule/System/Output 5관점으로 정리 | GB02부터 핵심 개념(Covered Tax, GloBE Income, ETR, Top-up Tax 등) 등장 시마다 반복 |
| Calculation Trace | GB02 | 계산 파이프라인상 현재 위치 표시 (다크 톤 소형 박스) | Flow 성격의 챕터에서 사용 |
| Data Modeling Insight | GB03 | 챕터 단위의 짧은 통찰 (Calculation Platform Insight와 달리 챕터별, navy 테두리) | GB03부터 각 챕터 말미에 상시 삽입 |
| ERD / Structure Diagram | GB03 | 관계 중심의 세로형 트리 (Flow 다이어그램과 시각적으로 구분) | Structure를 다루는 챕터의 대표 다이어그램 |
| Identifier 표기 | GB03 | Business Object의 유일 식별자 속성 | Object 등장 시 `[id-tag]`로 표기, Catalog에 정식 컬럼화 |
| Logical/Physical Bridge | GB03(Wrap-up) · GB04 | Logical Model → Physical Model → SAP 3단 전환 | Part I 마지막(GB04) Layer 전환에 사용, 이후 반복 없음 |
| Mapping Table + Confidence | GB04 | Business Object → SAP Example, HIGH/MEDIUM/LOW 확신도 태그 | "예시"라는 표현과 항상 병기, 정답처럼 서술 금지 |
| ADR Box (Decision + Reason) | GB04 | 챕터별 아키텍처 결정 기록, ID는 `ADR-GB0X-0Y` | 시리즈 전체에서 고유 ID 유지, 이후 모듈에서 인용 가능 |
| Calculation Boundary Diagram | GB04 | SAP Standard 영역과 Calculation Platform/Add-on 영역의 경계 시각화 | 표준 범위 밖 기능을 설명할 때 사용 |
| Capability Card (+Success Criteria) | GB05 | Capability/Purpose/Input/Output/Owner/Success Criteria 6필드 | GB05~07 전체에서 동일 포맷 재사용 |
| Maturity Ladder | GB05 | Level 1~4, **조직 기준**(개인 숙련도 아님) | Capability 성숙도 논의 시 재사용 |
| Capability Dependency | GB05 | Capability 간 의존 관계(상위가 하위에 의존) 시각화 | 신규 Capability 추가 시 재사용 |
| Series Milestone | GB04 도입 (Series Conclusion 개념 확정은 GB07) | GB01~07 진행 상황(✓/□) | 매 모듈 Wrap-up에 누적 갱신 |
| Support Level Tag | GB06 | NATIVE/EXTENDED/PARTNER/CUSTOM/NOT AVAILABLE, "구현 책임"과 병기 | 벤더 평가 시 ○△◎ 대신 항상 이 태그 사용 |
| Capability Assessment Matrix | GB06 | Capability × 벤더 Support Level 평가표 | "비교표"가 아니라 "평가"라는 프레이밍 유지 |
| Gap Type Card / Gap Card (+Owner) | GB06 | Functional/Process/Ownership 3분류, Gap Card는 5필드(Capability/Gap Type/Impact/Owner/Possible Solution) | 제품으로 이어지지 않는 Gap(Ownership 등)을 의도적으로 최소 1건 포함 |
| Architecture Layer Stack | GB07 | Capability를 제품 독립적 Layer로 재구성 | 제품명 없이 먼저 제시 (Ch1 원칙) |
| Platform Principle Card | GB07 | 시리즈 전체를 관통하는 설계 원칙 선언 | AGRA 제품군 설계 기준으로 승격 |
| ADR Summary | GB07 | GB03~06의 개별 ADR/결정을 출처와 함께 한 곳에 집약 | 시리즈 종결 모듈에서 1회 사용 |
| Series Conclusion Chain | GB07 | Problem→...→Architecture 전체 여정 + 최종 선언 문장 | 시리즈 종결 전용, 반복하지 않음 |
| **Calculation Platform Insight** | GB01 (#01) | 모듈 전체 결론 수준의 통찰, 다크 톤 대형 박스, 번호 순차 부여 | **전 모듈 Wrap-up에 상시 배치.** RN-001 등 내부 문서명을 직접 언급하지 않고 내용만 인용 |

---

## 4. Writing Principle

**절제된 서술 원칙**: SAP 공식 문서·공개 자료로 확인된 내용만 단언한다. 확인되지 않은 사항은 "프로젝트별 확인 필요" 또는 "확인 필요" 표기로 명시하고 넘어간다. (GB03 PE 판단기준, GB04 SAP BAdI/CDS/OData 확장포인트, GB06 SAP 열 평가 등)

**일반화 주의**: 규제·기능 범위가 계속 바뀌는 영역(Safe Harbour, QDMTT 시행 현황 등)은 콜아웃으로 스냅샷 시점을 명시한다.

**Business First**: 벤더 중립적 개념을 먼저 서술하고, SAP는 그 다음 단락에서 "구현 예시"로 배치한다(GB01 Ch4에서 확립: "GB 시리즈는 SAP 제품 교육이 아니라 GloBE 교육이다"). GB04 이후에는 이 원칙이 "Mapping Rule 3원칙"(Business Object 우선/SAP는 구현 예시/프로젝트마다 상이)으로 공식화된다.

**"예시" 반복 표기**: Mapping Table, Product Mapping 등에서 특정 시스템·제품을 "정답"처럼 서술하지 않고 "예시"라는 표현을 의도적으로 반복한다.

**단순화 명시**: 교육적 단순화를 적용한 경우(GB02 Top-up Tax의 SBIE 제외 등) 반드시 콜아웃으로 실제 규정과의 차이를 알린다.

**내부 문서 비노출**: RN-001, G0 등 내부 전략 문서명을 교육 모듈 본문에 직접 언급하지 않는다. 그 내용(철학·통찰)만 교육생이 이해할 수 있는 문장으로 녹여낸다.

---

## 5. Business Capability → Architecture → Product 원칙

GB 시리즈 전체를 관통하는 순서 원칙이다.

```
Part I:  Why → Flow → Structure(Logical Model) → Mapping(Physical Model)
Part II: Capability → Assessment(Gap) → Architecture → (예시로서) Product
```

- 제품은 Architecture Layer가 정의된 **이후에만** 등장한다(GB07 Ch1은 제품명 없이 시작).
- Architecture Layer 중 제품으로 채워지지 않는 계층(Governance Layer 등)이 존재할 수 있으며, 이를 숨기지 않고 "왜 제품이 아닌가"까지 설명한다(GB06/GB07 Governance 사례).
- 이 원칙은 GB뿐 아니라 향후 다른 도메인 시리즈(ESG, Transfer Pricing, Treasury 등)에도 그대로 적용 가능한 것으로 간주한다.

---

## 6. Learning Path / Part 표기 규칙

- Hero에는 `GB SERIES` 배지와 `PART I · FOUNDATION` 또는 `PART II · STRATEGY` 배지를 함께 표기한다.
- Wrap-up의 Roadmap Grid(Learning Path)는 GB01~07 전체를 항상 포함하며, Part 경계에 `part-divider`(전체 폭 구분선)를 삽입한다.
- 현재 모듈은 `roadmap-card current`로 강조하고, Series Milestone(GB04 이후 도입)에는 완료(✓)/현재(강조 ✓)/대기(□) 상태를 함께 표기한다.
- 새 모듈 추가 시, 이전 모든 모듈의 Roadmap Grid에도 새 카드를 소급 반영하는 것을 원칙으로 하되, 최소 요건으로 Wrap-up 텍스트만이라도 갱신한다.

---

## 7. 모듈 요약표 (GB01~07)

| 모듈 | 제목 | 핵심 문장 | Insight # |
|---|---|---|---|
| GB01 | GloBE란 무엇인가 | GloBE는 연결재무데이터에서 시작된다 | #01 |
| GB02 | GloBE 계산 메커니즘 | GloBE는 하나의 계산이 아니라, 데이터와 규칙이 결합된 계산 체계이다 | #02 |
| GB03 | GloBE Data Model | GloBE는 데이터를 계산하는 것이 아니라, 데이터 모델 위에서 계산한다 | #03 |
| GB04 | Mapping the GloBE Data Model to SAP | 좋은 데이터 모델은 하나지만, 좋은 구현은 여러 가지가 존재할 수 있다 | #04 |
| GB05 | Enterprise GloBE Capability | 소프트웨어는 기능을 제공하지만, Capability는 업무를 완성한다 | #05 |
| GB06 | Capability Assessment — Gap Analysis | Capability Gap은 문제를 정의한다. Architecture Decision은 해결 방향을 결정한다. Product는 그 결과일 뿐이다 | #06 |
| GB07 | Enterprise GloBE Reference Architecture | 좋은 제품은 기능을 연결한다. 좋은 플랫폼은 Capability를 연결한다 | #07 |

---

## 8. Running Case — Nova Global Holdings (NGH)

- 구조: NGH (Korea, HQ) / Germany / France / Singapore / Vietnam
- GB01에서 구조만 소개, GB02부터 실제 수치(GloBE Income, Covered Tax, ETR) 등장
- 검증된 NGH 데이터셋(GB02 기준): Korea 102,400/22,528(22.0%), Germany 58,300/17,490(30.0%), France 41,200/11,124(27.0%), Singapore 31,800/3,180(10.0%), Vietnam 19,600/1,960(10.0%)
- GR 시리즈의 K100과 독립적이며, GB뿐 아니라 향후 PP·ESG·Transfer Pricing·Treasury 시리즈에서도 재사용 가능한 범용 케이스로 설계됨(GB03 NGH Germany 구조 — Legal Entity/PE 예시 포함)

---

## 9. 버전 관리 정책

Series_Design_Standard의 버전 정책을 준용한다.

- v1.x: 표현·기술 정확도 업데이트 (예: SAP 공식 문서로 재검증된 사항 반영)
- v2.x: 컴포넌트·챕터 구조 변경
- v3.x: 커리큘럼 수준 재설계(Part 구조 변경 등)

본 문서는 GB01~07 Freeze 시점 기준 v1.0이다.

---

## 10. 향후 계획 (Deferred — 본 문서 범위 밖)

다음 항목은 GB_Series_Constitution 승인 이후 별도로 진행한다.

1. **시리즈 전체 QA**: 용어 통일(Business Object/Capability/Architecture/Mapping Rule/Architecture Decision/Support Level 등), 개념 설명 일관성, Learning Path/Part 표기 일관성, 컴포넌트 재사용 여부 점검
2. **Reference Guide**: GloBE Vocabulary, Business Object Catalog, Capability Reference, ADR Index, Insight Index, Acronym Index — 교육 모듈과 별도의 사전형 참조 문서
3. **GB08 이후 여부**: GB07에서 논리적 완결. 필요 시 심화편(Safe Harbour, GIR Filing, SAP PaPM Implementation, Data Collection Architecture, Review & Audit Workspace 등) 후보로 검토
4. **PP 시리즈**: RN-001의 Enterprise Calculation Platform 가설은 유효하나, GB 시리즈의 실제 프로젝트·고객 피드백 검증 이후 별도 착수

---

*이 문서는 ASPN BAC사업부 GB 시리즈의 기준 문서이며, GB08 이상이 추가되더라도 본 문서의 원칙을 우선 적용한다.*
