# Smartface RAU module
This extension is to speed up RAU implementation by writing the code required and implementing required localization and permissions

## Install
```shell
npm i -S https://github.com/alperozisik/sf-extension-rau.git
```
## Require
```javascript
const rau = require('sf-extension-rau');
```
## Default usage
```javascript
rau.checkUpdate();
```


## Best practice usage
First page code
```javascript
page.onShow = function onShow(data) {
    if (data && data.checkUpdate) { //checkUpdate flag is used for for the app start
        setTimeout(function() { // call it via setTimeout to not to block UI rendering
            rau.checkUpdate();
        }, 10);
    }
};
```


app.js code
```javascript
Router.go("firstPage", {
    checkUpdate: true
});
```
## Localization
RAU module uses global lang varaible to set some values for the given texts. Here are the list for them
- newVersionAvailable
- version
- isReadyToInstall
- updateMandatory
- updateOptional
- updateNow
- later
- updateFail
- updateIsInProgress

## Peer Dependencies
* Alerts used in this extension are based on the [sf-extension-alert](https://github.com/alperozisik/sf-extension-alert)
* Android permissions are managed by the [sf-extension-permission](https://github.com/alperozisik/sf-extension-permission)
