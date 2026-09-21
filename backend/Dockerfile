# BASE IMAGE
FROM python:3.14

# 작업 디렉토리
WORKDIR /app

COPY requirementes.txt /app/
RUN pip install --no-cache-dir --upgrade pip && \ 
    pip install --no-cache-dir -r requirementes.txt

COPY . /app/

# 애플리케이션이 사용할 포트번호
EXPOSE 8000

# 서버 실행 명령어
CMD []
