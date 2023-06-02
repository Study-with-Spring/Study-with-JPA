# week1 - ER 다이어그램

---

## ER 다이어그램

- ER 다이어그램 : Entity-Relationship Diagram의 줄임말이며 간단히 ERD라고 표기한다.
- 엔티티들과 엔티티 안에 포함될 속성들, 엔티티들 간의 관계를 선으로 표시한 도표


**Entity**

엔티티란 업무의 관심 대상이 되는 정보를 갖고 있거나 그에 대한 정보를 관리할 필요가 있는 유형, 무형의 객체를 말한다.

Ex) 쇼핑 사이트에서 상품을 판매하는 업무의 엔티티 : 구매자, 상품, 쇼핑카트

<img width="241" alt="Untitled 1" src="https://github.com/Study-with-Spring/Study-with-JPA/assets/80103052/d77d56c1-4ee4-4dbe-ae10-d0a6193644da">

**속성(Attribute)**

엔티티에서 관리해야할 최소 단위의 정보 항목을 말한다.

Ex) 회원 엔티티의 속성 : ID, 이름, 주소, 전화번호

<img width="244" alt="Untitled 2" src="https://github.com/Study-with-Spring/Study-with-JPA/assets/80103052/62bfc31e-371f-49b7-aae3-564d759a8ff5">

**주식별자와 외래식별자**

관계형 모델에서 기본키와 외래키에 대응하는 개념이다.

주식별자는 엔티티 박스의 상단에 표기하고, 외래 식별자는 하단에 일반 속성들과 함께 표기를 하되 (FK)를 붙인다.

<img width="443" alt="Untitled 3" src="https://github.com/Study-with-Spring/Study-with-JPA/assets/80103052/2086b2c2-b94f-430f-bdd1-a72ea0aea702">

**관계**

- 두 엔티티가 관계가 있을 때 ER 다이어그램에서는 두 엔티티를 선으로 연결하여 관계가 있음을 나타낸다.
- 두 엔티티가 관계가 있다는 것은 일반적으로 두 엔티티가 외래 식별자에 의해서 연결되어 있다는 것을 의미한다.

<img width="439" alt="Untitled 4" src="https://github.com/Study-with-Spring/Study-with-JPA/assets/80103052/11708529-1f52-4107-ba2f-26b4d6165411">

**관계 표시**

<img width="550" alt="image" src="https://github.com/Study-with-Spring/Study-with-JPA/assets/80103052/01292ee5-8e18-495d-9b62-ff592701698f">
<img width="606" alt="image" src="https://github.com/Study-with-Spring/Study-with-JPA/assets/80103052/553f10b9-95e9-4ea7-89ac-f2b661fb50fa">


**함수적 종속성(functional dependency)**

- 주식별자(기본 키)는 릴레이션(테이블)내에서 인스턴스(튜플)을 식별하는 역할을 하므로 주식별자가 아닌 모든 속성들의 집합은 주식별자에 함수적으로 종속이어야 한다.

<img width="599" alt="Untitled 7" src="https://github.com/Study-with-Spring/Study-with-JPA/assets/80103052/c90ece13-f4a8-4154-b4f2-e92033c97827">

완전 함수 종속

주식별자가 여러개인 릴레이션에서 주식별자가 아닌 속성들이 주식별자 전체 속성에 함수적으로 종속된 경우

부분 함수 종속

주식별자가 아닌 속성들이 주식별자의 부분 속성에 함수적으로 종속된 경우
