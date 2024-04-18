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

## Notification > RCS Bizmessage > 서비스 정책

### 개인정보 처리에 대한 안내
RCS Bizmessage 서비스를 이용하는 과정에서 고객은 이용자의 개인정보를 수집할 수 있습니다. 따라서 본 서비스를 이용하는 고객은 개인정보보호법에 따라 이용자에게 법적 고지사항을 알리고 동의를 받아야 합니다. 또한, 이 과정에서 고객과 NHN Cloud 간 개인정보처리에 관한 업무 위수탁 관계가 발생할 수 있습니다. 위탁자 지위에 있는 고객은 수탁자인 NHN Cloud와 별도 
서면에 의한 위탁 계약을 체결할 수 있으며 고객이 운영하는 개인정보처리 방침에 아래 내용을 참고하여 고지할 수 있습니다.

[예시]
- 수탁 업체: 엔에이치엔클라우드㈜
- 위탁 업무의 내용: RCS Bizmessage 서비스 제공 업무

### 지원하는 발송 유형

<table class="custom-table" style="text-align: center">
    <tr>
        <td>NO</td>
        <td>상품</td>
        <td>상품명</td>
        <td>카드 타입</td>
        <td>카드 수</td>
        <td>메시지 최대 길이</td>
        <td>카드별</td>
        <td>버튼</td>
        <td>이미지</td>
    </tr>
    <tr>
        <td>1</td>
        <td>SMS</td>
        <td>SMS</td>
        <td>Standalone</td>
        <td>1</td>
        <td>100</td>
        <td>1</td>
        <td>17</td>
        <td>-</td>
    </tr>
    <tr>
        <td>2</td>
        <td>LMS</td>
        <td>LMS</td>
        <td>Standalone</td>
        <td>1</td>
        <td>1300</td>
        <td>3</td>
        <td>17</td>
        <td>-</td>
    </tr>
    <tr>
        <td>3</td>
        <td rowspan="2">MMS</td>
        <td>세로형(Tall)</td>
        <td>Standalone Media Top</td>
        <td>1</td>
        <td>1300</td>
        <td>2</td>
        <td>17</td>
        <td>Tall(568x528)</td>
    </tr>
    <tr>
        <td>4</td>
        <td>세로형(Medium)</td>
        <td>Standalone Media Top</td>
        <td>1</td>
        <td>1300</td>
        <td>2</td>
        <td>17</td>
        <td>Medium(568x336)</td>
    </tr>
    <tr>
        <td>5</td>
        <td rowspan="5">텍스트<br/>템플릿</td>
        <td>서술 템플릿_타이틀 선택형</td>
        <td>Description</td>
        <td>1</td>
        <td>90자</td>
        <td>2</td>
        <td>17</td>
        <td rowspan="5">-</td>
    </tr>
    <tr>
        <td>6</td>
        <td>서술 템플릿_타이틀 자유형</td>
        <td>Description</td>
        <td>1</td>
        <td>90자</td>
        <td>2</td>
        <td>16</td>
    </tr>
    <tr>
        <td>7</td>
        <td>스타일 템플릿_타이틀 선택형</td>
        <td>Cell</td>
        <td>1</td>
        <td>90자</td>
        <td>2</td>
        <td>17</td>
    </tr>
    <tr>
        <td>8</td>
        <td>스타일 템플릿_타이틀 자유형</td>
        <td>Cell</td>
        <td>1</td>
        <td>90자</td>
        <td>2</td>
        <td>16</td>
    </tr>
    <tr>
        <td>9</td>
        <td>기본 템플릿_타이틀 자유형</td>
        <td>Free</td>
        <td>1</td>
        <td>90자</td>
        <td>0</td>
        <td>0</td>
    </tr>
    <tr>
        <td>10</td>
        <td rowspan="8">이미지<br/>템플릿</td>
        <td>이미지 & 타이틀 강조형 (3:4)</td>
        <td>Highlighted Image n Title</td>
        <td>1</td>
        <td>500자</td>
        <td>2</td>
        <td>16</td>
        <td>Long(900x1200)</td>
    </tr>
    <tr>
        <td>11</td>
        <td>이미지 & 타이틀 강조형 (1:1)</td>
        <td>Highlighted Image n Title</td>
        <td>1</td>
        <td>500자</td>
        <td>2</td>
        <td>16</td>
        <td>Square(900x900)</td>
    </tr>
    <tr>
        <td>12</td>
        <td>이미지 강조형 (3:4)</td>
        <td>Highlighted Image</td>
        <td>1</td>
        <td>500자</td>
        <td>2</td>
        <td>16</td>
        <td>Long(900x1200)</td>
    </tr>
    <tr>
        <td>13</td>
        <td>이미지 강조형 (1:1)</td>
        <td>Highlighted Image</td>
        <td>1</td>
        <td>500자</td>
        <td>2</td>
        <td>16</td>
        <td>Square(900x900)</td>
    </tr>
    <tr>
        <td>14</td>
        <td>썸네일형 (세로)</td>
        <td>Thumbnail</td>
        <td>1</td>
        <td>500자</td>
        <td>2</td>
        <td>16</td>
        <td>Vertical(900x560)</td>
    </tr>
    <tr>
        <td>15</td>
        <td>썸네일형 (가로)</td>
        <td>Thumbnail</td>
        <td>1</td>
        <td>500자</td>
        <td>2</td>
        <td>16</td>
        <td>Horizontal(900x560)</td>
    </tr>
    <tr>
        <td>16</td>
        <td>SNS형</td>
        <td>SNS</td>
        <td>1</td>
        <td>500자</td>
        <td>2</td>
        <td>16</td>
        <td>Square(900x900)</td>
    </tr>
    <tr>
        <td>17</td>
        <td>SNS형 (중간버튼)</td>
        <td>SNS</td>
        <td>1</td>
        <td>500자</td>
        <td>2</td>
        <td>16</td>
        <td>Rectangle(900x560)</td>
    </tr>
</table>

### 대체 발송 미지원 발송 유형
- TEMPLATE: 이미지 템플릿

