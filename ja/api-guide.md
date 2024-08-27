## Notification > RCS Bizmessage > API v1.0 Guide

## v1.0 API紹介
### [APIドメイン]
```
https://rcs-bizmessage.api.nhncloudservice.com
```

## メッセージ送信

### SMSタイプ送信
[Method, URI]

```
POST /rcs/v1.0/messages/sms
Content-Type: application/json
```

[Header]
```
"X-TC-APP-KEY" : String,
"X-SECRET-KEY": String
```

[Request Body]

| フィールド | タイプ | 必須かどうか | 説明 | 備考 |
| --- | --- | --- | --- | --- |
| sendDateTime | String | X | 送信希望時間 | 形式: YYYY-MM-DD hh:mm:ss <br>以前の時間不可、デフォルト値:現在時間 |
| brandId | String | O | ブランドID |  |
| chatbotId | String | O | 発信番号 |  |
| recipientNumber | String | O | 受信番号 | 空白不可、入力値例: 01012345678, +821012345678 |
| isAd | Boolean | X | 広告送信か | デフォルト値: false |
| unsubscribeNumber | String | X | 受信拒否番号 | 広告がTrueの場合、必須 |
| body | String | O | 本文 | 最大100文字 |
| buttons | List | X | ボタン | 最大1個 |
| button.buttonType | String | X | ボタンタイプ | <ul><li>チャットルームを開く(COMPOSE)</li><li>コピーする(CLIPBOARD)</li><li>電話をかける(DIALER)</li><li>マップを表示する(MAP_SHOW)</li><li>マップ検索する(MAP_QUERY)</li><li>現在位置を共有する(MAP_SHARE)</li><li>URL接続する(URL)</li><li>予定を登録する(CALENDAR)</li><ul> |
| button.buttonJson | String | X | ボタンJson | ボタンタイプに合ったフォーマット確認 |
| isFallback | Boolean | X | 代替送信の有無 | デフォルト値: false |

* リクエスト例
```json
{
	"brandId":"sampleBrandId",
	"chatbotId":"15881234",
	"recipientNumber":"01012345678",
	"isAd": false,
	"body":"testBody",
	"buttons" : [
		{
			"buttonType" : "URL",
			"buttonJson" : "{ \"action\": { \"urlAction\":{\"openUrl\":{\"url\":\"http://www.test.com\"} },\"displayText\":\"Webサイトに移動\"}}"
		}
	]
}
```

[Response Body]

[成功例]
```json
{
    "header": {
        "resultCode": 0,
        "resultMessage": "success",
        "isSuccessful": true
    },
    "messageId" : "20220914184500weq0u9pNu30"
}
```
[失敗例]
```json
{
    "header": {
        "resultCode": -3000,
        "resultMessage": "Invalid button parameter",
        "isSuccessful": false
    }
}
```
	

| フィールド | タイプ | 説明 |
| --- | --- | --- |
| header.resultCode | Integer | 結果コード |
| header.resultMessage | String | 結果メッセージ |
| header.isSuccessful | Boolean | 成否 |


### LMSタイプ送信
[Method, URI]

```
POST /rcs/v1.0/messages/lms
Content-Type: application/json
```

[Header]
```
"X-TC-APP-KEY" : String,
"X-SECRET-KEY": String
```

[Request Body]

| フィールド | タイプ | 必須かどうか | 説明 | 備考 |
| --- | --- | --- | --- | --- |
| sendDateTime | String | X | 送信希望時間 | 形式: YYYY-MM-DD hh:mm:ss <br>以前の時間不可、デフォルト値:現在時間 |
| brandId | String | O | ブランドID |  |
| chatbotId | String | O | 発信番号 |  |
| recipientNumber | String | O | 受信番号 | 空白不可、入力値例: 01012345678, +821012345678 |
| isAd | Boolean | X | 広告送信か | デフォルト値: false |
| unsubscribeNumber | String | X | 受信拒否番号 | 広告がTrueの場合、必須 |
| title | String | X | タイトル | 最大30文字 |
| body | String | O | 本文 | 最大1300文字 |
| buttons | List | X | ボタン | 最大3個 |
| button.buttonType | String | X | ボタンタイプ | <ul><li>チャットルームを開く(COMPOSE)</li><li>コピーする(CLIPBOARD)</li><li>電話をかける(DIALER)</li><li>マップを表示する(MAP_SHOW)</li><li>マップ検索する(MAP_QUERY)</li><li>現在位置を共有する(MAP_SHARE)</li><li>URL接続する(URL)</li><li>予定を登録する(CALENDAR)</li><ul> |
| button.buttonJson | String | X | ボタンJson | ボタンタイプに合ったフォーマット確認 |
| isFallback | Boolean | X | 代替送信の有無 | デフォルト値: false |

* リクエスト例
```json
{
	"brandId":"sampleBrandId",
	"chatbotId":"15881234",
	"recipientNumber":"01012341234",
	"isAd": false,
    "title":"testTitle",
	"body":"testBody",
	"buttons" : [
		{
			"buttonType" : "URL",
			"buttonJson" : "{ \"action\": { \"urlAction\":{\"openUrl\":{\"url\":\"http://www.test.com\"} },\"displayText\":\"Webサイトに移動\"}}"
		}
	]
}
```

[Response Body]

[成功例]
```json
{
    "header": {
        "resultCode": 0,
        "resultMessage": "success",
        "isSuccessful": true
    },
    "messageId" : "20220914184500weq0u9pNu30"
}
```
[失敗例]
```json
{
    "header": {
        "resultCode": -3000,
        "resultMessage": "Invalid button parameter",
        "isSuccessful": false
    }
}
```
	

| フィールド | タイプ | 説明 |
| --- | --- | --- |
| header.resultCode | Integer | 結果コード |
| header.resultMessage | String | 結果メッセージ |
| header.isSuccessful | Boolean | 成否 |

### MMSタイプ送信
[Method, URI]
f
```
POST /rcs/v1.0/messages/mms
Content-Type: application/json
```

[Header]
```
"X-TC-APP-KEY" : String,
"X-SECRET-KEY": String
```

[Request Body]

