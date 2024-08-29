---
description: >-
  Viction DA, the interconnecting data layer for Web3, breaking down
  communication barriers between blockchain platforms.
---

# Viction DA RPC API

You can make JSON RPC calls to Viction via those following URLs:

**DA-Testnet:** [https://da-testnet.viction.xyz](https://da-testnet.viction.xyz)

**DA-Mainnet:** [https://da.viction.xyz](https://da.viction.xyz)



{% file src="../.gitbook/assets/Viction DA Collection.postman_collection.json" %}

## Postman collection



## Commit data

<mark style="color:yellow;">`POST`</mark> `/commit`

Commit data to the DA Layer & returns Commitment for each given Blob



**RequestBody:** The argument is byte array

{% tabs %}
{% tab title="Body" %}
```json
{
    "jsonrpc": "2.0",
    "id": 128,
    "method": "commit",
    "params": [
        [
            [
                104,
                101,
                108,
                108,
                111
            ]
        ],
        "namespace"
    ]
}
```
{% endtab %}
{% endtabs %}

**Response**

Success response should return an array of commitments of the byte array

{% tabs %}
{% tab title="200" %}
```json
{
    "jsonrpc": "2.0",
    "result": [
        [
            179,
            75,
            83,
            34,
            165,
            175,
            249,
            223,
            47,
            197,
            64,
            246,
            39,
            144,
            246,
            178,
            41,
            129,
            180,
            213,
            74,
            140,
            54,
            81,
            194,
            150,
            87,
            48,
            172,
            66,
            114,
            200,
            132,
            185,
            173,
            238,
            171,
            189,
            233,
            151,
            60,
            138,
            111,
            177,
            2,
            96,
            22,
            134
        ]
    ],
    "id": 128
}
```
{% endtab %}

{% tab title="400" %}
```json
{
  "error": "Invalid request"
}
```
{% endtab %}
{% endtabs %}



## Get Blob

<mark style="color:green;">`GET`</mark> `/get`

Return Blob for each given ID

**RequestBody**

{% tabs %}
{% tab title="Body" %}
```json
{
    "jsonrpc":"2.0",
    "id": 128,
        "method": "get",
    "params": [
        [
            [1,97,54,102,57,50,55,97,102,51,53,100,98,50,50,100,49,55,98,53,51,100,55,102,54,51,97,52,98,52,97,102,102,99,55,48,49,48,55,100,54,56,49,97,98,101,98,48,102,97,53,50,53,57,57,101,56,57,50,57,49,54,99,97]
        ],
        "namespace"
    ]
}
```
{% endtab %}
{% endtabs %}



**Response**

{% tabs %}
{% tab title="200" %}
```json
{
    "jsonrpc": "2.0",
    "result": [
        [
            104,
            101,
            108,
            108,
            111
        ]
    ],
    "id": 128
}
```
{% endtab %}

{% tab title="400" %}
```json
{
  "error": "Invalid request"
}
```
{% endtab %}
{% endtabs %}

!!! In case there is no data in storage(means nothing was submitted before) it returns `empty bytes array`

## Get Proof

<mark style="color:green;">`GET`</mark> `/get_proofs`

Return Proofs for each given ID

**RequestBody**

{% tabs %}
{% tab title="Body" %}
```json
{
    "jsonrpc":"2.0",
    "id": 128,
    "method": "get_proofs",
    "params": [
        [
            [1,97,54,102,57,50,55,97,102,51,53,100,98,50,50,100,49,55,98,53,51,100,55,102,54,51,97,52,98,52,97,102,102,99,55,48,49,48,55,100,54,56,49,97,98,101,98,48,102,97,53,50,53,57,57,101,56,57,50,57,49,54,99,97]
        ],
        "namespace"
    ]
}
```
{% endtab %}
{% endtabs %}



**Response**

{% tabs %}
{% tab title="200" %}
```json
{
    "jsonrpc": "2.0",
    "result": [
        [
            166,
            226,
            152,
            3,
            148,
            197,
            142,
            68,
            37,
            3,
            30,
            235,
            83,
            168,
            156,
            244,
            25,
            94,
            85,
            95,
            38,
            18,
            205,
            209,
            242,
            109,
            0,
            45,
            121,
            48,
            13,
            160,
            133,
            205,
            96,
            223,
            139,
            179,
            76,
            141,
            151,
            183,
            74,
            156,
            153,
            101,
            48,
            136
        ]
    ],
    "id": 128
}
```
{% endtab %}

{% tab title="400" %}
```json
{
  "error": "Invalid request"
}
```
{% endtab %}
{% endtabs %}



## Submit

<mark style="color:yellow;">`POST`</mark> `/submit`

Submit data to Data layer & returns tuple of ID and Commitment for each given Blob

**RequestBody**

{% tabs %}
{% tab title="Body" %}
```json
{
    "jsonrpc":"2.0",
    "id": 128,
    "method": "submit",
    "params": [
        [[104,101,108,108,111]],
        "namespace"
    ]
}
```
{% endtab %}
{% endtabs %}

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
    "jsonrpc":"2.0",
    "result":[
        [
            [50,99,102,50,52,100,98,97,53,102,98,48,97,51,48,101,50,54,101,56,51,98,50,97,99,53,98,57,101,50,57,101,49,98,49,54,49,101,53,99,49,102,97,55,52,50,53,101,55,51,48,52,51,51,54,50,57,51,56,98,57,56,50,52],
            [166,54,159,144,72,207,81,43,3,233,138,181,14,56,147,45,171,85,142,173,92,28,238,112,164,213,203,130,110,6,33,97,93,73,204,147,28,226,140,248,191,103,232,253,200,84,209,89]
        ]
    ],
    "id":128
}
```
{% endtab %}

{% tab title="400" %}
```json
{
  "error": "Invalid request"
}
```
{% endtab %}
{% endtabs %}



## Validate

<mark style="color:yellow;">`POST`</mark> `/validate`

Request body 1st params argument is a "hello" string Id and Commitment**("${Id}-{Commitment}")**

Kindly view `Submit` example 2nd onw is a data with corrupted proof byte array

**RequestBody**

`ERROR RESPONSE` In case the request has invalid params

{% tabs %}
{% tab title="Body" %}
```json
   {
    "jsonrpc":"2.0",
    "id": 128,
    "method": "validate",
    "params": [
        [
            [1,97,54,102,57,50,55,97,102,51,53,100,98,50,50,100,49,55,98,53,51,100,55,102,54,51,97,52,98,52,97,102,102,99,55,48,49,48,55,100,54,56,49,97,98,101,98,48,102,97,53,50,53,57,57,101,56,57,50,57,49,54,99,97]
        ],
        [
            [179,75,83,34,165,175,249,223,47,197,64,246,39,144,246,178,41,129,180,213,74,140,54,81,194,150,87,48,172,66,114,200,132,185,173,238,171,189,233,151,60,138,111,177,2,96,22,134]
        ],
        [
            [166,226,152,3,148,197,142,68,37,3,30,235,83,168,156,244,25,94,85,95,38,18,205,209,242,109,0,45,121,48,13,160,133,205,96,223,139,179,76,141,151,183,74,156,153,101,48,136]
        ],
        "namespace"
    ]
}
```
{% endtab %}

{% tab title="Invalid Body" %}
```json
{
    "jsonrpc":"2.0",
    "id": 128,
    "method": "submit",
    "params": [22]
}
```
{% endtab %}
{% endtabs %}



**Response**

Success response should return **true** and **false**

{% tabs %}
{% tab title="200" %}
```json
{
    "jsonrpc": "2.0",
    "result": [
        true
    ],
    "id": 128
}
```
{% endtab %}

{% tab title="200 with Error response" %}
```json
{
    "jsonrpc": "2.0",
    "error": {
        "code": -32602,
        "message": "Invalid params",
        "data": "invalid type: integer `22`, expected byte array at line 1 column 3"
    },
    "id": 128
}
```
{% endtab %}

{% tab title="400" %}
```json
{
  "error": "Invalid request"
}
```
{% endtab %}
{% endtabs %}

!!! In case there is no data in storage(means nothing was submitted before) it returns `false` validation result

