# Join

다른 entity를 Join 해도 join 한 entity는 영속성 컨텍스트에서 관리하지 않고 SELECT한 주체가 되는 entity만 관리합니다.

# Join Fetch

fetch join은 SQL에서 말하는 join과 같은 개념이 아닙니다. JPQL에서 성능최적화를 위해 제공하는 JOIN의 종류입니다. 연관된 엔티티나 컬렉션을 한 번에 같이 조회할 수 있는 기능입니다. JOIN FETCH 명령어로 사용할 수 있습니다.

![N+1](https://github.com/Study-with-Spring/Study-with-JPA/assets/5775698/cac09da4-6a89-447b-85e3-1c56c55413de)

## 무조건 Fetch JOIN을 써야할까?

Fetch Join을 무지성으로 쓰면 영속성 컨텍스트에 너무 많이 올려지기 때문에 일반 JOIN을 적절히 섞어서 필요한 Entity만을 골라 가져오는 것이 좋습니다. 또한 연관 관계가 있는 Entity가 쿼리 검색 조건에는 필요하지만 실제 데이터는 필요하지 않은 상황일 경우에도 일반 JOIN을 사용하는 것이 좋습니다.
