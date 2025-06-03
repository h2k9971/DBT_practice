# dbt_practice

A personal project to learn and practice using dbt (data build tool) with Redshift.

## 📚 What I Learned Today

### dbt 프로젝트 구성

- 'dbt init' 으로 기본 디렉토리 생성
- 'dbt_project.yml': 모델 경로 및 기본 materialization 설정

### 모델 구조 구성

- `models/src/` : staging 레이어 → `ephemeral`로 처리 (DB에 테이블 미생성)
- `models/dim/` : dimension 레이어 → `table` materialization 사용
- `models/fact/` : fact 레이어 → 최종 분석 테이블 → `table`로 변경

### Materialization 이해

- `ephemeral`: 쿼리 내부에서 CTE로 작동, DB 객체 생성 X
- `view`: 쿼리 결과를 뷰로 저장, 가볍고 공유 용이
- `table`: 쿼리 결과를 테이블로 저장, 성능 개선 시 유리

### 🧪 기타 명령어 정리

```bash
dbt debug       # 연결 확인 및 설정 검증
dbt run         # 모델 실행
dbt test        # 테스트 실행
dbt clean       # 빌드 결과 정리 (target/ 등 삭제)
