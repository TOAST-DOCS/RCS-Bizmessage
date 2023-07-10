## Notification > RCS Bizmessage > Console Usage Guide

```
To use the RCS Bizmessage service, you can use it after completing identity verification in [Console > RCS Bizmessage > Identity Verification] (Article 84 of the Telecommunications Business Act). 
```

## Send

* To send an RCS Bizmessage, you must first proceed with the brand linkage in the \[Manage RCS Bizmessage] menu.
* After the brand linkage, you can send a message by selecting a brand and a chat room (sender number).

### Send Regular SMS
1. Select Sending brand.
2. Select a chat room (sender number).
3. Select whether the outgoing content is an ad or not. If this is an ad, you have to select the 080 Deny-to- receive number.
4. Select the sending type as **SMS**.
5. **Add message content (maximum 100 characters) and buttons (maximum one).**
7. Under Receiver Settings on the right, create the receiver number you want to send and click the Add button (maximum 50 people)
8. Click Send button

### Send General LMS
1. Select Sending brand.
2. Select a chat room (sender number).
3. Select whether the outgoing content is an ad or not. If this is an ad, you have to select the 080 Deny-to- receive number.
4. Select the sending type as **LMS**.
5. **Add message titles (maximum 30 characters), content (maximum 1300 characters) and buttons (maximum 3 characters).**
7. Under Receiver Settings on the right, create the receiver number you want to send and click the Add button (maximum 50 people).
8. Click Send button

### Send MMS
1. Select Sending brand.
2. Select a chat room (sender number).
3. Select whether the outgoing content is an ad or not. If this is an ad, you have to select the 080 Deny-to- receive number.
4. Select the send type as **MMS**.
5. Under Select Details, select **Horizontal or Vertical**.
6. **Add titles (maximum 30 characters), content (maximum 1300 characters), images (maximum one) and buttons (maximum two per card).**
9. Under Receiver Settings on the right, create the receiver number you want to send and click the Add button (maximum 50 people).
10. Click Send button

### Send MMS (Card Type)
1. Select Sending brand.
2. Select a chat room (sender number).
3. Select whether the outgoing content is an ad or not. If this is an ad, you have to select the 080 Deny-to- receive number.
4. Select the send type as **MMS**.
5. Under Select Details, select **slide type and slide size**.
6. Set the number of slides in the message (minimum 3 and maximum 6).
7. **Enter a title (maximum 30 characters), content (maximum 30 characters), images (maximum one) and buttons (maximum two) for each card.**
8. Under Receiver Settings on the right, create the receiver number you want to send and click the Add button (maximum 50 people).
9. Click Send button

### Send Template
1. Select Sending brand.
2. Select a chat room (sender number).
3. Select the send type as **Template**.
4. Select the template you want to send.
5. If it is a free template, create a message (maximum 90 characters) to send.
6. Under Receiver Settings on the right, create the receiver number you want to send and click the Add button (maximum 50 people).
7. For each receiver, ** enter the appropriate value for the template replacement**.
8. Click Send button

## Retrieve Send Results 

* You can retrieve the results of the RCS Bizmessage request.
* You can set the conditions for each item to retrieve.
    * Send type is a required value.
    * You can use either the date and time of sending or the date and time of receipt as a condition.
    * The time condition is available maximum one month.

### Send Result Status
* Total
* Prepare to send: The request has been made, but the sending has not been processed yet.
* Sending: RCS message sending is in progress and has not yet been received.
* Sending successful: The RCS message sending request has been completed successfully and the message has been reached on the receiver device.
* Sending failed: The Receiver device was not reached because the sending of the RCS message has failed.
* Sending canceled: RCS messages sending has been cancelled by the NHN Cloud operator.

## Manage RCS Bizmessage

### Brand Management
* To use the RCS Bizmessage service, you have to register your brand after signing up for the RCS Biz Center. [[Go to the RCS Biz Center](https://www.rcsbizcenter.com/main)]
    * After registering the brand, please designate NHN Cloud as an agency in the RCS Biz Center brand operation management menu.
    * Brand linkage is done based on the business registration number on the attached business registration card when authenticating yourself.
* Clicking on **+ Link Brand** button also links brands and sub-resources (chat rooms, templates).
* If there are any changes after the interlock, press the **Link Brand** button to proceed with the synchronization.
* You can check the brand information registered with the RCS Biz Center in the brand list.
    * Only approved brands identified in the list can be used for sending.
    * The date and time of approval means the date and time approved by the RCS Biz Center, and the date and time of linking means the date and time when the brand is linked to NHN Cloud's RCS Bizmessage service.

### Retrieve Chat Room (sender number)
* You must register a chat room (sender number) in the RCS Biz Center.
* Once the brand linkage is complete, you can look up the list of chat rooms (sender numbers) registered with the brand.
* If you select the brand you want from the drop box, you can look up the list of chat rooms (sender numbers) registered with that brand.

### Retrieve Template
* You have to register the template in the RCS Biz Center.
* Once the brand linkage is complete, you can look up the list of templates registered with the brand.
* If you select the brand you want from the drop box, you can retrieve the list of templates registered with that brand.


## Manage Sending

* You must use the SMS service to set alternative sending settings and 080 Deny-to-receive number in the RCS Bizmessage service.
* Once the SMS service is set up, you can set up a sender number for alternative sending and retrieve the list of 080 Deny-to-receive numbers for sending advertising messages.

### Use SMS Service
* Only SMS services enabled in the same project can be linked.
* You can use the toggle button to switch the SMS service status to Active or Disabled.
* Touch the Save button to update the SMS service linking status.

### Set up Alternative Sending 
* If you fail to send RCS Bizmessage, you can replace it with an SMS message to send a message.
* Click the Set button in the chat room (sender number) list to set the alternative sending status and alternative sending number.
    * Alternative sending sender numbers can only be set if they are registered with SMS service.
    * Only messages from chat rooms (sender numbers) that have failed to send will be sent by LMS or SMS instead.

### Retrieve 080 Deny-to-receive number
* When sending a message with advertising information, you can select and send the 080 Deny-to-receive number registered with the SMS service.
* You can look up the 080 Deny-to-receive number registered with the SMS service.

## Identity Verification

* The identity verification process has been applied to the RCS Bizmessage service to comply with the revision notice related to Article 84-2 of the Telecommunications Business Act.
* To use the RCS Bizmessage service, the identity verification process is required. Identity verification basically requires mobile phone identification and additional document screening according to the member type.
  * Without identity verification, all features other than the **Identity verification tab** will be disabled.
  * The RCS Bizmessage service is not available to individual members.
* The name and mobile phone number entered at the time of membership must match the information entered at the time of identity verification to be approved for identity verification.

### Required documents according to membership type
| Member Type | Verification Method | Required Documents | | --- | --- | --- | | Business Representative | Mobile Phone Identification | Business Registration Certificate, Certificate of Employment | Business Executives and Employees | Mobile Phone Identification | Business Registration Certificate, Certificate of Employment|

### Identity verification process
1. Click **Mobile Verification and Add Required Documents** to begin the process.
2. Agree after checking the consent to collect and use personal information.
3. Proceed with the identity verification process through mobile phone text authentication or simple identity verification.
4. If you need any documents, register them with the documents attached.
5. Wait for the operator inspection and approval process.
6. Once the identity verification process is completed, the approval results will be sent to the mail registered with your account.
