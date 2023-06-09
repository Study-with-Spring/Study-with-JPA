# 스프링 JPA 정리

---

### 1. JPA란?(Java Persistence API)

: 우선 JPA 자체는 API 즉, 특정 기술에 대한 표준을 의미한다. 여기서 특정 기술은 ORM(Object Relational Mapping), **객체와 관계형 데이터베이스를 매핑**해주는 것을 의미한다. 서로 다른 목표로 설계된 JAVA와 관계형 데이터베이스 사이의 이음새 역할을 해주는 것이 바로 JPA이다. JPA는 인터페이스인 만큼 여러 구현체가 있는데 가장 많이 사용되는 것이 Hibernate가 있다.

- JPA의 장단점
    - JPA 사용 시 **장점**
    
    <aside>
    💡 1. 특정 데이터베이스에 종속되지 않음
    2. 객체지향적 프로그래밍
    3. 생산성 향상
    
    </aside>
    
    - JPA 사용 시 **단점**
    
    <aside>
    💡 1. 복잡한 쿼리 작성 한계 → JPQL 사용
    2. 성능 저하 위험 ← 객체 간의 매핑 설계를 잘못 했을 시 성능 저하 발생 가능
    
    </aside>
    

### 2. JPA 주요 용어 및 작동 방식

[https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fbk2AgJ%2FbtrtITslQVf%2FjDzkGqNam5qCHct9N3QVU0%2Fimg.png](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fbk2AgJ%2FbtrtITslQVf%2FjDzkGqNam5qCHct9N3QVU0%2Fimg.png)

- 엔티티 : 데이터베이스의 테이블에 대응하는 클래스. 해당 엔티티를 통해 데이터베이스 내에 데이터베이스를 생성 가능.
    - **엔티티의 생명주기**
        
        
        | 1. 비영속 | new 키워드를 통해 새로 생성된 상태, 영속성 컨텍스트와는 관련이 없는 상태 |
        | --- | --- |
        | 2. 영속 | 엔티티가 영속성 컨텍스트에 저장되어 관리되는 상태
        ex) em.persisnt(member)
        ex) em.find(member) ← 멤버 엔티티가 1차 캐시에 없었을 때 |
        | 3. 준영속 상태 | 영속성 컨텍스트에서 해당 엔티티가 삭제된 상태
        ex) em.detach(member)
        ex) em.clear() |
        | 4. 삭제 상태 | 실제 DB에서 해당 엔티티가 삭제된 상태
        ex) em.remove(member) |
- 엔티티 매니저 팩토리 : 엔티티 매니저 인스턴스를 관리하는 주체, 데이터베이스와의 연결 및 JPA 설정, 커넥션 풀 초기화 등 여러 작업을 수행하기 때문에 생성 비용이 커 보통 하나만 선언해 사용함.
- 앤티티 매니저 : 영속성 컨텍스트에 접근하여 엔티티에 대한 데이터베이스 작업(CRUD)을 제공.
- **영속성 컨텍스트** : 쉽게 설명하면 임시 저장소 느낌이다. 현재 다루고 있는 엔티티를 임시 저장해둠으로써 캐싱 효과 및 동일성 보장 효과를 주며, 쓰기 지연을 통해 트랜잭션들을 모아놨다가 한번에 처리한다. 이로 인해 데이터베이스와의 통신 횟수를 줄임으로써 성능을 향상시킬 수 있다.