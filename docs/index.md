# Payments Auth Documentation

API reference for Auth endpoints and webhooks

Retrieve bank account information to set up electronic funds transfers, such as ACH payments in the US, EFT payments in Canada, BACS payments in the UK, and IBAN / SIC payments in the EU.

The Payments Auth Microservice allows you to request a user's checking or savings account and routing number, making it easy for you to initiate credits or debits via ACH, wire transfer, or equivalent international networks. For example, your app might allow users to accumulate a credit balance that they can cash out to a bank account, or it might allow users to pay you using their bank account information (pay by bank). With Payments Auth, a user can provide this information in a frictionless way, simply by authenticating into their bank account.

Auth can only be used with checking or savings accounts. Auth cannot be used with other depository accounts, such as money market accounts. Credit-type accounts, including credit cards, cannot receive payments directly via electronic interbank transfers, and Auth data cannot be used to set up credit card payments. Auth can not be used to connect debit cards; instead, you can make a transfer directly from the user's bank account, saving you money over using the debit card network.

## Using a Payments Service
Looking for bank-to-bank transfer capabilities and don't have a payment processor yet? Check out our recommended Transfer service (US only) for a comprehensive money movement solution with built-in payment processing capabilities.

When using Payments Auth, you will send Auth data to a payments service to initiate an interbank transfer; the Payments Auth Microservice does not function as the payment processor. While our service is processor-agnostic and allows you to work with any partner you want, one easy way to make transfers is to work with a payments platform that partners with us, such as Dwolla or Stripe. Working with these partners, you will not call the /auth/get endpoint, so you will not obtain a user's bank account information. Instead, you will call /processor/token/create or /processor/stripe/bank_account_token/create to obtain a token that you will provide to the partner and that allows them to make these API calls as needed.

If you choose to use a payments provider who is not a partner, you will need to obtain bank account numbers and codes using /auth/get. Given the sensitive nature of this information, we recommend that you consult the Open Finance Data Security Standard for security best practices. We also recommend that you do not store account numbers. You can integrate with one of our Data Security partners to process and share tokenized bank account numbers instead of raw bank account numbers. Contact your Account Manager to learn more about these partnerships.

## The Auth microservice offers the following endpoints:

- `GET /auth/get`: Fetch account information.
- `GET /bank_transfer/event/list`: Search for micro-deposit verification updates.
- `GET /bank_transfer/event/sync`: Get updates on micro-deposit verification statuses.

