# SQL_Assignment

Assignment: Analyzing Big Data with SQL   
Name: 박철우   

## 목표
한 회사에서 지하 고속 여객 철도 터널을 건설해야 합니다.   
터널로 연결할 주요 공항 2개를 결정하기 위해 데이터를 확인해야 합니다.   
두 공항 간의 거리는 지정된 범위 내에 있어야 하며, 두 공항의 많은 이용객 수가 확인되어야 합니다.   
회사는 이 철도 건설로 인해 공항의 매우 긴 비행 지연 시간을 줄일 수 있다고 생각합니다.   
조건에 맞는 두 공항을 찾아 회사에 추천해야 합니다.   
추천한 공항의 평균 이용객 수, 평균 지연 시간 등의 정보도 함께 제공    


## Assignment   
Recommend which pair of United States airports should be connected with a high-speed passenger rail tunnel. To do this, write and run a SELECT statement to return pairs of airports that are ***between 300 and 400 miles*** apart and that had ***at least 5,000 (five thousand) flights per year on average*** in each direction between them. Arrange the rows to identify which one of these pairs of airports has largest total number of seats on the planes that flew between them. Your SELECT statement must return all the information required to fill in the table below.   

1. 두 공항 간의 거리는 300~400 miles 내에 있어야 한다.   
2. 공항의 일년 평균 이용객이 5000명 이상이어야 한다.

## Tables


#### Table: flights   
Description: Data on all domestic flights by major US air carriers for the full decade from January 1, 2008 through December 31, 2017   


Number of rows: 61,392,822   
![flight](https://user-images.githubusercontent.com/33015847/124713389-72fa4180-df3b-11eb-9743-d10521255290.JPG)


#### Table: planes   
Description: Information about various aircraft, which might or might not be included in the flights table   


Number of rows: 453,361   
![planes](https://user-images.githubusercontent.com/33015847/124713398-78578c00-df3b-11eb-8a43-0da1cb7ba54a.JPG)

## Method

Unique 값인 비행기의 tailnum 값을 이용해 flights와 planes 테이블을 JOIN한다.   
10년 동안 기록된 데이터이기 때문에 연평균 데이터를 구하기 위해 10을 나누어준다.   
조건 설정, 그룹화 및 정렬    

**SELECT**    
  origin,    
  dest,    
  AVG(distance) AS avg_distance,   
  ROUND(COUNT(*)/10) AS avg_num_flights,   
  ROUND(SUM(seats)/10) AS annual_passenger_capacity,   
  ROUND(AVG(arr_delay),1) AS avg_arr_delay   
     
     
**FROM** fly.flights **AS** f **LEFT JOIN** fly.planes **AS** p **ON** f.tailnum=p.tailnum    
**WHERE** distance BETWEEN 300 AND 400    
**GROUP BY** origin, dest    
**HAVING** COUNT(*)/10  > 5000   
**ORDER BY** SUM(seats) DESC    
;   


![sql](https://user-images.githubusercontent.com/33015847/124715724-41cf4080-df3e-11eb-8090-e6a1ebca1af0.JPG)


## Result


![result](https://user-images.githubusercontent.com/33015847/124715770-4d226c00-df3e-11eb-89f1-12dd5267a635.JPG)



## Recommendation
![recommend](https://user-images.githubusercontent.com/33015847/124717193-dab28b80-df3f-11eb-9f2a-bc983050f809.JPG)




