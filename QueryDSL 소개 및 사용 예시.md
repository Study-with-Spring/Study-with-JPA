# QueryDSL 소개 및 사용 예시

## **QueryDSL 이란?**

QueryDSL은 Java에서 사용하는 오픈 소스 라이브러리로, 타입 세이프하게 SQL과 유사한 쿼리를 작성할 수 있게 해준다. QueryDSL은 JPQL, JPA, SQL, JDO, Lucene, Hibernate Search, MongoDB, Collections 등 다양한 백엔드를 지원한다. 이 라이브러리를 사용하면 복잡한 쿼리를 안전하고, 가독성 높게 작성할 수 있다.

## **QueryDSL의 장점**

- **타입 세이프(Type Safe)**: 쿼리를 작성하는 시점에 컴파일 타임 체크가 가능하여, 쿼리에 오타나 타입 불일치 등의 실수를 줄일 수 있다.
- **가독성**: SQL과 유사한 문법으로 쿼리를 작성할 수 있으며, 메서드 체이닝을 사용하여 코드가 깔끔해진다.
- **동적 쿼리 작성 용이**: 조건에 따라 동적으로 쿼리를 생성하는 것이 간단하다.

## **QueryDSL 설정 및 사용 예시의존성 설정**

### **엔티티 정의 (예시)**

```
javaCopy code
@Entity
public class Book {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String title;
    private String author;
    private int pages;

    // getters and setters
}
```

### **QueryDSL 설정 및 Q 클래스 생성**

QueryDSL을 사용하기 위해서는 엔티티를 바탕으로 Q 클래스를 생성해야 한다. 이 클래스들은 쿼리를 타입 세이프하게 작성하는데 사용된다. Gradle 빌드를 실행하면 **`Book`** 엔티티에 대한 **`QBook`** 클래스가 생성된다다.

### **쿼리 작성 예시**

QueryDSL로 쿼리를 작성하는 방법에 대해 간단한 예시

```
javaCopy code
@Repository
public class BookRepositoryCustomImpl implements BookRepositoryCustom {

    private final JPAQueryFactory queryFactory;

    public BookRepositoryCustomImpl(EntityManager em) {
        this.queryFactory = new JPAQueryFactory(em);
    }

    @Override
    public List<Book> findBooksByAuthor(String author) {
        QBook book = QBook.book;
        return queryFactory.selectFrom(book)
                           .where(book.author.eq(author))
                           .fetch();
    }
}

```

위 예제에서는 **`author`**가 주어진 값과 같은 책들을 조회하는 쿼리를 QueryDSL을 사용하여 작성했다. **`QBook`**은 QueryDSL이 생성한 Q 클래스로, 엔티티 필드에 안전하게 접근할 수 있게 해준다 QueryDSL을 사용하면 동적 쿼리 작성, 조인, 그룹핑 등 다양한 쿼리 작성과 최적화에 유용하게 쓰일 수 있다.