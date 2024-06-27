# Stock-advisor-development-project

멀티캠퍼스에서 주최한 프로젝트에서 최우수상을 받은 프로젝트입니다. "머신러닝 기술과 소셜 데이터를 활용한 주가 어드바이저"를 개발하였으며, 실제 정확도는 75%정도로 성공적으로 마무리하였습니다.

이 프로젝트는 미국 반도체 업종에 집중 투자하는 ETF인 'SOXL'의 주가데이터와 소셜데이터를 심층 분석하여 투자 결정을 돕고자 했으며, 이를 위해 사용자에게 특정 날짜를 입력받아 소셜데이터를 investing, naver, reddit에서 뉴스의 헤드라인과 댓글을 크롤링 후 분석하여 'soxl'의 종가를 예측하여 5단계(강력매도, 매도, 중립, 매수, 강력매수)로 나눠진 의견을 제시하였습니다. 

저는 소셜데이터인 뉴스 헤드라인과 댓글 수집, 전처리 등 비정형 데이터 구축 및 streamlit 구현을 맡았습니다. 글로벌 경제 동향과 주식시장의 변화를 빠르게 파악할 수 있는 커뮤니티인 investing닷컴의 뉴스의 헤드라인과 댓글의 크롤링을 맡아서 하였으며, 총 16,000여개의 데이터를 수집하였습니다. 수집한 데이터들을 IQR을 이용하여 단어의 수가 많은 경우 허깅페이스의 문서요약모델인 'Falconsia/text_summarization'모델을 사용하여 문서요약하여 이상치를 식별하였습니다. 또한 주식 커뮤니티의 특성에 따라 financial한 용어들과 신조어 들을 학습해놓은 'distilbert-base-uncased-sentiment-reddit-crypto'모델을 사용하여 감성분석을 진행하여 정확도를 높였습니다. 그 다음, 주가의 변동량을 계산하였습니다. y값으로 예측할 데이터에 대해서 주가의 변동량을 구간별로 나누어 평균 주가 변동량의 150% 를 강력 매수로 예측했으며 이 과정에서 과거와 현재 데이터의 변동량을 포함하여 성능이 상승했습니다. 또한, 뉴스 헤드라인과 댓글에 대해 Word2Vec을 사용하였습니다. 이렇게 전처리를 마친 후 모델링을 위해 9개의 모델(Logistic Regression, Random Forest Classifier, KNN, Support Vector Classifier, Naive Bayes, Gradient Boosting, Decision Tree Classifier, Bagging, XGBClassifier)을 사용하였으며, 이 중 성능이 가장 좋았던 Gradient Boosting을 사용해 예측을 진행하여 목표로 했던 성능인 75%에 도달하여 성공적으로 목표치에 도달하였습니다.

이 후 streamlit을 활용하여 만들어놓은 모델이 돋보이는 웹페이지를 구현하며 프로젝트를 최우수상 수상까지 이끌어냈습니다.
