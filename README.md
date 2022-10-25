# Curse-words_Detection
 욕설로 판단되는 문장을 감지하는 모델
<br>
- 알고리즘 순서도 <br>
<br>
- 결과 <br>
<br>
- 유의점 <br>
   - 데이터셋에 구분자인 "|"가 2개인 데이터가 존재 <br>
   ![error](https://user-images.githubusercontent.com/86700191/197709787-1df7be8c-26a1-452f-8c31-5a07217ba57c.PNG)
   [해당 데이터셋 repository의 issue](https://github.com/2runo/Curse-detection-data/issues/1) 에도 제기된 문제이나 업데이트가 되지 않았기 때문에 해당 데이터를 삭제하여 진행한다.
<br><br>
- 사용한 언어 모델, 데이터<br>
   - Pre-trained Model : [KcELECTRA by Beomi](https://github.com/Beomi/KcELECTRA)
   - Fine-tuning Data : [욕설 감지 데이터셋 by 2runo](https://github.com/2runo/Curse-detection-data)
