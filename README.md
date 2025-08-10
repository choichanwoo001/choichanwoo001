# 👋 안녕하세요, AI와 백엔드를 융합하는 개발자 최찬우입니다.

<div align="center">

**AI 로봇학과에서 얻은 데이터 분석 및 머신러닝 지식과<br>Java, Spring Boot 기반의 견고한 백엔드 개발 역량을 결합하여<br>지능적이고 혁신적인 서비스를 만드는 것을 목표로 하고 있습니다.**

<br>

<a href="https://github.com/choichanwoo001">
  <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" />
</a>
<a href="mailto:jonadan3495@gmail.com">
  <img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" />
</a>

</div>

---

## 🛠️ Tech Stack & Skills

- **Backend**: Java, Spring Boot, Spring Data JPA, RESTful API  
- **Database**: MySQL, JPA, Database Design (ERD)  
- **AI & ML**: Python, Scikit-learn, Pandas, Matplotlib  
- **Frontend**: HTML5, CSS3, JavaScript, Thymeleaf, Bootstrap  
- **DevOps**: Docker, docker-compose, Git/GitHub  
- **Core**: OOP, Design Patterns

<div>
  <img src="https://img.shields.io/badge/Java-ED8B00?logo=openjdk&logoColor=white&style=for-the-badge" />
  <img src="https://img.shields.io/badge/Spring%20Boot-6DB33F?logo=springboot&logoColor=white&style=for-the-badge" />
  <img src="https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white&style=for-the-badge" />
  <img src="https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white&style=for-the-badge" />
  <img src="https://img.shields.io/badge/MySQL-4479A1?logo=mysql&logoColor=white&style=for-the-badge" />
  <img src="https://img.shields.io/badge/Scikit--learn-F7931E?logo=scikitlearn&logoColor=white&style=for-the-badge" />
  <img src="https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=white&style=for-the-badge" />
  <img src="https://img.shields.io/badge/Matplotlib-11557c?logo=plotly&logoColor=white&style=for-the-badge" />
</div>

---

## 🚀 Featured Projects (Pinned)

아래 6개 핀 레포지토리를 중심으로 역량을 보여줍니다.  
핀 정보 출처: [GitHub 프로필](https://github.com/choichanwoo001)

| 프로젝트 | 스택 | 핵심 포인트 | 링크 |
|---|---|---|---|
| Toy_4 | Python(FastAPI), RAG(ChromaDB), OpenAI API, Spring Boot, Docker | AI 일기 분석/대화 RAG + 스프링 백엔드 통합, 도커 Compose로 멀티서비스 구동 | https://github.com/choichanwoo001/Toy_4 |
| Stop-eat | JavaScript, Web | 다이어트 서비스(학술제 출품), 사용자 상호작용 중심 기능 | https://github.com/choichanwoo001/Stop-eat |
| Machine_Learning-AI-Projects | Python, Scikit-learn, Pandas | 식습관 기반 질병(당뇨 등) 예측 모델, 비교·튜닝·시각화 파이프라인 | https://github.com/choichanwoo001/Machine_Learning-AI-Projects |
| Online_ShoppingMall | Java | 온라인 옷 쇼핑몰 토이, 상품/주문 플로우 구현 | https://github.com/choichanwoo001/Online_ShoppingMall |
| ShoppingMall | Spring Boot, JPA, MySQL, Thymeleaf | 온라인 책방(사용자/관리자 분리, 장바구니·주문·재고·결제 플로우) | https://github.com/choichanwoo001/ShoppingMall |
| ShoppingMall-DB | MySQL, ERD | 대규모 전자상거래 DB 논리 모델링(정규화·관계 설계) | https://github.com/choichanwoo001/ShoppingMall-DB |

---

## 🧩 In-Depth: Toy_4 — AI × Backend 통합 프로젝트

AI 기반 일기 분석과 대화(감정/이벤트 인식, RAG 응답)를 제공하는 **Python AI 서비스**와, 사용자 화면/데이터를 담당하는 **Spring Boot 백엔드**를 **도커 컴포즈**로 함께 구동합니다.

### 🏗️ 아키텍처 개요

```mermaid
graph TD
  A[Web Client (HTML/JS/Thymeleaf)] --> B[Spring Boot Backend]
  B -->|REST API| C[AI Service (FastAPI, Python)]
  C -->|LLM API| D[(LLM Provider)]
  C -->|RAG Query| E[(ChromaDB Vector Store)]
  B -->|JPA| F[(MySQL)]
  subgraph Repo Structure
    B --- G[backend/ ...]
    C --- H[ai-service/ ...]
  end
```

- **AI 서비스**: `ai-service/app` 라우터 기반(대화/일기 분석), `core/vector_db.py`로 ChromaDB 활용, `app/prompts`로 프롬프트 관리
- **백엔드**: `backend/src/main/java/...` 컨트롤러·서비스·리포지토리 계층, `Thymeleaf` 기반 화면
- **테스트/배포**: `docker-compose.yml`로 로컬 멀티서비스 구동, `pytest` 기반 AI 서비스 테스트

### 🔎 대표 엔드포인트 예시

- 대화/요약/최근 대화 등: `/api/v1/conversation/...`
- 일기 분석: `/api/v1/diary/analyze`

예시 요청:
```bash
curl -X POST "http://localhost:8000/api/v1/diary/analyze" \
  -H "Content-Type: application/json" \
  -d '{"date":"2025-01-01","content":"오늘은 즐거운 하루였다. 친구를 만나서 기분이 좋았다!"}'
```

예시 응답(요약):
```json
{
  "sentiment": "positive",
  "key_events": ["친구 만남"],
  "advice": "즐거웠던 활동을 주간 루틴으로 만들어 보세요."
}
```

### 🌟 Toy_4에서 보여준 역량
- **AI×도메인 모델링**: 감정/이벤트 추출 → RAG 응답 → 대화 컨텍스트 유지
- **확장성 고려 설계**: 프롬프트/라우터/서비스/벡터DB 분리
- **운영 효율**: 도커 컴포즈로 환경 일원화, 테스트 코드로 회귀 방지

---

## 📚 추가 대표 작업

### 📚 Spring Boot 기반 북스토어
- 회원/관리자 분리, 장바구니/주문/재고, 카카오페이 결제 연동
- `Spring Boot`, `JPA`, `MySQL`, `Thymeleaf`, `JavaScript`

### 🤖 생활 습관 기반 예측 모델(ML)
- EDA → 학습/튜닝 → 시각화 파이프라인 정립
- `RandomForest`, `SVM` 등 모델 비교 및 최적화

### 🎮 OOP 멀티플레이어 포커 게임
- 역할/책임 기반 설계, 100라운드 자동 테스트
- 캡슐화/상속/다형성 적용으로 확장성 확보

### 🛍️ E-commerce 대규모 DB 설계
- 50개+ 테이블, 정규화/무결성 중심의 관계형 모델
- ERD 문서화 및 시각화

---

## 💡 Work Style & Value

- **문제정의 → 데이터/요구분석 → 설계 → 구현 → 검증** 풀사이클 지향  
- 유지보수/확장성 고려한 **모듈화**, **테스트 우선**  
- 사용자 가치와 **운영 안정성**을 함께 보는 균형감

---

## 📫 Contact

- GitHub: https://github.com/choichanwoo001  
- Email: jonadan3495@gmail.com
