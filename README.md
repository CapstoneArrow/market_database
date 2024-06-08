 # market_database
1. 웹과 앱서비스에 대한 전통시장정보, 주차장정보, 지역축제정보, 지역특화거리정보, 특산물정보 데이터를 직접 수집하였습니다.
   
 ![1](https://github.com/CapstoneArrow/market_database/assets/71175335/707b8931-e23c-4a6c-943d-33bc779d6b77)

--- 
2. 수집한 데이터를 앱과 웹에서 사용할 수 있는 형태로 데이터를 처리하기 위해 데이터 파일을 *pandas 형태로 바꿔주고 *df.iloc을 사용하여 사용할 데이터 범위를 정해준뒤 *rename과 *replace 함수를 통해 데이터의 Unnamed 값을 알맞은 형태의 값으로 바꿔주었습니다.
   
![2](https://github.com/CapstoneArrow/market_database/assets/71175335/81a6e8df-3b82-4e0d-be0e-5a11d1f20cf0)![3](https://github.com/CapstoneArrow/market_database/assets/71175335/32e5423b-8728-47a9-9880-bb0275fb529a)

---
3. 앱과 웹에서 주로 강원도 데이터를 사용했기 때문에 모든 정보 데이터에서 강원도 데이터만 추출하고, 추출한 데이터에서 non 값을 가진 데이터는 없애거나 다른 값으로 치환하고 이미 사라진 전통시장 혹은 주차장 그리고 중복되는 데이터 값들을 모두 처리하여 정리하였습니다. 

*str.contain함수: 원하는 값을 포함한 데이터만 추출 

*drop함수: 필요하지 않은 데이터 열 값을 삭제 

*dropna함수: non 값을 가진 모든 열과 행 데이터 삭제 

*fillna함수: 빈 데이터를 원하는 값으로 치환 

4. 전통시장 데이터의 경우 앱과 웹에 표시할 때 경도와 위도의 정보가 필요하기 때문에 주소 데이터의 *geocoding 함수를 통해서 경도와 위도를 담은 데이터 파일을 따로 만들어줬습니다.
   
5. 데이터의 경우 FireBase Realtime Database를 이용해 데이터를 저정하고 실시간으로 가져올 수 있도록 설정해 두었는데, Firebase의 DB에 데이터를 업로드 할 때 데이터 파일이 ASCII 제어문자 0~31, 127을 포함하면 업로드가 되지 않기 때문에 데이터 파일에 있는 문제가 되는 제어문자를 모두 제거해 주었습니다.

---

6. 정리한 xlsx 파일을 csv(쉼표) UTF-8 형식으로 바꾸고 이 파일을 json 파일 형태로 바꾸어 Firebase DB에 업로드 하였습니다.

![4](https://github.com/CapstoneArrow/market_database/assets/71175335/75d17f60-a89b-4a99-a788-6e54812084a3)
![5](https://github.com/CapstoneArrow/market_database/assets/71175335/fe0b6f57-52dd-4dcc-8fc1-73e0793dd26f)
![6](https://github.com/CapstoneArrow/market_database/assets/71175335/04fa4d79-553c-4675-a3f1-e926a37e7890)

---
7. 전통시장과 지역축제 등 다양한 이미지 데이터를 사용하기 위해서 이미지 데이터를 수집하고, 수집한 데이터를 같은 크기로 수정해주는 *resize 함수를 통해 모두 같은 크기로 만들어 이미지 데이터를 Firebase Storage에 업로드해서 데이터 파일과 같이 언제든지 저장하고 가져올 수 있도록 설정해두었습니다.
![7](https://github.com/CapstoneArrow/market_database/assets/71175335/ff6c7015-a784-44a0-b4bc-5ca1342ae6a4)
![8](https://github.com/CapstoneArrow/market_database/assets/71175335/1aaade3b-72ad-414e-919a-2ce5707cee6c)


