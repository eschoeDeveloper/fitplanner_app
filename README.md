# ⚡ FitPlanner 프로젝트 포트폴리오

![FitPlanner 스크린샷](./assets/fitplanner.png)

---

## 📖 프로젝트 개요

**FitPlanner**는 AI 기반 AR 체형 분석을 통해 개인 맞춤형 운동 프로그램을 생성하고, 자동으로 Notion에 보고서를 작성해주는 웹 애플리케이션입니다.

* **기간:** 2025년 3월 – 2025년 7월
* **팀 규모:** 개인 프로젝트
* **역할:** 백엔드 설계·구현, API 연동, 인프라 구축

---

## 🛠 주요 기능

1. **실시간 AR 체형 분석**

   * 클라이언트 카메라 스트림을 활용한 체형 3D 모델 생성
2. **개인 맞춤 운동 추천**

   * 분석 결과 기반으로 운동 종목·세트 수 자동 제안
3. **Notion 보고서 자동 생성**

   * 운동 이력 및 분석 결과를 Notion API로 정리하여 문서 자동 작성
4. **사용자 관리**

   * Spring Security + JWT 기반 인증·인가

---

## 🏗 아키텍처 및 기술 스택

### 아키텍처 다이어그램

![아키텍처 다이어그램](./docs/architecture.png)

### 백엔드

* **언어 & 프레임워크:** Java 17, Spring Boot 3
* **API 문서화:** SpringDoc OpenAPI
* **인증/인가:** Spring Security, JWT
* **데이터베이스:** PostgreSQL 17 (NCP RDS)
* **캐시:** Redis (NCP ElastiCache)

### 머신러닝 & AR

* **모델:** TensorFlow 기반 체형 분류 모델
* **AR SDK:** ARCore (Android) / ARKit (iOS)

### 인프라 & DevOps

* **클라우드:** NCP VPC, LB, SSL VPN
* **컨테이너:** Docker, Kubernetes (ap-northeast-2)
* **CI/CD:** GitHub Actions → Docker 이미지 빌드 → NCP Container Registry 배포
* **모니터링:** Prometheus, Grafana

---

## 🚀 설치 및 실행

1. 저장소 클론

   ```bash
   git clone https://github.com/username/fitplanner.git
   cd fitplanner
   ```
2. 환경 변수 설정 (`.env` 파일)

   ```dotenv
   DATABASE_URL=jdbc:postgresql://{호스트}:{포트}/{DB명}
   REDIS_URL=redis://{호스트}:{포트}
   NOTION_API_KEY=secret_XXXXX
   JWT_SECRET=your_jwt_secret
   ```
3. Docker Compose로 로컬 실행

   ```bash
   docker-compose up -d
   ```
4. API 문서 확인

   ```
   ```

### [http://localhost:8080/swagger-ui.html](http://localhost:8080/swagger-ui.html)

```

---

## 📂 주요 폴더 구조

```

├── src/main/java/com/fitplanner
│   ├── controller   # API 엔드포인트
│   ├── service      # 비즈니스 로직
│   ├── repository   # DB 연동 (JpaRepository)
│   ├── security     # 인증/인가 설정
│   └── dto          # 요청/응답용 객체
├── src/main/resources
│   ├── application.yml
│   └── db
│       └── migration  # Flyway 마이그레이션
├── docs
│   ├── architecture.png
│   └── api-usage.md
└── assets
└── fitplanner.png

```

---

## 📈 성과 및 회고

- **모델 정확도:** 체형 분류 모델 92% 이상 달성
- **API 응답 시간:** 평균 120ms 이내
- **회고:** AR 처리 지연 이슈 해결을 위해 모델 경량화 및 캐싱 적용 후 UX 개선

---

## 🤝 기여 및 연락처

- **GitHub:** [github.com/username/fitplanner](https://github.com/username/fitplanner)  
- **Email:** your.email@example.com  
- **LinkedIn:** [linkedin.com/in/username](https://linkedin.com/in/username)

---

## 📜 라이선스

MIT License © 2025 Your Name

```
