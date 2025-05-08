## Use Case Description: 대여소 검색
Actor Action(Client) | System Response
---|---
&nbsp;| 1. '대여소 이름'을 입력할 수 있는 대여소 검색 화면을 표시한다.
<br>2. '대여소 이름'을 입력하여 대여소를 검색해서 '검색' 버튼을 클릭한다.| &nbsp;
<br>&nbsp;|3. 입력된 대여소 이름과 같은 대여소 리스트를 출력한다.
<br>

## Use Case Description: 대여소 상세 정보 조회
Actor Action(Client) | System Response
---|---
&nbsp;|1.선택된 대여소에 대한 '대여소 이름, 대여소 위치, 자전거 목록'을 출력한다.
### Extenstions
- After step 1 (`<<extend>>` 자전거 예약 대기)
    - Actor Action(Client): 현재 자전거가 남아있지 않은 경우, '예약 대기' 버튼 클릭한다.
    - System Response: 예약 대기 완료 팝업이 표시가 되고, 문자 알림을 통해 예약 대기 내용을 전송한다.

## Use Case Description: 자전거 즉시 대여
Actor Action(Client) | System Response
---|---
&nbsp;| 1.선택한 특정 대여소의 상세 정보 화면을 출력한다.
<br>2. 현재 자전거가 남아있는 경우 '대여' 버튼을 클릭한다.| &nbsp;
&nbsp;|3. 문자 알림을 통해 해당 내용을 전송한다.

## Use Case Description: 자전거 대여 정보 조회
Actor Action(Client) | System Response
---|---
&nbsp;|1.현재 대여 중인 자전거 리스트가 출력되며, 각 항목에는 '대여소 이름, 대여소 위치, 자전거 ID, 자전거 제품명, 자전거 유형'을 보여준다.
### Extenstions
- After step 1 ('`<<extend>>` 자전거 반납)
    - Actor Action(Client): 특정 자전거를 선택하여 '반납' 버튼을 클릭한다.
    - System Response: 사용 시간에 따라 요금이 자동 결제/반납 완료되며, 해당 자전거에 대기 예약한 회원이 있는 경우 대기 1순위 회원에게 예약 되었다는 이메일을 보낸다. 이후, 식당 추천 여부 팝업이 활성화 된다.
### Extenstions
- After step 1 (`<<extend>>` 식당 예약 외부 시스템 연결)
    - Actor Action(Client): '식당 추천' 버튼을 클릭한다.
    - System Response: 근처 식당을 추천받아서 예약할 수 있는 외부 서비스와 연결한다.