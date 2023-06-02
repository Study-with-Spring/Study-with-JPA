# week1 - ER 다이어그램

---

## ER 다이어그램

- ER 다이어그램 : Entity-Relationship Diagram의 줄임말이며 간단히 ERD라고 표기한다.
- 엔티티들과 엔티티 안에 포함될 속성들, 엔티티들 간의 관계를 선으로 표시한 도표

<img width="241" alt="Untitled 1" src="https://github.com/Study-with-Spring/Study-with-JPA/assets/80103052/76b0a559-c9a0-4526-9ee8-3e41c44f604f">

**Entity**

엔티티란 업무의 관심 대상이 되는 정보를 갖고 있거나 그에 대한 정보를 관리할 필요가 있는 유형, 무형의 객체를 말한다.

Ex) 쇼핑 사이트에서 상품을 판매하는 업무의 엔티티 : 구매자, 상품, 쇼핑카트

<img width="244" alt="Untitled 2" src="https://github.com/Study-with-Spring/Study-with-JPA/assets/80103052/c2886a28-7d9d-4b96-b225-e0911fff18b0">

**속성(Attribute)**

엔티티에서 관리해야할 최소 단위의 정보 항목을 말한다.

Ex) 회원 엔티티의 속성 : ID, 이름, 주소, 전화번호

<img width="443" alt="Untitled 3" src="https://github.com/Study-with-Spring/Study-with-JPA/assets/80103052/0528d078-e2ee-4010-969e-4b0e09c28c60">

**주식별자와 외래식별자**

관계형 모델에서 기본키와 외래키에 대응하는 개념이다.

주식별자는 엔티티 박스의 상단에 표기하고, 외래 식별자는 하단에 일반 속성들과 함께 표기를 하되 (FK)를 붙인다.

<img width="439" alt="Untitled 4" src="https://github.com/Study-with-Spring/Study-with-JPA/assets/80103052/d7107db1-60ea-4f44-912d-342a7ed8ec40">

**관계**

- 두 엔티티가 관계가 있을 때 ER 다이어그램에서는 두 엔티티를 선으로 연결하여 관계가 있음을 나타낸다.
- 두 엔티티가 관계가 있다는 것은 일반적으로 두 엔티티가 외래 식별자에 의해서 연결되어 있다는 것을 의미한다.

![Untitled 5](https://github.com/Study-with-Spring/Study-with-JPA/assets/80103052/80b4ded7-3b75-4d54-828d-d3fc536882e3)

**관계 표시**

![Untitled 6](https://github.com/Study-with-Spring/Study-with-JPA/assets/80103052/7f60dae7-53b3-46d4-9d96-372df5c09865)

<img width="599" alt="Untitled 7" src="https://github.com/Study-with-Spring/Study-with-JPA/assets/80103052/ec430c0f-a629-4cd9-bbba-047c708e86e2">

**함수적 종속성(functional dependency)**

- 주식별자(기본 키)는 릴레이션(테이블)내에서 인스턴스(튜플)을 식별하는 역할을 하므로 주식별자가 아닌 모든 속성들의 집합은 주식별자에 함수적으로 종속이어야 한다.

<img width="381" alt="Untitled" src="https://github.com/Study-with-Spring/Study-with-JPA/assets/80103052/f5745495-4550-4441-a0e9-f68ad7908d98">

완전 함수 종속

주식별자가 여러개인 릴레이션에서 주식별자가 아닌 속성들이 주식별자 전체 속성에 함수적으로 종속된 경우

부분 함수 종속

주식별자가 아닌 속성들이 주식별자의 부분 속성에 함수적으로 종속된 경우
