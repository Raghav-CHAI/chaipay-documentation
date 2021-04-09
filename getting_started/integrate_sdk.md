---
layout: default
title: SDK Integration
parent: Getting started
nav_order: 3
order: 3
---

# Integrate JS SDK
---

- Embed the following javascript in the checkout page.

```javascript
<script src="https://cdn.jsdelivr.net/npm/axios@0.18.0/dist/axios.min.js"></script>
<script src="https://iamport-admin-vuejs-main.herokuapp.com/js/chaipay.js"></script>
```

- Use following JS code snippet to initiate the payment using the respective supported payment channels (e.g. MomoPay, ZaloPay, Mastercard, etc).

```javascript
<script>
const chaipay = new window.ChaiPay({
    // Your Chai Pay Key
    chaiPayKey: 'pptafmcddmszvgXl'
})

chaipay.paymentService.payment({
    // new uniform payment request format example for Momopay
    "pmt_channel": "MOMOPAY",
    "pmt_method": "MOMOPAY_TESTWALLET",
    "merchant_order_id":"MERCHANT1617366877238",
    "amount": 1000,
    "currency": "VND",
    "billing_details": {
        "billing_name": "Mark Weins",
        "billing_email": "markweins@gmail.com",
        "billing_phone": "1234567890",
        "billing_address": {
            "city": "Ho Chi Minh City",
            "country_code": "VN",
            "locale": "en",
            "line_1": "address_1",
            "line_2": "address_2",
            "postal_code": "400202",
            "state": "Mah"
        }
    },
    "shipping_details": {
        "shipping_name": "Mark Weins",
        "shipping_email": "markweins@gmail.com",
        "shipping_phone": "1234567890",
        "shipping_address": {
            "city": "Ho Chi Minh City",
            "country_code": "VN",
            "locale": "en",
            "line_1": "address_1",
            "line_2": "address_2",
            "postal_code": "400202",
            "state": "Mah"
        }
    },
    "order_details": [
        {
            "id": "knb",
            "name": "kim nguyen bao",
            "price": 1000,
            "quantity": 1
        }
    ],
    "success_url": "http://www.coolmate.me/result/success",
    "failure_url": "http://www.coolmate.me/result/failure",
})
</script>
```

- For ZaloPay use following values in payload

```javascript
    "pmt_channel": "ZALOPAY",
    "pmt_method": "ZALOPAY_TESTWALLET",
```

---
