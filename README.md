# Cordova Plugin Fingerprint All-In-One
## **A** ndroid and **IO** s

[![NPM](https://nodei.co/npm/cordova-plugin-fingerprint-aio.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/cordova-plugin-fingerprint-aio/)


This plugin is an attempt to provide a single interface for accessing fingerprint hardware on both Android 6+ and iOS.

There are some great cordova plugins out there that make use of the fingerprint APIs provided by Android and iOS. But I could not find a project which supports both platforms (correct me if I am wrong). I decided to take their native code and bundle it together in one plugin.

## Disclaimer
The plugin is still under development. At the moment the API could change every day and the plugin build could crash or have secutity issues. If you use fingerprint authentication in production use the plugins below.

## Features

* Check if fingerprint scanner is available
* fingerprint authentication

## Features - Work in Progress

* Swift 2 support
* ngCordova support
* password fallback


### Platforms

* Android works
* iOS works only if **XCode 8** is installed - Plugin uses Swift 3

## How to use

### Check if fingerprint authentication is available
```javascript
Fingerprint.isAvailable(isAvailableSuccess, isAvailableError);
    $scope.available = "Not checked";

    function isAvailableSuccess(result) {
      $scope.available = "Fingerprint available";
    }

    function isAvailableError(message) {
      console.error(message);
    }
```

### Show authentication dialogue
```javascript
Fingerprint.show({
      clientId: "Fingerprint-Demo",
      clientSecret: "password" //Only necessary for Android
    }, successCallback, errorCallback);

    function successCallback(){
      alert("Authentication successfull");
    }

    function errorCallback(err){
      alert("Authentication invalid " + err);
    }
```

[Example](https://github.com/NiklasMerz/fingerprint-aio-demo/blob/master/www/js/controllers.js)

Demo app: https://github.com/NiklasMerz/fingerprint-aio-demo

## Thanks to the authors of the original fingerprint plugin:

[Android](https://github.com/mjwheatley/cordova-plugin-android-fingerprint-auth)

[iOS](https://github.com/EddyVerbruggen/cordova-plugin-touch-id)
