# Curse-words_Detection
- 알고리즘 순서도 <br>
- 결과 <br>
- 주의한 점 <br>
   - 데이터셋에 구분자인 "|"가 2개인 데이터가 존재 <br>
   ![error](https://user-images.githubusercontent.com/86700191/197709787-1df7be8c-26a1-452f-8c31-5a07217ba57c.PNG) <br><br>
   [해당 데이터셋 repository의 issue](https://github.com/2runo/Curse-detection-data/issues/1) 에도 제기된 문제이나 업데이트가 되지 않았기 때문에 해당 데이터를 삭제하여 진행한다.
<br><br>
   - 텍스트 간 길이의 차이로 인한 pad_token의 길이차이 <br>
   <table border ="0">
    <tr>
      <td><img src="https://user-images.githubusercontent.com/86700191/199435127-e3e85a27-0026-4447-b2c0-3407adc8290a.PNG" width="100%" height="100%"></td>
      <td><img src="https://user-images.githubusercontent.com/86700191/199435135-eb16f923-182f-4d6c-9757-b72af3c1ae0f.PNG" width="100%" height="100%"></td>
    </tr>
   </table>
   max_length를 정하지 않고 쓰게 되면 왼쪽의 두 문장을 반복하여 쓴 텍스트로 인해 길이가 456으로 고정되어 오른쪽과 같이 짧은 텍스트에는 pad token이 쓸데없이 많이 생긴다. 따라서max_length의 길이를 256으로 정하여 pad_token을 줄이며, 세번째로 긴 텍스트까지는 뒷부분을 잘랴내어 사용한다.

- 사용한 언어 모델, 데이터 <br>
   - Pre-trained Model : [KcELECTRA by Beomi](https://github.com/Beomi/KcELECTRA)
   - Fine-tuning Data : [욕설 감지 데이터셋 by 2runo](https://github.com/2runo/Curse-detection-data)
