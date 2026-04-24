````markdown
# 🧪 Winning Tech Agent (v0.62)

**Intent‑aware Technology Scouting & Evaluation Agent**  
_딱 맞는 기술만 남기는 LLM 기반 기술 발굴·평가 에이전트_

---

## What is this?

**Winning Tech Agent**는  
특정 기술 도메인을 질문했을 때 **무관한 기술을 구조적으로 차단**하고,  
멀티턴 대화에서도 **안정적으로 발굴·평가를 이어가는** 기술 스카우팅 에이전트입니다.

> 예:  
> “최근 **컴프레서** 관련 Winning Tech 알려줘”  
> → 컴프레서와 무관한 기술이 나오지 않도록 설계됨

---

## Key Features

- ✅ **Intent‑aware discovery**
  - 도메인(예: compressor, heat exchanger 등)을 명시적으로 인식
  - 범용 키워드로 발산되는 문제 방지

- ✅ **Hard relevance gate**
  - 관련성 없는 기술은 *평가 전에* 제거
  - Lexical + Embedding 기반 2‑단계 필터

- ✅ **Cache‑safe multi‑turn**
  - 캐시 비활성 시 항상 새로운 탐색
  - 멀티턴에서 잘못된 결과 재사용 방지

- ✅ **Evaluation fallback**
  - “~을 평가해줘” 질문 시  
    → 이전 발굴에 없어도 자동으로 발굴 → 평가 수행

---

## Typical Use Cases

- 기술 트렌드 / Winning Tech 후보 탐색
- 특정 도메인(컴프레서, 열교환기 등) 중심 기술 필터링
- R&D 전략·기획용 기술 후보 스크리닝
- LLM 기반 기술 인텔리전스 PoC

---

## Quick Start

### Install
```bash
pip install streamlit numpy
# optional
pip install sentence-transformers langchain-community scikit-learn
````

### Run

```bash
streamlit run 2026-04-24_hara_chatbot_v0.62.py
```

***

## Example Queries

```text
최근 일주일 진동소음 관련 Winning Tech 될만한 기술 알려줘
```

```text
모터제어 기반 ANC에 대해서 평가해줘
```

```text
위에서 나온 것 중에서 고효율 중심으로만 보여줘
```

***

## Design Philosophy

> **“도메인이 지정된 질문에서는,  
> 관련 없는 기술은 ‘틀린 답변’이다.”**

*   정확도 > 발산
*   필터링은 LLM 출력 *이후*가 아니라 *구조적으로*
*   실제 R\&D 판단에 바로 쓰일 결과만 남기기

***

## Notes

*   본 저장소의 Scout / Evaluator는 **구조 검증용 최소 구현(stub)** 입니다.
*   실제 운영 환경에서는:
    *   외부 데이터 수집기
    *   LLM 기반 테마 생성
    *   조직별 평가 기준(Excel‑aligned scoring)
    으로 쉽게 교체할 수 있도록 설계되어 있습니다.

***

## License

Internal / research use.  
(Adjust before public or commercial release.)

