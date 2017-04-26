---

copyright:

  years: 2017

lastupdated: "2017-04-26"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}


# Getting started with PayPal for IBM Cloud

## Special Notes for Integrating with PayPal
When completing a transaction using PayPal, we recommend adding the **BUTTONSOURCE** parameter to the API operation.  The **BUTTONSOURCE** parameter is a code that is used by PayPal to identify the transactions were integrated with the Bluemix platform.

### Express Checkout transactions

In the **DoExpressCheckoutPayment** API operation, add the following parameter and value.

```
BUTTONSOURCE=Bluemix_SP
```

### PayPal Payments Pro transactions

In the **DoDirectPayment** API operation, add the following parameter and value.

```
BUTTONSOURCE=Bluemix_SP
```
 
PayPal is the faster, safer way to pay and get paid online, via a mobile device and in store. It allows a person to send money without sharing financial information, with the flexibility to pay using their account balances, bank accounts, credit cards or promotional financing.

##PayPal Overview

###PayPal Express Checkout
Add PayPal as a payment option to any checkout with Express Checkout. Express Checkout offers the ease of convenience and security of PayPal, can be set up in minutes and turns more shoppers into buyers. 

* Increase conversions - PayPal customers transact nearly twice as often as non-PayPal customers
* Faster checkout - Customers can bypass guest checkout pages to avoid entering billing and shipping information.
* Grow your customer base - Recent testing at major retailers showed that after PayPal was integrated, total customers increased by 27%.

####PayPal Express Checkout Fees
2.9% + $0.30. Volume and non-profit discounts are available upon approval. ec base rate of 2.9% + $0.30 per transaction with no monthly fees, hidden fees or surcharges. Lower rates start at just $3,000 per month in transaction volume. 

###PayPal Payments Pro
PayPal Payments Pro has the customization capability, technical maturity, and proven security that is needed to build professional-grade eCommerce sites. Plus, because it’s from PayPal it enables you to offer more ways to get paid from a broader audience, 148+ million to be exact. 


* Fully customizable - PayPal Payments Pro is a true enterprise-class payments system that can be configured in any way that your business demands. If you’re looking for shopping cart integration you’re in luck. PayPal supports almost all major shopping carts out of the box.
* All payments accepted - PayPal gives your customers more payment options at checkout, which increases your chances of getting the sale. With PayPal you can accept credit & debit cards, bank transfers, phone payments, and in-person payments.
* Offer customer financing - PayPal Credit offers your customers the chance to buy now and pay later with special financing. The best part is that your get paid right away with no wait. PayPal Credit is built in to the PayPal checkout at no extra cost.

####PayPal Payments Pro Fees
$30 per month, plus 2.9% + $0.30 per transaction.
Discounts available for large volume customers and non-profits. No hidden fees or surcharges. 

