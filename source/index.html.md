---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - curl

toc_footers:
  - <a href='#'>Get in Touch with Blockchain Technologies</a>
  - <a href='#'>Documentation created by Kesholabs Team</a>

includes:
  - errors

search: true

code_clipboard: true
---

# Introduction

Welcome to the **BlockchainTechnologies Limited(LTD)** API! *Documetation.*

You can use our API to access Blockchain technologies Know Your Transaction (KYT) API endpoints,
which can get  live and historical transaction data from major blockchain Chains { Bitcoin  & Ethereum }

<!-- We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/slatedocs/slate). Feel free to edit it and use it as a base for your own API's documentation. -->

# Ethereum

## Get All Flagged Transactions

```shell
curl -X GET "http://35.239.97.241:8000/api/v1/Ethereum/alerts"
    -H "accept: application/json"
  
```

```javascript

```

> The above command returns JSON structured like this:

```json
 [
   {
  "message": "OK",
  "data": [
    {
      "chain": "Ethereum",
      "amount": 89.997404,
      "transactionHash": "0c64f96eb6aeb174107428ba7e1492927d1223269900e883afdfa38faf6850aa",
      "transactionDate": "6/22/2020",
      "transactionDetails": [
        {
          "From": "1H9oF8DuCitD6CxvaaWWVybM3sEchoVWzd",
          "value": 89.997404,
          "confirmed": 338
        }
      ]
    }
  ]
  }
 ]
```

This endpoint retrieves all transactions that been  flagged on Ethereum Chain.



### HTTP Request

`GET http://35.239.97.241:8000/api/v1/Ethereum/alerts`

 <a href='http://35.239.97.241:8000/api-docs/#/Ethereum%20/get_Ethereum_alerts'>click here  to try out </a>

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
no parameters Accepted | --------|--------

<aside class="primary">
Remember — a this are only transactions that have transacted above 500 ETH!
</aside>

## All transactions of address


```shell
curl -X GET "http://35.239.97.241:8000/api/v1/Ethereum/0x3868CC0c31A8B868C9AE98840C9bDab5C5DB65d4" 
  -H "accept: */*"
```

> The above command returns JSON structured like this:

```json
{
  "message": "OK",
  "data": [
    {
      "time": "6/25/2020",
      "value": "0.20090294",
      "to": "0x986ccf5234d9cfbb25246f1a5bfa51f4ccfcb308",
      "from": "0x590cf475c0c98e00079f5c2572cc1ffc6cf4f5b7",
      "transactionStatus": "1",
      "transactionHash": "0x1105d47c241c8d74772a8514a51b65fe0bdd91714ce2c75c95f80f1722256687"
    }....
  ]
}
```

This endpoint retrieves a specific Address transactions .

<!-- <aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside> -->

### HTTP Request

`GET http://35.239.97.241:8000/api/v1/Ethereum/{Address}`

<a href='http://35.239.97.241:8000/api-docs/#/Ethereum%20/get_Ethereum_alerts'>click here  to try out </a>

### URL Parameters

Parameter | Description
--------- | -----------
Address | The  Ethereum Address of the account to retrieve

## Get Specific transaction by Hash

```shell
   curl -X GET "http://35.239.97.241:8000/api/v1/Ethereum/tx/{TransactionHash}" 
   -H "accept: */*"
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "txId": "18f166fbfba28d4a67f80642164b0756e6e17faf511fdcfa11dff5ad67be64b9",
    "value": 0.23687965,
    "blockhash": "000000000000000000027a59435ea0dadaff542615927ba1bb44df4af29ff988",
    "confirmations": 1,
    "transactionhash": "18f166fbfba28d4a67f80642164b0756e6e17faf511fdcfa11dff5ad67be64b9",
    "sender": "1FJCU7bq3bA8btrZF46hDXpTSNum6Zy2vD",
    "Time": "6/25/2020"
  }
}
```

This endpoint get transaction detail of a specific transaction by hash


### HTTP Request

`GET http://35.239.97.241:8000/api/v1/Ethereum/{TransactionHash}`

 <a href='http://35.239.97.241:8000/api-docs/#/Ethereum%20/get_Ethereum_alerts'>click here  to try out </a>

### URL Parameters

Parameter | Description
--------- | -----------
Transaction Hash  | The Hash of the transaction tto get 

