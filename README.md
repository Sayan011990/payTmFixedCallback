# CordovaPayTM

Supporting platform

|    Platform     |    OS level    |
|:---------------:|:--------------:|
|     Android     |  Android 4.0+  | 
|     iOS         |   iOS 7.0+     | 

This plugin was based on this Apache project and has a compatible API.

## Installation

    // you may also install directly from this repo
    
    cordova plugin add https://github.com/isathyam/CordovaPayTM.git --variable GENERATE_URL=<Checksum Generation URL> --variable VERIFY_URL=<Checksum Validation Url> --variable MERCHANT_ID=<MerchantID> --variable INDUSTRY_TYPE_ID=<IndustryType> --variable WEBSITE=<WAPWebsiteName>
    
This plugin has only been tested in Cordova 3.2 or greater, and its use in previous Cordova versions is not recommended (potential conflict with keyboard customization code present in the core in previous Cordova versions).

If you do use this plugin in an older Cordova version (again, not recommended), you have to make sure the HideKeyboardFormAccessoryBar and KeyboardShrinksView preference values are always false, and only use the API functions to turn things on/off.

## Usage
window.plugins.paytm.startPayment(txn_id, customer_id, email, phone, amount, method, successCallback, failureCallback);  
  
## Methods

- staging support
    Pass "staging" for Staging(Testing support)
    
- live support
    Pass "product" for Live Product(Live support or before releasing app) 
  
## Example

  //Example
  
        window.plugins.paytm.startPayment(txn_id, customer_id, "idevsathya@gmail.com" ,"******9055", "10", "staging", successCallback, failureCallback);
              function successCallback(response) {
              //staging (or) product 
                var transactionBankTxnId = response.MID;
                var transactionMId = response.ORDERID;
                var transactionOrderId = response.TXNID;
                var transactionTxnDate = response.TXNDATE;
                var transactionTxnId = response.BANKTXNID;

                alert(JSON.stringify(response));
                console.log("Payed Successfully");
            }

            function failureCallback(message) {
                alert('Failed because: ' + message);
                console.log('Failed because: ' + message);
            }
  
## Credits
It was originally created by samyam-a, and i have updated callback success response, error response with code, staging(testing) and live support.

## Issues or New enhancements
Feel free ask ask questions n even i love new request..

