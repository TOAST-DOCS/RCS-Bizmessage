<!-- pre-align:aligned sig=6a12872db115 -->

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

<a id="notification-rcs-bizmessage-overview"></a>
## Notification > RCS Bizmessage > 概要 { #notification-rcs-bizmessage-overview }

RCS BizmessageサービスはRCS Bizmessage送信およびブランド、テンプレート管理機能を提供するサービスです。 RCS Bizmessageサービスを通じて、ユーザーは様々なタイプのメッセージを送信し、企業と顧客間の接続のためのブランド情報を管理し、提供できます。
簡単な連携のためのREST APIを提供します。

<a id="main-features"></a>
## 主な機能 { #main-features }

* 豊富な情報のメッセージ送信
    * SMS最大100文字、 LMS/MMS最大1300文字入力可能で、MMS添付ファイルは最大6個まで入力可能です。    
    * さまざまなメッセージ送信タイプを提供します。 MMSタイプでメッセージ送信時、横/縦/スライド形式で送信できます。
    * メッセージ送信時、ボタンに機能が入ったアクションボタンを追加できます。
* 代替送信
    * RCS Bizmessageを受信できない端末の場合、既存SMSサービスで代替送信する機能を提供します。
* 簡単な連動
    * 本人認証手続きを通じて認証された事業者登録情報でRCS Biz Centerに登録したブランド、テンプレート情報を連動させることができます。
    * 顧客のアプリケーションで使用できるRCS Bizmessage送信機能と照会REST APIを提供します。

<a id="rcs-delivery-supported-types"></a>
## RCS送信サポートタイプ { #rcs-delivery-supported-types }

<table class="custom-table" style="text-align: center">
  <thead>
    <tr>
      <th>区分</th>
      <th colspan="3">一般</th>
      <th colspan="2">テンプレート</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>商品名</td>
      <td>RCS SMS</td>
      <td>RCS LMS</td>
      <td>RCS MMS</td>
      <td>テキストテンプレート</td>
      <td>イメージテンプレート</td>
    </tr>
    <tr>
      <td>用途</td>
      <td>情報/広告</td>
      <td>情報/広告</td>
      <td>情報/広告</td>
      <td>情報</td>
      <td>情報/広告</td>
    </tr>
    <tr>
      <td>事前承認</td>
      <td>不要</td>
      <td>不要</td>
      <td>不要</td>
      <td>承認必要</td>
      <td>承認必要</td>
    </tr>
    <tr>
      <td>最大文字</td>
      <td>100文字</td>
      <td>1,300文字</td>
      <td>1,300文字<br/>+1MBメディア(カード毎)</td>
      <td>90文字</td>
      <td>500文字<br/>+ 1MBメディア(カード毎)</td>
    </tr>
    <tr>
      <td>最大ボタン</td>
      <td>1個</td>
      <td>6個</td>
      <td>2個(カード毎)</td>
      <td>1個</td>
      <td>2個(カード毎)</td>
    </tr>
    <tr>
      <td>

[サポートフォーマット](./service-policy)
</td>
      <td>1個</td>
      <td>1個</td>
      <td>4個</td>
      <td>4個</td>
      <td>4個</td>
    </tr>
  </tbody>
</table>

<a id="service-targets"></a>
## サービス対象 { #service-targets }

* 豊富な情報とユーザーアクションを含むメッセージを送信したい顧客
* 大量のRCS Bizmessageを送信したい顧客
* REST APIで簡単にRCS Bizmessageサービスを連動させたいお客様
