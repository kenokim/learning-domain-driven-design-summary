프로젝트의 복잡성을 줄이기 위해 DDD 를 사용한다. 유비쿼터스 언어를 살펴보고 의심스러운 경우 이벤트스토밍을 진행하라.

솔루션은 문제 정의 -> 해결책 -> 구현의 단계를 거친다.

## Chapter01. 비즈니스 도메인 분석하기

비즈니스 도메인은 하위 도메인으로 나뉜다. 

하위 도메인은 핵심 / 일반 / 지원 하위 도메인으로 나뉘며, 핵심 하위 도메인은 특히 중요하다.

하위 도메인의 경계를 식별하기 위해 응집된 유스케이스의 집합을 하위 도메인으로 정의한다.

비즈니스 하위 도메인의 경계와 유형을 식별해야 한다.








## Chapter02. 도메인 지식 찾아내기

비즈니스 하위 도메인을 식별한 후, 비즈니스의 도메인을 모델링해야 한다.

이는 기술적인 모델링 보다는 비즈니스적인 언어로 정의하는 모델링이다.

이를 위해 도메인 전문가와 지속적으로 상호작용 해야 하며 유비쿼터스 언어, 즉 일치한 언어로 도메인 전문가의 생각을 이해해야 한다.

유비쿼터스 언어를 발전시켜 비즈니스 도메인 모델을 구축하게 되며, 이는 도메인 전문가의 멘탈 모델을 포착하고 business entity 의 행동, 인과 관계, 불변성을 반영해야 한다.

유비쿼터스 언어를 수집하고 관리하는 도구로는 용어집(명사), 유스케이스(행동)가 있다. 두 가지를 모두 유지보수하는 것이 좋다. 


## Chapter03. 도메인 복잡성 관리

하위 도메인은 발견하는 것이고, 바운디드 컨텍스트는 설계하는 것이다.

유비쿼터스 언어는 바운디드 컨텍스트 안에서만 효과적이다.

유비쿼터스 언어를 여러 개의 작은 언어로 나누고 각 언어를 바운디드 컨텍스트에 할당하라.

바운디드 컨텍스트는 하나의 독립적인 서비스로 발전한다.





## Chapter05, 06. 비즈니스 로직

 트랜잭션 스크립트 : 시스템 작업을 절차지향 프로시저로 구현해서, 트랜잭션이 성공하거나 실패하도록 구성한다.

액티브 레코드 : 비즈니스 로직이 복잡한 자료구조에서 작동하는 경우 CRUD 접근 방법을 제공하는 자료구조를 구현한다.

밸류 오브젝트 : 값과 행동을 모델링하고 ID 가 없다.

애그리게이트 : 트랜잭션 경계를 공유하는 엔티티의 계층이다. 비즈니스 로직의 구현을 통해 일관성을 유지해야 한다.

도메인 서비스 : 도메인 모델에서 애그리게이트 또는 밸류 오브젝트에 속하지 않는 비즈니스 로직을 담는 stateless 객체이다.

## Chapter08. 아키텍처 패턴

계층형 아키텍처 = 프레젠테이션, 서비스, 비즈니스 로직, 데이터 접근

서비스 계층과 비즈니스 로직 계층은 분리할수도, 통합할 수도 있다.

비즈니스 로직이 트랜잭션 스크립트 또는 액티브 레코드 패턴을 사용하여 구현할 경우 계층형 아키텍처 패턴이 적합하다.

## Chapter 14. 마이크로서비스

MSA = 빠르게 바뀌고 확장되며 클라우드에 맞춰야 하는 요구사항에 강하다. 잘못 쪼개면 모놀리식보다 분산된 진흙이 된다.

서비스는 자신의 public interface 에 의해 정의된다. 마이크로서비스는 자신의 마이크로 프론트 도어에 의해 정의되는 서비스다.

서비스의 기능은 인터페이스에 의해 정의되므로 데이터베이스를 노출하지 않는다. 이는 자신의 인터페이스의 크기를 줄이는 역할을 한다.

서비스를 너무 잘게 쪼개면 서비스간의 연동이 심해져 분산된 진흙이 된다.

서비스의 크기는 로컬 복잡성과 글로벌 복잡성의 trade-off 관계이고 따라서 적절한 타협점을 찾아야 한다.
