## Notification > RCS Bizmessage > リリースノート

### 2024. 08. 27.
#### 機能改善/変更
* [API]送信APIリクエスト時の受信者番号形式の検証を強化
  * 詳細は[[APIガイド](./api-guide/#_1)]を参照してください。

### 2024. 04. 23.
#### 機能改善/変更
* [API]詳細照会APIレスポンス中のresultCodeの更新タイミングを変更
  * 送信完了直後に2000で更新されていたresultCodeが受信結果反映後に更新されるように変更されました。
* [API]送信希望時間の設定最大値を変更
  * 設定可能な発送希望時間が最大60日以降に変更されました。
* [API]リスト照会APIの照会条件の検証を強化
  * messageIdが照会条件に含まれる場合、正確なmessageIdのみを受け取るように検証を強化しました。
* [Console]リスト照会画面で照会条件の検証を強化
  * リクエストIDフィールドが照会条件に含まれる場合、正確なmessageIdのみを受け取るように検証を強化しました。

### 2024. 01. 23.
#### 機能追加
* [Console]夜間広告送信制限機能を追加
  * 夜間広告送信制限の有無及び制限時間を設定できる機能が追加されました。 

### 2023. 12. 19.
#### 機能改善/変更
* [API]必須テンプレートパラメータが不足している場合のエラーメッセージを追加
    * 必須テンプレートパラメータが不足している場合のエラーコードが追加されました。
    * 詳細は[[結果コード](./result-code/#_1)]の結果コード**-4024**を参照してください。

### 2023. 11. 14.
#### 機能追加
* [API]イメージテンプレート送信追加
    * イメージテンプレート（イメージ＆タイトル強調型、イメージ強調型、SNS型、サムネイル型）を利用して送信できる機能が追加されました。
* [Console]イメージテンプレート送信を追加
    * イメージテンプレート(イメージ＆タイトル強調型、イメージ強調型、SNS型、サムネイル型)を利用して送信できる機能が追加されました。

### 2023. 09. 12.
#### 機能追加
* [API]詳細照会API追加
    * すべてのメッセージタイプ(SMS/LMS/MMS/Template)に対して、特定のメッセージの詳細情報を照会できるAPIが追加されました。
    * 詳細は[[APIガイド ](./api-guide/#_3)] を参照してください。

### 2023. 08. 17.
#### 機能改善/変更
* [Console]リスト照会画面フィールドを追加
    * **送信結果**タブでメッセージリスト照会時、**代替送信状態**、**代替送信時間**フィールドが追加されました。
* [API]リスト照会APIレスポンスフィールド追加
    * すべてのメッセージタイプ(SMS/LMS/MMS/Template)のリスト照会APIレスポンスに**代替送信ステータス**、**代替送信時間**フィールドが追加されました。
* [API]送信APIエラーレスポンス改善
    * 送信API呼び出し時、リクエストに対する検証を強化しました。

### 2023. 07. 25.
#### 機能改善/変更
* [Console]本人認証手続きの改善
    * 本人認証の否認および再要求時に、ユーザーが組織に登録された事業者登録証を変更できるように改善しました。
    * 本人認証の際、その他書類の添付項目を追加しました。

### 2023. 06. 27.

#### 新規サービスリリース
* RCS BizmessageサービスはRCS Bizmessage送信およびブランド、チャットボット、テンプレート管理機能を提供するサービスです。
* RCS Bizmessageサービスを通じて、ユーザーはメッセージ送信からブランド管理を通じて企業と顧客間の接続のためのブランド情報を提供することができ、さまざまなタイプのメッセージを送信できます。
* 簡単な連携のためのREST APIを提供します。
