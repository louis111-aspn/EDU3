# GB Series QA Report v1.0

**대상**: GB01~07 (7개 HTML 모듈) — GB_Series_Constitution v1.0 기준 점검
**방법**: 소스 레벨 정량 점검(grep/텍스트 추출 기반) + 내용 검토. 실제 브라우저 렌더링 QA는 별도.

---

## 요약

| 영역 | 결과 |
|---|---|
| Vocabulary (Confidence vs Support Level) | ✅ PASS |
| Story Flow (Why→Flow→Structure→Mapping→Capability→Assessment→Architecture) | ✅ PASS |
| Insight 번호 (#01~#07) | ✅ PASS |
| Running Case(NGH) 데이터 일관성 | ✅ PASS |
| Learning Path Part 구분선 존재 여부 | ✅ PASS |
| Learning Path 모듈 라벨 표기 | ~~❌ FAIL~~ → ✅ **RESOLVED** (즉시 조치 완료) |
| 챕터 구조(Section Kicker/Wrap-up) | ✅ PASS |
| Data Modeling Insight 컴포넌트 사용 빈도 | ⚠️ NOTE — 의도된 진화로 판단, 아래 상세 |
| ADR Index 완결성 | ~~⚠️ NOTE~~ → ✅ **RESOLVED** (GB_Reference_Guide Part E.2에서 해결) |

---

## 1. Vocabulary — ✅ PASS

- `Confidence`(HIGH/MEDIUM/LOW)는 GB04에서만 사용되며, "SAP 매핑 구현의 확신도"라는 의미로 일관되게 쓰였다.
- `Support Level`(NATIVE/EXTENDED/PARTNER/CUSTOM/NOT AVAILABLE)은 GB06~07에서만 사용되며, "벤더가 Capability를 어느 방식으로 지원하는가"라는 의미로 일관되게 쓰였다.
- 두 용어가 비슷한 "정도를 나타내는 척도"이지만 혼용된 사례는 발견되지 않았다. 다만 **두 용어의 관계(왜 다른 척도를 쓰는지)는 어느 모듈에서도 명시적으로 설명되지 않는다** — Reference Guide 작성 시 "Confidence(GB04, Mapping 신뢰도) vs Support Level(GB06, Capability 지원 수준)" 구분을 명문화할 필요가 있다.
- `Business Object`는 GB03에서 정의된 이후 GB05(1회)·GB06(1회)·GB07(2회)에서 GB03 정의를 전제로 재인용되며, Capability와 혼용된 사례는 없었다.

## 2. Story Flow — ✅ PASS

각 모듈 인트로 문단을 검토한 결과, "이전 모듈 결론 → 이번 모듈 질문"의 연결이 7개 모듈 모두에서 명시적 문장으로 확인된다(예: GB03 인트로 "GB02는 ... Flow 관점에서 설명했다. 이번 모듈은 ... Structure를 다룬다"). Part I→II 전환점(GB05 인트로)에서도 "GB01~04는 Foundation, GB05부터 Strategy"라는 전환 콜아웃이 명확하다.

## 3. Insight 번호 — ✅ PASS

`grep`으로 전수 확인 결과 #01~#07이 모듈당 정확히 1회씩, 중복·누락 없이 등장한다.

## 4. Running Case(NGH) 데이터 일관성 — ✅ PASS

GB02에서 확정된 데이터셋(Korea 102,400/22,528, Germany 58,300/17,490, France 41,200/11,124, Singapore 31,800/3,180, Vietnam 19,600/1,960)이 이후 모듈에서 숫자로 재인용되는 경우는 없었고(GB03~07은 구조·개념 설명에 NGH를 사용, 수치는 GB02 내에서만 사용), 이로 인한 데이터 불일치 리스크는 없다. GB02 내부에서 Singapore/Vietnam의 GloBE Income(31,800/19,600)이 ETR 표와 Top-up Tax 표에 중복 등장하는 것은 동일 모듈 내 정상적인 재사용이다.

## 5. Learning Path Part 구분선 — ✅ PASS

7개 모듈 모두 Roadmap Grid 내 `part-divider`가 "PART I — FOUNDATION", "PART II — STRATEGY" 2개씩 정확히 존재한다.

## 6. Learning Path 모듈 라벨 표기 — ✅ RESOLVED

**문제(발견 시점)**: GB02~GB07 각 모듈명이 시리즈 진행에 따라 용어가 정착되었으나(Flow/Structure/Mapping/Capability/Assessment/Architecture), 이 정착 이전에 만들어진 GB01~03의 Learning Path에는 구버전 라벨이 그대로 남아있었다.

**정식 명칭(Canonical Set)** — GB04~07에서 실제로 정착되어 있던 체인을 기준으로 확정:

| 모듈 | 정식 라벨 |
|---|---|
| GB01 | Why |
| GB02 | Flow |
| GB03 | Structure |
| GB04 | Mapping |
| GB05 | Capability |
| GB06 | Assessment |
| GB07 | Architecture |

**조치**: 7개 파일 전체의 Learning Path(`rc-tag`) 라벨을 위 정식 명칭으로 일괄 치환했다. 이제 어느 모듈의 Learning Path를 보더라도 GB01~07의 이름이 완전히 동일하다(치환 결과: 파일당 7개 태그, 총 49개 태그 갱신, div 태그 균형 재검증 완료).

**Resolution**: Learning Path labels standardized across GB01–GB07 (Why / Flow / Structure / Mapping / Capability / Assessment / Architecture). 이는 표기 수정(Label Refactoring)이며 각 모듈의 실제 콘텐츠·설계는 변경되지 않았다. 따라서 Constitution v1.0 개정 대상이 아니며 시리즈 버전업으로도 간주하지 않는다.

## 7. Data Modeling Insight 컴포넌트 사용 빈도 — ⚠️ NOTE

Constitution은 "GB03부터 각 챕터 말미에 상시 삽입"이라고 규정하지만, 실제 사용 빈도는 다음과 같다.

| 모듈 | 사용 횟수 | 비고 |
|---|---|---|
| GB03 | 4 | 챕터당 1개, 규정대로 |
| GB04 | 0 | ADR Box로 대체됨(사용자 승인 사항) |
| GB05 | 0 | Capability Card/Declaration으로 대체됨 |
| GB06 | 1 | Ch3에만 1회 사용(Gap 유형 챕터) |
| GB07 | 1 | "예고" 형태로 1회만 사용, 실질적 통찰이 아니라 다음 섹션 안내 문구 |

**판단**: GB04·GB05의 대체는 사용자가 각 모듈 승인 과정에서 명시적으로 지시한 컴포넌트 진화(ADR Box, Capability Card)이므로 오류가 아니다. 다만 Constitution 3장의 "GB03부터 상시 삽입"이라는 서술은 실제와 맞지 않으므로, **QA 결과에 따른 사실 반영**이 필요하다 — Constitution 자체를 지금 수정하지 않는다는 원칙에 따라, 이 QA Report에 정정 사실을 기록해두고 차기 Constitution v1.1(컴포넌트 구조 변경 시점) 발행 시 반영 대상으로 남긴다.

## 8. ADR Index 완결성 — ✅ RESOLVED

**문제(발견 시점)**: GB04에서 생성된 4개 ADR(ADR-GB04-01~04) 중, GB07의 ADR Summary에는 01과 04만 인용되고 02(Jurisdiction 매핑)·03(Covered Tax 매핑)은 요약에서 누락되어 있었다.

**조치**: GB_Reference_Guide v1.0 Part E.2("ADR Index")에 4개 ADR 전체(Decision + Reason)를 인덱싱했다. GB07의 ADR Summary는 "원칙 요약"으로서의 역할을 유지하고, 전체 인덱스 역할은 Reference Guide가 담당하는 것으로 문서 간 역할이 명확히 분리되었다.

**Resolution**: ADR Index completed in GB_Reference_Guide Part E.2 (all 4 ADRs indexed with Decision + Reason).

---

## 조치 필요 항목 요약 (최종 상태)

| # | 항목 | 심각도 | 조치 |
|---|---|---|---|
| 1 | GB01~03 Learning Path 라벨 구버전 잔존 | High | ✅ **Resolved** — 7개 파일 전체 정식 명칭으로 일괄 치환 완료 |
| 2 | Constitution 3장 "Data Modeling Insight 상시 삽입" 서술과 실제 불일치 | Low | Constitution v1.1 발행 시 반영 예정 (유일한 미해결 항목) |
| 3 | ADR Index 미완결 | Low | ✅ **Resolved** — GB_Reference_Guide Part E.2에서 4개 ADR 전체 인덱싱 완료 |

**최종 집계**: High 1건(Resolved) · Low 2건 중 1건 Resolved, 1건 Constitution v1.1 대기.

---

*본 리포트는 GB_Series_Constitution v1.0을 기준으로 GB01~07 산출물을 점검한 결과이며, Constitution 자체는 변경하지 않았다. 본 문서는 GB_Series_QA_Report_v1.0(Updated)로 관리하며, 별도 버전업은 하지 않는다.*
