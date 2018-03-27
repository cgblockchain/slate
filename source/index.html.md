---
title: CG API Reference

language_tabs:
  - shell
  - python(`TODO`)

toc_footers:
  - <a href='#'>More info</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the CG API Documentation! You can use our API to access CG API endpoints.


# New Order `POST api/v1/NewOrder`

> To authorize, use this code:

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
          "ALLOCATIONS": : ""[
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
  -u "<client_id>:<client_secret>" {base_url/url}

```

```python
import requests
from requests.auth import HTTPBasicAuth
headers = {
  "Content-Type" : "application/json"
}
data = {
  "grant_type" : "password",
  "username" : "<username>",
  "password" : "<password>"
}
auth = HTTPBasicAuth('<client_id>', '<client_secret>')

response = requests.post('http://www.cg.info/oauth/token/',
            auth=auth, json=data, headers=headers)

```

> The above command returns JSON structured like this:

```json
{

}
```

> Base URL is the follow for all the endpoints `http://cg-api.com/` .

CG uses API keys with Oauth authetication to allow access to the API. You can register a new cg API key at our [developer portal](oauth/applications/).

cg expects for the Token Access to be included in all API requests to the server in a header that looks like the following:

`Authorization: Bearer meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
Just be sure that <code>Authorization grant type</code> is set to <code>Resource owner password-cased</code> when create a new Application API.
</aside>

# Payload

## Get the PDF Crypto Signed!

```shell
curl -X POST \
  http://www.cg.info/api/v1/sign/ \
  -H 'authorization: Bearer 12hRiSaV7M97hILdzEBpc3IgIBhyKB' \
  -H 'content-type: application/json' \
  -d '{

}'
```

> Make sure to replace Bearer 12hRiSaV7M97hILdzEBpc3IgIBhyKB with your own Access Token, get it in the previous step.

```python
import requests

ACCESS_TOKEN = "12hRiSaV7M97hILdzEBpc3IgIBhyKB" # Get it with the previous step.

headers = {
  "Authorization": "Bearer {}".format(ACCESS_TOKEN),
  "Content-Type" : "application/json"
}

data ={

}

response = requests.post('{urlbase}{urlendpoint}'.format(),json=data, headers=headers)

# save it
with open("./myfile.pdf", "wb") as f:
    f.write(response.content)

# or display it
print(response.content)

```


> That's all

This endpoint retrieves the pdf crypto signed.

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
