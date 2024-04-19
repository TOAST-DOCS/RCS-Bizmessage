<style>
    .custom-table thead {
        background-color: #FAFAFA;
    }
    
    .custom-table tbody tr {
        background-color: white;
    }
    
    .custom-table td {
        vertical-align: middle;
    }
</style>

## Notification > RCS Bizmessage > 개요

RCS Bizmessage 서비스는 RCS Bizmessage 발송 및 브랜드, 템플릿 관리 기능을 제공하는 서비스입니다. RCS Bizmessage 서비스를 통해 사용자는 메시지 발송에서 나아가 브랜드 관리를 통해 기업과 고객 간 연결을 위한 브랜드 정보를 제공할 수 있고, 다양한 유형의 메시지를 발송할 수 있습니다.
손쉬운 연동을 위한 REST API를 제공합니다.

## 주요 기능

* 풍부한 정보의 메시지 발송
    * SMS 최대 100자, LMS/MMS 최대 1300자 입력 가능하며, MMS 첨부파일은 최대 6개까지 입력 가능합니다.    
    * 다양한 메시지 발송 유형을 제공합니다. MMS 유형으로 메시지 발송 시 가로/세로/슬라이드 형태로 발송할 수 있습니다.
    * 메시지 발송 시 버튼에 기능이 담긴 액션 버튼을 추가할 수 있습니다.
* 대체 발송
    * RCS Bizmessage를 수신하지 못하는 단말기의 경우 기존 SMS 서비스로 대체 발송하는 기능을 제공합니다.
* 손쉬운 연동
    * 본인 인증 절차를 통해 인증된 사업자 등록 정보를 통해 RCS Biz Center에 등록한 브랜드, 템플릿 정보를 연동할 수 있습니다.
    * 고객의 애플리케이션에서 사용할 수 있는 RCS Bizmessage 발송 기능과 조회 REST API를 제공합니다.

## RCS 발송 지원 타입

<table class="custom-table" style="text-align: center">
  <thead>
    <tr>
      <th>구분</th>
      <th colspan="3">일반</th>
      <th colspan="2">템플릿</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>상품명</td>
      <td>RCS SMS</td>
      <td>RCS LMS</td>
      <td>RCS MMS</td>
      <td>텍스트 템플릿</td>
      <td>이미지 템플릿</td>
    </tr>
    <tr>
      <td>용도</td>
      <td>정보/광고</td>
      <td>정보/광고</td>
      <td>정보/광고</td>
      <td>정보</td>
      <td>정보/광고</td>
    </tr>
    <tr>
      <td>사전 승인</td>
      <td>불필요</td>
      <td>불필요</td>
      <td>불필요</td>
      <td>승인 필요</td>
      <td>승인 필요</td>
    </tr>
    <tr>
      <td>최대 글자</td>
      <td>100자</td>
      <td>1,300자</td>
      <td>1,300자<br/>+1MB 미디어 (카드당)</td>
      <td>90자</td>
      <td>500자<br/>+ 1MB 미디어 (카드당)</td>
    </tr>
    <tr>
      <td>최대 버튼</td>
      <td>1개</td>
      <td>6개</td>
      <td>2개 (카드당)</td>
      <td>1개</td>
      <td>2개 (카드당)</td>
    </tr>
    <tr>
      <td>

[지원 포맷](./service-policy)
</td>
      <td>1개</td>
      <td>1개</td>
      <td>4개</td>
      <td>4개</td>
      <td>4개</td>
    </tr>
  </tbody>
</table>

## 서비스 대상

* 풍부한 정보와 사용자 액션을 담고 메시지를 발송하고자 하는 고객
* 대량의 RCS Bizmessage를 발송하고자 하는 고객
* REST API를 통해 손쉽게 RCS Bizmessage 서비스 연동하고자 하는 고객