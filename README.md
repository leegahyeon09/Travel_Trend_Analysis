# Travel_Trend_Analysis

여행 빅데이터 분석 프로젝트 (2018–2024)

본 프로젝트는 네이버 데이터랩, Google Trends, 한국관광공사(KTO), 문화체육관광부(MCST) 등
다양한 공공·플랫폼 데이터를 통합하여 2018~2024년 국내·해외 여행 트렌드 분석을 수행한 프로젝트입니다.

다양한 시각화, 군집분석(KMeans), PCA, WordCloud, Cosine Similarity 추천 시스템, Prophet 예측을 활용하여
코로나 전·중·후에 따른 여행 관심도 변화와 2025년 전망을 도출하였습니다.

 1. 프로젝트 개요
분석 데이터 출처

    출처	                                               내용
네이버 데이터랩	                   국내/해외 여행 검색량, 자연휴양·도시관광·가족레저 관심도
Google Trends                    	domestic, overseas 월별 검색량
한국관광공사(KTO)	                 국민 해외출국자 월별 통계
문화체육관광부(MCST)	               국내여행 횟수 통계(성별·연령·유형별)
네이버 지역 기반 데이터	             부산·서울·제주 등 지역별 관심도 (도시관광/자연휴양/해외)

분석 목표
- 국내/해외 여행 장기 추세 분석
- 코로나 전·중·후 관심도 비교
- 성별·연령·유형별 여행 패턴 분석
- 지역별 관심도 기반 KMeans 군집화 & PCA
- Cosine Similarity 기반 추천 시스템 구축
- Prophet 기반 2025년 관심도 예측

2. 데이터 전처리

- 여러 출처의 데이터를 통일하기 위해 다음 전처리를 수행했습니다.
- 날짜 형식 통일(YYYY-MM-01)
- 문자열 정제(“1,234” → 1234)
- 네이버 지역명 “○○여행” → “○○”로 자동 추출
- type_map으로 여행유형 매핑
- 2025년 데이터 제거하여 2018~2024 통일
- google/naver/kto/mcst 모든 데이터를 공통 구조(date/value/source/keyword)로 통합
- 코로나 단계 라벨링(pre/mid/post)

 3. 주요 분석 결과 (EDA)
- 여행유형 관심도 (자연·도시·가족) → 2018~2024 전체 변화 라인그래프
- 성별 국내여행 규모
- 연령대 국내여행
- 여행유형별 규모 변화
- 국내 vs 해외 관심도 변화
- 코로나 전·중·후 비교
- 해외 관심도 vs 출국자수 상관관계

4. 지역 기반 분석
- 국내 여행지 인기 TOP
- WordCloud
- KMeans 군집 결과
- PCA 지역 패턴 시각화

5. 추천 시스템 (Cosine Similarity)
인천 → '강릉', '광주', '부산', '춘천', '울산'
강릉 →'속초', '인천', '부산', '울산', '여수'
 
6. 2025 여행 관심도 예측 (Prophet)

7. 코드 실행 방법
1) 필요 라이브러리 설치
pip install pandas numpy seaborn matplotlib scikit-learn prophet wordcloud plotly adjustText
2) 노트북 실행
final_travel_analysis.ipynb

8. 프로젝트 파일 구조
travel-analysis/
 ├── final_travel_analysis.ipynb
 ├── README.md
 ├── /images
 │     ├── trend_keywords.png
 │     ├── trend_gender.png
 │     ├── ...
 ├── /data
 │     ├── 국내여행횟수.xlsx
 │     ├── datalab_도시관광.xlsx
 │     ├── ...

9. 결과 요약

- 코로나 mid 구간 → 국내여행 관심도 최고
- 코로나 이후(post) → 해외여행 폭발적 증가
- 20~40대가 핵심 수요
- 자연휴양은 계절성이 뚜렷
- PCA & KMeans로 지역별 패턴 명확히 구분
- 2025년 해외여행 관심도는 계속 증가할 전망

10. GitHub 링크
https://github.com/leegahyeon09/Travel_Trend_Analysis
