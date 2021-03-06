﻿# Search and Reconciliation

An important part of the generation of payments is the reconciliation. The API allows you to search your `advanced payments` in order to reconcile all the transactions that were made through your Marketplace.

It is possible to search through the Advanced Payments API.

#### Request
```curl
curl -X POST \
    -H 'Accept":"application/json' \
    -H 'Content-Type: application/json' \
    'https://api.mercadopago.com/v1/advanced_payments/search?access_token=MKT_ACCESS_TOKEN&limit=10&offset=0'
```

#### Response
Which returns the results in a structure that also shows the amount of results and information for its pagination.
```json
{
  "paging": {
    "total": 3,
    "limit": 10,
    "offset": 0
  },
  "results": [
    {
      "id": 11111111,
      "status": "approved",
      ...
    },
    {
      "id": 22222222,
      "status": "rejected",
      ...
    },
    {
      "id": 33333333,
      "status": "pending",
      ...
    }
  ]
}
```

#### Search filters

State                       |Description                                                            |
----------------------------|-----------------------------------------------------------------------|
date_created                |Advanced Payment creation date.                                        |
status                      |Advanced Payment status.                                               |
payment.id                  |Buyer’s payment ID.                                                    |
payment.payment_method_id   |Payment method.                                                        |
payment.external_reference  |ID generated for this particular entry payment.                        |
payment.transaction_amount  |Payment amount.                                                        |
payer.id                    |Buyer ID.                                                              |
payer.email                 |Buyer’s email address.                                                 |
disbursement.collector_id   |Seller ID.                                                             |
external_reference          |ID generated by the marketplace which identifies the Advanced Payment. |

### Export Activities

There is also the possibility of exporting the activities from the list of your Mercado Pago account with the link `Export`.

![export_activities](/images/advanced-payments/export_activities_es.png)

You can select the filters you need and choose the CSV or XLS format to perform the reconciliation manually.

![export_activities_2](/images/advanced-payments/export_activities_2_es.png)
