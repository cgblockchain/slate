---
title: CryptoSign API Reference

language_tabs:
  - shell
  - python

toc_footers:
  - <a href='https://cryptosign.herokuapp.com/'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the CryptoSign API Documentation! You can use our API to access Cryptosign API endpoints, which can get information about how auth and to send payloads to retrieve a pdf signed.

We have language bindings in curl on shell and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.


# Authentication

> To authorize, use this code:

```shell
# With curl, you can just pass the correct header with each request
curl -X POST \
  -d "grant_type=password&username=<username>&password=<password>" \
  -u "<client_id>:<client_secret>" https://cryptosign.herokuapp.com/oauth/token/

```

```python
import requests
from requests.auth import HTTPBasicAuth

data = {
  "grant_type" : "password",
  "username" : "<username>",
  "password" : "<password>"
}
auth = HTTPBasicAuth('<client_id>', '<client_secret>')

response = requests.post('https://cryptosign.herokuapp.com/oauth/token/', auth=auth, data=data)

```

> Make sure to replace `<username>` with your username, `<password>` with your password, `<client_id>` with your client ID and `<client_secret>` with your client secret key.

Cryptosign uses API keys with Oauth authetication to allow access to the API. You can register a new Cryptosign API key at our [developer portal](http://cryptosign.herokuapp.com/oauth/applications/).

Cryptosign expects for the Token Access to be included in all API requests to the server in a header that looks like the following:

`Authorization: Bearer meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
Just be sure that <code>Authorization grant type</code> is set to <code>Resource owner password-cased</code> when create a new Application API.
</aside>

# Payload

## Get All Kittens

```ruby
require 'Cryptosign'

api = Cryptosign::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import Cryptosign

api = Cryptosign.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const Cryptosign = require('Cryptosign');

let api = Cryptosign.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'Cryptosign'

api = Cryptosign::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import Cryptosign

api = Cryptosign.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const Cryptosign = require('Cryptosign');

let api = Cryptosign.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

