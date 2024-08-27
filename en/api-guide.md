## Notification > RCS Bizmessage > API v1.0 Guide

## Overview of v1.0 API
### [API Domain]
```
https://rcs-bizmessage.api.nhncloudservice.com
```

## Send Messages

### Send SMS Type
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

| Field | Type | Required | Description | Note |
| --- | --- | --- | --- | --- |
| sendDateTime | String | X | Desired Sending Time | Format: YYYY-MM-DD hh:mm:ss <br>Time before the current time unavailable, default: current time |
| brandId | String | O | Brand ID |  |
| chatbotId | String | O | Sender number |  |
| recipientNumber | String | O | Recipient number | Space not allowed, example input: 01012345678, +821012345678 |
| isAd | Boolean | X | Ad sending or not | Default: false |
| unsubscribeNumber | String | X | Deny-to-receive number | Required If ad is true |
| body | String | O | Body | Max. 100 characters, |
| buttons | List | X | Button | Max 100 |
| button.buttonType | String | X | Button type | <ul><li>Open a chat room (COMPOSE)</li><li>Copy (CLIPBOARD)</li><li>Make a call</li><li>Show map (MAP_SHOW)</li><li>Query a map (MAP_QUERY)</li><li>Share your current location (MAP_SHARE)</li><li>Connect URL (URL)</li><li>Register a schedule (CALENDAR)</li><ul> |
| button.buttonJson | String | X | Button Json | Check the format for the button type |
| isFallback | Boolean | X | Alternative sending or not | Default: false |

* Request example
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
"buttonJson" : "{ \"action\": { \"urlAction\":{\"openUrl\":{\"url\":\"http://www.test.com\"} },\"displayText\":\"Go to the homepage\"}}"
}
]
}
```

[Response Body]

[Success example]
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
[Failure example]
```json
{
    "header": {
        "resultCode": -3000,
        "resultMessage": "Invalid button parameter",
        "isSuccessful": false
    }
}
```
	

| Field | Type | Description |
| --- | --- | --- |
| header.resultCode | Integer | Result code |
| header.resultMessage | String | Result message |
| header.isSuccessful | Boolean | Successful or not |


### Send LMS Type
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

| Field | Type | Required | Description | Note |
| --- | --- | --- | --- | --- |
| sendDateTime | String | X | Desired Sending Time | Format: YYYY-MM-DD hh:mm:ss <br>Time before the current time unavailable, default: current time |
| brandId | String | O | Brand ID |  |
| chatbotId | String | O | Sender number |  |
| recipientNumber | String | O | Recipient number | Space not allowed, example input: 01012345678, +821012345678 |
| isAd | Boolean | X | Ad sending or not | Default: false |
| unsubscribeNumber | String | X | Deny-to-receive number | Required If ad is true |
| title | String | X | Title | Max. 30 characters |
| body | String | O | Body | Max. 1300 characters |
| buttons | List | X | Button | Max 3 ea |
| button.buttonType | String | X | Button type | <ul><li>Open a chat room (COMPOSE)</li><li>Copy (CLIPBOARD)</li><li>Make a call</li><li>Show map (MAP_SHOW)</li><li>Query a map (MAP_QUERY)</li><li>Share your current location (MAP_SHARE)</li><li>Connect URL (URL)</li><li>Register a schedule (CALENDAR)</li><ul> |
| button.buttonJson | String | X | Button Json | Check the format for the button type |
| isFallback | Boolean | X | Alternative sending or not | Default: false |

* Request example
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
			"buttonJson" : "{ \"action\": { \"urlAction\":{\"openUrl\":{\"url\":\"http://www.test.com\"} },\"displayText\":\"Go to homepage\"}}"
		}
	]
}
```

[Response Body]

[Success example]
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
[Failure example]
```json
{
    "header": {
        "resultCode": -3000,
        "resultMessage": "Invalid button parameter",
        "isSuccessful": false
    }
}
```
	

| Field | Type | Description |
| --- | --- | --- |
| header.resultCode | Integer | Result code |
| header.resultMessage | String | Result message |
| header.isSuccessful | Boolean | Successful or not |

### Send LMS Type
[Method, URI]

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

