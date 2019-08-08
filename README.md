# SourceKnowledge tracking script
This is an official SourceKnowledge tracking script template for google tag manager.

# Release notes
| Date | Notes |
|------|-------|
| 06 Aug 2019 | First version |

# Details
Provides options to add:
* Account/Advertiser ID (required)
* Product IDs
* Order ID (required for sales confirmation)
* Order Value (required for sales confirmation)

#Integrating
###1. Create Data Layer
The Data layer is a javascript code snippet used to send information to Google Tag Manager. This snippet should be placed directly on your website just before the GTM container snippet. E.g. 
###For Home Page/All Pages - Lead
```
<script type="text/javascript">
var dataLayer = dataLayer || [];
dataLayer.push({
'pageType':'Lead',
'productIdList' : ['ProductID_1', 'ProductID_2', 'ProductID_3']
});
</script>
<!-- Google Tag Manager -->
  	...
<!-- End Google Tag Manager -->
```
Note: You can ommit the productIdList if there are no products on the page

#### For Cart

```
<script type="text/javascript">
var dataLayer = dataLayer || [];
dataLayer.push({
'pageType':'Cart',
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
var dataLayer = dataLayer || [];
dataLayer.push({
'pageType':'Sale',
'productIdList' : ['ProductID_1', 'ProductID_2', 'ProductID_3'],
'orderId' : 'uq_order_id',
'orderAmount' : '50',
});
</script>
<!-- Google Tag Manager -->
  	...
<!-- End Google Tag Manager -->
```
Note: You can ommit the productIdList if there are no products info but orderId and orderAmount are mandatory
### 2. Tag Configuration - Choose Variables
To create the variable in GTM, click on the Variables tab. 
#### Account Id
Create a constant type GTM variable with value as your accout or advertiser id and give it a name e.g. AccountId. Select this variable for Account Id field. 
#### Data Layer Variables e.g. Order Id
Create a data layer GTM variable. Input `orderId` defined in step 1 as `Data Layer Variable Name`. Select this variable for Account Id field. Follow this for other vriables. 

### 3. Tag Configuration - Setup the Trigger
Specify when the Criteo OneTag should be fired on your website. Click on the triggers tab under the current workspace to create the trigger.


### 4. Preview & Publish
Click on the preview button to test and preview this tag before setting it live. If the tag successfully fired publish the new changes to the workflow.

More documentation about pixels provided here: http://www.sourceknowledge.com/help
