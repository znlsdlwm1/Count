# Count
비가공된 데이터로 통계 뽑기

유저가 다운로드한 count수를 가지고 월별 일별 통계를 뽑아보려고 한다

월별쿼리는 월별 최대 다운로드한 count수 그리고 해달 월에 가장 많이 다운로드한 일, 날짜를 같이 가져오도록 하고

일별쿼리는 해당 월에 날짜 수와 요일 count수을 추가해서 각각 다른 쿼리로 출력해보기 (완벽한 쿼리를 추구하지말자)

추가할 테이블

CREATE TABLE downloadCount</br>
(</br>
   idx NUMBER NOT NULL        </br>
  ,REG_DATE DEFAULT SYSDATE   </br>
);


![image](https://user-images.githubusercontent.com/77945497/193173740-73a988e3-c2f9-4ca7-bd94-e45f06d915f1.png)

count 수는 idx를 count로 해서 reg_date값으로 무슨 년도 월일에 몇개가 다운로드가 되어있는지 빼보도록 하자

SELECT </br>
  TO_CHAR(REG_DATE, 'YYYY-MMDD') AS REGDATE</br>
  ,COUNT(idx) AS aCount</br>
FROM downloadCount </br>
 WHERE idx =  '67' </br>
 AND TO_CHAR(REG_DATE, 'YYYY-MM') =  '2022-09'</br>
GROUP BY TO_CHAR(REG_DATE, 'YYYY-MMDD')
</br>
![image](https://user-images.githubusercontent.com/77945497/193218336-b4bd49fd-3cd8-449a-a46e-c70906f6e05b.png)


