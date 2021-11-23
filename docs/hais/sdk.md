# Getting Started with Drona-Web-SDK

For development resources or contributing, visit [footloose-labs@github](https://github.com/footlooselabs/).
<br/> For any queries, write to us at : team[at]footloose.io

## Adding sdk to any app
 Add the following in the `<head> </head>` of the html -

    <script inline-src src="https://s3.ap-south-1.amazonaws.com/drona-staging.footloose/sdk.min.js"></script>


## Connecting with DRONA-Robot
`var <DRONA_SDK> = new drona_web_sdk.DronaStoreSdk({"label": "sandbox"})` <br/>
<i>// This instantiates & connects SDK with the 'sandbox' robot-store.</i>


## Communicating with DRONA-Robot 
<br/>`<DRONA_SDK>.communicate(<api>, <payload>)` 

Test with randomly generated payload : <br/>
`<DRONA_SDK>.communicate("DispenseRequest", "random")`

Payload Reference : <a href="https://sandbox.autostore-sdk.drona.footloose.io/ "> API PLAYGROUND </a>
#### Robot Communication Reference
 - DispenseRequest
 - ViewInventory
 - ConfigureInventoryRequest
 - AddItemsRequest
 - ViewOutboundOrders
 - SubscribeToOrderUpdates
 - SubscribeToOperationUpdates
 - SubscribeToStateUpdates
 - DiscardOperation