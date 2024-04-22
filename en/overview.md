<style>
    .custom-table thead {
        background-color: #FAFAFA;
    }
    
    .custom-table tbody tr {
        background-color: white!important;
    }
    
    .custom-table td {
        vertical-align: middle;
    }
</style>

## Notification > RCS Bizmessage > Overview

The RCS Bizmessage service allows users to send various types of messages, manage and provide branded information for connecting businesses with their customers.
REST APIs for easy integration are provided.

## Main Features

* Send message full of rich information 
    * You can enter maximum 100 SMS characters, 1300 LMS/MMS characters and maximum 6 MMS attachments.    
    * Provides a variety of message types. When sending a message as an MMS type, it can be sent in horizontal/vertical/slide form.
    * When you send a message, you can add an action button with a function to the button.
* Alternate sending
    * For devices that do not receive RCS Bizmessage, it provides function to send it as an alternative to an existing SMS service.
* Easy linkage
    * You can link brand and template information registered with the RCS Biz Center through the certified business registration information through the identity verification process.
    * Provides the RCS Bizmessage sending feature and query REST API that can be used in customer applications.

## RCS Delivery Supported Types

<table class="custom-table" style="text-align: center">
  <thead>
    <tr>
      <th>Category</th>
      <th colspan="3">General</th>
      <th colspan="2">Template</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Product name</td>
      <td>RCS SMS</td>
      <td>RCS LMS</td>
      <td>RCS MMS</td>
      <td>Text template</td>
      <td>Image template</td>
    </tr>
    <tr>
      <td>Purpose</td>
      <td>Information/Advertising</td>
      <td>Information/Advertising</td>
      <td>Information/Advertising</td>
      <td>Information</td>
      <td>Information/Advertising</td>
    </tr>
    <tr>
      <td>Pre-approval</td>
      <td>Not required</td>
      <td>Not required</td>
      <td>Not required</td>
      <td>Approval required</td>
      <td>Approval required</td>
    </tr>
    <tr>
      <td>Maximum characters</td>
      <td>100 characters</td>
      <td>1,300 characters</td>
      <td>1,300 characters<br/>+1 MB media (per card)</td>
      <td>90 characters</td>
      <td>500 characters<br/>+ 1 MB media (per card)</td>
    </tr>
    <tr>
      <td>Maximum number of buttons</td>
      <td>1 button</td>
      <td>6 buttons</td>
      <td>2 buttons (per card)</td>
      <td>1 button</td>
      <td>2 buttons (per card)</td>
    </tr>
    <tr>
        <td>

[Supported formats](./service-policy)
</td>
      <td>1</td>
      <td>1</td>
      <td>4</td>
      <td>4</td>
      <td>4</td>
    </tr>
  </tbody>
</table>

## Service Targets

* Customers looking to send messages with rich information and user action
* Customers looking to send large amounts of RCS Bizmessage
* Customers who want to easily link RCS Bizmessage services through REST APIs