# Curse-words_Detection
- 알고리즘 순서도 <br><br>
  ![Curse_detection_algorithm](https://user-images.githubusercontent.com/86700191/202083274-ce262b67-e1b7-488b-b74d-50defe6fbeba.png)
<br><br>
- 결과 <br>
  - train, validation 단계 <br>
  <table border ="0">
    <tr>
      <td><img src="https://user-images.githubusercontent.com/86700191/201509619-6b70da59-89a0-42a0-8b43-43ca9a1c0f57.PNG" width="100%" height="100%"></td>
      <td><img src="https://user-images.githubusercontent.com/86700191/202083288-efa375be-e881-4db6-a299-68b1af4eee71.PNG" width="100%" height="100%"></td>
    </tr>
    <tr>
      <td align ="center">1회차</td>
      <td align ="center">2회차</td>
    </tr>
   </table>
  1회차에서 마지막 5번째 epoch에서 validation loss의 값이 높아지나 2회차에선 그렇지 않아 overfitting이 시작될 수 있는 구간이라 볼 수 있다.
  <br><br>
  - test 단계 <br>
  <table border ="0">
    <tr>
      <td><img src="https://user-images.githubusercontent.com/86700191/201509621-2837d67d-420b-44a0-a3cd-c012badadbb0.PNG" width="100%" height="100%"></td>
      <td><img src="https://user-images.githubusercontent.com/86700191/202084774-71d73e26-ea0c-47b1-9137-029c2ee506e9.PNG" width="100%" height="100%"></td>
    </tr>
    <tr>
      <td align ="center">1회차</td>
      <td align ="center">2회차</td>
    </tr>
   </table>
  1회차에선 test data에 대해 약 86%의 정확도를 기록하고, 2회차에선 약 90%의 정확도를 기록하여 무난한 결과를 얻었다고 볼 수 있다. validation의 정확도보다 test의 정확도가 낮은 이유는 데이터의 양이 2배이기 때문이다.
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
