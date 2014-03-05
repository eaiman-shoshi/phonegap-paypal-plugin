phonegap-paypal-plugin
======================
<h1><s>Not under maintanance</s></h1>
<h3>Android part is functional, you can use it for Phonegap Android part</h3>
**(iOS part is under Construction, please don't use it for your project)**

<h3>Installation:</h3>
    cordova plugin add https://github.com/Eaiman/phonegap-paypal-plugin.git
    or
    phonegap local plugin add https://github.com/Eaiman/phonegap-paypal-plugin.git

<h3>NOTE:</h3>
    For live mode, you don't need to set any environment or use "PayPalEnvironmentProduction".
    There are three Environment available. Choices are:
      1. PayPalEnvironmentNoNetwork
      2. PayPalEnvironmentSandbox
      3. PayPalEnvironmentProduction
    When you call presentPaymentUI() method, you can pass "someuser@somedomain.com" as null.
    For further information check out these links:
      1. http://stackoverflow.com/questions/19507904/is-there-any-documentation-on-what-if-any-controls-we-have-over-the-sdk#19552043
      2. http://stackoverflow.com/questions/18980564/what-is-payerid-in-paypal-ios-sdk#18994299
    

<h3>Code sample:</h3>

          // See PayPalMobilePGPlugin.js for better understanding
		  // set environment you want to use
		  window.plugins.PayPalMobile.setEnvironment("PayPalEnvironmentNoNetwork");

		  // define a callback when payment has been completed
		  var completionCallback = function(proofOfPayment) {
		  // TODO: Send this result to the server for verification;
		  // see "https://developer.paypal.com/webapps/developer/docs/integration/mobile/verify-mobile-payment/"
		     for details.
		    console.log("Proof of payment: " + JSON.stringify(proofOfPayment));
		  }

		  // define a callback if payment has been canceled
		  var cancelCallback = function(reason) {
		    console.log("Payment cancelled: " + reason);
		  }

		  // launch UI, the PayPal UI will be present on screen until user cancels it or payment completed
		  window.plugins.PayPalMobile.presentPaymentUI("YOUR_CLIENT_ID", "YOUR_PAYPAL_EMAIL_ADDRESS", 
		        "someuser@somedomain.com", ["1.99", "USD", "Awesome saws"], completionCallback, cancelCallback);

A simple paypal phonegap plugin only for android and ios.

For any questions or information check out: http://www.technextit.com

    Developer (Android): Eaiman Shoshi
    Developer (iOS): Ashraful Prium
    Email: coolshoshi.cse@gmail.com
  
Feel free to use it in your project. And let me know about any issue about this plugin.

Technext
