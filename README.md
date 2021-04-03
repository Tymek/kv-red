KV-Red
===

Simple key-value store backend service. Augmenting serverless applications.

This is a [Node Red](https://nodered.org/) project.

## Usage

Add "tokens" in "Administration" part of the flow in Node-Red dashboard.
Every token creates separate "scope" (same values will not be visible when using other token).

### Making requests
Add `Authorization: Bearer` header with token provided in setup step, for example:
```sh
curl \
-X POST \
-d '{"value":"world!"}' \
-H "Content-type: application/json" \
-H 'Accept: application/json' \
-H "Authorization: Bearer 123456789012345678901234567890" \
https://nodered.example.com/kv/HELLO
```


## Endpoints

GET `/kv`. Returns JSON with all saved keys `{ "YOUR_KEY": "<your_value>" }`.

GET `/kv/:key`, for example `/kv/YOUR_KEY`. Returns JSON with `{ key: "YOUR_KEY", value?: "<your_value>" }`.

POST `/kv/:key`, accepts JSON `{ value: "<your_new_value>" }`

PUT `/kv/:key`, like POST, but sets value only if it was undefined.

DELETE `/kv/:key`, removes a key.

DELETE `/kv` removes all stored key-value pairs.

---

![Preview](./preview.png?raw=true "Optional Title")
