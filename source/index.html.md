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
Every endpoint will use CRUD based on API RestFul implementation.
You need to change {base_url} for base url our site that is `https://www.cgblockchain.com/` and then use endpoint url that every endpoint has, i.e `New Order ENDPOINT "url" : "api/v1/neworder"` `https://www.cgblockchain.com/api/v1/neworder`


# Order  `api/v1/order`

## New order

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



> Base URL is the follow for all the endpoints `https://www.cgblockchain.com/` and url for this endpoint is `api/v1/order` .


<aside class="notice">
Just sure to have the correct credentials every endpoint
</aside>

## Order Ammend

## Order Cancel/Complete

## Run compliance

## Sent to trade
## Parent Order Creation

# Assign / adquire
# Merge/split
## Merge
## Split
# Sweep
# Placements

## New Placement
## Placement Amend
## Placement Cancel
# Executions
## Execution
## Execution ammend
## Execution cancel


# Post Trade Allocation
# Exeption
# archive


