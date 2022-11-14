> Error Code: 1054. Unknown column '컬럼명' in 'field list'

### 에러 원인

column이 테이블에 존재하지 않거나, 사용자가 문자열로 준 데이터가 ''로 감싸져있지 않음. <br />
나의 경우에는 SELECT SPJ.JNUM FROM SPJ, SUPPLIER, PROJECT 을 하려다가 'FROM SPJ, SUPPLIER PROJECT'로 적어서 (SUPPLIER과 PROJECT는 다른 테이블인데 ','가 없어서 PROJECT가 다른 테이블이 아닌 alias로 인식됨) 발생.

### 해결법

위의 실수나 테이블에 해당 column을 안 만들었는지, 오타는 없는지, 문자열을 ''로 감쌌는지 확인한다.
