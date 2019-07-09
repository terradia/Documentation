
# IAP Purchases
## Technologies

Currently mobiles applications can use 3 types of technologies for payments.

 - IAP Purchases (In App Purchases)
 - Stripe (this is an exemple we can use other technologies for cards)
 - Paypal

## Cost
Depending to the used technology cost are different.
Stripe : 2.9 % + 0.30 $ for every successful card charge
IAP: 30% for every successful card charge

Obviously the best choice is stripe. But according to the application we can't use Stripe in all cases.

## IAP or Stripe

If  your application sell virtual products you must use IAP, otherwise you sell real products you are allowed to use stripe, PayPal...

## UI and UX

STRIPE: Stripe is an Api, provided by Javascript packages. Then you should make you own view, and your UI and UX will fit with your application. When transaction is done stripe respond an object with contain all payments informations.

IAP: The design is already made by the StoreKit framework, and kits the same for all application, but easier to deploy on application because you don't have to create a view.

## Exemple
IAP: You made a game like clash of clan and and sell virtual money called gem, then you must use IAP and pay 30 % fees.

STRIPE: You made an application like deliver where you sell food then you are allowed to use stripe.

Useful link: https://medium.com/@jessesahli3/ios-renewable-subscriptions-overview-stripe-vs-in-app-purchases-4fdb02bec0da