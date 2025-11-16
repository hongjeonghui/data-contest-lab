# 2025 Kookmin AIBD Competition

제3회 국민대학교 AI빅데이터 분석 경진대회 프로젝트 저장소입니다.  
데이터 분석, EDA, 모델링 실험, 회의 기록, 최종 결과물까지 한 흐름으로 정리된 구조를 사용합니다.

---

## 프로젝트 구조
```
2025-kookmin-aibd
 ┣ 00_setup
 │   ┗ 프로젝트 설정, 환경 설정, 공통 가이드
 │
 ┣ 01_data
 │   ┣ raw              (원본 데이터)
 │   ┣ processed        (전처리된 데이터)
 │   ┗ eda              (EDA 노트북 및 시각화 파일)
 │
 ┣ 02_experiments
 │   ┣ notebooks        (모델 실험용 노트북)
 │   ┣ models           (모델 코드 및 스크립트)
 │   ┗ results          (실험 결과, 로그, 성능표)
 │
 ┣ 03_meetings
 │   ┗ 회의록 정리 (날짜별 markdown)
 │
 ┣ 04_final
 │   ┣ submissions      (대회 제출 파일)
 │   ┣ report           (최종 보고서)
 │   ┗ presentation     (발표 자료)
 │
 ┗ README.md
```
---

## 진행 순서

1. 데이터 확인 및 EDA 작성 (01_data/eda)
2. 전처리 및 특징 생성 (01_data/processed)
3. 모델링 실험 및 성능 비교 (02_experiments)
4. 회의록에 주요 논의사항 기록 (03_meetings)
5. 최종 모델 선정 및 제출 파일 생성 (04_final/submissions)
6. 최종 보고서 및 발표자료 작성 (04_final/report, presentation)

---

## 팀 협업 규칙

- 노트북 실험 결과는 02_experiments/results 에 기록
- 전처리 코드 및 모델 코드는 반드시 py 파일로 관리
- 회의 내용은 날짜별로 03_meetings 에 markdown 파일로 작성
- 데이터(raw)는 변경하지 않음. 전처리는 processed 폴더에 저장

---

## 환경 설정

- requirements.txt 참고
- 필요한 경우 00_setup 내에 추가 설정 파일 작성

