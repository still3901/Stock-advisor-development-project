# Stock-advisor-development-project

멀티캠퍼스에서 주최한 세미프로젝트에서 최우수상을 받은 프로젝트입니다. "머신러닝 기술과 소셜 데이터를 활용한 주가 어드바이저"를 개발하였으며, 실제 정확도는 75%정도로 성공적으로 마무리하였습니다.

이 프로젝트는 SOXL 주가에 대해 강력 매수, 매수, 중립, 매도, 강력 매도의 5가지 추천을 제공했습니다. 저는 데이터 수집 및 전처리, 그리고 모델링 파트를 담당했습니다. 특히 레딧에서 셀레니움을 활용하여 데이터 크롤링하여 습니다. 추가로 인베스팅닷컴과 네이버 종목토론방에서 크롤링을 진행하여 약 16,000개의 데이터를 수집하였습니다. 전처리 과정에서 다양한 기법을 사용했습니다. 특히 성능이 가장 좋았던 방법은 IQR을 이용해 문서의 단어 수가 많은 경우 허깅페이스 모델을 이용해 문서 요약을 진행한 후 감성 분석을 하는 것이었습니다. 문서 요약을 통해 이상치를 식별하고, 감성 분석의 정확도를 높일 수 있었습니다. 두 번째 전처리는 데이터의 출처와 추출된 키워드를 원-핫 인코딩하는 것이었습니다. 세 번째 전처리는 주가의 변동량을 계산하는 것이었습니다. y 값으로 예측할 데이터에 대해서는 주가의 변동량을 구간별로 나누어 평균 주가 변동량의 150% 를 강력 매수로 예측했습니다. 과거와 현재 데이터의 변동량을 포함하니 성능이 상승했습니다. 네 번째 전처리는 헤드라인과 댓글에 대해 Word2Vec을 사용한 것이었고, 다섯 번째 전처리는 날짜 정보(며칠인지, 몇 월인 지, 무슨 요일인지, 일 년 중 몇 번째 주인지 등)를 포함하는 것이었습니다. 이렇게 전처리를 마친 후 모델링에는 9개의 모델을 사용했습니다: Logistic Regression, Random Forest Classifier, KNN, Support Vector Classifier, Naive Bayes, Gradient Boosting, Decision Tree Classifier, Bagging, XGBClassifier. 이 중 성능이 가장 좋았던 Gradient Boosting을 사용해 예측을 진행했으며, 목표로 했던 성능인 75%를 넘길 수 있었습니다.

이 프로젝트는 미국 반도체 업종에 집중 투자하는 ETF인 'SOXL'의 주가데이터와 소셜데이터를 심층 분석하여 투자할 때 유용한 지표를 제공하는 것을 목표로 하였습니다. 변동성이 큰 반도체 시장에서 투자 결정을 돕기 위해 특정 날짜를 입력 시 해당날짜에 해당하는 investing, naver, reddit ‘SOXL’에 대하여 5단계(강력매도, 매도, 중립, 매수, 강력매수)로 나눠진 의견을 제시하였습니다. 
