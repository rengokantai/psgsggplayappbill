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
(getPurchases, getSkuDetails)->getBuyIntent->onActivityResult

###4 Methods for In-app Billing
