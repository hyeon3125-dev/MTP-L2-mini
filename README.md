---

# 1. Overview (개요)

## EN

MTP-L2 is a deterministic AI orchestration framework that allows users to directly control execution paths using a structured command interface (DSL).

Unlike conventional AI systems that rely on probabilistic responses, MTP-L2 enforces **explicit tool usage and execution routing**, eliminating ambiguity and reducing hallucinations.

## KR

MTP-L2는 DSL(명령어 기반 인터페이스)을 통해 사용자가 AI의 실행 경로를 직접 제어하는 **결정론적 오케스트레이션 프레임워크**임.

기존 AI처럼 확률적으로 답을 생성하는 방식이 아니라,
👉 **도구 실행을 명시적으로 지정**하여
모호성과 환각 문제를 구조적으로 제거함

---

# 2. Key Concept (핵심 개념)

## EN

Traditional AI:

```id="phtdsv"
User → Natural Language → LLM → Output (probabilistic)
```

MTP-L2:

```id="p1cfbi"
User → DSL (@lib/@exec) → Router → Tool/API → Output (deterministic)
```

## KR

기존 방식:

* 자연어 → AI가 알아서 판단 → 결과 생성 (확률 기반)

MTP-L2 방식:

* 명령어 → 실행 경로 지정 → 도구 호출 → 결과 (결정론 기반)

---

# 3. Why It Matters (왜 중요한가)

## EN

Current LLM systems suffer from:

* Hallucinations (incorrect confident answers)
* Unpredictable tool usage
* High iteration cost

MTP-L2 solves this by:

* Forcing deterministic execution paths
* Separating reasoning and execution layers
* Enabling reproducible outputs

## KR

기존 AI 문제:

* 틀린 답을 확신 있게 말하는 “환각”
* 도구 사용이 불안정
* 원하는 결과까지 여러 번 질문 필요

MTP-L2 해결 방식:

* 실행 경로를 강제 (결정론)
* 추론과 실행 분리
* 동일 입력 → 동일 결과 보장

---

# 4. Core Commands (핵심 명령어)

```bash
@lib forecast Seoul     # 외부 API 호출
@exec python "print(2+2)"  # 코드 실행
@recall mtp_notes       # 메모 조회
@think "business idea"  # 아이디어 생성
```

## KR 설명

| 명령어     | 역할         |
| ------- | ---------- |
| @lib    | 데이터/API 조회 |
| @exec   | 코드 실행      |
| @recall | 저장된 정보 조회  |
| @think  | AI 추론      |

---

# 5. Performance Summary (성능 요약)

## EN

| Metric        | Baseline AI | MTP-L2      |
| ------------- | ----------- | ----------- |
| Accuracy      | 25%         | **95–100%** |
| Hallucination | 25%         | **0%**      |
| Tool Usage    | 0%          | **100%**    |
| Latency       | ~2.8s       | ~0–0.2s     |

## KR

| 지표    | 기존 AI  | MTP-L2      |
| ----- | ------ | ----------- |
| 정답률   | 25%    | **95~100%** |
| 환각률   | 25%    | **0%**      |
| 도구 활용 | 0%     | **100%**    |
| 응답 속도 | 약 2.8초 | 거의 즉시       |

---

# 6. Key Insight (핵심 발견)

## EN

Even when tools are available, conventional LLMs often fail to use them reliably.

MTP-L2 enforces tool usage through explicit routing, ensuring consistency and correctness.

## KR

도구를 제공해도 기존 AI는
👉 스스로 판단해서 사용하지 않는 경우가 많음

MTP-L2는
👉 사용자가 직접 실행 경로를 지정
→ 항상 도구 사용 → 오류 제거

---

# 7. Architecture (구조)

```id="fkjrhl"
User
 ↓
Command Parser
 ↓
 ├─ Library Router (@lib)
 │    └─ API / DB / RAG
 │
 └─ Executor Router (@exec)
      └─ Python / Shell
```

---

# 8. Reproducibility (재현 방법)

## EN

```bash
git clone https://github.com/hyeon3125-dev/MTP-L2-mini
cd MTP-L2-mini
pip install -r requirements.txt
python kibo_fair_test.py
```

## KR

