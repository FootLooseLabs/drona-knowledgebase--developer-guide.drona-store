# Getting Started with Drona-Web-SDK wiki

For development resources or contributing, visit [footloose-labs@github](https://github.com/footlooselabs/).
<br/> For any queries, write to us at : team[at]footloose.io

## Adding sdk to your app

Add the following in the `<head> </head>` of your html -

    <script inline-src src="https://s3.ap-south-1.amazonaws.com/drona-staging.footloose/sdk.min.js"></script>

Connecting With DRONA-Robot
--------------------------------

```javascript
 var ds = new drona_web_sdk.DronaStoreSdk({
    "label": "sandbox",
    "token": "accessToken",
    "client_id": "clientId"
});

// initializing callback for connect event
ds.on("connect", connected);

function connected() {
    console.log("The Robot is connected now")
}

//connect function will return the promise
ds.connect().then((_res) => {
}).catch((_err) => {
    console.error(_err);
});
```

## Communicating with DRONA-Robot

```javascript
ds.communicate(<api>,
    <payload>);
```

Test with randomly generated payload :

```
<DRONA_SDK>.communicate("DispenseRequest", "random")
```

Payload Reference : <a target="_blank" href="https://sandbox.autostore-sdk.drona.footloose.io/ "> API PLAYGROUND </a>

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

## Callback to the various robot communication

```javascript
//For any incoming message from robot this will return event as well as message
ds.on("incoming-msg", onMsg);
//this is return all events from the robot
ds.on("incoming-event", onEvent);
// this is return all the message other then event from robot
ds.on("incoming-response", onResponse);
// this is return the error from the robot
ds.on("error", onError);
//this callback funtion will be initiated when the sdk socket is closing
ds.on("close", onClose);

function onClose(res) {
    console.error("This is closed connection ", res)
}

function onError(error) {
    console.error("This is error from SDK", error);
}

function onMsg(msg) {
    console.debug("This is incoming message", msg);
}

function onEvent(event) {
    console.debug("This is event from robot", event)
}

function onResponse(res) {
    console.debug("This is response from robot ", res)
}
```
