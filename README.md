# Project Example (Monorepo)


### 참고
```
이 파일은 참고용으로 작성된 내용입니다.
반드시 본인이 사용하는 기술 스택에 맞도록 수정해서 사용해야 합니다.
```

1. 기술 스택 (Tech Stack)

<예시 내용>
Backend: Python (FastAPI / Django / Flask) 

Frontend:

Database: MySQL 8.4 LTS

Infrastructure: Docker / Docker Compose

2. 프로젝트 디렉토리 구조

project_ex/
├── .gitignore              # Git 추적 제외 설정
├── docker-compose.yml      # 백엔드 & MySQL DB 실행 컨테이너 Orchestration
├── .env.example            # 루트 및 공통 환경변수 템플릿
├── README.md               # 프로젝트 매뉴얼
│
├── backend/                # 백엔드 작업 디렉토리 (Python)
│   ├── Dockerfile          # 백엔드 컨테이너 빌드 설정 (python:3.11-slim 기반)
│   ├── **.dockerignore**   # Docker 빌드 제외 목록
│   ├── **.env**            # 백엔드 로컬 환경변수 (Git 추적 안 됨)
│   ├── **.env.example**    # 백엔드 환경변수 템플릿
│   └── requirements.txt    # Python 패키지 의존성 목록
│
└── frontend/               # 프론트엔드 작업 디렉토리 (Flutter)
    ├── **.env**             # 프론트엔드 로컬 환경변수 (Git 추적 안 됨)
    └── **.env.example**      # 프론트엔드 환경변수 템플릿


3. 시작하기 (Quick Start)

① 레포지토리 클론 (Clone)

git clone https://github.com/yhh10/Project_example.git
cd Project_example

```.env 파일은 /backend 와 /frontend 에 직접 추가```

4. 실행 방법

백엔드 & 데이터베이스 (Docker Compose)

백엔드 서버와 MySQL 8.4 데이터베이스는 Docker Compose를 이용해 통합 실행합니다.

# 백엔드 및 DB 컨테이너 빌드 및 백그라운드 실행
docker compose up -d --build

# 실행 상태 확인
docker compose ps

# 백엔드 및 DB 로그 확인
docker compose logs -f

# 컨테이너 종료 (데이터 볼륨 유지)
docker compose down


5. 협업 및 Git 워크플로우

.env 파일 커밋 금지: 실제 비밀번호나 API Key가 포함된 .env 파일은 절대 Git 저장소에 커밋하지 않습니다. 신규 변수가 추가될 경우 .env.example을 업데이트합니다.

역할 분담 및 작업 경로:

백엔드 작업 시: backend/ 디렉터리 내에서 커밋

프론트엔드 작업 시: frontend/ 디렉터리 내에서 커밋