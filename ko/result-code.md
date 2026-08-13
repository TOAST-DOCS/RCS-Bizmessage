<!-- pre-align:aligned sig=89afce9eccbc -->

<a id="notification-rcs-bizmessage-result-code"></a>
## Notification > RCS Bizmessage > 결과 코드 { #notification-rcs-bizmessage-result-code }

<a id="api-result-code"></a>
### API 결과 코드 { #api-result-code }
| 결과 코드 | 설명 | API 응답 메시지 | 비고 |
| --- | --- | --- | --- |
| 0 | 성공 | success | |
| 400 | 사용자 오류 | Client exception | |
| -3000 | 버튼 유효성 검사 실패 | Client Error. Invalid button parameter. |  |
| -3001 | 080 수신거부 번호 없음 | Client Error. Unsubscribe number is required when send ad. | |
| -3002 | 발송 요청 시간 오류 | Client Error. SendDateTime cannot be set before now. | |
| -3003 | 예약 가능 최대 일자 초과 | Client Error. SendDateTime cannot be set to a point in time after 60 days. | |
| -3030 | MMS 가로형, 세로형 카드 수 오류 | Client Error. Horizontal and vertical type can enroll only one card. | | 
| -3031 | MMS 제목 길이 초과 | Client Error. Over mms type title length 30. | | 
| -3032 | MMS 가로형, 세로형 내용 길이 초과 | Client Error. Over horizontal and vertical type body length 1300. | | 
| -3033 | MMS 슬라이드형 카드 수 오류 | Client Error. Carousel type can enroll more than 3, less than 6. | | 
| -3034 | MMS 슬라이드형 소형 내용 길이 초과 | Client Error. Over Carousel small type body length 30 per card. | | 
| -3035 | MMS 슬라이드형 중형 내용 길이 초과 | Client Error. Over Carousel medium type body length 60 per card. | | 
| -4000 | 브랜드 없음 | Client Error. Not exist brand. | | 
| -4001 | 브랜드 상태 오류 | Invalid status brand. | | 
| -4010 | 대화방(발신 번호) 없음 | Client Error. Not exist chatbot. | | 
| -4011 | 대화방(발신 번호) 상태 오류 | Invalid status chatbot. | | 
| -4020 | 템플릿 없음 | Client Error. Not exist template. | | 
| -4021 | 템플릿 상태 오류 | Invalid status template. | | 
| -4022 | 지원하지 않은 템플릿 | Unsupported template. | |
| -4023 | 광고 발송이 허용되지 않은 템플릿 | Ad not allowed template. | |
| -4024 | 템플릿 파라미터 입력값 누락 | Missing template parameter input. | |
| -4030 | 첨부파일 없음 | Client Error. Not exist media. | | 
| -4031 | 첨부파일 만료 | Expired media. | | 
| -4032 | 첨부파일 타입 오류 | Client Error. Invalid media type. | | 
| -4033 | 첨부파일 크기 초과 | Client Error. Exceed max file size. | | 
| -4034 | 첨부파일 형식 오류 | Client Error. Invalid media format. | | 
| -4040 | 080 수신거부 번호 없음 | Not exist block service. | |
| -4041 | 080 수신거부 번호 상태 오류 | Invalid status block service. | |
| -4042 | 080 수신거부 대상 | Blocked recipient number. | |
| -4050 | 대체 발신 번호 없음 | Not exist send number. | | 
| -4060 | 대체 발신 미지원 타입 | Fallback unsupported type. | | 
| -5000 | 080 수신거부 번호 조회 실패 | Fail to call SMS block service API. | |
| -5001 | 080 수신거부 대상 조회 실패 | Fail to call SMS block recipient API. | |
| -5002 | SMS 발신 번호 조회 실패 | Fail to call SMS send number API. | |
| -6000 | SMS 프로젝트 조회 실패 | Fail to call CAB read project API. | |
| -6001 | SMS 프로젝트 활성화 실패 | Fail to call CAB enable project SMS API. | |
| -7000 | 발송 조회 타입 오류 | Client Error. Invalid search type on url path. (sms, lms, mms, template) | |
| -7001 | 조회 필수 파라미터 오류 | Client Error. Send date time or receive date time or message id is required. | |
| -7002 | 조회 기간 조건 오류 | Client Error. Send date time and receive date time cannot be requested once. | 발송 요청 시간 조건, 수신 시간 조건은 함께 사용 불가 |
| -7003 | 조회 기간 조건 초과 | Client Error. Invalid date time search parameter. | 최대 31일까지 지정 가능 |
| -7004 | 메시지 상태 조건 오류 | Client Error. Invalid message status parameter. | |
| -7005 | 메시지 ID 없음 | Client Error. Not Exist Message ID. | |
| -8000 | 대체 발송 요청 실패 | Fail to call SMS send API. | |
| -9000 | 야간 광고 발송 제한됨 | Night ad delivery is limited. | |
| -9999 | 내부 에러 | System error. Please inquire at support@toast.com. | |

