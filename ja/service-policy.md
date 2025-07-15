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

## Notification > RCS Bizmessage > サービスポリシー

### 個人情報処理についてのご案内
RCS Bizmessageサービスを利用する過程で、顧客は利用者の個人情報を収集できます。したがって、本サービスを利用する顧客は、個人情報保護法に基づき、利用者に法的告知事項を通知し、同意を得なければなりません。また、この過程で、顧客とNHN Cloudの間で個人情報処理に関する業務委託関係が発生する可能性があります。委託者の地位にある顧客は、受託者であるNHN Cloudと別途に 
書面による委託契約を締結することができ、顧客が運営する個人情報処理方針に以下の内容を参考にして告知することができます。

[例]
- 受託業者: NHNクラウド(株)
- 委託業務の内容: RCS Bizmessageサービス提供業務

### サポートする送信タイプ

<table class="custom-table" style="text-align: center">
    <tr>
        <td>NO</td>
        <td>商品</td>
        <td>商品名</td>
        <td>カードタイプ</td>
        <td>カード数</td>
        <td>メッセージ最大長さ</td>
        <td>カード別ボタン数</td>
        <td>ボタン名の最大長さ</td>
        <td>イメージ</td>
        <td>備考</td>        
    </tr>
    <tr>
        <td>1</td>
        <td>SMS</td>
        <td>SMS</td>
        <td>Standalone</td>
        <td>1</td>
        <td>100文字</td>
        <td>1</td>
        <td>17文字</td>
        <td>-</td>
        <td>-</td>
    </tr>
    <tr>
        <td>2</td>
        <td>LMS</td>
        <td>LMS</td>
        <td>Standalone</td>
        <td>1</td>
        <td>1300文字</td>
        <td>3</td>
        <td>17文字</td>
        <td>-</td>
        <td>-</td>
    </tr>
    <tr>
        <td>3</td>
        <td rowspan="2">MMS</td>
        <td>縦型(Tall)</td>
        <td>Standalone Media Top</td>
        <td>3~6</td>
        <td>1300文字</td>
        <td>2</td>
        <td>17文字</td>
        <td>Tall(568x528)</td>
        <td>-</td>        
    </tr>
    <tr>
        <td>4</td>
        <td>縦型(Medium)</td>
        <td>Standalone Media Top</td>
        <td>3~6</td>
        <td>1300文字</td>
        <td>2</td>
        <td>17文字</td>
        <td>Medium(568x336)</td>
        <td>-</td>        
    </tr>
    <tr>
        <td>5</td>
        <td rowspan="5">テキスト<br/>テンプレート</td>
        <td>書式テンプレート_タイトル選択型</td>
        <td>Description</td>
        <td>1</td>
        <td>90文字</td>
        <td>2</td>
        <td>17文字</td>
        <td rowspan="5">-</td>
        <td>-</td>        
    </tr>
    <tr>
        <td>6</td>
        <td>書式テンプレート_タイトル自由型</td>
        <td>Description</td>
        <td>1</td>
        <td>90文字</td>
        <td>2</td>
        <td>16文字</td>
        <td>-</td>
    </tr>
    <tr>
        <td>7</td>
        <td>スタイルテンプレート_タイトル選択型</td>
        <td>Cell</td>
        <td>1</td>
        <td>90文字</td>
        <td>2</td>
        <td>17文字</td>
        <td>-</td>
    </tr>
    <tr>
        <td>8</td>
        <td>スタイルテンプレート_タイトル自由型</td>
        <td>Cell</td>
        <td>1</td>
        <td>90文字</td>
        <td>2</td>
        <td>16文字</td>
        <td>-</td>
    </tr>
    <tr>
        <td>9</td>
        <td>基本テンプレート_タイトル自由型</td>
        <td>Free</td>
        <td>1</td>
        <td>90文字</td>
        <td>0</td>
        <td>-</td>
        <td>-</td>
    </tr>
    <tr>
        <td>10</td>
        <td rowspan="8">イメージ<br/>テンプレート</td>
        <td>イメージ&タイトル強調型(3:4)</td>
        <td>Highlighted Image n Title</td>
        <td>1</td>
        <td>500文字</td>
        <td>2</td>
        <td>16文字</td>
        <td>Long(900x1200)</td>
        <td rowspan="8">金融コンプライアンス告知フィールド追加(2025. 04. 25)前に作成されたテンプレートのみサポート</td>        
    </tr>
    <tr>
        <td>11</td>
        <td>イメージ&タイトル強調型(1:1)</td>
        <td>Highlighted Image n Title</td>
        <td>1</td>
        <td>500文字</td>
        <td>2</td>
        <td>16文字</td>
        <td>Square(900x900)</td>
    </tr>
    <tr>
        <td>12</td>
        <td>イメージ強調型(3:4)</td>
        <td>Highlighted Image</td>
        <td>1</td>
        <td>500文字</td>
        <td>2</td>
        <td>16文字</td>
        <td>Long(900x1200)</td>
    </tr>
    <tr>
        <td>13</td>
        <td>イメージ強調型(1:1)</td>
        <td>Highlighted Image</td>
        <td>1</td>
        <td>500文字</td>
        <td>2</td>
        <td>16文字</td>
        <td>Square(900x900)</td>
    </tr>
    <tr>
        <td>14</td>
        <td>サムネイル型(縦)</td>
        <td>Thumbnail</td>
        <td>1</td>
        <td>500文字</td>
        <td>2</td>
        <td>16文字</td>
        <td>Vertical(900x560)</td>
    </tr>
    <tr>
        <td>15</td>
        <td>サムネイル型(横)</td>
        <td>Thumbnail</td>
        <td>1</td>
        <td>500文字</td>
        <td>2</td>
        <td>16文字</td>
        <td>Horizontal(900x560)</td>
    </tr>
    <tr>
        <td>16</td>
        <td>SNS型</td>
        <td>SNS</td>
        <td>1</td>
        <td>500文字</td>
        <td>2</td>
        <td>16文字</td>
        <td>Square(900x900)</td>
    </tr>
    <tr>
        <td>17</td>
        <td>SNS型(中間ボタン)</td>
        <td>SNS</td>
        <td>1</td>
        <td>500文字</td>
        <td>2</td>
        <td>16文字</td>
        <td>Rectangle(900x560)</td>
    </tr>
</table>

### 代替送信未サポート送信タイプ
- TEMPLATE:イメージテンプレート
