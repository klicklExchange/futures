# Futures API
https://github.com/klicklExchange/futures/blob/main/docs/futuresAPI.md


## SIGNED (TRADE and USER_DATA) Endpoint Security
SIGNED endpoints require an additional parameter, X-SIGNATURE, to be sent in the http header.
Endpoints use HMAC SHA256 signatures. The HMAC SHA256 signature is a keyed HMAC SHA256 operation. Use your secretKey as the key and totalParams as the value for the HMAC operation.
