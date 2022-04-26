# Futures API
https://github.com/klicklExchange/futures/blob/main/docs/futuresAPI_zh.md
https://github.com/klicklExchange/futures/blob/main/docs/futuresAPI_en.md

## SIGNED (TRADE and USER_DATA) Endpoint Security

1. SIGNED endpoints require an additional parameter, X-SIGNATURE, to be sent in the Request Headers.

2. Endpoints use HMAC SHA256 signatures. The HMAC SHA256 signature is a keyed HMAC SHA256 operation. Use your secretKey as the key and totalParams as the value for the HMAC operation.`

## Timing Security
* A SIGNED endpoint also requires a header parameter, X-TIMESTAMP, to be sent which should be the millisecond timestamp of when the request was created and sent.
* An additional header parameter, X-RECVWINDOW, may be sent to specify the number of milliseconds after timestamp the request is valid for. If recvWindow is not sent, it defaults to 5000.
* Serious trading is about timing. Networks can be unstable and unreliable, which can lead to requests taking varying amounts of time to reach the servers. With X-RECVWINDOW, you can specify that the request must be processed within a certain number of milliseconds or be rejected by the server.

## Example 1: As a query string
*queryString:

marginMode=0&price=1000&side=0&size=1&symbol=BTCUSDT&timestamp=1650959189709&type=6&unitMode=0

## Example 2: As a request body
*requestBody:

orders=%5b%7b%22clientId%22%3a%221518409519707852800%22%2c%22marginMode%22%3a0%2c%22price%22%3a39068.1%2c%22side%22%3a0%2c%22size%22%3a0.293%2c%22symbol%22%3a%22BTCUSDT%22%2c%22type%22%3a6%2c%22unitMode%22%3a1%7d%2c%7b%22clientId%22%3a%221518409519707852801%22%2c%22marginMode%22%3a0%2c%22price%22%3a39061%2c%22side%22%3a0%2c%22size%22%3a0.566%2c%22symbol%22%3a%22BTCUSDT%22%2c%22type%22%3a6%2c%22unitMode%22%3a1%7d%2c%7b%22clientId%22%3a%221518409519707852802%22%2c%22marginMode%22%3a0%2c%22price%22%3a39054.6%2c%22side%22%3a0%2c%22size%22%3a0.311%2c%22symbol%22%3a%22BTCUSDT%22%2c%22type%22%3a6%2c%22unitMode%22%3a1%7d%5d&timestamp=1650959189838

