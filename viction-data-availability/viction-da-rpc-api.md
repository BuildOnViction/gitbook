# Viction DA RPC API

You can make JSON RPC calls to Viction DA-Testnet endpoints at [https://da.viction.xyz](https://da.viction.xyz)



{% hint style="info" %}
Viction DA Mainnet will be released soon. Stay tuned!
{% endhint %}

## Commit data

<mark style="color:yellow;">`POST`</mark> `/commit`

Commit data to the DA Layer & returns Commitment for each given Blob



**RequestBody:** The argument is byte array

{% tabs %}
{% tab title="Body" %}
```json
   {
    "jsonrpc":"2.0",
    "id": 128,
    "method": "commit",
    "params": [[
            104,
            101,
            108,
            108,
            111
        ]]
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
    "jsonrpc":"2.0",
    "result":[[166,54,159,144,72,207,81,43,3,233,138,181,14,56,147,45,171,85,142,173,92,28,238,112,164,213,203,130,110,6,33,97,93,73,204,147,28,226,140,248,191,103,232,253,200,84,209,89]],
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
    "params": [[50,99,102,50,52,100,98,97,53,102,98,48,97,51,48,101,50,54,101,56,51,98,50,97,99,53,98,57,101,50,57,101,49,98,49,54,49,101,53,99,49,102,97,55,52,50,53,101,55,51,48,52,51,51,54,50,57,51,56,98,57,56,50,52]]
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
    "result":[[104,101,108,108,111]],
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
    "params": [[50,99,102,50,52,100,98,97,53,102,98,48,97,51,48,101,50,54,101,56,51,98,50,97,99,53,98,57,101,50,57,101,49,98,49,54,49,101,53,99,49,102,97,55,52,50,53,101,55,51,48,52,51,51,54,50,57,51,56,98,57,56,50,52]]
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
    "result":[[144,47,134,41,117,49,191,68,156,37,166,90,140,241,75,47,222,167,84,165,107,140,94,28,131,176,116,5,231,224,32,15,124,67,40,78,20,108,25,21,201,196,118,111,14,79,131,242]],
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
    "params": [[
            104,
            101,
            108,
            108,
            111
        ]]
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
            [50,99,102,50,52,100,98,97,53,102,98,48,97,51,48,101,50,54,101,56,51,98,50,97,99,53,98,57,101,50,57,101,49,98,49,54,49,101,53,99,49,102,97,55,52,50,53,101,55,51,48,52,51,51,54,50,57,51,56,98,57,56,50,52]
        ],
        [
            [166,54,159,144,72,207,81,43,3,233,138,181,14,56,147,45,171,85,142,173,92,28,238,112,164,213,203,130,110,6,33,97,93,73,204,147,28,226,140,248,191,103,232,253,200,84,209,89]
        ],
        [
            [144,47,134,41,117,49,191,68,156,37,166,90,140,241,75,47,222,167,84,165,107,140,94,28,131,176,116,5,231,224,32,15,124,67,40,78,20,108,25,21,201,196,118,111,14,79,131,242]
        ]
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

