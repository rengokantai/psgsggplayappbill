# psgsggplayappbill
##2. Creating Digital Products in Google Play
###2 Add User Permission
AndroidManifest.xml
```
<uses-permission android:name="com.android.vending.BILLING"/>
```
###3 Add a new app
Build->generate signed APK
####01:14
alpha testing

###4 Set up In-app Billing
####01:50 Managed Product
- Tracked Ownership
- One-time purchase

####02:33 Subscription
- Automated, recurring billing
- Manually Cancellation
- Trial period
- Updrade, downgrade


##3. Purchasing and Testing In-app Products
###2 Preparation for In-app Billing
install lib  
Tools->android->SDK manager  
second tab(SDK Tools), install Google Play Billing Library  
then refer to [this](https://developer.android.com/google/play/billing/billing_integrate.html)  

####step
- create folder aidl in root level
- create package com.android.vending.billing
- find IInAppBillingService.aidl in <sdk>/extras/google/play_billing, copy to package


###3 Purchase Process
(getPurchases, getSkuDetails)->getBuyIntent->onActivityResult (startIntentSenderForResult)

###4 Methods for In-app Billing

####getSkuDetails
```
Bundle getSkuDetails(int apiVersion, String packageName, String type, Bundle skusBundle)
```


####Purchase result
```
RESPONSE_CODE
INAPP_PURCHASE_DATA
INAPP_DATA_SIGNATURE
```

####08:58
```
int consumePurchase(int apiVersion,String packageName, String purchaseToken);
```
###5 Summing Up
####managed items
getPurchases->onCreate--(if sth not consumed)->consumePurchase--(else)-->getBuyIntent->consumePurchase

####subscriptions
subs
```
Bundle bundle = inAppBillingService.getPurchases(3,packageName,"subs");
```

####02:02 Blocking UI?
safe for UI: isBillingSupported  getBuyIntent  
Blocking UI: getPurchases consumePurchase getSkuDetails