| Field | Type | Required | Description | Note |
| --- | --- | --- | --- | --- |
| sendDateTime | String | X | Desired Sending Time | Format: YYYY-MM-DD hh:mm:ss <br>Time before the current time unavailable, default: current time |
| brandId | String | O | Brand ID |  |
| chatbotId | String | O | Sender number |  |
| recipientNumber | String | O | Recipient number | Space not allowed, example input: 01012345678, +821012345678 |
| isAd | Boolean | X | Ad sending or not | Default: false |
| unsubscribeNumber | String | X | Deny-to-receive number | Required when ad is true |
| mmsType | String | O | MMS type | <ul><li>Horizontal</li><li>Vertical</li><li>Slide Medium (CAROUSEL_MEDIUM)</li><li>Slide Small (CAROUSEL_SMALL)</li></ul> |
| cards | List | O | Cards | HORIZONTAL(1), VERTICAL(1), CAROUSEL_MEDIUM(3 ~ 6), CAROUSEL_SMALL(3 ~ 6) |
| card.title | String | X |  Title | Max. 30 characters |
| card.description | String | X | Content | Slide X(Max:1300), CAROUSEL_MEDIUM(Max:60), CAROUSEL_SMALL(MAX:30) |
| card.media | String | O | Attachment ID | ID value issued when uploading an attached file |
| card.buttons | List | X | Button | Max 2 ea |
| card.button.buttonType | String | X | Button type | <ul><li>Open a chat room (COMPOSE)</li><li>Copy (CLIPBOARD)</li><li>Make a call</li><li>Show map (MAP_SHOW)</li><li>Query a map (MAP_QUERY)</li><li>Share your current location (MAP_SHARE)</li><li>Connect URL (URL)</li><li>Register a schedule (CALENDAR)</li><ul> |
| card.button.buttonJson | String | X | Button Json | Check the format for the button type |
| isFallback | Boolean | X | Alternative sending or not | Default: false |

