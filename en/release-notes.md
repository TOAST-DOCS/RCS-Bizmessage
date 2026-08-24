<!-- pre-align:aligned sig=7fe60833ab4e -->

<a id="notification-rcs-bizmessage-release-notes"></a>
## Notification > RCS Bizmessage > Release Notes { #notification-rcs-bizmessage-release-notes }

<a id="august-26-2025"></a>
### August 26, 2025 { #august-26-2025 }
<a id="august-26-2025-feature-updates"></a>
#### Feature Updates
* [API/Console] Image template support with financial compliance notice field
  * Supports integration and sending of image templates that include financial compliance notice fields.

<a id="august-27-2024"></a>
### August 27, 2024 { #august-27-2024 }
<a id="august-27-2024-feature-updates"></a>
#### Feature Updates
* [API] Enhanced validation of recipient number formats when the send API request is made
  * For more information, see [[API Guide](./api-guide/#_1)].

<a id="april-23-2024"></a>
### April 23, 2024 { #april-23-2024 }
<a id="april-23-2024-feature-updates"></a>
#### Feature Updates
* [API] Changed the update timing for resultCode from the retrieve details API response
    * Changed resultCode from updating to 2000 immediately after sending completion to update after reflecting the received results.
* [API] Changed the maximum value for the desired send time setting
    * Changed the configurable desired send time to up to 60 days later.
* [API] Enhanced validation of search conditions for the retrieve list API
    * Enhanced validation to ensure that only the correct messageId is received when a messageId is included in a search condition.
* [Console] Enhanced search condition validation on the retrieve list screen
    * Enhanced validation to ensure that only the correct messageId is received when the request ID field is included in the search condition.

<a id="january-23-2024"></a>
### January 23, 2024 { #january-23-2024 }
<a id="january-23-2024-added-features"></a>
#### Added Features
* [Console] Added night ad delivery restriction
    * Added the feature to enable night ad delivery restriction and set up restriction times

<a id="december-19-2023"></a>
### December 19, 2023 { #december-19-2023 }
<a id="december-19-2023-feature-updates"></a>
#### Feature Updates
* [API] Added error messages when required template parameters are omitted
    * Added error codes when required template parameters are omitted.
    * For more information, see the result code **4024** from [[Result Code](./result-code/#_1)].

<a id="november-14-2023"></a>
### November 14, 2023. { #november-14-2023 }
<a id="november-14-2023-added-features"></a>
#### Added Features
* [API] Added image template sending
    * Added a feature to send with image templates (image & title highlighted, image highlighted, social media, and thumbnail).
* [Console] Added image template sending
    * Added a feature to send with image templates (image & title highlighted, image highlighted, social media, and thumbnail).

<a id="september-12-2023"></a>
### September 12, 2023 { #september-12-2023 }
<a id="september-12-2023-added-features"></a>
#### Added Features
* [API] Added Query Details API
    * Added the API to query detailed information of a specific message for all message types (SMS/LMS/MMS/Template).
    * For more information, refer to [[API Guide](./api-guide/#_3)].

<a id="august-17-2023"></a>
### August 17, 2023 { #august-17-2023 }
<a id="august-17-2023-feature-updates"></a>
#### Feature Updates
* [Console] Added a field to the queried list page
    * Added the **Alternative Delivery Status** and **Alternative Delivery Time** fields when querying message lists from the **Send Result** tab.
* [API] Added a response field to the Query List API
    * Added the **Alternative Delivery Status** and **Alternative Delivery Time** fields to the response of the Query List API for all message types (SMS/LMS/MMS/Template).
* [API] Improved error response of the send API
    * Reinforced verification of requests when calling the send API.

<a id="july-25-2023"></a>
### July 25, 2023 { #july-25-2023 }
<a id="july-25-2023-feature-updates"></a>
#### Feature Updates
* [Console] Improved the identity verification process
    * Improved so that, when identity verification is rejected or requested again, users can change business registration certificates registered in the organization.
    * Added the attachment field when verifying identities.

<a id="june-27-2023"></a>
### June 27, 2023 { #june-27-2023 }
<a id="june-27-2023-release-of-a-new-service"></a>
#### Release of a New Service
* RCS Bizmessage service provides RCS Bizmessage sending and brand, chatbot, and template management features.
* With the RCS Bizmessage service, you can send messages and provide brand information for connection between companies and customers through brand management and also send various types of messages.
* REST API is provided for easy integration.
