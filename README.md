# dataanalysis

# <데이터베이스 공부>
### 보조키 = 대체키
### PL/SQL -> 변수, 조건문, 반복문 등 프로그래밍 언어ㅔ서 제공하는 요소를 사용하여 데이터 관리를 할 수 있다
### 테이블 구성 확인 -> DESC EMP(테이블명);
### SCOTT계정에는 EMP, DEPT, SALGRADE 등 다양한 테이블이 있다
### 조인 -> 두개 이상의 테이블을 양옆에 연결하여 마치 하나의 테이블인것처럼 데이터를 조회하는 방식
### SELECT [조회할 열이름] FROM [조회할 테이블이름];
- 중복데이터 삭제 -> DISTINCT -> ex) SELECT DISTINCT JOB, DEPTNO FROM EMP;
- 중복되는 열 제거없이 그대로 출력 (DISTICT와 반대) ALL 
- 별칭사용 -> SELECT SAL*12+COMM AS ANNSAL FROM EMP; -> SAL*12+COMM 을 ANNSAL이라는 별칭으로 사용
- ORDER BY -> 원하는 순서로 출력 데이터 정렬, SELECT작성시 사용할 수 있는 여러 절 중 가장 마지막 부분에 쓴다
           -> SELECT * FROM EMP ORDER BY SAL; (오름차순)
           -> SELECT * FROM EMP ORDER BY SAL DESC; (내림차순)
           
- WHERE절 -> 조건 -> SELECT * FROM WHERE [조회할 행을 선별하기 위한 조건식]; -> 조건식을 AND, OR연산자로 여러개 지정할 수 있다
          -> SELECT * FROM EMP WHERE DEPTNO=30 AND JOB='CLERK';
- 연산자 -> 1. 산술연산자 -> +, -, *, /
         -> 2. 비교연산자 -> >=, <=, <, >, =, !=. <>, ^=(  !=. <>, ^= 는 같은것-> A,B 값 다를 경우 true, 같을경우 false)
         -> 3. 논리부정연산자 -> NOT 
         SELECT * FROM EMP WHERE NOT SAL=3000;
         
- IN -> SELECT * FROM EP WHERE JOB='MANAGER' OR JOB='SALESMAN' OR JOB='CLERK'; == SELECT * FROM EMP WHRER JOB IN ('MANAGER', 'SALESMAN', 'CLERK');
     -> SELECT * FROM EP WHERE JOB!='MANAGER' OR JOB<>'SALESMAN' OR JOB^='CLERK'; == SELECT * FROM EMP WHRER JOB NOT IN ('MANAGER', 'SALESMAN', 'CLERK');
- (NOT) BETWEEN A AND B -> ~이상 ~이하 -> SELECT * FROM EMP WHRER SAL >= 2000 AND SAL <= 3000; == SELECT * FROM EMP WHERE SAL BETWEEN 2000 AND 3000;
- LIKE 연산자 -> 일부 문자열이 포함된 데이터 조회시 사용 -> SELECT * FROM EMP WHERE ENAME (not) LIKE 'S%'; -> _ 는 한개, %는 여러개 (_를 문자로 쓰려면 \뒤에 사용)