| フィールド | タイプ | 必須かどうか | 説明 | 備考 |
| --- | --- | --- | --- | --- |
| sendDateTime | String | X | 送信希望時間 | 形式: YYYY-MM-DD hh:mm:ss <br>以前の時間不可、デフォルト値:現在時間 |
| brandId | String | O | ブランドID |  |
| chatbotId | String | O | 発信番号 |  |
| recipientNumber | String | O | 受信番号 | 空白不可、入力値例: 01012345678, +821012345678 |
| isAd | Boolean | X | 広告送信か | デフォルト値: false |
| unsubscribeNumber | String | X | 受信拒否番号 | 広告がTrueの場合、必須 |
| mmsType | String | O | MMSタイプ | <ul><li>横型(HORIZONTAL)</li><li>縦型(VERTICAL)</li><li>スライド中型(CAROUSEL_MEDIUM)</li><li>スライド小型(CAROUSEL_SMALL)</li></ul> |
| cards | List | O | カード | HORIZONTAL(1)、VERTICAL(1)、CAROUSEL_MEDIUM(3 ～ 6)、CAROUSEL_SMALL(3 ～ 6) |
| card.title | String | X | タイトル | 最大30文字 |
| card.description | String | X | 内容 | スライドX(最大:1300)、 CAROUSEL_MEDIUM(最大:60)、 CAROUSEL_SMALL(MAX:30) |
| card.media | String | O | 添付ファイルID | 添付ファイルアップロード時に発行されるID値 |
| card.buttons | List | X | ボタン | 最大2個 |
| card.button.buttonType | String | X | ボタンタイプ | <ul><li>チャットルームを開く(COMPOSE)</li><li>コピーする(CLIPBOARD)</li><li>電話をかける(DIALER)</li><li>マップを表示する(MAP_SHOW)</li><li>マップ検索する(MAP_QUERY)</li><li>現在位置を共有する(MAP_SHARE)</li><li>URL接続する(URL)</li><li>予定を登録する(CALENDAR)</li><ul> |
| card.button.buttonJson | String | X | ボタンJson | ボタンタイプに合ったフォーマット確認 |
| isFallback | Boolean | X | 代替送信の有無 | デフォルト値: false |

* リクエスト例
```json
{
	"brandId":"sampleBrandId",
	"chatbotId":"15881234",
	"recipientNumber":"01012341234",
	"isAd": false,
    "mmsType": "HORIZONTAL",
	"cards": [
        {
          "title":"testTitle",
          "description":"testBody",
          "media":"fileId",
          "buttons" : [
            {
              "buttonType" : "URL",
              "buttonJson" : "{ \"action\": { \"urlAction\":{\"openUrl\":{\"url\":\"http://www.test.com\"} },\"displayText\":\"Webサイトに移動\"}}"
            },
            {
              "buttonType" : "URL",
              "buttonJson" : "{ \"action\": { \"urlAction\":{\"openUrl\":{\"url\":\"http://www.test.com\"} },\"displayText\":\"Webサイトに移動\"}}"
            }
          ]
        }
    ]
}
```


[Response Body]

[成功例]
```json
{
    "header": {
        "resultCode": 0,
        "resultMessage": "success",
        "isSuccessful": true
    },
    "messageId" : "20220914184500weq0u9pNu30"
}
```
[失敗例]
```json
{
    "header": {
        "resultCode": -3000,
        "resultMessage": "Invalid button parameter",
        "isSuccessful": false
    }
}
```
	

| フィールド | タイプ | 説明 |
| --- | --- | --- |
| header.resultCode | Integer | 結果コード |
| header.resultMessage | String | 結果メッセージ |
| header.isSuccessful | Boolean | 成否 |

### Templateタイプ送信
[Method, URI]

```
POST /rcs/v1.0/messages/template
Content-Type: application/json
```

[Header]
```
"X-TC-APP-KEY" : String,
"X-SECRET-KEY": String
```

[Request Body]

| フィールド | タイプ | 必須かどうか | 説明 | 備考 |
| --- | --- | --- | --- | --- |
| sendDateTime | String | X | 送信希望時間 | 形式: YYYY-MM-DD hh:mm:ss <br>以前の時間不可、デフォルト値:現在時間 |
| brandId | String | O | ブランドID |  |
| chatbotId | String | O | 発信番号 | 空白不可、入力値例: 01012345678, +821012345678 |
| messagebaseId  | String | O | テンプレートID | |
| recipientNumber | String | O | 受信番号 |  |
| body | String | X | 本文 | 最大90文字、 Freeテンプレートの場合にのみ該当 |
| templateParameter | Map | X | 日本語識別子key, value |
| isFallback | Boolean | X | 代替送信の有無 |  |

* リクエスト例
```json
{
	"sendDateTime" : "2022-11-21 00:00:00",
	"brandId":"sampleBrandId",
	"chatbotId":"15881234",
    "messagebaseId":"UBR.AGNtIngI0u-GG000F",
    "templateParameter" : {
        "key1":"value1"
    },
	"recipientNumber":"01012341234"
}
```

[Response Body]

[成功例]
```json
{
    "header": {
        "resultCode": 0,
        "resultMessage": "success",
        "isSuccessful": true
    },
    "messageId" : "20220914184500weq0u9pNu30"
}
```
[失敗例]
```json
{
    "header": {
        "resultCode": -3000,
        "resultMessage": "Invalid button parameter",
        "isSuccessful": false
    }
}
```
	

| フィールド | タイプ | 説明 |
| --- | --- | --- |
| header.resultCode | Integer | 結果コード |
| header.resultMessage | String | 結果メッセージ |
| header.isSuccessful | Boolean | 成否 |

## メッセージ照会

### SMSメッセージ照会API
[Method, URI]
```
GET /rcs/v1.0/messages/sms
Content-Type: application/json
```

[Header]
```
"X-TC-APP-KEY" : String
"X-SECRET-KEY" : String
```

[Query Parameter]

| フィールド | タイプ | 必須かどうか | 説明 | 備考 |
| --- | --- | --- | --- | --- |
| messageId | String | O(選択的必須) | メッセージID | リクエスト時に発行されるメッセージID |
| brandId | String | X | ブランドID |  |
| chatbotId | String | X | 発信番号 |  |
| messageStatus | String | X | メッセージ状態 | <ul><li>準備(READY)</li><li>送信中(IN_PROGRESS)</li><li>受信(DELIVERED)</li><li>失敗(FAILED)</li><li>キャンセル(CANCELED)</li></ul> |
| startSendDateTime | String | O(選択的必須) | リクエスト時間from | 形式: YYYY-MM-DD hh:mm:ss <br>from～to最大31日 |
| endSendDateTime | String | O(選択的必須) | リクエスト時間to | 形式: YYYY-MM-DD hh:mm:ss <br>from～to最大31日 |
| startReceiveDateTime | String | O(選択的必須) | 受信時間from | 形式: YYYY-MM-DD hh:mm:ss <br>from～to最大31日 |
| endReceiveDateTime | String | O(選択的必須) | 受信時間to | 形式: YYYY-MM-DD hh:mm:ss <br>from～to最大31日 |
| limit | Integer | X | Limit | デフォルト値: 15 max: 1000 |
| offset | Integer | X | offset | デフォルト値: 0 |

