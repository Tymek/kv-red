KV-Red
===

Simple key-value store backend service. Augmenting serverless applications.

This is a [Node Red](https://nodered.org/) project.

## Usage

Add "tokens" in "Administration" part of the flow in Node-Red dashboard.
Every token creates separate "scope" (same values will not be visible when using other token).

## Endpoints

GET `/kv`. Returns JSON with all saved keys `{ "YOUR_KEY": "<your_value>" }`.

GET `/kv/:key`, for example `/kv/YOUR_KEY`. Returns JSON with `{ key: "YOUR_KEY", value?: "<your_value>" }`.

POST `/kv/:key`, accepts JSON `{ value: "<your_new_value>" }`

PUT `/kv/:key`, like POST, but sets value only if it was undefined.

DELETE `/kv/:key`, removes a key.

DELETE `/kv` removes all stored key-value pairs.
