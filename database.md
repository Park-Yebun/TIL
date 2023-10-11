### RDBMS
**관계형 데이터베이스를 관리하는 프로그램**<br/>
**SQLite, MySQL, PostgreSQL Oracle Database,,,**

### SQL
-  SQL statement / SQL문(=쿼리문:데이터 베이스에 요청하는 문법)

|유형|역할|SQL 키워드|
|-----|---|---|
|DDL<br/>(data definition language)|데이터의 기본 구조 및 형식 변경|CREATE<br/>DROP<br/> ALTER|
|DQL<br/>(data query language)|데이터 검색|SELECT|
|DML<br/>(data manipulation language)|데이터 조작<br/>(추가, 수정, 삭제)|INSERT<br/>UPDATE<br/>DELETE|
|DCL<br/>(data control language)|데이터 및 작업에 대한 사용자 권한 제어|COMMIT<br/>ROLLBACK<br/>GRANT<br/>REVOKE|


1. DDL
```
* 테이블 생성
CREATE TABLE 테이블 이름(
    필드 이름 V 필드 타입 V 제약 조건 V (필드 속성)
);
```
- SQLite의 필드 데이터 타입: NULL, INTEGER, REAL, TEXT, BLOB
- 제약조건은 데이터의 무결성과 일관성을 보장하는 기준이 됨 (primary key, not null, foreign key등)
- AUTOINCREMENT: 필드의 자동증가를 나타내는 필드 속성, 작성된 새로운 레코드에 대해 이전 최대 값보다 큰 값을 할당함

```
* 필드 추가
ALTER TABLE
    테이블 이름
ADD COLUMN
    필드 이름 V 필드 타입 V 제약 조건 V (필드 속성);

* 필드 이름 변경
ALTER TABLE
    테이블 이름
RENAME COLUMN
    기존 이름 TO 새로운 이름;

* 필드 삭제
ALTER TABLE
    테이블 이름
DROP COLUMN
    필드 이름;

* 테이블 이름 변경
ALTER TABLE
    테이블 이름
RENAME TO 새로운 이름;
```

2. DQL
```
* 테이블에서 데이터를 조회하는 구문

SELECT
    필드 이름
FROM
    테이블 이름;
```
- 모든 필드를 조회할 시에는 애스터리스크(*)사용
- 다중 필드를 조회할 시에는 ,로 필드 구분
- 필드의 이름을 임의로 변경해 조회할 때는 ```필드이름 AS '이름'```의 형태로 작성
- 필드 타입이 정수인 경우 연산자 활용 가능 ex) ```Milliseconds / 60000```
```
* 레코드 정렬하는 구문
SELECT
    필드 이름
FROM
    테이블 이름
ORDER BY
    기준 필드 이름 V ASC|DESC;
```
- ASC(오름차순, 기본값), DESC(내림차순)
- 두개 이상의 기준 필드가 있을 경우 첫번째 기준대로 우선 정렬된 후 두번째 기준에서는 첫번째 범위의 안에서 재정렬됨
- NULL값은 0보다 작은 수로 분류됨


#### filtering data
```
* 중복된 레코드를 제거하는 구문
SELECT DISTINCT
    필드 이름
FROM
    테이블 이름;
```
```
* 특정 조건을 지정하는 구문(조건문)
SELECT
    필드 이름
FROM
    테이블 이름
WHERE
    조건;
```
- 모든 변수 값은 연산자를 사용, 다만 NULL값은 등호 대신 IS 사용
- AND, OR과 같은 논리 연산자는 줄바꿈된 조건식의 맨 앞에 위치시키는 것을 권장
- 부등호는 BETWEEN num AND num과 같이 대체해 쓸 수 있음
- IN/NOT IN을 쓸때는 리스트를 튜플 형태로 묶어주기
- LIKE는 특정문자열을 포함한 데이터를 조회할 때 사용 ('%'- 문자열의 자리수에 상관없이 시작하거나 끝나는 문자열 검색, '_'-문자열의 자리수만큼 언더바를 사용해서 검색), %와 _을 혼용하여 사용할 수도 있음

```
* 레코드 수를 제한하여 조회하는 구문
SELECT
    필드 이름
FROM
    테이블 이름
LIMIT
    상쇄할 데이터 수 V 보여줄 데이터 수;
```
- 하나 또는 두개의 인자를 사용할 수 있음
- 인자는 반드시 0 또는 양의 정수

#### grouping data
```
SELECT
    필드 이름
FROM
    테이블 이름
GROUP BY
    필드 목록;
```
- 집계함수(aggregation functions)를 함께 사용하여 레코드의 요약본을 생성하는 절
- 집계함수는 SELECT절에 위치
- 세부 조건을 지정할 때는 WHERE가 아니라 HAVING구문을 사용할 것

![SQL문 실행순서](https://cdn.sisense.com/wp-content/uploads/image-1-order-blog.png)

3. DML
4. DCL