* messageIdまたはstartSendDateTime / endSendDateTimeまたはstartReceiveDateTime / endReceiveDateTimeの中から1つを必ず入力する必要があります。
* リクエスト時間と受信時間の日付を同時に検索することはできません。


[成功例]
```json
{
    "header": {
        "resultCode": 0,
        "resultMessage": "success",
        "isSuccessful": true
    },
    "data": [
        {
            "messageId": "20230503100623Uc3C0JDd0u0",
            "recipientSequence": 0,
            "messageType": "SMS",
            "brandId": "sampleBrandId",
            "chatbotId": "15881234",
            "recipientNumber": "01012341234",
            "messagebaseId": "SS000000",
            "title": "",
            "body": "testBody",
            "messageStatus": "DELIVERED",
            "sendDateTime": "2023-05-03T10:06:23.000+09:00",
            "receiveDateTime" : "2023-05-03T10:07:23.000+09:00",
            "fallbackStatus" : "NONE",
            "fallbackDateTime" : ""
        }
    ],
    "pagination": {
        "offset": 0,
        "limit": 15,
        "total": 1
    }
}
```


[失敗例]
```json
{
    "header": {
        "resultCode": 500,
        "resultMessage": "Internal Error. It is not handled. Please report this. 'https://toast.com/support/inquiry.",
        "isSuccessful": false
    }
}
```

