# 주문과 할인 도메인 설계

### 주문과 할인 정책
- 회원은 상품을 주문할 수 있다.
- 회원 등급에 따라 할인 정책을 적용할 수 있다. 
- 할인 정책은 모든 VIP는 1000원을 할인해주는 고정 금액 할인을 적용해달라.(나중에 변경 될 수
  있다.)
- 할인 정책은 변경 가능성이 높다. 회사의 기본 할인 정책을 아직 정하지 못했고, 오픈 직전까지 고민을 미루고 싶다. 최악의 경우 할인을 적용하지 않을 수 도 있다.(미확정)
<br><br>

### 주문 도메인 협력, 역할, 책임
<img src="https://user-images.githubusercontent.com/90389517/221651836-eaf1d060-fa29-4ee1-9b1c-7ff475bd5c72.png">

1. 주문 생성 : 클라이언트는 주문 서비스에 주문 생성을 요청한다.
2. 회원 조회 : 할인을 위해서는 회원 등급이 필요하다. 그래서 주문 서비스는 회원 저장소에서 회원을 조회한다.
3. 할인 적용 : 주문 서비스는 회원 등급에 따른 할인 여부를 할인 정책에 위임한다.
4. 주문 결과 반환 : 주문 서비스는 할인 결과를 포함한 주문 결과를 반환한다.
<br><br>

### 주문 도메인 전체
<img src="https://user-images.githubusercontent.com/90389517/221652290-ce81eee6-c29a-47d9-9c3e-fccbfae06c62.png"><br>
역할과 구분을 분리해서 자유롭게 구현 객체를 조립할 수 있게 설계한다. 
<br><br>

### 주문 클래스 다이어그램
<img src="https://user-images.githubusercontent.com/90389517/221652590-9d141cd2-7a3e-4432-86cc-b7da429a8fe5.png">
<br><br>

### 주문 도메인 객체 다이어그램1
<img src="https://user-images.githubusercontent.com/90389517/221652685-4930d261-8ede-4de6-acf9-7d54211ed52c.png"><br>
역할들의 협력 관계를 그대로 재사용 할 수 있다.
<br><br>

### 주문 도메인 객체 다이어그램2
<img src="https://user-images.githubusercontent.com/90389517/221652792-fb31e76e-41e7-4973-9246-db6a648d3763.png"><br>
역할들의 협력 관계를 그대로 재사용 할 수 있다.