```bash
git clone https://github.com/hyeon3125-dev/MTP-L2-mini
cd MTP-L2-mini
pip install -r requirements.txt
python kibo_fair_test.py
```

실행 시 CSV 결과 자동 생성됨

---

# 9. Use Cases (활용 사례)

## EN

* Developer automation
* Data analysis
* AI-assisted workflows
* Personal knowledge systems

## KR

* 개발 자동화
* 데이터 분석
* 업무 자동화
* 개인 지식 시스템

---

# 10. Appendix (부록 - 쉽게 이해하기)

## 🧠 AI를 이렇게 생각하면 쉬움

### EN

* Traditional AI = “Assistant that guesses”
* MTP-L2 = “Computer that executes commands”

### KR

* 기존 AI = “추측해서 답하는 비서”
* MTP-L2 = “명령을 그대로 실행하는 컴퓨터”

---

## 🔧 예시 비교

### 기존 AI

👉 “서울 날씨 알려줘”
→ AI가 기억/추측해서 답

### MTP-L2

```bash
@lib forecast Seoul
```

→ 실제 API 호출 → 정확한 데이터 반환

---

## ⚡ 핵심 차이

| 기존 AI | MTP-L2 |
| ----- | ------ |
| 추측    | 실행     |
| 확률    | 결정     |
| 대화    | 명령     |

---

# 11. One-Line Summary

## EN

**MTP-L2 transforms AI from a probabilistic assistant into a deterministic execution system.**

## KR

**MTP-L2는 AI를 “확률적 비서”에서 “결정론적 실행 시스템”으로 바꾸는 기술임**

---

# 12. License / Contribution

## 📄 License

### EN

This project is released as open-source software.

You are free to use, modify, and distribute this code for both personal and commercial purposes.

**Requirements:**

* Proper attribution must be given to the original author (e.g., repository link or project name).

**Note:**

* This project is provided “as is”, without warranty of any kind.
* The author is not responsible for any damages or issues arising from its use.

---

### KR

본 프로젝트는 오픈소스로 공개되어 있습니다.

개인 및 상업적 목적 모두 자유롭게 사용, 수정, 배포가 가능합니다.

**조건:**

* 반드시 원작자에 대한 출처 표기를 포함해야 합니다 (예: GitHub 링크 또는 프로젝트명)

**주의:**

* 본 소프트웨어는 어떠한 보증 없이 제공됩니다.
* 사용으로 인해 발생하는 문제에 대해 개발자는 책임을 지지 않습니다.

---

## 🤝 Contribution & Commercial Use

### EN

Contributions are welcome.

If you plan to:

* build commercial products,
* integrate this framework into enterprise systems,
* or explore business partnerships,

please contact the author for collaboration opportunities.

---

### KR

기여(Contribution)는 언제든지 환영합니다.

다음과 같은 경우:

* 상업적 제품 개발
* 기업 시스템 통합
* 사업 확장 및 협업

👉 별도 문의를 통해 협업을 진행해주시기 바랍니다.

---

# 👍 추가 팁 (중요)

조금 더 신뢰도 올리고 싶으면 맨 아래 한 줄 추가해:

### EN

**Attribution example:**
“Powered by MTP-L2 Framework ([https://github.com/...)”](https://github.com/...%29”)

### KR

**출처 표기 예시:**
“Powered by MTP-L2 Framework ([https://github.com/...)”](https://github.com/...%29”)

### 📄 LICENSE (MIT + Attribution Note)
MIT License

Copyright (c) 2026 MTP-L2 Framework

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

Attribution Requirement:
Users must provide appropriate credit to the original project.
Example:
"Powered by MTP-L2 Framework (https://github.com/hyeon3125-dev/MTP-L2-mini)"

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.

### 본 프로젝트는 MIT 라이선스를 따릅니다.

누구나 자유롭게 사용, 수정, 배포 및 상업적 활용이 가능하며,
다만 반드시 원작자에 대한 출처 표기를 포함해야 합니다.

출처 표기 예시:
"Powered by MTP-L2 Framework (https://github.com/hyeon3125-dev/MTP-L2-mini)"

본 소프트웨어는 어떠한 보증 없이 제공되며,
사용으로 인해 발생하는 문제에 대해 책임지지 않습니다.

---