| フィールド | タイプ | 説明 |
| --- | --- | --- |
| header.resultCode | Integer | 結果コード |
| header.resultMessage | String | 結果メッセージ |
| header.isSuccessful | Boolean | 成否 |
| data | - | メッセージ情報 |
| data.messageId | String | メッセージID |
| data.recipientSeq | Integer | 受信者順序 | 
| data.messageType | String | メッセージタイプ |
| data.brandId | String | ブランドID|
| data.chatbotId | String | チャットボットID | 
| data.recipientNumber | String | 受信者番号 |
| data.messagebaseId | String | メッセージタイプ |
| data.title | String | タイトル |
| data.body | String | 本文 |
| data.messageStatus | String | メッセージ状態<br><ul><li>準備(READY)</li><li>送信中(IN_PROGRESS)</li><li>受信(DELIVERED)</li><li>失敗(FAILED)</li><li>キャンセル(CANCELED)</li></ul> |
| data.sendDateTime | dateTime | リクエスト時間(YYYY-MM-DDThh:mm:ss.SSS±hh:mm) | 
| data.receiveDateTime | dateTime | 受信時間(YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |
| data.fallbackStatus | String | 代替送信ステータス<br><ul><li>代替送信対象ではない(NONE)</li><li>代替送信中(IN_PROGRESS)</li><li>代替送信完了(COMPLETE)</li><li>代替送信失敗(SEND_FAILED)</li></ul>  |
| data.fallbackDateTime | dateTime | 代替送信リクエスト時間(YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |

### LMSメッセージ照会API
[Method, URI]

```
GET /rcs/v1.0/messages/lms
Content-Type: application/json
```

[Header]
```
"X-TC-APP-KEY" : String
"X-SECRET-KEY" : String
```

[Query Parameter]

| フィールド | タイプ | 必須かどうか | 説明 | 備考 |
| --- | --- | --- | --- | --- |
| messageId | String | O(選択的必須) | メッセージID | リクエスト時に発行されるメッセージID |
| brandId | String | X | ブランドID |  |
| chatbotId | String | X | 発信番号 |  |
| messageStatus | String | X | メッセージ状態 | <ul><li>準備(READY)</li><li>送信中(IN_PROGRESS)</li><li>受信(DELIVERED)</li><li>失敗(FAILED)</li><li>キャンセル(CANCELED)</li></ul> |
| startSendDateTime | String | O(選択的必須) | リクエスト時間from | 形式: YYYY-MM-DD hh:mm:ss <br>from～to最大31日 |
| endSendDateTime | String | O(選択的必須) | リクエスト時間to | 形式: YYYY-MM-DD hh:mm:ss <br>from～to最大31日 |
| startReceiveDateTime | String | O(選択的必須) | 受信時間from | 形式: YYYY-MM-DD hh:mm:ss <br>from～to最大31日 |
| endReceiveDateTime | String | O(選択的必須) | 受信時間to | 形式: YYYY-MM-DD hh:mm:ss <br>from～to最大31日 |
| limit | Integer | X | Limit | デフォルト値: 15 max: 1000 |
| offset | Integer | X | offset | デフォルト値: 0 |

* messageIdまたはstartSendDateTime/endSendDateTimeまたはstartReceiveDateTime/endReceiveDateTimeの中から1つを必ず入力する必要があります。
* リクエスト時間と受信時間の日付を同時に検索することはできません。

[成功例]
```json
{
    "header": {
        "resultCode": 0,
        "resultMessage": "success",
        "isSuccessful": true
    },
    "data": [
        {
            "messageId": "20230503100623Uc3C0JDd0u0",
            "recipientSequence": 0,
            "messageType": "LMS",
            "brandId": "sampleBrandId",
            "chatbotId": "15881234",
            "recipientNumber": "01012341234",
            "messagebaseId": "SS000000",
            "title": "",
            "body": "testBody",
            "messageStatus": "DELIVERED",
            "sendDateTime": "2023-05-03T10:06:23.000+09:00",
            "receiveDateTime" : "2023-05-03T10:07:23.000+09:00",
            "fallbackStatus" : "NONE",
            "fallbackDateTime" : ""
        }
    ],
    "pagination": {
        "offset": 0,
        "limit": 15,
        "total": 1
    }
}
```


[失敗例]
```json
{
    "header": {
        "resultCode": 500,
        "resultMessage": "Internal Error. It is not handled. Please report this. 'https://toast.com/support/inquiry.",
        "isSuccessful": false
    }
}
```

| フィールド | タイプ | 説明 |
| --- | --- | --- |
| header.resultCode | Integer | 結果コード |
| header.resultMessage | String | 結果メッセージ |
| header.isSuccessful | Boolean | 成否 |
| data | - | メッセージ情報 |
| data.messageId | String | メッセージID |
| data.recipientSeq | Integer | 受信者順序 | 
| data.messageType | String | メッセージタイプ | 
| data.brandId | String | ブランドID|
| data.chatbotId | String | チャットボットID | 
| data.recipientNumber | String | 受信者番号 |
| data.messagebaseId | String | メッセージタイプ |
| data.title | String | タイトル |
| data.body | String | 本文 |
| data.messageStatus | String | メッセージ状態<br><ul><li>準備(READY)</li><li>送信中(IN_PROGRESS)</li><li>受信(DELIVERED)</li><li>失敗(FAILED)</li><li>キャンセル(CANCELED)</li></ul> |
| data.sendDateTime | dateTime | リクエスト時間(YYYY-MM-DDThh:mm:ss.SSS±hh:mm) | 
| data.receiveDateTime | dateTime | 受信時間(YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |
| data.fallbackStatus | String | 代替送信ステータス<br><ul><li>代替送信対象ではない(NONE)</li><li>代替送信中(IN_PROGRESS)</li><li>代替送信完了(COMPLETE)</li><li>代替送信失敗(SEND_FAILED)</li></ul>  |
| data.fallbackDateTime | dateTime | 代替送信リクエスト時間(YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |

### MMSメッセージ照会API
[Method, URI]

```
GET /rcs/v1.0/messages/mms
Content-Type: application/json
```

[Header]
```
"X-TC-APP-KEY" : String
"X-SECRET-KEY" : String
```

[Query Parameter]

| フィールド | タイプ | 必須かどうか | 説明 | 備考 |
| --- | --- | --- | --- | --- |
| messageId | String | O(選択的必須) | メッセージID | リクエスト時に発行されるメッセージID |
| brandId | String | X | ブランドID |  |
| chatbotId | String | X | 発信番号 |  |
| messageStatus | String | X | メッセージ状態 | <ul><li>準備(READY)</li><li>送信中(IN_PROGRESS)</li><li>受信(DELIVERED)</li><li>失敗(FAILED)</li><li>キャンセル(CANCELED)</li></ul> |
| startSendDateTime | String | O(選択的必須) | リクエスト時間from | 形式: YYYY-MM-DD hh:mm:ss <br>from～to最大31日 |
| endSendDateTime | String | O(選択的必須) | リクエスト時間to | 形式: YYYY-MM-DD hh:mm:ss <br>from～to最大31日 |
| startReceiveDateTime | String | O(選択的必須) | 受信時間from | 形式: YYYY-MM-DD hh:mm:ss <br>from～to最大31日 |
| endReceiveDateTime | String | O(選択的必須) | 受信時間to | 形式: YYYY-MM-DD hh:mm:ss <br>from～to最大31日 |
| limit | Integer | X | Limit | デフォルト値: 15 max: 1000 |
| offset | Integer | X | offset | デフォルト値: 0 |

* messageIdまたはstartSendDateTime/endSendDateTimeまたはstartReceiveDateTime/endReceiveDateTimeの中から1つを必ず入力する必要があります。
* リクエスト時間と受信時間の日付を同時に検索することはできません。

[成功例]
```json
{
    "header": {
        "resultCode": 0,
        "resultMessage": "success",
        "isSuccessful": true
    },
    "data": [
        {
            "messageId": "20230503100623Uc3C0JDd0u0",
            "recipientSequence": 0,
            "messageType": "MMS",
            "brandId": "sampleBrandId",
            "chatbotId": "15881234",
            "recipientNumber": "01012341234",
            "messagebaseId": "SS000000",
            "title": "",
            "body": "testBody",
            "messageStatus": "DELIVERED",
            "sendDateTime": "2023-05-03T10:06:23.000+09:00",
            "receiveDateTime" : "2023-05-03T10:07:23.000+09:00",
            "fallbackStatus" : "NONE",
            "fallbackDateTime" : ""
        }
    ],
    "pagination": {
        "offset": 0,
        "limit": 15,
        "total": 1
    }
}
```


[失敗例]
```json
{
    "header": {
        "resultCode": 500,
        "resultMessage": "Internal Error. It is not handled. Please report this. 'https://toast.com/support/inquiry.",
        "isSuccessful": false
    }
}
```

| フィールド | タイプ | 説明 |
| --- | --- | --- |
| header.resultCode | Integer | 結果コード |
| header.resultMessage | String | 結果メッセージ |
| header.isSuccessful | Boolean | 成否 |
| data | - | メッセージ情報 |
| data.messageId | String | メッセージID |
| data.recipientSeq | Integer | 受信者順序 | 
| data.messageType | String | メッセージタイプ |
| data.brandId | String | ブランドID|
| data.chatbotId | String | チャットボットID | 
| data.recipientNumber | String | 受信者番号 |
| data.messagebaseId | String | メッセージタイプ |
| data.title | String | タイトル(最初のカード) |
| data.body | String | 本文(最初のカード) |
| data.messageStatus | String | メッセージ状態<br><ul><li>準備(READY)</li><li>送信中(IN_PROGRESS)</li><li>受信(DELIVERED)</li><li>失敗(FAILED)</li><li>キャンセル(CANCELED)</li></ul> |
| data.sendDateTime | dateTime | リクエスト時間(YYYY-MM-DDThh:mm:ss.SSS±hh:mm) | 
| data.receiveDateTime | dateTime | 受信時間(YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |
| data.fallbackStatus | String | 代替送信ステータス<br><ul><li>代替送信対象ではない(NONE)</li><li>代替送信中(IN_PROGRESS)</li><li>代替送信完了(COMPLETE)</li><li>代替送信失敗(SEND_FAILED)</li></ul>  |
| data.fallbackDateTime | dateTime | 代替送信リクエスト時間(YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |

### TEMPLATEメッセージ照会API
[Method, URI]

```
GET /rcs/v1.0/messages/template
Content-Type: application/json
```

[Header]
```
"X-TC-APP-KEY" : String
"X-SECRET-KEY" : String
```

[Query Parameter]

| フィールド | タイプ | 必須かどうか | 説明 | 備考 |
| --- | --- | --- | --- | --- |
| messageId | String | O(選択的必須) | メッセージID | リクエスト時に発行されるメッセージID |
| brandId | String | X | ブランドID |  |
| chatbotId | String | X | 発信番号 |  |
| messageStatus | String | X | メッセージ状態 | <ul><li>準備(READY)</li><li>送信中(IN_PROGRESS)</li><li>受信(DELIVERED)</li><li>失敗(FAILED)</li><li>キャンセル(CANCELED)</li></ul> |
| startSendDateTime | String | O(選択的必須) | リクエスト時間from | 形式: YYYY-MM-DD hh:mm:ss <br>from～to最大31日 |
| endSendDateTime | String | O(選択的必須) | リクエスト時間to | 形式: YYYY-MM-DD hh:mm:ss <br>from～to最大31日 |
| startReceiveDateTime | String | O(選択的必須) | 受信時間from | 形式: YYYY-MM-DD hh:mm:ss <br>from～to最大31日 |
| endReceiveDateTime | String | O(選択的必須) | 受信時間to | 形式: YYYY-MM-DD hh:mm:ss <br>from～to最大31日 |
| limit | Integer | X | Limit | デフォルト値: 15 max: 1000 |
| offset | Integer | X | offset | デフォルト値: 0 |

* messageIdまたはstartSendDateTime/endSendDateTimeまたはstartReceiveDateTime/endReceiveDateTimeの中から1つを必ず入力する必要があります。
* リクエスト時間と受信時間の日付を同時に検索することはできません。

[成功例]
```json
{
    "header": {
        "resultCode": 0,
        "resultMessage": "success",
        "isSuccessful": true
    },
    "data": [
        {
            "messageId": "20230503100623Uc3C0JDd0u0",
            "recipientSequence": 0,
            "messageType": "TEMPLATE",
            "brandId": "sampleBrandId",
            "chatbotId": "15881234",
            "recipientNumber": "01012341234",
            "messagebaseId": "SS000000",
            "title": "",
            "body": "testBody",
            "messageStatus": "DELIVERED",
            "sendDateTime": "2023-05-03T10:06:23.000+09:00",
            "receiveDateTime" : "2023-05-03T10:07:23.000+09:00",
            "fallbackStatus" : "NONE",
            "fallbackDateTime" : ""
        }
    ],
    "pagination": {
        "offset": 0,
        "limit": 15,
        "total": 1
    }
}
```


[失敗例]
```json
{
    "header": {
        "resultCode": 500,
        "resultMessage": "Internal Error. It is not handled. Please report this. 'https://toast.com/support/inquiry.",
        "isSuccessful": false
    }
}
```

| フィールド | タイプ | 説明 |
| --- | --- | --- |
| header.resultCode | Integer | 結果コード |
| header.resultMessage | String | 結果メッセージ |
| header.isSuccessful | Boolean | 成否 |
| data | - | メッセージ情報 |
| data.messageId | String | メッセージID |
| data.recipientSeq | Integer | 受信者順序 | 
| data.messageType | String | メッセージタイプ |
| data.brandId | String | ブランドID|
| data.chatbotId | String | チャットボットID | 
| data.recipientNumber | String | 受信者番号 |
| data.messagebaseId | String | テンプレートID |
| data.title | String | タイトル |
| data.body | String | 本文 |
| data.messageStatus | String | メッセージ状態<br><ul><li>準備(READY)</li><li>送信中(IN_PROGRESS)</li><li>受信(DELIVERED)</li><li>失敗(FAILED)</li><li>キャンセル(CANCELED)</li></ul> |
| data.sendDateTime | dateTime | リクエスト時間(YYYY-MM-DDThh:mm:ss.SSS±hh:mm) | 
| data.receiveDateTime | dateTime | 受信時間(YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |
| data.fallbackStatus | String | 代替送信ステータス<br><ul><li>代替送信対象ではない(NONE)</li><li>代替送信中(IN_PROGRESS)</li><li>代替送信完了(COMPLETE)</li><li>代替送信失敗(SEND_FAILED)</li></ul>  |
| data.fallbackDateTime | dateTime | 代替送信リクエスト時間(YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |

## メッセージ詳細照会
### SMSメッセージ詳細照会API
[Method, URI]

```
GET /rcs/v1.0/messages/sms/{messageId}
Content-Type: application/json
```

[Header]
```
"X-TC-APP-KEY" : String
"X-SECRET-KEY" : String
```
[Path Parameter]

| フィールド | タイプ | 必須かどうか | 説明 | 備考 |
| --- | --- | --- | --- | --- |
| messageId | String | O | メッセージID | リクエスト時に発行されるメッセージID |

[成功例]
```json
{
    "header": {
        "resultCode": 0,
        "resultMessage": "success",
        "isSuccessful": true
    },
    "messageRecipient": {
        "messageId": "20230503100623Uc3C0JDd0u0",
        "sendDateTime": "2023-05-03T10:06:23.000+09:00",
        "messageType": "SMS",
        "brandId": "sampleBrandId",
        "chatbotId": "15881234",
        "recipientNumber": "01012341234",
        "messagebaseId": "SS000000",
        "isAd": false,
        "unsubscribeNumber": "",
        "body": "testBody",
        "buttons": [
            {
                "buttonType": "URL",
                "buttonJson": "{ \"action\": { \"urlAction\":{\"openUrl\":{\"url\":\"http://www.test.com\"} },\"displayText\":\"Webサイトに移動\"}}",
            }
        ],
        "messageStatus": "DELIVERED",
        "resultCode": 2000,
        "telecom": "kt",
        "receiveDateTime": "2023-05-03T10:06:23.000+09:00",
        "resultDateTime": "2023-05-03T10:06:23.000+09:00",
        "isFallback": false,
        "fallbackStatus": "NONE",
        "fallbackRequestId": "",
        "fallbackResultCode": "",
        "fallbackDateTime": ""
    }
}
```


[失敗例]
```json
{
    "header": {
        "resultCode": 500,
        "resultMessage": "Internal Error. It is not handled. Please report this. 'https://toast.com/support/inquiry.",
        "isSuccessful": false
    }
}
```

| フィールド | タイプ | 説明 |
| --- | --- | --- |
| header.resultCode | Integer | 結果コード |
| header.resultMessage | String | 結果メッセージ |
| header.isSuccessful | Boolean | 成否 |
| message | - | メッセージ詳細情報 |
| message.messageId | String | メッセージID |
| message.messageType | String | メッセージタイプ |
| message.brandId | String | ブランドID|
| message.chatbotId | String | チャットボットID | 
| message.recipientNumber | String | 受信者番号 |
| message.messagebaseId | String | テンプレートID |
| message.body | String | 本文 |
| message.buttons | - | ボタン情報 |
| message.buttons.buttonType | String | ボタンタイプ<br><ul><li>チャットルームを開く(COMPOSE)</li><li>コピーする(CLIPBOARD)</li><li>電話をかける(DIALER)</li><li>マップを表示する(MAP_SHOW)</li><li>マップ検索する(MAP_QUERY)</li><li>現在位置を共有する(MAP_SHARE)</li><li>URL接続する(URL)</li><li>予定を登録する(CALENDAR)</li><ul> |
| message.buttons.buttonJson | String | ボタンJson |
| message.messageStatus | String | メッセージ状態<br><ul><li>準備(READY)</li><li>送信中(IN_PROGRESS)</li><li>受信(DELIVERED)</li><li>失敗(FAILED)</li><li>キャンセル(CANCELED)</li></ul> |
| message.resultCode | String | 結果コード |
| message.telecom | String | サービスプロバイダー(skt, kt, lgu) |
| message.sendDateTime | dateTime | リクエスト時間(YYYY-MM-DDThh:mm:ss.SSS±hh:mm) | 
| message.receiveDateTime | dateTime | 受信時間(YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |
| message.isFallback | Boolean | 代替送信かどうか |
| message.fallbackStatus | String | 代替送信ステータス<br><ul><li>代替送信対象ではない(NONE)</li><li>代替送信中(IN_PROGRESS)</li><li>代替送信完了(COMPLETE)</li><li>代替送信失敗(SEND_FAILED)</li></ul>  |
| message.fallbackRequestId | String | 代替送信SMSリクエストID |
| message.fallbackResultCode | String | 代替送信結果コード |
| message.fallbackDateTime | dateTime | 代替送信リクエスト時間(YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |

### LMSメッセージ詳細照会API
[Method, URI]

```
GET /rcs/v1.0/messages/lms/{messageId}
Content-Type: application/json
```

[Header]
```
"X-TC-APP-KEY" : String
"X-SECRET-KEY" : String
```
[Path Parameter]

| フィールド | タイプ | 必須かどうか | 説明 | 備考 |
| --- | --- | --- | --- | --- |
| messageId | String | O | メッセージID | リクエスト時に発行されるメッセージID |

[成功例]
```json
{
    "header": {
        "resultCode": 0,
        "resultMessage": "success",
        "isSuccessful": true
    },
    "messageRecipient": {
        "messageId": "20230503100623Uc3C0JDd0u0",
        "sendDateTime": "2023-05-03T10:06:23.000+09:00",
        "messageType": "LMS",
        "brandId": "sampleBrandId",
        "chatbotId": "15881234",
        "recipientNumber": "01012341234",
        "messagebaseId": "SL000000",
        "isAd": false,
        "unsubscribeNumber": "",
        "title": "testTitle",
        "body": "testBody",
        "buttons": [
            {
                "buttonType": "URL",
                "buttonJson": "{ \"action\": { \"urlAction\":{\"openUrl\":{\"url\":\"http://www.test.com\"} },\"displayText\":\"Webサイトに移動\"}}",
            }
        ],
        "messageStatus": "DELIVERED",
        "resultCode": 2000,
        "telecom": "kt",
        "receiveDateTime": "2023-05-03T10:06:23.000+09:00",
        "resultDateTime": "2023-05-03T10:06:23.000+09:00",
        "isFallback": false,
        "fallbackStatus": "NONE",
        "fallbackRequestId": "",
        "fallbackResultCode": "",
        "fallbackDateTime": ""
    }
}
```


[失敗例]
```json
{
    "header": {
        "resultCode": 500,
        "resultMessage": "Internal Error. It is not handled. Please report this. 'https://toast.com/support/inquiry.",
        "isSuccessful": false
    }
}
```

| フィールド | タイプ | 説明 |
| --- | --- | --- |
| header.resultCode | Integer | 結果コード |
| header.resultMessage | String | 結果メッセージ |
| header.isSuccessful | Boolean | 成否 |
| message | - | メッセージ詳細情報 |
| message.messageId | String | メッセージID |
| message.messageType | String | メッセージタイプ |
| message.brandId | String | ブランドID|
| message.chatbotId | String | チャットボットID | 
| message.recipientNumber | String | 受信者番号 |
| message.messagebaseId | String | テンプレートID |
| message.title | String | タイトル |
| message.body | String | 本文 |
| message.buttons | - | ボタン情報 |
| message.buttons.buttonType | String | ボタンタイプ<br><ul><li>チャットルームを開く(COMPOSE)</li><li>コピーする(CLIPBOARD)</li><li>電話をかける(DIALER)</li><li>マップを表示する(MAP_SHOW)</li><li>マップ検索する(MAP_QUERY)</li><li>現在位置を共有する(MAP_SHARE)</li><li>URL接続する(URL)</li><li>予定を登録する(CALENDAR)</li><ul> |
| message.buttons.buttonJson | String | ボタンJson |
| message.messageStatus | String | メッセージ状態<br><ul><li>準備(READY)</li><li>送信中(IN_PROGRESS)</li><li>受信(DELIVERED)</li><li>失敗(FAILED)</li><li>キャンセル(CANCELED)</li></ul> |
| message.resultCode | String | 結果コード |
| message.telecom | String | サービスプロバイダー(skt, kt, lgu) |
| message.sendDateTime | dateTime | リクエスト時間(YYYY-MM-DDThh:mm:ss.SSS±hh:mm) | 
| message.receiveDateTime | dateTime | 受信時間(YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |
| message.isFallback | Boolean | 代替送信かどうか |
| message.fallbackStatus | String | 代替送信ステータス<br><ul><li>代替送信対象ではない(NONE)</li><li>代替送信中(IN_PROGRESS)</li><li>代替送信完了(COMPLETE)</li><li>代替送信失敗(SEND_FAILED)</li></ul>  |
| message.fallbackRequestId | String | 代替送信SMSリクエストID |
| message.fallbackResultCode | String | 代替送信結果コード |
| message.fallbackDateTime | dateTime | 代替送信リクエスト時間(YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |

### MMSメッセージ詳細照会API
[Method, URI]

```
GET /rcs/v1.0/messages/mms/{messageId}
Content-Type: application/json
```

[Header]
```
"X-TC-APP-KEY" : String
"X-SECRET-KEY" : String
```
[Path Parameter]

| フィールド | タイプ | 必須かどうか | 説明 | 備考 |
| --- | --- | --- | --- | --- |
| messageId | String | O | メッセージID | リクエスト時に発行されるメッセージID |

[成功例]
```json
{
    "header": {
        "resultCode": 0,
        "resultMessage": "success",
        "isSuccessful": true
    },
    "messageRecipient": {
        "messageId": "20230503100623Uc3C0JDd0u0",
        "sendDateTime": "2023-05-03T10:06:23.000+09:00",
        "messageType": "MMS",
        "brandId": "sampleBrandId",
        "chatbotId": "15881234",
        "recipientNumber": "01012341234",
        "messagebaseId": "SMwThM00",
        "isAd": false,
        "unsubscribeNumber": "",
        "mmsType": "HORIZONTAL",
        "cards": [
            {
                "title": "testTitle",
                "description": "testBody",
                "media": "file.xx.xx.xxxxxxxxxxxxx",
                "buttons": [
                    {
                        "buttonType": "URL",
                        "buttonJson": "{ \"action\": { \"urlAction\":{\"openUrl\":{\"url\":\"http://www.test.com\"} },\"displayText\":\"Webサイトに移動\"}}",
                    }
                ],
            }
        ],
        "messageStatus": "DELIVERED",
        "resultCode": 2000,
        "telecom": "kt",
        "receiveDateTime": "2023-05-03T10:06:23.000+09:00",
        "resultDateTime": "2023-05-03T10:06:23.000+09:00",
        "isFallback": false,
        "fallbackStatus": "NONE",
        "fallbackRequestId": "",
        "fallbackResultCode": "",
        "fallbackDateTime": ""
    }
}
```


[失敗例]
```json
{
    "header": {
        "resultCode": 500,
        "resultMessage": "Internal Error. It is not handled. Please report this. 'https://toast.com/support/inquiry.",
        "isSuccessful": false
    }
}
```

| フィールド | タイプ | 説明 |
| --- | --- | --- |
| header.resultCode | Integer | 結果コード |
| header.resultMessage | String | 結果メッセージ |
| header.isSuccessful | Boolean | 成否 |
| message | - | メッセージ詳細情報 |
| message.messageId | String | メッセージID |
| message.messageType | String | メッセージタイプ |
| message.brandId | String | ブランドID|
| message.chatbotId | String | チャットボットID | 
| message.recipientNumber | String | 受信者番号 |
| message.messagebaseId | String | テンプレートID |
| message.isAd | Boolean | 広告かどうか |
| message.unsubscribeNumber | String | 受信拒否番号 |
| message.mmsType | String | MMSタイプ<br><ul><li>横型(HORIZONTAL)</li><li>縦型(VERTICAL)</li><li>スライド中型(CAROUSEL_MEDIUM)</li><li>スライド小型(CAROUSEL_SMALL)</li></ul> |
| message.cards | - | カード |
| message.cards.title | String | タイトル |
| message.cards.description | String | 内容 |
| message.cards.media | String | 添付ファイルID |
| message.cards.buttons | - | ボタン |
| message.cards.button.buttonType | String | ボタンタイプ<br>チャットルームを開く(COMPOSE)、コピーする(CLIPBOARD)、電話をかける(DIALER)、マップを表示する(MAP_SHOW)、マップを検索する(MAP_QUERY)、現在 
| message.card.button.buttonJson | String | X | ボタンJson | ボタンタイプに合ったフォーマット確認 |
| message.messageStatus | String | メッセージ状態<br><ul><li>準備(READY)</li><li>送信中(IN_PROGRESS)</li><li>受信(DELIVERED)</li><li>失敗(FAILED)</li><li>キャンセル(CANCELED)</li></ul> |
| message.resultCode | String | 結果コード |
| message.telecom | String | サービスプロバイダー(skt, kt, lgu) |
| message.sendDateTime | dateTime | リクエスト時間(YYYY-MM-DDThh:mm:ss.SSS±hh:mm) | 
| message.receiveDateTime | dateTime | 受信時間(YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |
| message.isFallback | Boolean | 代替送信かどうか |
| message.fallbackStatus | String | 代替送信ステータス<br><ul><li>代替送信対象ではない(NONE)</li><li>代替送信中(IN_PROGRESS)</li><li>代替送信完了(COMPLETE)</li><li>代替送信失敗(SEND_FAILED)</li></ul>  |
| message.fallbackRequestId | String | 代替送信SMSリクエストID |
| message.fallbackResultCode | String | 代替送信結果コード |
| message.fallbackDateTime | dateTime | 代替送信リクエスト時間(YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |

### TEMPLATEメッセージ詳細照会API
[Method, URI]

```
GET /rcs/v1.0/messages/template/{messageId}
Content-Type: application/json
```

[Header]
```
"X-TC-APP-KEY" : String
"X-SECRET-KEY" : String
```
[Path Parameter]

| フィールド | タイプ | 必須かどうか | 説明 | 備考 |
| --- | --- | --- | --- | --- |
| messageId | String | O | メッセージID | リクエスト時に発行されるメッセージID |

[成功例]
```json
{
    "header": {
        "resultCode": 0,
        "resultMessage": "success",
        "isSuccessful": true
    },
    "messageRecipient": {
        "messageId": "20230503100623Uc3C0JDd0u0",
        "sendDateTime": "2023-05-03T10:06:23.000+09:00",
        "messageType": "TEMPLATE",
        "brandId": "sampleBrandId",
        "chatbotId": "15881234",
        "recipientNumber": "01012341234",
        "messagebaseId": "UBR.xxxxxxxxxxxxx",
        "isAd": false,
        "unsubscribeNumber": "",
        "body": "testBody",
        "buttons": [
            {
                "buttonType": "URL",
                "buttonJson": "{ \"action\": { \"urlAction\":{\"openUrl\":{\"url\":\"http://www.test.com\"} },\"displayText\":\"Webサイトに移動\"}}",
            }
        ],
        "messageStatus": "DELIVERED",
        "resultCode": 2000,
        "telecom": "kt",
        "receiveDateTime": "2023-05-03T10:06:23.000+09:00",
        "resultDateTime": "2023-05-03T10:06:23.000+09:00",
        "isFallback": false,
        "fallbackStatus": "NONE",
        "fallbackRequestId": "",
        "fallbackResultCode": "",
        "fallbackDateTime": ""
    }
}
```


[失敗例]
```json
{
    "header": {
        "resultCode": 500,
        "resultMessage": "Internal Error. It is not handled. Please report this. 'https://toast.com/support/inquiry.",
        "isSuccessful": false
    }
}
```

| フィールド | タイプ | 説明 |
| --- | --- | --- |
| header.resultCode | Integer | 結果コード |
| header.resultMessage | String | 結果メッセージ |
| header.isSuccessful | Boolean | 成否 |
| message | - | メッセージ詳細情報 |
| message.messageId | String | メッセージID |
| message.messageType | String | メッセージタイプ |
| message.brandId | String | ブランドID|
| message.chatbotId | String | チャットボットID | 
| message.recipientNumber | String | 受信者番号 |
| message.messagebaseId | String | テンプレートID |
| message.body | String | 本文 |
| message.buttons | - | ボタン情報 |
| message.buttons.buttonType | String | ボタンタイプ<br><ul><li>チャットルームを開く(COMPOSE)</li><li>コピーする(CLIPBOARD)</li><li>電話をかける(DIALER)</li><li>マップを表示する(MAP_SHOW)</li><li>マップ検索する(MAP_QUERY)</li><li>現在位置を共有する(MAP_SHARE)</li><li>URL接続する(URL)</li><li>予定を登録する(CALENDAR)</li><ul> |
| message.buttons.buttonJson | String | ボタンJson |
| message.messageStatus | String | メッセージ状態<br><ul><li>準備(READY)</li><li>送信中(IN_PROGRESS)</li><li>受信(DELIVERED)</li><li>失敗(FAILED)</li><li>キャンセル(CANCELED)</li></ul> |
| message.resultCode | String | 結果コード |
| message.telecom | String | サービスプロバイダー(skt, kt, lgu) |
| message.sendDateTime | dateTime | リクエスト時間(YYYY-MM-DDThh:mm:ss.SSS±hh:mm) | 
| message.receiveDateTime | dateTime | 受信時間(YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |
| message.isFallback | Boolean | 代替送信かどうか |
| message.fallbackStatus | String | 代替送信ステータス<br><ul><li>代替送信対象ではない(NONE)</li><li>代替送信中(IN_PROGRESS)</li><li>代替送信完了(COMPLETE)</li><li>代替送信失敗(SEND_FAILED)</li></ul>  |
| message.fallbackRequestId | String | 代替送信SMSリクエストID |
| message.fallbackResultCode | String | 代替送信結果コード |
| message.fallbackDateTime | dateTime | 代替送信リクエスト時間(YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |


## リソースAPI

### 添付ファイルアップロードAPI
[Method, URI]

```
POST /rcs/v1.0/media
Content-Type: multipart/form-data
```

[Header]
```
"X-TC-APP-KEY" : String
"X-SECRET-KEY" : String
```

* 添付ファイルの有効期間は7日です。
* ファイル容量制限は1MBです。
* 画像の添付は'jpg'、'jpeg'、'png'、'gif'、'bmp'拡張子のみサポートします。

[Request Body]

| フィールド | タイプ | 必須かどうか | 説明 | 備考 |
| --- | --- | --- | --- | --- |
| uploadFile | MultipartFile | O | 添付ファイル |  |
| uploadUser | String | X | アップロードユーザー名 |  |

[Response Body]

[成功例]
```json
{
    "header": {
        "resultCode": 0,
        "resultMessage": "success",
        "isSuccessful": true
    }
}
```

[失敗例]
```json
{
    "header": {
        "resultCode": 500,
        "resultMessage": "Internal Error. It is not handled. Please report this. 'https://toast.com/support/inquiry.",
        "isSuccessful": false
    }
}
```

| フィールド | タイプ | 説明 |
| --- | --- | --- |
| header.resultCode | Integer | 結果コード |
| header.resultMessage | String | 結果メッセージ |
| header.isSuccessful | Boolean | 成否 |


## ボタンタイプ

### チャットルームを開く

```json
{
    "action": {
        "composeAction": {
            "composeTextMessage": {
                "phoneNumber": "01000000000",
                "text": "転送するメッセージ"
            }
        },
        "displayText": "チャットルームを開く"
    }
}
```


| フィールド | 説明 | 備考 |
| --- | --- | --- |
| action.displayText | ボタン名 | 最大17文字 |
| action.composeAction.composeTextMessage.phoneNumber | メッセージ受信番号 | |
| action.composeAction.composeTextMessage.text | 転送するメッセージ | 最大100文字 |

### コピーする

```json
{
    "action": {
        "clipboardAction": {
            "copyToClipboard": {
                "text": "コピーするメッセージ"
            }
        },
        "displayText": "コピーする"
    }
}
```

| フィールド | 説明 | 備考 |
| --- | --- | --- |
| action.displayText | ボタン名 | 最大17文字 |
| action.clipboardAction.copyToClipboard.text | クリップボードにコピーする内容 | 最大200文字 |

### 電話をかける

```json
{
    "action": {
        "dialerAction": {
            "dialPhoneNumber": {
                "phoneNumber": "16446114"
            }
        },
        "displayText": "電話をかける"
    }
}
```

| フィールド | 説明 | 備考 |
| --- | --- | --- |
| action.displayText | ボタン名 | 最大17文字 |
| action.dialerAction.dialPhoneNumber.phoneNumber | 電話番号 | |

### マップを表示する

```json
{
    "action": {
        "mapAction": {
            "showLocation": {
                "location": {
                    "latitude": "37.400977",
                    "longitude": "127.104239",
                    "label": "NHN"
                },
                "fallbackUrl": "https://www.google.co.kr/maps"
            }
        },
        "displayText": "マップを表示する"
    }
}
```

| フィールド | 説明 | 備考 |
| --- | --- | --- |
| action.displayText | ボタン名 | 最大17文字 |
| action.mapAction.showLocation.location.latitude | 緯度 | |
| action.mapAction.showLocation.location.longitude | 経度 | |
| action.mapAction.showLocation.location.label | 位置名 | 最大200文字 |
| action.mapAction.showLocation.fallbackUrl | アクション失敗時に呼び出すリンク | |

### マップを検索する

```json
{
    "action": {
        "mapAction": {
            "showLocation": {
                "location": {
                    "query": "NHN"
                },
                "fallbackUrl": "https://www.google.co.kr/maps"
            }
        },
        "displayText": "マップを検索する"
    }
}
```

| フィールド | 説明 | 備考 |
| --- | --- | --- |
| action.displayText | ボタン名 | 最大17文字 |
| action.mapAction.showLocation.location.query | 検索キーワード | 最大200文字 |
| action.mapAction.showLocation.fallbackUrl | 該当位置を照会するサイト | |

### 現在位置を共有する

```json
{
    "action": {
        "mapAction": {
            "requestLocationPush": {
                "currentLocation": true
            }
        },
        "displayText": "現在位置を共有する"
    }
}
```

| フィールド | 説明 | 備考 |
| --- | --- | --- |
| action.displayText | ボタン名 | 最大17文字 |
| action.mapAction.requestLocationPush.currentLocation | 現在位置共有の有無 | ボタンの機能を正常に使用するために当該値はtrueに指定する必要があります |

### URL接続する

```json
{
    "action": {
        "urlAction": {
            "openUrl": {
                "url": "http://www.test.com"
            }
        },
        "displayText": "ページに移動"
    }
}
```

| フィールド | 説明 | 備考 |
| --- | --- | --- |
| action.displayText | ボタン名 | 最大17文字 |
| action.urlAction.openUrl.url | 接続するURLアドレス | |

### 予定を登録する

```json
{
    "action": {
        "calendarAction": {
            "createCalendarEvent": {
                "startTime": "2020-03-31T15:00:00.000Z",
                "endTime": "2020-03-31T15:00:00.000Z",
                "title": "予定登録",
                "description": "記念日登録です。"
            }
        },
        "displayText": "予定を登録する"
    }
}
```

| フィールド | 説明 | 備考 |
| --- | --- | --- |
| action.displayText | ボタン名 | 最大17文字 |
| action.calendarAction.createCalendarEvent.startTime | 開始日 | 形式: yyyy-MM-ddTHH:mm:ss+9:00Z (韓国基準)<br>形式に合っていない場合は1970年1月1日08時59分に設定 |
| action.calendarAction.createCalendarEvent.endTime | 終了日 | 形式: yyyy-MM-ddTHH:mm:ss+9:00Z (韓国基準)<br>形式に合っていない場合は1970年1月1日08時59分に設定 |
| action.calendarAction.createCalendarEvent.title | タイトル | 最大17文字 |
| action.calendarAction.createCalendarEvent.description | 内容 | 最大500文字 |