<a id="result-code-of-receiving"></a>
### 수신 결과 코드 { #result-code-of-receiving }

| 결과 코드 | 설명 | 비고 |
| --- | --- | --- |
| 50000 | MatchedtoNewSpecifications | | 
| 50001 | Missing Authorization header | | 
| 50002 | Missing token | | 
| 50003 | Invaild token | | 
| 50004 | Token has expired | | 
| 50005 | Authorization Error | | 
| 50006 | Invalid client id | | 
| 50007 | Invalid sender id | | 
| 50008 | Invalid password | | 
| 50009 | NonAllowedIp | | 
| 50100 | Invalid state | | 
| 50201 | Message TPS Exceeded | | 
| 50202 | Message Quota Exceeded | | 
| 51101 | AgencyKeyNotFound | | 
| 51102 | InvaildAgencyKey | | 
| 51103 | BrandKeyNotFound | | 
| 51104 | InvaildBrandKey | | 
| 51003 | DuplicationError | | 
| 51004 | ParameterError | | 
| 51005 | JsonParsingError | | 
| 51006 | DataNotFound | | 
| 51900 | Not Found Handler | | 
| 51901 | Samsung MaaP Connect IF Error | | 
| 51902 | Samsung MaaP Service IF Error | | 
| 51903 | Capri IF Error | | 
| 51904 | Webhook Execute Imposible Status Failure | | 
| 51905 | Webhook CDR Log Writing Failure | | 
| 51906 | Invalid Webhook Url | | 
| 51907 | Expired Webhook Message | | 
| 51908 | Exceed Retry Count to Send Message | | 
| 51909 | Non Existing Webhook Message | | 
| 51910 | Non Existing Webhook GW Vendor | | 
| 51911 | No Subscription | | 
| 52001 | Invalid phone number format | | 
| 52002 | Invalid message status | | 
| 52003 | Bot Aleady Exists | | 
| 52004 | Bot Creation Failed | | 
| 52005 | Bot Update Failed | | 
| 52006 | Brand Delete Failed | | 
| 52007 | InvalidChatbotServiceType | | 
| 52008 | MismatchedChatbotId | | 
| 52016 | Message transmission time exceeding | | 
| 52023 | Messagebase id stopped temporarily | | 
| 53001 | Invalid file type | | 
| 53002 | File Attribute Error | | 
| 53003 | FileID format Error | | 
| 53004 | FileUploadError | | 
| 53005 | InvalidMultiPartRequest | | 
| 53006 | Attached file size Error | | 
| 55001 | Corp Content Error | | 
| 55002 | Invalid property | | 
| 55101 | Agency Content Error | | 
| 55102 | Invalid AgencyId | | 
| 55103 | AgencyID permission error | | 
| 55104 | Contract Content Error | | 
| 55201 | Brand Content Error | | 
| 55202 | Brand name Error | | 
| 55203 | Brand profile image Error | | 
| 55204 | Brand CS number Error | | 
| 55205 | Brand menu Error | | 
| 55206 | Brand category Error | | 
| 55207 | Brand homepage Error | | 
| 55208 | Brand email Error | | 
| 55209 | Brand address Error | | 
| 55210 | Invalid BrandID | | 
| 55301 | Bot Content Error | | 
| 55302 | Invalid BotID | | 
| 55304 | BotID permission error | | 
| 55501 | Messagebase Content Error | | 
| 55502 | Invalid MessagebaseID | | 
| 55503 | MessagebaseID permission error | | 
| 55504 | Invalid formatstring | | 
| 55505 | Invalid messagebase Policy Info | | 
| 55506 | Invalid messagebase param | | 
| 55507 | Invalid messagebase attribute | | 
| 55508 | Invalid messagebase type | | 
| 55509 | mismatching Product type | | 
| 55601 | MessagebaseForm Content Error | | 
| 55602 | Invalid messagebaseformID | | 
| 55603 | InvalidMessageBaseProductCode | | 
| 55701 | prohibited text content | | 
| 55702 | Action button Permission error | | 
| 55703 | prohibited header value | | 
| 55704 | prohibited footer field | | 
| 55705 | missing footer content | | 
| 55706 | footer content syntax Error | | 
| 55707 | content pattern error | | 
| 55708 | Exceeded max character of title | | 
| 55709 | Exceeded max character of description | | 
| 55710 | Exceeded max number of buttons | | 
| 55711 | mismatching number of carousel card | | 
| 55712 | Exceeded max size of media | | 
| 55801 | GwVendor Content Error | | 
| 55802 | Invalid message | | 
| 55803 | Message Syntax Error | | 
| 55804 | Missing message content | | 
| 55805 | Invalid message content | | 
| 55806 | Duplicated MessageId | | 
| 55807 | Invalid Chatbot Permission | | 
| 55808 | Invalid Chatbot Status | | 
| 55809 | Invalid Agency Permission | | 
| 55810 | Invalid Expiry Field | | 
| 55811 | Exceeded Max Character Of Param | | 
| 55812 | Invalid Reseller Id | | 
| 55813 | Exceed Button Text Length | | 
| 55814 | Invalid MessageBase Buttons | | 
| 55815 | Message Body File Not Found | | 
| 55816 | Mismatched Suggestions Count | | 
| 55817 | Invalid Dest Phone Number | | 
| 55818 | Invalid messagebaseID | | 
| 55819 | Invalid Chatbot Id | | 
| 55820 | Revoked Message | | 
| 55821 | Etc TimeOut | | 
| 55822 | Canceled Message | | 
| 55900 | Non Retryable Error Caused By Invalid Message | | 
| 56002 | Revocation Failed | | 
| 56007 | Expired Before Session Establishment | | 
| 59999 | Etc Error | | 
| 59001 | Internal Error | | 
| 59002 | IOError | | 
| 59003 | Backend Timeout | | 
| 54001 | Invaild Contact number User | | 
| 54002 | No Rcs Capability | | 
| 54003 | Unable Sending to Recipient  | | 
| 54004 | Internal Server Error | | 
| 40001 | Missing Authorization header | | 
| 40002 | Missing token | | 
| 40003 | Invalid token | | 
| 40004 | Token has expired | | 
| 40005 | Malformed token payload | | 
| 40006 | Invalid client id | | 
| 40007 | Insufficient scope | | 
| 41000 | Internal Server Error | | 
| 41001 | RCS Request Timeout | | 
| 41003 | Throttled by message rate | | 
| 41004 | RCS Server Busy | | 
| 41005 | RCS Server Temporarily unavailable | | 
| 41006 | Session does not exist | | 
| 41007 | Revoked | | 
| 41008 | Session already expired | | 
| 41100 | SUBSCRIBE Timeout | | 
| 41101 | User Not Found | | 
| 41200 | User for Message receiving Not Foun d | | 
| 41201 | Message Not Acceptable | | 
| 41202 | Message was already revoked | | 
| 41210 | User is not capable for TEXT | | 
| 41211 | User is not capable for FT | | 
| 41212 | User is not capable for RICHCARD | | 
| 41220 | User is not capable for XBOTMESSA GE 1.0 | | 
| 41221 | User is not capable for XBOTMESSA GE 1.1 | | 
| 41222 | User is not capable for XBOTMESSA GE 1.2 | | 
| 41230 | User is not capable for OPENRICHAR D 1.0 | | 
| 41231 | User is not capable for OPENRICHAR D 1.1 | | 
| 41232 | User is not capable for OPENRICHAR D 1.2 | | 
| 41240 | User is not capable for GEOLOCATIO N PUSH REQUEST | | 
| 41250 | Failed to get message content type | | 
| 42001 | Invalid state | | 
| 42002 | Invalid message | | 
| 42003 | Invalid date/time format | | 
| 42004 | Missing contact | | 
| 42005 | Invalid contact | | 
| 42006 | Emulator access only | | 
| 42007 | Contact not in whitelist | | 
| 42008 | Missing message content | | 
| 42009 | Invalid message content | | 
| 42010 | Ambiguous message | | 
| 42011 | Invalid message status | | 
| 42012 | Invalid isTyping status | | 
| 42013 | Invalid traffic type | | 
| 42014 | Invalid suggested chiplist association | | 
| 42015 | Empty text message | | 
| 42031 | Missing richcard | | 
| 42032 | Ambiguous richcard | | 
| 42033 | Too many richcards | | 
| 42034 | Missing richcard layout | | 
| 42035 | Missing richcard content | | 
| 42036 | Invalid cardOrientation | | 
| 42037 | Missing image alignment | | 
| 42038 | Invalid image alignment | | 
| 42039 | Redundant image alignment | | 
| 42040 | Invalid richcard carousel cardWidth | | 
| 42041 | Mismatched media height | | 
| 42042 | Invalid richcard content | | 
| 42043 | Invalid suggestions | | 
| 42044 | Too many suggestions in chiplist (max 11) | | 
| 42045 | Invalid suggestion | | 
| 42046 | Ambiguous suggestion | | 
| 42047 | Ambiguous suggested action | | 
| 42048 | Too many suggestions in richcard (max 4) | | 
| 42049 | Too many suggestion data (max 2048) | | 
| 42050 | Invalid Action | | 
| 42051 | Invalid location | | 
| 42052 | Ambiguous location | | 
| 42053 | Invalid mapAction | | 
| 42054 | Ambiguous mapAction | | 
| 42055 | Invalid dialerAction | | 
| 42056 | Ambiguous dialerAction | | 
| 42057 | Invalid composeAction | | 
| 42058 | Ambiguous composeAction | | 
| 42059 | Invalid settingsAction | | 
| 42060 | Ambiguous settingsAction | | 
| 42061 | Invalid ClipboardAction | | 
| 42062 | Missing localBrowserAction | | 
| 42063 | Invalid ShareAction | | 
| 42064 | Missing CalendarAction | | 
| 42065 | Invalid CalendarAction | | 
| 42066 | Invalid CalendarAction title (min1 max100) | | 
| 42067 | Invalid CalendarAction description (min1 max500) | | 
| 42068 | Invalid ComposeAction composeTextMessage (missing phone number) or (text min 1 max 100) | | 
| 42069 | Invalid ComposeAction composeRecodingMessage (missing phone number) or (type 'AUDIO' or 'VIDEO') | | 
| 42070 | Missing DeviceAction | | 
| 42071 | Invalid dialerAction (missing phone number) or (subject max 60) | | 
| 42072 | Missing mapAction showLocation location | | 
| 42073 | Missing urlAction openUrl | | 
| 42100 | Invalid thumbnail | | 
| 42101 | Missing fileUrl | | 
| 42102 | Missing audio fileUrl | | 
| 42103 | Missing pos | | 
| 42104 | Missing Media information | | 
| 42105 | Missing Media information | | 
| 42106 | Missing Media information | | 
| 42107 | Missing Media information | | 
| 42108 | Missing postback data | | 
| 42200 | Invalid URI format | | 
| 42201 | Invalid Location | | 
| 42202 | Invalid media content description | | 
| 42203 | Invalid media title | | 
| 42204 | Invalid media description | | 
| 42205 | Too many contents in richard carous el | | 
| 42206 | Invalid media file size | | 
| 42207 | Invalid expiry time format | | 
| 42208 | Invalid expiry time | | 
| 42301 | Ambiguous Openrichcard | | 
| 42302 | Missing Openrichcard | | 
| 42303 | Missing Openrichcard Layout Widget | | 
| 42304 | Missing Openrichcard View Content | | 
| 42305 | Missing Openrichcard LinearLayout C ontent | | 
| 42306 | Missing Openrichcard Textview Conte nt | | 
| 42307 | Invalid Contents In Openrichcard Tex tview | | 
| 42308 | Invalid Text Length In Openrichcard Textview | | 
| 42309 | Missing Openrichcard Imageview Con tent | | 
| 42310 | Too Small Media In Openrichcard Im ageview | | 
| 42311 | Invalid Openrichcard Imageview Scal etype | | 
| 42312 | Missing Openrichcard width or height | | 
| 42313 | Invalid Openrichcard width or height | | 
| 42314 | Invalid Openrichcard Common Conte nts | | 
| 42315 | Too many child in open rich card | | 
| 42401 | Invalid file type | | 
| 42402 | Download failure | | 
| 42501 | Missing contact | | 
| 42502 | Missing content | | 
| 42503 | Missing title | | 
| 42504 | Missing description | | 
| 42505 | Missing image url | | 
| 42506 | Missing image type | | 
| 42507 | Missing button link | | 
| 42508 | Missing button text | | 
| 42509 | Invalid title | | 
| 42510 | Invalid description | | 
| 42511 | Invalid image url address | | 
| 42512 | Invalid button url address | | 
| 42513 | Invalid button text | | 
| 42514 | Duplicated message ID | | 
| 42601 | Too Many Request | | 
| 42602 | message filtered | | 
| 45000 | Internal Server Error | | 
| 45001 | Handle bot data error | | 
| 45002 | Handle capability data error | | 
| 45003 | Handle xml data error | | 
| 45004 | Access MessageInfo Cache Failed | | 
| 45005 | Access ChatInfo Cache Failed | | 
| 45006 | Create Http client for maap registry | | 
| 45007 | Create Http client for bot | | 
