# JDBC 라이브러리 구현하기

## 🚀 1단계 - JDBC 라이브러리 구현하기
### 기능 요구 사항
개발자는 SQL 쿼리 작성, 쿼리에 전달할 인자, SELECT 구문일 경우 조회 결과를 추출하는 것만 집중할 수 있도록 라이브러리를 만들자.

### 체크리스트
- [x] UserDaoTest의 모든 테스트 케이스가 통과한다.
- [x] UserDao가 아닌 JdbcTemplate 클래스에서 JDBC와 관련된 처리를 담당하고 있다.

---

## 🚀 2단계 - JDBC 리팩터링
### 기능 요구 사항
- JDBC 라이브러리를 리팩터링한다.

### 체크리스트
- [x] SQLException은 Checked Exception이다. 커스텀 Exception을 추가해서 사용자는 Unchecked Exception이 되도록 변경하자.
- [x] RowMapper 인터페이스는 Object를 반환하고 있어서 캐스팅이 사용된다. 제네릭을 사용하도록 개선해보자.
- [x] 매번 PreparedStatementSetter 인터페이스를 구현하려니 번거롭다. 람다를 적극적으로 활용해서 코드량을 줄여보자.

---

## 🚀 3단계 - Transaction 적용하기
### 기능 요구 사항
- 원자성을 보장하기 위해 트랜잭션을 적용하자.

### 체크리스트
- [x] 트랜잭션 롤백이 적용되어 UserServiceTest 클래스의 testTransactionRollback() 테스트 케이스가 통과한다.
- [x] 트랜잭션 서비스와 애플리케이션 서비스가 분리되었다.