* Request example
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
              "buttonJson" : "{ \"action\": { \"urlAction\":{\"openUrl\":{\"url\":\"http://www.test.com\"} },\"displayText\":\"Go to homepage\"}}"
            },
            {
              "buttonType" : "URL",
              "buttonJson" : "{ \"action\": { \"urlAction\":{\"openUrl\":{\"url\":\"http://www.test.com\"} },\"displayText\":\"Go to homepage\"}}"
            }
          ]
        }
    ]
}
```


[Response Body]

[Success example]
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
[Failure example]
```json
{
    "header": {
        "resultCode": -3000,
        "resultMessage": "Invalid button parameter",
        "isSuccessful": false
    }
}
```
	

| Field | Type | Description |
| --- | --- | --- |
| header.resultCode | Integer | Result code |
| header.resultMessage | String | Result message |
| header.isSuccessful | Boolean | Successful or not |

### Send Template Type
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

| Field | Type | Required | Description | Note |
| --- | --- | --- | --- | --- |
| sendDateTime | String | X | Desired Sending Time | Format: YYYY-MM-DD hh:mm:ss <br>Time before the current time unavailable, default: current time |
| brandId | String | O | Brand ID |  |
| chatbotId | String | O | Sender number |  |
| messagebaseId  | String | O | Template ID | |
| recipientNumber | String | O | Recipient number | Space not allowed, example input: 01012345678, +821012345678  |
| isAd | Boolean | X | Send ads or not | Default: false, ads can only be sent for image templates |
| unsubscribeNumber | String | X | Unsubscribe number | Required when isAd is true |
| body | String | X | Body | Up to 90 characters, only for free templates |
| templateParameter | Map | X | Substituent key, value |
| isFallback | Boolean | X | Alternative sending or not |  |

* Request example
```json
{
	"sendDateTime" : "2022-11-21 00:00:00",
	"brandId":"sampleBrandId",
	"chatbotId":"15881234",
    "messagebaseId":"UBR.AGNtIngI0u-GG000F",
    "templateParameter" : {
        "key1":"value1"
    },
    "isAd": true,
    "unsubscribeNumber": "0801234567",
	    "recipientNumber":"01012341234"
}
```

[Response Body]

[Success example]
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
[Failure example]
```json
{
    "header": {
        "resultCode": -3000,
        "resultMessage": "Invalid button parameter",
        "isSuccessful": false
    }
}
```
	

| Field | Type | Description |
| --- | --- | --- |
| header.resultCode | Integer | Result code |
| header.resultMessage | String | Result message |
| header.isSuccessful | Boolean | Successful or not |

## Query Messages

### Query SMS Message API
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

| Field | Type | Required | Description | Note |
| --- | --- | --- | --- | --- |
| messageId | String | O (optional required) | Message ID | Message ID issued upon request |
| brandId | String | X | Brand ID |  |
| chatbotId | String | X | Sender number |  |
| messageStatus | String | X | Message status | <ul><li>Ready</li><li>In progress</li><li>Delivered</li><li>Failed</li><li>Cancelled</li></ul> |
| startSendDateTime | String | O (optional required) | Request time from | Format: YYYY-MM-DD hh:mm:ss <br>from~to up to 31 days |
| endSendDateTime | String | O (optional required) | Request time to | Format: YYYY-MM-DD hh:mm:ss <br>from~to up to 31 days |
| startReceiveDateTime | String | O (optional required) | Receive time from | Format: YYYY-MM-DD hh:mm:ss <br>from~to up to 31 days |
| endReceiveDateTime | String | O (optional required) | Receive time to | Format: YYYY-MM-DD hh:mm:ss <br>from~to up to 31 days |
| limit | Integer | X | Limit | Default: 15 max: 1000 |
| offset | Integer | X | offset | Default: 6 |

* MessageId or one of startSendDateTime / endSendDateTime or startReceiveDateTime / endReceiveDateTime is mandatory.
* It is not possible to search request time and receive time date at the same time.


[Success example]
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


[Failure example]
```json
{
    "header": {
        "resultCode": 500,
        "resultMessage": "Internal Error. It is not handled. Please report this. 'https://toast.com/support/inquiry.",
        "isSuccessful": false
    }
}
```

| Field | Type | Description |
| --- | --- | --- |
| header.resultCode | Integer | Result code |
| header.resultMessage | String | Result message |
| header.isSuccessful | Boolean | Successful or not |
| data | - | Message information |
| data.messageId | String | Message ID |
| data.recipientSeq | Integer | Recipient sequence | 
| data.messageType | String | Message type |
| data.brandId | String | Brand ID|
| data.chatbotId | String | Chatbot ID | 
| data.recipientNumber | String | Recipient number |
| data.messagebaseId | String | Message type |
| data.title | String | Title |
| data.body | String | Body |
| data.messageStatus | String | Message status<br><ul><li>Ready</li><li>In progress</li><li>Delivered</li><li>Failed</li><li>Cancelled</li></ul> |
| data.sendDateTime | dateTime | Request time (YYYY-MM-DDThh:mm:ss.SSS±hh:mm) | 
| data.receiveDateTime | dateTime | Receive Time (YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |
| data.fallbackStatus | String | Alternative Delivery Status<br><ul><li>Not eligible for alternative delivery (NONE)</li><li>Alternative delivery in progress</li><li>Alternative delivery completed</li><li>Alternative delivery failed</li></ul>  |
| data.fallbackDateTime | dateTime | Alternative Delivery Request Time (YYYY-MM-DDThh:mm:ss.SSS±HH) |

### Query LMS Message API
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

| Field | Type | Required | Description | Note |
| --- | --- | --- | --- | --- |
| messageId | String | O (optional required) | Message ID | Message ID issued upon request |
| brandId | String | X | Brand ID |  |
| chatbotId | String | X | Sender number |  |
| messageStatus | String | X | Message status | <ul><li>Ready</li><li>In progress</li><li>Delivered</li><li>Failed</li><li>Cancelled</li></ul> |
| startSendDateTime | String | O (optional required) | Request time from | Format: YYYY-MM-DD hh:mm:ss <br>from~to up to 31 days |
| endSendDateTime | String | O (optional required) | Request time to | Format: YYYY-MM-DD hh:mm:ss <br>from~to up to 31 days |
| startReceiveDateTime | String | O (optional required) | Receive time from | Format: YYYY-MM-DD hh:mm:ss <br>from~to up to 31 days |
| endReceiveDateTime | String | O (optional required) | Receive time to | Format: YYYY-MM-DD hh:mm:ss <br>from~to up to 31 days |
| limit | Integer | X | Limit | Default: 15 max: 1000 |
| offset | Integer | X | offset | Default: 6 |

* MessageId or one of startSendDateTime/endSendDateTime or startReceiveDateTime/endReceiveDateTime is mandatory.
* It is not possible to search request time and receive time date at the same time.

[Success example]
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


[Failure example]
```json
{
    "header": {
        "resultCode": 500,
        "resultMessage": "Internal Error. It is not handled. Please report this. 'https://toast.com/support/inquiry.",
        "isSuccessful": false
    }
}
```

| Field | Type | Description |
| --- | --- | --- |
| header.resultCode | Integer | Result code |
| header.resultMessage | String | Result message |
| header.isSuccessful | Boolean | Successful or not |
| data | - | Message information |
| data.messageId | String | Message ID |
| data.recipientSeq | Integer | Recipient sequence | 
| data.messageType | String | Message type | 
| data.brandId | String | Brand ID|
| data.chatbotId | String | Chatbot ID | 
| data.recipientNumber | String | Recipient number |
| data.messagebaseId | String | Message type |
| data.title | String | Title |
| data.body | String | Body |
| data.messageStatus | String | Message status<br><ul><li>Ready</li><li>In progress</li><li>Delivered</li><li>Failed</li><li>Cancelled</li></ul> |
| data.sendDateTime | dateTime | Request time (YYYY-MM-DDThh:mm:ss.SSS±hh:mm) | 
| data.receiveDateTime | dateTime | Receive Time (YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |
| data.fallbackStatus | String | Alternative Delivery Status<br><ul><li>Not eligible for alternative delivery (NONE)</li><li>Alternative delivery in progress</li><li>Alternative delivery completed</li><li>Alternative delivery failed</li></ul>  |
| data.fallbackDateTime | dateTime | Alternative Delivery Request Time (YYYY-MM-DDThh:mm:ss.SSS±HH) |

### Query MMS Message API
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

| Field | Type | Required | Description | Note |
| --- | --- | --- | --- | --- |
| messageId | String | O (optional required) | Message ID | Message ID issued upon request |
| brandId | String | X | Brand ID |  |
| chatbotId | String | X | Sender number |  |
| messageStatus | String | X | Message status | <ul><li>Ready</li><li>In progress</li><li>Delivered</li><li>Failed</li><li>Cancelled</li></ul> |
| startSendDateTime | String | O (optional required) | Request time from | Format: YYYY-MM-DD hh:mm:ss <br>from~to up to 31 days |
| endSendDateTime | String | O (optional required) | Request time to | Format: YYYY-MM-DD hh:mm:ss <br>from~to up to 31 days |
| startReceiveDateTime | String | O (optional required) | Receive time from | Format: YYYY-MM-DD hh:mm:ss <br>from~to up to 31 days |
| endReceiveDateTime | String | O (optional required) | Receive time to | Format: YYYY-MM-DD hh:mm:ss <br>from~to up to 31 days |
| limit | Integer | X | Limit | Default: 15 max: 1000 |
| offset | Integer | X | offset | Default: 6 |

* MessageId or one of startSendDateTime/endSendDateTime or startReceiveDateTime/endReceiveDateTime is mandatory.
* It is not possible to search request time and receive time date at the same time.

[Success example]
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


[Failure example]
```json
{
    "header": {
        "resultCode": 500,
        "resultMessage": "Internal Error. It is not handled. Please report this. 'https://toast.com/support/inquiry.",
        "isSuccessful": false
    }
}
```

| Field | Type | Description |
| --- | --- | --- |
| header.resultCode | Integer | Result code |
| header.resultMessage | String | Result message |
| header.isSuccessful | Boolean | Successful or not |
| data | - | Message information |
| data.messageId | String | Message ID |
| data.recipientSeq | Integer | Recipient sequence | 
| data.messageType | String | Message type |
| data.brandId | String | Brand ID|
| data.chatbotId | String | Chatbot ID | 
| data.recipientNumber | String | Recipient number |
| data.messagebaseId | String | Message type |
| data.title | String | Title (first card) |
| data.body | String | Body (first card) |
| data.messageStatus | String | Message status<br><ul><li>Ready</li><li>In progress</li><li>Delivered</li><li>Failed</li><li>Cancelled</li></ul> |
| data.sendDateTime | dateTime | Request time (YYYY-MM-DDThh:mm:ss.SSS±hh:mm) | 
| data.receiveDateTime | dateTime | Receive Time (YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |
| data.fallbackStatus | String | Alternative Delivery Status<br><ul><li>Not eligible for alternative delivery (NONE)</li><li>Alternative delivery in progress</li><li>Alternative delivery completed</li><li>Alternative delivery failed</li></ul>  |
| data.fallbackDateTime | dateTime | Alternative Delivery Request Time (YYYY-MM-DDThh:mm:ss.SSS±HH) |

### Query TEMPLATE Message API
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

| Field | Type | Required | Description | Note |
| --- | --- | --- | --- | --- |
| messageId | String | O (optional required) | Message ID | Message ID issued upon request |
| brandId | String | X | Brand ID |  |
| chatbotId | String | X | Sender number |  |
| messageStatus | String | X | Message status | <ul><li>Ready</li><li>In progress</li><li>Delivered</li><li>Failed</li><li>Cancelled</li></ul> |
| startSendDateTime | String | O (optional required) | Request time from | Format: YYYY-MM-DD hh:mm:ss <br>from~to up to 31 days |
| endSendDateTime | String | O (optional required) | Request time to | Format: YYYY-MM-DD hh:mm:ss <br>from~to up to 31 days |
| startReceiveDateTime | String | O (optional required) | Receive time from | Format: YYYY-MM-DD hh:mm:ss <br>from~to up to 31 days |
| endReceiveDateTime | String | O (optional required) | Receive time to | Format: YYYY-MM-DD hh:mm:ss <br>from~to up to 31 days |
| limit | Integer | X | Limit | Default: 15 max: 1000 |
| offset | Integer | X | offset | Default: 6 |

* MessageId or one of startSendDateTime/endSendDateTime or startReceiveDateTime/endReceiveDateTime is mandatory.
* It is not possible to search request time and receive time date at the same time.

[Success example]
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


[Failure example]
```json
{
    "header": {
        "resultCode": 500,
        "resultMessage": "Internal Error. It is not handled. Please report this. 'https://toast.com/support/inquiry.",
        "isSuccessful": false
    }
}
```

| Field | Type | Description |
| --- | --- | --- |
| header.resultCode | Integer | Result code |
| header.resultMessage | String | Result message |
| header.isSuccessful | Boolean | Successful or not |
| data | - | Message information |
| data.messageId | String | Message ID |
| data.recipientSeq | Integer | Recipient sequence | 
| data.messageType | String | Message type |
| data.brandId | String | Brand ID|
| data.chatbotId | String | Chatbot ID | 
| data.recipientNumber | String | Recipient number |
| data.messagebaseId | String | Template ID |
| data.title | String | Title |
| data.body | String | Body |
| data.messageStatus | String | Message status<br><ul><li>Ready</li><li>In progress</li><li>Delivered</li><li>Failed</li><li>Cancelled</li></ul> |
| data.sendDateTime | dateTime | Request time (YYYY-MM-DDThh:mm:ss.SSS±hh:mm) | 
| data.receiveDateTime | dateTime | Receive Time (YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |
| data.fallbackStatus | String | Alternative Delivery Status<br><ul><li>Not eligible for alternative delivery (NONE)</li><li>Alternative delivery in progress</li><li>Alternative delivery completed</li><li>Alternative delivery failed</li></ul>  |
| data.fallbackDateTime | dateTime | Alternative Delivery Request Time (YYYY-MM-DDThh:mm:ss.SSS±HH) |

## Query Message Details
### Query SMS Message Details API
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

| Field | Type | Required | Description | Note |
| --- | --- | --- | --- | --- |
| messageId | String | O | Message ID | Message ID issued upon request |

[Success example]
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
                "buttonJson": "{ \"action\": { \"urlAction\":{\"openUrl\":{\"url\":\"http://www.test.com\"} },\"displayText\":\"Go to the homepage\"}}",
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


[Failure example]
```json
{
    "header": {
        "resultCode": 500,
        "resultMessage": "Internal Error. It is not handled. Please report this. 'https://toast.com/support/inquiry.",
        "isSuccessful": false
    }
}
```

| Field | Type | Description |
| --- | --- | --- |
| header.resultCode | Integer | Result code |
| header.resultMessage | String | Result message |
| header.isSuccessful | Boolean | Successful or not |
| message | - | Message Details |
| message.messageId | String | Message ID |
| message.messageType | String | Message type |
| message.brandId | String | Brand ID|
| message.chatbotId | String | Chatbot ID | 
| message.recipientNumber | String | Recipient number |
| message.messagebaseId | String | Template ID |
| message.body | String | Body |
| message.buttons | - | Button information |
| message.buttons.buttonType | String | Button type<br><ul><li>Open a chat room (COMPOSE)</li><li>Copy (CLIPBOARD)</li><li>Make a call</li><li>Show map (MAP_SHOW)</li><li>Query a map (MAP_QUERY)</li><li>Share your current location (MAP_SHARE)</li><li>Connect URL (URL)</li><li>Register a schedule (CALENDAR)</li><ul> |
| message.buttons.buttonJson | String | Button Json |
| message.messageStatus | String | Message status<br><ul><li>Ready</li><li>In progress</li><li>Delivered</li><li>Failed</li><li>Cancelled</li></ul> |
| message.resultCode | String | Result code |
| message.telecom | String | Mobile carrier (skt, kt, lgu) |
| message.sendDateTime | dateTime | Request time (YYYY-MM-DDThh:mm:ss.SSS±hh:mm) | 
| message.receiveDateTime | dateTime | Receive Time (YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |
| message.resultDateTime | dateTime | Result time (YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |
| message.isFallback | Boolean | Alternative sending or not |
| message.fallbackStatus | String | Alternative Delivery Status<br><ul><li>Not eligible for alternative delivery (NONE)</li><li>Alternative delivery in progress</li><li>Alternative delivery completed</li><li>Alternative delivery failed</li></ul>  |
| message.fallbackRequestId | String | Resending SMS request ID |
| message.fallbackResultCode | String | Alternative Delivery Result Code |
| message.fallbackDateTime | dateTime | Alternative Delivery Request Time (YYYY-MM-DDThh:mm:ss.SSS±HH) |

### Query LMS Message Details API
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

| Field | Type | Required | Description | Note |
| --- | --- | --- | --- | --- |
| messageId | String | O | Message ID | Message ID issued upon request |

[Success example]
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
        "body": "testBody",
        "buttons": [
            {
                "buttonType": "URL",
                "buttonJson": "{ \"action\": { \"urlAction\":{\"openUrl\":{\"url\":\"http://www.test.com\"} },\"displayText\":\"Go to the homepage\"}}",
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


[Failure example]
```json
{
    "header": {
        "resultCode": 500,
        "resultMessage": "Internal Error. It is not handled. Please report this. 'https://toast.com/support/inquiry.",
        "isSuccessful": false
    }
}
```

| Field | Type | Description |
| --- | --- | --- |
| header.resultCode | Integer | Result code |
| header.resultMessage | String | Result message |
| header.isSuccessful | Boolean | Successful or not |
| message | - | Message Details |
| message.messageId | String | Message ID |
| message.messageType | String | Message type |
| message.brandId | String | Brand ID|
| message.chatbotId | String | Chatbot ID | 
| message.recipientNumber | String | Recipient number |
| message.messagebaseId | String | Template ID |
| message.title | String | Title |
| message.body | String | Body |
| message.buttons | - | Button information |
| message.buttons.buttonType | String | Button type<br><ul><li>Open a chat room (COMPOSE)</li><li>Copy (CLIPBOARD)</li><li>Make a call</li><li>Show map (MAP_SHOW)</li><li>Query a map (MAP_QUERY)</li><li>Share your current location (MAP_SHARE)</li><li>Connect URL (URL)</li><li>Register a schedule (CALENDAR)</li><ul> |
| message.buttons.buttonJson | String | Button Json |
| message.messageStatus | String | Message status<br><ul><li>Ready</li><li>In progress</li><li>Delivered</li><li>Failed</li><li>Cancelled</li></ul> |
| message.resultCode | String | Result code |
| message.telecom | String | Mobile carrier (skt, kt, lgu) |
| message.sendDateTime | dateTime | Request time (YYYY-MM-DDThh:mm:ss.SSS±hh:mm) | 
| message.receiveDateTime | dateTime | Receive Time (YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |
| message.resultDateTime | dateTime | Result time (YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |
| message.isFallback | Boolean | Alternative sending or not |
| message.fallbackStatus | String | Alternative Delivery Status<br><ul><li>Not eligible for alternative delivery (NONE)</li><li>Alternative delivery in progress</li><li>Alternative delivery completed</li><li>Alternative delivery failed</li></ul>  |
| message.fallbackRequestId | String | Resending SMS request ID |
| message.fallbackResultCode | String | Alternative Delivery Result Code |
| message.fallbackDateTime | dateTime | Alternative Delivery Request Time (YYYY-MM-DDThh:mm:ss.SSS±HH) |

### Query MMS Message Details API
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

| Field | Type | Required | Description | Note |
| --- | --- | --- | --- | --- |
| messageId | String | O | Message ID | Message ID issued upon request |

[Success example]
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
                        "buttonJson": "{ \"action\": { \"urlAction\":{\"openUrl\":{\"url\":\"http://www.test.com\"} },\"displayText\":\"Go to homepage\"}}",
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


[Failure example]
```json
{
    "header": {
        "resultCode": 500,
        "resultMessage": "Internal Error. It is not handled. Please report this. 'https://toast.com/support/inquiry.",
        "isSuccessful": false
    }
}
```

| Field | Type | Description |
| --- | --- | --- |
| header.resultCode | Integer | Result code |
| header.resultMessage | String | Result message |
| header.isSuccessful | Boolean | Successful or not |
| message | - | Message Details |
| message.messageId | String | Message ID |
| message.messageType | String | Message type |
| message.brandId | String | Brand ID|
| message.chatbotId | String | Chatbot ID | 
| message.recipientNumber | String | Recipient number |
| message.messagebaseId | String | Template ID |
| message.isAd | Boolean | Ad or not |
| message.unsubscribeNumber | String | Deny-to-receive number |
| message.mmsType | String | MMS type<br><ul><li>Horizontal</li><li>Vertical</li><li>Slide Medium (CAROUSEL_MEDIUM)</li><li>Slide Small (CAROUSEL_SMALL)</li></ul> |
| message.cards | - | Cards |
| message.cards.title | String | Title |
| message.cards.description | String | Content |
| message.cards.media | String | Attachment ID |
| message.cards.buttons | - | Button |
| message.cards.button.buttonType | String | Button type<br>Open chat room (COMPOSE), copy (CLIPBOARD), make a call (DIALER), show map (MAP_SHOW), search map (MAP_QUERY), current 
| message.card.button.buttonJson | String | X | Button Json | Check the format for the button type |
| message.messageStatus | String | Message status<br><ul><li>Ready</li><li>In progress</li><li>Delivered</li><li>Failed</li><li>Cancelled</li></ul> |
| message.resultCode | String | Result code |
| message.telecom | String | Mobile carrier (skt, kt, lgu) |
| message.sendDateTime | dateTime | Request time (YYYY-MM-DDThh:mm:ss.SSS±hh:mm) | 
| message.receiveDateTime | dateTime | Receive Time (YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |
| message.resultDateTime | dateTime | Result time (YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |
| message.isFallback | Boolean | Alternative sending or not |
| message.fallbackStatus | String | Alternative Delivery Status<br><ul><li>Not eligible for alternative delivery (NONE)</li><li>Alternative delivery in progress</li><li>Alternative delivery completed</li><li>Alternative delivery failed</li></ul>  |
| message.fallbackRequestId | String | Resending SMS request ID |
| message.fallbackResultCode | String | Alternative Delivery Result Code |
| message.fallbackDateTime | dateTime | Alternative Delivery Request Time (YYYY-MM-DDThh:mm:ss.SSS±HH) |

### Query TEMPLATE Message Details API
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

| Field | Type | Required | Description | Note |
| --- | --- | --- | --- | --- |
| messageId | String | O | Message ID | Message ID issued upon request |

[Success example]
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
                "buttonJson": "{ \"action\": { \"urlAction\":{\"openUrl\":{\"url\":\"http://www.test.com\"} },\"displayText\":\"Go to the homepage\"}}",
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


[Failure example]
```json
{
    "header": {
        "resultCode": 500,
        "resultMessage": "Internal Error. It is not handled. Please report this. 'https://toast.com/support/inquiry.",
        "isSuccessful": false
    }
}
```

| Field | Type | Description |
| --- | --- | --- |
| header.resultCode | Integer | Result code |
| header.resultMessage | String | Result message |
| header.isSuccessful | Boolean | Successful or not |
| message | - | Message Details |
| message.messageId | String | Message ID |
| message.messageType | String | Message type |
| message.brandId | String | Brand ID|
| message.chatbotId | String | Chatbot ID | 
| message.recipientNumber | String | Recipient number |
| message.messagebaseId | String | Template ID |
| message.body | String | Body |
| message.buttons | - | Button information |
| message.buttons.buttonType | String | Button type<br><ul><li>Open a chat room (COMPOSE)</li><li>Copy (CLIPBOARD)</li><li>Make a call</li><li>Show map (MAP_SHOW)</li><li>Query a map (MAP_QUERY)</li><li>Share your current location (MAP_SHARE)</li><li>Connect URL (URL)</li><li>Register a schedule (CALENDAR)</li><ul> |
| message.buttons.buttonJson | String | Button Json |
| message.messageStatus | String | Message status<br><ul><li>Ready</li><li>In progress</li><li>Delivered</li><li>Failed</li><li>Cancelled</li></ul> |
| message.resultCode | String | Result code |
| message.telecom | String | Mobile carrier (skt, kt, lgu) |
| message.sendDateTime | dateTime | Request time (YYYY-MM-DDThh:mm:ss.SSS±hh:mm) | 
| message.receiveDateTime | dateTime | Receive Time (YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |
| message.resultDateTime | dateTime | Result time (YYYY-MM-DDThh:mm:ss.SSS±hh:mm) |
| message.isFallback | Boolean | Alternative sending or not |
| message.fallbackStatus | String | Alternative Delivery Status<br><ul><li>Not eligible for alternative delivery (NONE)</li><li>Alternative delivery in progress</li><li>Alternative delivery completed</li><li>Alternative delivery failed</li></ul>  |
| message.fallbackRequestId | String | Resending SMS request ID |
| message.fallbackResultCode | String | Alternative Delivery Result Code |
| message.fallbackDateTime | dateTime | Alternative Delivery Request Time (YYYY-MM-DDThh:mm:ss.SSS±HH) |


## Resource API

### Upload Attachment API
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

* Attachments are valid for 7 days.
* The file size limit is 1 MB.
* Image attachment supports only 'jpg', 'jpeg', 'png', 'gif', 'bmp' extensions.

[Request Body]

| Field | Type | Required | Description | Note |
| --- | --- | --- | --- | --- |
| uploadFile | MultipartFile | O | Attachment |  |
| uploadUser | String | X | Upload user name |  |

[Response Body]

[Success example]
```json
{
    "header" : {
        "resultCode" :  0,
        "resultMessage" :  "SUCCESS",
        "isSuccessful" :  true
    }
}
```

[Failure example]
```json
{
    "header": {
        "resultCode": 500,
        "resultMessage": "Internal Error. It is not handled. Please report this. 'https://toast.com/support/inquiry.",
        "isSuccessful": false
    }
}
```

| Field | Type | Description |
| --- | --- | --- |
| header.resultCode | Integer | Result code |
| header.resultMessage | String | Result message |
| header.isSuccessful | Boolean | Successful or not |


## Button Type

### Open Chat Room

```json
{
    "action": {
        "composeAction": {
            "composeTextMessage": {
                "phoneNumber": "01000000000",
                "text": "Message to send"
            }
        },
        "displayText": "Open a chat room"
    }
}
```


| Field | Description | Note |
| --- | --- | --- |
| action.displayText | Button name | Max. 17 characters |
| action.composeAction.composeTextMessage.phoneNumber | Message recipient number | |
| action.composeAction.composeTextMessage.text | Message to be sent | Max. 100 characters, |

### Copy

```json
{
    "action": {
        "clipboardAction": {
            "copyToClipboard": {
                "text": "Message to copy"
            }
        },
        "displayText": "Copy"
    }
}
```

| Field | Description | Note |
| --- | --- | --- |
| action.displayText | Button name | Max. 17 characters |
| action.clipboardAction.copyToClipboard.text | Content to copy to clipboard | Max. 200 characters |

### Make a Call

```json
{
    "action": {
        "dialerAction": {
            "dialPhoneNumber": {
                "phoneNumber": "16446114"
            }
        },
        "displayText": "Make a call"
    }
}
```

| Field | Description | Note |
| --- | --- | --- |
| action.displayText | Button name | Max. 17 characters |
| action.dialerAction.dialPhoneNumber.phoneNumber | Phone number | |

### Show Map

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
        "displayText": "Show map"
    }
}
```

