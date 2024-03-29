## Notification > RCS Bizmessage > Release Notes

### January 23, 2024
#### Added Features
* [Console] Added night ad delivery restriction
  * Added the feature to enable night ad delivery restriction and set up restriction times

### December 19, 2023
#### Feature Updates
* [API] Added error messages when required template parameters are omitted
    * Added error codes when required template parameters are omitted.
    * For more information, see the result code **4024** from [[Result Code](./result-code/#_1)].

### November 14, 2023.
#### Added Features
* [API] Added image template sending
    * Added a feature to send with image templates (image & title highlighted, image highlighted, social media, and thumbnail).
* [Console] Added image template sending
    * Added a feature to send with image templates (image & title highlighted, image highlighted, social media, and thumbnail).

### September 12, 2023
#### Added Features
* [API] Added Query Details API
    * Added the API to query detailed information of a specific message for all message types (SMS/LMS/MMS/Template).
    * For more information, refer to [[API Guide](./api-guide/#_3)].

### August 17, 2023
#### Feature Updates
* [Console] Added a field to the queried list page
    * Added the **Alternative Delivery Status** and **Alternative Delivery Time** fields when querying message lists from the **Send Result** tab.
* [API] Added a response field to the Query List API
    * Added the **Alternative Delivery Status** and **Alternative Delivery Time** fields to the response of the Query List API for all message types (SMS/LMS/MMS/Template).
* [API] Improved error response of the send API
    * Reinforced verification of requests when calling the send API.

### July 25, 2023
#### Feature Updates
* [Console] Improved the identity verification process
    * Improved so that, when identity verification is rejected or requested again, users can change business registration certificates registered in the organization.
    * Added the attachment field when verifying identities.

### June 27, 2023
#### Release of a New Service
* RCS Bizmessage service provides RCS Bizmessage sending and brand, chatbot, and template management features.
* With the RCS Bizmessage service, you can send messages and provide brand information for connection between companies and customers through brand management and also send various types of messages.
* REST API is provided for easy integration.
