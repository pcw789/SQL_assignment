# sql_

Assignment: Analyzing Big Data with SQL   
Name: 박철우   

한 회사에서 지하 고속 여객 철도 터널을 건설해야 합니다.   
터널로 연결할 주요 공항 2개를 결정하기 위해 데이터를 확인해야 합니다.
두 공항 간의 거리는 지정된 범위 내에 있어야 하며, 두 공항의 많은 이용객 수가 확인되어야 합니다.   
회사는 이 철도 건설로 인해 공항의 매우 긴 비행 지연 시간을 줄일 수 있다고 생각합니다.   
조건에 맞는 두 공항을 찾아 회사에 추천해야 합니다.

## Assignment   
Recommend which pair of United States airports should be connected with a high-speed passenger rail tunnel. To do this, write and run a SELECT statement to return pairs of airports that are ***between 300 and 400 miles*** apart and that had ***at least 5,000 (five thousand) flights per year on average*** in each direction between them. Arrange the rows to identify which one of these pairs of airports has largest total number of seats on the planes that flew between them. Your SELECT statement must return all the information required to fill in the table below.   

1. 두 공항 간의 거리는 300~400 miles 내에 있어야 한다.   
2. 공항의 일년 평균 이용객이 5000명 이상이어야 한다.

