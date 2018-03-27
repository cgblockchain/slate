---
title: CG API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='#'>More info</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the CG API Documentation! You can use our API to access CG API endpoints.


# New Order api/v1/order

> To create new Order, use this code:

```shell
# With curl, you can just pass the correct header with each request
curl -X POST \
  -d "{
        "ORDER_ATTRIBUTES" : {
          "PROGRAM_ID": "",
          "PARENT_ID": "",
          "QUANTITY": "",
          "SIDE": "",
          "PRICE": "",
          "ALLOCATIONS": :[
            {
              "ALLOCATION_ACCOUNT": "",
              "ALLOCATION_QUANTITY: """
            }
          ],
          "PRICE_TYPE_QUALIFIER": "",
          "TIF": "",
          "EXPIRY": "",
          "SETTLEMENT_DATE": "",
          "CCY_PAIR": "",
          "FIXING_DATE": "",
          "ORDER_TYPE": "",
          "STOP_PRICE": "",
          "PAR_VALUE": "",
          "MATURITY_DATE": "",
          "STRIKE_PRICE": "",
          "EXECUTED_VOLUME": "",
          "COMMITTED_VOLUME": "",
          "OWNER": "",
          "ORDER_ATTRIBUTE_ID": "",

        },
        "SECURITY" : {
          "CCY_PAIR_NEAR_DATE_FAR_DATE_ENTERED_TIMESTAMP": "",
          "SEDOL": "",
          "OCC_Symbol": "",
          "TICKER": "",
          "Instrument_Symbol": "",
          "SECURITY_ID: """

        },
        "SENDER" : {
          "FIRM_ID": "",
          "USER": "",
          "TIMESTAMP": "",
          "SENDER_ID": "",

        },
        "ORDER_STATUS": {
          "NEW_ORDER": "",
          "ORDER_AMEND": "",
          "ORDER_CANCEL": "",
          "ORDER_COMPLETE": "",
          "SENT_TO_TRADE": "",
          "PARENT_ORDER_CREATION": "",
          "ARCHIVE": "",
          "ORDER_STATUS_ID: """

        }

    }" \
  -u "<client_id>:<client_secret>" {base_url}{url}

```



> Base URL is the follow for all the endpoints `http://cg-api.com/` and url is `api/v1/order` .

CG uses API keys with Oauth authetication to allow access to the API. You can register a new cg API key at our [developer portal](#).



<aside class="notice">
Just sure to have the correct credentials every endpoint
</aside>

# Payload

## Get the PDF CG !

```shell
curl -X POST \
  http://www.cg.info/api/v1/sign/ \
  -H 'authorization: Bearer 12hRiSaV7M97hILdzEBpc3IgIBhyKB' \
  -H 'content-type: application/json' \
  -d '{

}'
```

> Make sure to replace Bearer 12hRiSaV7M97hILdzEBpc3IgIBhyKB with your own Access Token, get it in the previous step.

> That's all

This endpoint retrieves the pdf CG .

### HTTP Request

`POST http://www.cg.info/api/v1/sign/`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timezone | "UTC" | A valid timezone string code, Optional field by default "UTC"
pdf | A base64 File String | This is your pdf who is attach it to the signed doc, will be signed every page.
params.title | String | The title of the given pdf
params.file_name | String title | The filename with his extension, `mytitle.pdf`
params.logo | A png base 64 File String | This is your logo who will be show on the signed pdf.
signatures.hash | A hash string | This hash string is the sign of a person, represented as string.
signatures.email | Email String | The email of the person.
signatures.name | String | The name of the person.


<aside class="success">
  Note: ""
</aside>

<aside class="info">
  Another note
</aside>