# Bitcoin

## Get All Flagged Transactions

```shell
curl -X GET "http://35.239.97.241:8000/api/v1/Bitcoin/alerts"
    -H "accept: application/json"
```

> The above command returns JSON structured like this:

```json
 [
   {
  "message": "OK",
  "data": [
    {
      "chain": "Bitcoin",
      "txId": "0c64f96eb6aeb174107428ba7e1492927d1223269900e883afdfa38faf6850aa",
      "amount": 89.997404,
      "blockhash": "000000000000000000091f4074dc2bb86a5e33a078624a9f3f050fdead202037",
      "confirmations": 338,
      "transactionHash": "0c64f96eb6aeb174107428ba7e1492927d1223269900e883afdfa38faf6850aa",
      "sender": "1H9oF8DuCitD6CxvaaWWVybM3sEchoVWzd",
      "transactionDate": "6/22/2020",
      "transactionDetails": [
        {
          "From": "1H9oF8DuCitD6CxvaaWWVybM3sEchoVWzd",
          "value": 89.997404,
          "confirmed": 338
        }
      ]
    }
  ]
  }
 ]
```

This endpoint retrieves all transactions that been  flagged on Bitcoin Chain.



### HTTP Request

`GET http://35.239.97.241:8000/api/v1/Bitcoin/alerts`

 <a href='http://35.239.97.241:8000/api-docs/#/Bitcoin/get_Bitcoin_alerts'>click here  to try out </a>

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
This Endpoint Doesn't accept any parameters | -------| ---------

<aside class="success">
Remember — a this are only transactions that have transacted above 10 Bitcoins!
</aside>

## All transactions of address


```shell
curl -X GET "http://35.239.97.241:8000/api/v1/Bitcoin/1FJCU7bq3bA8btrZF46hDXpTSNum6Zy2vD"
 -H "accept: */*"
```

> The above command returns JSON structured like this:

```json
{
  "data": [
    {
      "hash": "18f166fbfba28d4a67f80642164b0756e6e17faf511fdcfa11dff5ad67be64b9",
      "value": 0.23687965,
      "time": "6/25/2020",
      "addresses": [
        "1FJCU7bq3bA8btrZF46hDXpTSNum6Zy2vD",
        "3NxfgCJqSxHN29hGmp6oK6yAGjL2HUtqnc"
      ]
    }
  ]
}
```

This endpoint retrieves all transactions transacted by  specific Bitcoin .

<!-- <aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside> -->

### HTTP Request

`GET http://35.239.97.241:8000/api/v1/Bitcoin/{Address}`

 <a href=' http://35.239.97.241:8000/api-docs/#/Bitcoin/get_Bitcoin__address_'>click here  to try out </a>

### URL Parameters

Parameter | Description
--------- | -----------
Address |  **Valid** Bitcoin Address of the account to retrieve

<aside class="primary">
Remember — a this are all transactions that have been transacted to and from  by the address!
</aside>

## Get Specific transaction by Hash

```shell
  curl -X GET "http://35.239.97.241:8000/api/v1/Bitcoin/tx/18f166fbfba28d4a67f80642164b0756e6e17faf511fdcfa11dff5ad67be64b9"
  -H "accept: */*"
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "txId": "18f166fbfba28d4a67f80642164b0756e6e17faf511fdcfa11dff5ad67be64b9",
    "value": 0.23687965,
    "blockhash": "000000000000000000027a59435ea0dadaff542615927ba1bb44df4af29ff988",
    "confirmations": 1,
    "transactionhash": "18f166fbfba28d4a67f80642164b0756e6e17faf511fdcfa11dff5ad67be64b9",
    "sender": "1FJCU7bq3bA8btrZF46hDXpTSNum6Zy2vD",
    "Time": "6/25/2020"
  }
}
```

This endpoint get transaction detail of a specific transaction by hash

### HTTP Request

`GET http://35.239.97.241:8000/api/v1/Bitcoin/tx/{TransactionHash}`

 <a href='http://35.239.97.241:8000/api-docs/#/Bitcoin/get_Bitcoin_tx__txhash'>click here  to try out </a>

### URL Parameters

Parameter | Description
--------- | -----------
Transaction Hash  | The Hash of the transaction to get