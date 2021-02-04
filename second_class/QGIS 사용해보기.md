# QGIS 사용해보기 

공부 할려고하면서 작성했기에 틀린내용 있을 수 도 있습니다.

피드백 주시면 수정하겠습니다!!! 

 

## 지도에 무언가 대입하기(라벨달기)





#### QGIS 지도 불러오기

![image](https://user-images.githubusercontent.com/48937399/106724794-02798c80-664c-11eb-9174-6f0bab55e77b.png)

QGIS 버전 3.10을 사용하겠습니다.





![image](https://user-images.githubusercontent.com/48937399/106725339-9b100c80-664c-11eb-89b2-9065f0c228d8.png)

상단 메뉴바에 플러그인 관리및 설치를 눌러줍니다.



![image](https://user-images.githubusercontent.com/48937399/106725594-e4605c00-664c-11eb-8bdc-f9f4e2a2d29a.png)

tms 를 검색하고 박스친 모양 얘를 선택해서 플러그인을 설치해줍니다.



그 후에 

![image](https://user-images.githubusercontent.com/48937399/106725955-3dc88b00-664d-11eb-90c3-2704ad3d44d9.png)

웹 -> TMS for Korea 에서 원하는 지도 플랫폼을 선택하면 됩니다. 저는 카카오 하이브리드로 가곘습니다.



![image](https://user-images.githubusercontent.com/48937399/106726530-d3fcb100-664d-11eb-8871-f3e5d4e3095e.png)



뭐 이런녀석이 뜨네요 !!

#### GIS 지도에 뭐 올리기!

 

http://openapi.nsdi.go.kr/nsdi/eios/ServiceDetail.do

국가공간정보포털 사이트에서 OPEN API 데이터를 받아왔습니다. 

귀찮으신분들은 

https://github.com/JaeHyunL/start_GIS/blob/master/second_class/AL_41480_D196_20210114.zip 

여기가서 다운로드 하시면됩니다 



![image](https://user-images.githubusercontent.com/48937399/106727545-f216e100-664e-11eb-8870-3ac62d13ec9d.png)

요기다가 요롷게 끌어다가 줍니다~ 



![image](https://user-images.githubusercontent.com/48937399/106727828-34402280-664f-11eb-97a4-62a0f83e5fcb.png)

지도에 무슨 꺼뭇 꺼뭇하게 생기긴했습니다.

신기하네요 ;; 



뭐 아무튼 제가 올렸던 자료는 파주시 건축물 연령정보입니다.



아무거나 하나 클락하셔서 속성테이블 열기를 눌러보시면 



![image](https://user-images.githubusercontent.com/48937399/106728495-d95afb00-664f-11eb-844c-4c507cbabbd9.png)

![image](https://user-images.githubusercontent.com/48937399/106728335-add81080-664f-11eb-8534-0fc7c5461780.png)

뭐 이러한 녀석이뜨네요 

안에 속성정보들이 담겨있는것 같네요 

제가 첨부한 파일은 국가공간정보포털에서 제공하는 파주시 건물 연령 데이터 였습니다 . 



![image](https://user-images.githubusercontent.com/48937399/106861291-e851b400-6708-11eb-8510-ab9e982c70a6.png)

아래 레이어에서 속성을클릭하고 

![image-20210204165052788](C:\Users\lodics\AppData\Roaming\Typora\typora-user-images\image-20210204165052788.png)

이렇게 라벨을 표시할 수 가있는데

라벨에 A25번째 값을 넣어줍니다. A25번이 건물 나이 컬럼입니다.



뭐 결과적으로는 



![image](https://user-images.githubusercontent.com/48937399/106861566-454d6a00-6709-11eb-984c-22108fff8aaf.png)



이런모양이 됩니다



이제 여기서 무언가 더 해볼 방법을 찾아보겠습니다! 