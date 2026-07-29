# PC Series HTML Template v1.1

**Governs**: PC01–PC07 HTML 모듈의 컴포넌트 구성 및 레이아웃 규격
**Relationship to Constitution**: Constitution(PC_Series_Constitution_v1.1)이 "왜"(원칙)를 정의한다면, 본 문서는 "어떻게"(컴포넌트 규격)를 정의한다. 본 문서는 Constitution의 Freeze Rule 1(원칙 안정성) 적용을 받지 않으며, 필요 시 독립적으로 v1.1, v1.2로 개정한다.

**Baseline**: PC01(발표의 본질), PC02(메시지 구조화) 제작 및 QA 결과를 기준으로 확정.

---

## 1. Component Status Table

| 컴포넌트 | 상태 | 비고 |
|---|---|---|
| Action Title | **Mandatory** | 모든 절(section) 상단, 완전한 문장 결론 |
| Hero Message | **Mandatory** | 챕터 최상단, 핵심 한 문장 |
| Misconception → Correction | **Mandatory** | 챕터당 최소 1개 이상. PC 시리즈의 정체성 — 설명력 교육은 항상 "잘못된 습관 → 올바른 방법" 교정 과정이다 |
| Key Takeaways (3개) | **Mandatory** | 절마다 3개 고정 |
| Quick Check (판단형) | **Mandatory** | 암기형 금지. 반드시 시나리오/판단 상황으로 구성 (§3 참조) |
| Chapter Summary | **Mandatory** | 챕터 종료 시 3문장 |
| QA Gate | **Mandatory** | Constitution §6 Quality Gates + Explainability + Can-be-applied-immediately 포함 (§4 참조) |
| Hero Exercise | **Recommended** | 체험적 학습이 이해를 크게 높이는 경우에만. 강제 금지 (§2 참조) |
| Before/After | **Strongly Recommended** | 새 프레임워크·규칙 소개 시 (Constitution 원칙 #7과 연동, §5 참조) |
| Compare Table | Optional | 필요시 보조 참고자료로 격하 가능 (예: PC02 TED vs 컨설턴트형 비교표를 `<details>` 접이식으로 처리) |
| Diagram / Journey / Flow | Optional | 개념 시각화가 필요한 경우 |
| Example Ownership Badge | Optional | 본문에는 Primary Example만 표시 (§6 참조) |

---

## 2. Hero Exercise — Recommended, Not Mandatory

> Recommended when experiential learning significantly improves understanding.

억지로 모든 챕터에 넣으면 흐름이 깨질 수 있다. 챕터 성격에 따라 판단한다.

**예상 적용 (참고용, 챕터 제작 시 재확인)**

| Chapter | Hero Exercise |
|---|---|
| PC01 | ✅ 적용 완료 |
| PC02 | ✅ 적용 완료 |
| PC03 | Before/After로 대체 (§2.1 Exception Rule 적용) |
| PC04 | ✅ (Concept→Mechanism→Business Value 패턴 자체가 체험형과 잘 맞음) |
| PC05 | △ (질문 대응 시뮬레이션 형태 검토) |
| PC06 | △ |
| PC07 | ❌ (체크리스트·실습 중심이라 별도 Exercise 불필요) |

### 2.1 Exception Rule — Before/After가 Hero Exercise를 대체할 수 있는 경우

> When the chapter itself teaches visual communication or presentation techniques, a Before/After demonstration may replace the Hero Exercise.

챕터의 주제가 시각적 전달 기법 자체(슬라이드 디자인, 화면 전환, 레이아웃 등)를 다루는 경우, 학습자가 문제를 직접 푸는 체험형보다 **잘못된 예시와 개선된 예시를 나란히 보여주는 것**이 더 효과적이다. 이 경우 Hero Exercise 자리에 Before/After(또는 3단계: Bad → Problem Analysis → Good)를 Hero로 승격한다. Learning Rhythm Rule의 "See" 단계가 핵심인 챕터일수록 이 예외가 적용될 가능성이 높다 — PC03이 최초 적용 사례이며, 향후 시각 전달·리팩터링 성격의 챕터에도 동일 기준을 적용한다.

---

## 3. Quick Check — 판단형으로 통일 (Freeze)

암기형("OO의 목적은?")은 검색으로 대체 가능하므로 금지한다. 반드시 다음 중 하나의 형태를 따른다:
- 시나리오 판단형: "OO 상황에서 가장 적절한 대응은?"
- 대상 선택형: "OO에게 설명할 때 무엇을 먼저 말해야 하는가?"
- 즉시 적용형: "다음 슬라이드 제목 중 원칙에 맞는 것은?"

---

## 4. QA Gate — 필수 점검 항목

Constitution §6 Quality Gates(기술적 정확성/실무 적용 가능성/예시의 일관성/교육 밀도/용어 일관성)에 더해 다음 두 항목을 모든 챕터에서 명시적으로 기록한다:

```
☐ Explainability Check
  이 장만 읽고 주니어가 "고객에게 설명"할 수 있는가?

☐ Can be applied immediately?
  오늘 슬라이드 하나를 바로 고칠 수 있는가?
```

두 항목 모두 Yes/No와 근거를 함께 기록한다 (PC01·PC02 QA Gate 참조).

---

## 5. Before/After — Strongly Recommended

Constitution 원칙 #7(Every Framework Needs a Before/After)의 실행 규격이다. 새 프레임워크나 규칙을 소개할 때는 설명(prose)만으로 끝내지 않고, 가능한 한 아래 형식의 시각적 대비를 포함한다.

```html
<div class="ba-pair">
  <div class="before"><span class="tag">BEFORE</span>...</div>
  <div class="after"><span class="tag">AFTER</span>...</div>
</div>
```

적용이 불가능하거나 어색한 경우(예: 순수 개념 정의)에는 생략할 수 있으나, 생략 사유를 QA Gate에 한 줄로 기록한다.

---

## 6. Example Ownership Badge — 단순화

본문에는 **Primary Example만** 표시한다. Reuse 정보는 본문에 노출하지 않고 Constitution §7 Example Ownership Registry에서만 관리한다.

**본문 표기 (단순화 후)**
```html
<div class="badge-row">
  <span class="badge">Primary Example · PC04</span>
</div>
```

**Registry 표기 (기존 유지)**
```
Primary Owner: PC04
Reuse: PC01 (Mindset), PC07 (Exercise)
```

> PC01·PC02에서 사용한 `Reuse · ...` 뱃지는 본문에서 제거하고 Registry로 이관한다 (§7 반영 작업 필요).

---

## 7. Learning Rhythm Rule (신규)

한 화면에서 텍스트 단락이 연속으로 3번 이상 나오면, 반드시 다음 중 하나가 뒤따라야 한다:
- Diagram (Pyramid, Flow, Journey 등)
- Exercise (Hero Exercise, Quick Check)
- Compare (비교표, Before/After)

```
읽기 → 보기 → 생각하기
```

의 리듬을 유지한다. 이는 HTML 기반 자율 학습 콘텐츠에서 특히 중요하다 — 텍스트만 이어지면 이탈률이 높아진다. 챕터 제작 시 절(section) 단위로 이 리듬이 지켜지는지 체크한다.

---

## 8. Freeze Status

본 Template은 PC01·PC02 기준으로 v1.0 Freeze, PC03 착수 시 §2.1 Exception Rule 추가로 v1.1로 개정한다. PC03부터는 본 템플릿을 기준으로 제작하며, 추가 변경이 필요할 경우 Constitution이 아니라 본 문서를 개정한다.
