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

## Notification > RCS Bizmessage > Service Policy

### Information on Processing of Personal Information
While using the RCS Bizmessage service, the customer may collect personal information of their users. Therefore, the customer of this service must inform a legal notice to their users as per the Personal Information Protection Act and acquire their consent regarding the matter. Also during this process, work consignment relation regarding the processing of personal information may arise between the customer and NHN Cloud. 
The customer who assumes the position of consignor may enter into a consignment contract with the consignee, NHN Cloud, separately in writing, and post a privacy policy notice by referencing the following.

[Example]
- Consignee: NHN Cloud Corp.
- Consignment Description: Providing RCS Bizmessage service

### Unsupported Sending Type
- MMS: Image & title highlighted, image highlighted, social media, thumbnail
- TEMPLATE: Image template (item details), LMS template

### Supported Sending Type

<table class="custom-table" style="text-align: center">
    <tr>
        <td>No</td>
        <td>Product</td>
        <td>Product name</td>
        <td>Card type</td>
        <td>Number of cards</td>
        <td>Maximum message length</td>
        <td>Number of buttons per card</td>
        <td>Button name maximum length</td>
        <td>Image</td>
        <td>Note</td>
    </tr>
    <tr>
        <td>1</td>
        <td>SMS</td>
        <td>SMS</td>
        <td>Standalone</td>
        <td>1</td>
        <td>100 characters</td>
        <td>1</td>
        <td>17 characters</td>
        <td>-</td>
        <td>-</td>
    </tr>
    <tr>
        <td>2</td>
        <td>LMS</td>
        <td>LMS</td>
        <td>Standalone</td>
        <td>1</td>
        <td>1300 characters</td>
        <td>3</td>
        <td>17 characters</td>
        <td>-</td>
        <td>-</td>
    </tr>
    <tr>
        <td>3</td>
        <td rowspan="2">MMS</td>
        <td>Portrait (Tall)</td>
        <td>Standalone Media Top</td>
        <td>3~6</td>
        <td>1300 characters</td>
        <td>2</td>
        <td>17 characters</td>
        <td>Tall (568x528)</td>
        <td>-</td>
    </tr>
    <tr>
        <td>4</td>
        <td>Portrait (Medium)</td>
        <td>Standalone Media Top</td>
        <td>3~6</td>
        <td>1300 characters</td>
        <td>2</td>
        <td>17 characters</td>
        <td>Medium(568x336)</td>
        <td>-</td>
    </tr>
    <tr>
        <td>5</td>
        <td rowspan="5">Text<br/>Template</td>
        <td>Description Template_Title Optional</td>
        <td>Description</td>
        <td>1</td>
        <td>90 characters</td>
        <td>2</td>
        <td>17 characters</td>
        <td rowspan="5">-</td>
        <td>-</td>
    </tr>
    <tr>
        <td>6</td>
        <td>Description Template_Title Freeform</td>
        <td>Description</td>
        <td>1</td>
        <td>90 characters</td>
        <td>2</td>
        <td>16 characters</td>
        <td>-</td>
    </tr>
    <tr>
        <td>7</td>
        <td>Style Template_Title Optional</td>
        <td>Cell</td>
        <td>1</td>
        <td>90 characters</td>
        <td>2</td>
        <td>17 characters</td>
        <td>-</td>
    </tr>
    <tr>
        <td>8</td>
        <td>Style Template_Title Freeform</td>
        <td>Cell</td>
        <td>1</td>
        <td>90 characters</td>
        <td>2</td>
        <td>16 characters</td>
        <td>-</td>
    </tr>
    <tr>
        <td>9</td>
        <td>Default Template_Title Freeform</td>
        <td>Free</td>
        <td>1</td>
        <td>90 characters</td>
        <td>0</td>
        <td>-</td>
        <td>-</td>
    </tr>
    <tr>
        <td>10</td>
        <td rowspan="8">Image<br/>Template</td>
        <td>Image &amp; Title Highlighted (3:4)</td>
        <td>Highlighted Image n Title</td>
        <td>1</td>
        <td>500 characters</td>
        <td>2</td>
        <td>16 characters</td>
        <td>Long(900x1200)</td>
        <td rowspan="8">Only templates created before the addition of the Financial Compliance Notice field (April 25, 2025) are supported.</td>
    </tr>
    <tr>
        <td>11</td>
        <td>Image &amp; Title Highlighted (1:1)</td>
        <td>Highlighted Image n Title</td>
        <td>1</td>
        <td>500 characters</td>
        <td>2</td>
        <td>16 characters</td>
        <td>Square(900x900)</td>
    </tr>
    <tr>
        <td>12</td>
        <td>Image Highlighted (3:4)</td>
        <td>Highlighted Image</td>
        <td>1</td>
        <td>500 characters</td>
        <td>2</td>
        <td>16 characters</td>
        <td>Long(900x1200)</td>
    </tr>
    <tr>
        <td>13</td>
        <td>Image highlighted (1:1)</td>
        <td>Highlighted Image</td>
        <td>1</td>
        <td>500 characters</td>
        <td>2</td>
        <td>16 characters</td>
        <td>Square(900x900)</td>
    </tr>
    <tr>
        <td>14</td>
        <td>Thumbnail (vertical)</td>
        <td>Thumbnail</td>
        <td>1</td>
        <td>500 characters</td>
        <td>2</td>
        <td>16 characters</td>
        <td>Vertical (900x560)</td>
    </tr>
    <tr>
        <td>15</td>
        <td>Thumbnail (horizontal)</td>
        <td>Thumbnail</td>
        <td>1</td>
        <td>500 characters</td>
        <td>2</td>
        <td>16 characters</td>
        <td>Horizontal(900x560)</td>
    </tr>
    <tr>
        <td>16</td>
        <td>Social media</td>
        <td>SNS</td>
        <td>1</td>
        <td>500 characters</td>
        <td>2</td>
        <td>16 characters</td>
        <td>Square(900x900)</td>
    </tr>
    <tr>
        <td>17</td>
        <td>Social (middle button)</td>
        <td>SNS</td>
        <td>1</td>
        <td>500 characters</td>
        <td>2</td>
        <td>16 characters</td>
        <td>Rectangle(900x560)</td>
    </tr>
</table>

### Alternative Sending Unsupported Type
- TEMPLATE: Image template
