# OrderLab Python CI/CD

Python 3.14 기반 CI/CD 실습 프로젝트입니다.

## 사용 도구

- Ruff
- pytest
- pytest-cov
- FastAPI
- GitHub Actions
- GitHub Pages

## 패키지 설치

python -m pip install -r requirements-dev.txt

## Ruff 검사

ruff check .
ruff format --check .

## pytest 실행

python -m pytest -q

## 커버리지 검사

python -m pytest --cov=orderlab --cov-report=term-missing

## HTML 보고서 생성

python generate_report.py

생성 파일: site/index.html

## CI/CD 동작

Pull Request에서는 quality 검사를 수행합니다.

main 브랜치에 Push하면 quality 검사를 먼저 실행합니다.

quality 검사 성공 시 GitHub Pages 배포를 실행합니다.

quality 검사 실패 시 배포를 차단합니다.

## 오류 재현 실습

- pytest AssertionError 발생 및 복구
- Ruff F401 발생 및 복구
- 배송비 50,000원 경계값 오류 발생 및 복구
- CSV 파일 누락 및 숫자 변환 오류 검사
- API 201, 200, 404, 422 응답 검사
- CI 실패 시 CD 배포 차단 확인