| Field | Description | Note |
| --- | --- | --- |
| action.displayText | Button name | Max. 17 characters |
| action.mapAction.showLocation.location.latitude | Latitude | |
| action.mapAction.showLocation.location.longitude | Longitude | |
| action.mapAction.showLocation.location.label | Location name | Max. 200 characters |
| action.mapAction.showLocation.fallbackUrl | Link to call when action fails | |

### Search a Map

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
        "displayText": "Search a map"
    }
}
```

| Field | Description | Note |
| --- | --- | --- |
| action.displayText | Button name | Max. 17 characters |
| action.mapAction.showLocation.location.query | Search keyword | Max. 200 characters |
| action.mapAction.showLocation.fallbackUrl | Website to query the location | |

### Share the Current Location

```json
{
    "action": {
        "mapAction": {
            "requestLocationPush": {
                "currentLocation": true
            }
        },
        "displayText": "Share the current location"
    }
}
```

| Field | Description | Note |
| --- | --- | --- |
| action.displayText | Button name | Max. 17 characters |
| action.mapAction.requestLocationPush.currentLocation | Whether to share the current location | In order to use the feature of the button normally, the corresponding value must be set to true. |

### Connect URL

```json
{
    "action": {
        "urlAction": {
            "openUrl": {
                "url": "http://www.test.com"
            }
        },
        "displayText": "Go to page"
    }
}
```

| Field | Description | Note |
| --- | --- | --- |
| action.displayText | Button name | Max. 17 characters |
| action.urlAction.openUrl.url | URL address to connect | |

### Register a Schedule

```json
{
    "action": {
        "calendarAction": {
            "createCalendarEvent": {
                "startTime": "2020-03-31T15:00:00.000Z",
                "endTime": "2020-03-31T15:00:00.000Z",
                "title": "Register Schedule",
                "description": "This is an anniversary registration."
            }
        },
        "displayText": "Register a schedule"
    }
}
```

| Field | Description | Note |
| --- | --- | --- |
| action.displayText | Button name | Max. 17 characters |
| action.calendarAction.createCalendarEvent.startTime | Start date | Format: yyyy-MM-ddTHH:mm:ss+9:00Z (Korean time)<br>Set to 1/1/1970 08:59 if not formatted |
| action.calendarAction.createCalendarEvent.endTime | End date | Format: yyyy-MM-ddTHH:mm:ss+9:00Z (Korean time)<br>Set to 1/1/1970 08:59 if not formatted |
| action.calendarAction.createCalendarEvent.title | Title | Max. 17 characters |
| action.calendarAction.createCalendarEvent.description | Content | Max. 500 characters |
