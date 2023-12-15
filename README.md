# final_project
---
## 1.프로젝트 내용
scikit learn으로 tumor dataset을 가져오고 scikitlearn이 제공하는 패키지를 통해 classification을 해보았다. 

특히, tumor데이터를 가장 높은 정확도로 분류해내는 모델을 찾기 위해 노력을 기울였다.

최적의 모델을 만들기 위해 하이퍼파라미터를 조정해나갔다. 

이때 greedsearch를 사용했다. 하이퍼파라미터의 성능을 비교할 때 쓰기 좋은 탐색방법이었기 때문이다.

---
## 2.training dataset 설명
training dataset 은 tumor dataset이다. tumor data set에는 pituitary_tumor, no_tumor, meningioma_tumor,glioma_tumor가 있다.

![image](https://github.com/yeojuni/final_project/assets/109058626/fd7c93c8-11f1-428e-9802-7e6b4834860f)

train_test_split 모듈을 활용하여 train set과 test set을 분리하였다.


## 3.선택한 알고리즘
선택한 알고리즘은 svm(Support Vector Machines)이다.

adaboost를 써보기도 했는데 성능이 좋지 않은 것 같았고, 하이퍼파라미터의 디폴트 값으로도 성능이 좋았던 svm을 사용하였다.


![image](https://github.com/yeojuni/final_project/assets/109058626/a4c8d221-5c17-4bc8-ac8c-c56ed3796c7d)


-> sklearn.svm.SVC 모듈을 활용하여 알고리즘을 사용했다.




## 4.하이퍼파라미터

svm의 하이퍼파라미터에는 C, kernel, degree, gamma 등이 있다.

greedsearch를 통해 최적의 하이퍼파라미터를 찾고자했다.

처음에는 위의 4가지 파라미터를 greedsearch에 넣어 탐색했으나, 하이퍼파라미터가 많아서인지 아무리 많은 시간을 들여도 실행완료가 되지 않았다.

결국 마지막에는 C와 gamma 2가지 하이퍼파라미터만으로 돌렸고 정확도가 크게 변하지 않을 때 쯤 greedsearch를 멈추었다. 

![image](https://github.com/yeojuni/final_project/assets/109058626/21f0e5ab-eafe-4730-9e02-b922f4d6aa60)

그렇게 찾아낸 최적의 하이퍼 파라미터는 kernel='linear',random_state=42, C = 6.2, gamma =  0.000285 이다.




