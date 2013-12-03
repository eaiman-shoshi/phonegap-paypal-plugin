phonegap-paypal-plugin
======================
<h3>Android part is functional, you can use it for Phonegap Android part</h3>
**(iOS part is under Construction, please don't use it in your project)**

<h3>NOTE:</h3>
    <ul>
    <li>For live mode, you don't need to set any environment or use "PayPalEnvironmentProduction".</li>
    <li>There are three Environment available. Choices are:
      <ul>
      <li>1. PayPalEnvironmentNoNetwork</li>
      <li>2. PayPalEnvironmentSandbox</li>
      <li>3. PayPalEnvironmentProduction</li>
      </ul>
    <li>When you call presentPaymentUI() method, you can pass "someuser@somedomain.com" as null.
      <ul>
       <li>For further information check out these links:</li>
       <li>1. http://stackoverflow.com/questions/19507904/is-there-any-documentation-on-what-if-any-controls-we-have-over-the-sdk#19552043</li>
       <li>2. http://stackoverflow.com/questions/18980564/what-is-payerid-in-paypal-ios-sdk#18994299</li>
       </ul>
    </li>   
    </ul>
    

<h3>Code sample:</h3>

             // See PayPalMobilePGPlugin.js for full documentation
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

Technext
