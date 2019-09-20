# SourceKnowledge Conversion Tag
This is an official SourceKnowledge tracking script template for Google Tag Manager. It provides options to add:
* Advertiser ID (required)
* Product IDs
* Order ID (required for sales confirmation)
* Order Value (required for sales confirmation)

# Integration Guide
### 1. Selecting SourceKnowledge Conversion Tag.
- Log into Google Tag Manager. 
- Go to `Tags` tab -> `New` -> `Tag Configuration` and search for `SourceKnowledge Conversion Tag` type.

### 2. Create Data Layer
The Data layer is a JavaScript code snippet used to send information to Google Tag Manager. This snippet should be placed directly on your website just before the GTM container snippet. E.g. 
#### For Lead/Home Page
```
<script type="text/javascript">
var dataLayer = [];
dataLayer.push({
'productIdList' : ['ProductID_1', 'ProductID_2', 'ProductID_3']
});
</script>
<!-- Google Tag Manager -->
  	...
<!-- End Google Tag Manager -->
```
Note: you can skip this if there is no product on the page. 
#### For Cart
```
<script type="text/javascript">
var dataLayer = [];
dataLayer.push({
'productIdList' : ['ProductID_1', 'ProductID_2', 'ProductID_3']
});
</script>
<!-- Google Tag Manager -->
  	...
<!-- End Google Tag Manager -->
```
#### For Sales Confirmation
```
<script type="text/javascript">
var dataLayer = [];
dataLayer.push({
'productIdList' : ['ProductID_1', 'ProductID_2', 'ProductID_3'],
'orderId' : 'uq_order_id',
'orderAmount' : '50',
});
</script>
<!-- Google Tag Manager -->
  	...
<!-- End Google Tag Manager -->
```

More Information about dataLayer: https://support.google.com/tagmanager/answer/6164391?hl=en
### 3. Tag Configuration - Choose Variables
To create the variable in GTM, click on the Variables tab. 
#### Advertiser ID and Tracker Type
- Create a `constant` type GTM variable with value as your Advertiser ID and give it a name e.g. AdvertiserID. Select this variable for Advertiser ID field. 
- Then select the Tracker Type from the drop down list.
#### Data Layer Variables - Product(s), Order Id & Order Amount
Create a data layer GTM variable. Input `orderID` defined in step 1 as `Data Layer Variable Name`. Select this variable for Order Id field. Follow this for other variables. 
### 4. Tag Configuration - Setup the Trigger
Under `Triggering` choose the correct trigger type for the tag such as lead/home pages, cart page, conversion event, etc. Then click save.

More Information: https://support.google.com/tagmanager/topic/7679384?hl=en&ref_topic=3441647

### 5. Preview & Publish
Click on the preview button to test and preview this tag before setting it live. If the tag successfully fires, publish the new changes to the workflow.

# More About SourceKnowledge Tags
Please visit: http://www.sourceknowledge.com/help#tab-pixel-setup
