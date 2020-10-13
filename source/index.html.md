---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://ui.motapi.com'>Sign Up for a Developer Key</a>

includes:
  - emotion
  - errors

search: true

code_clipboard: true
---

# Introduction

Welcome to the Motapi API. You can use our API to access NLP  endpoints, which allow you to get semantic insights from a submited text.

All endpoints are accessible on the https://api.motapi.com domain.

Our API servers do not record any request content nor response. They only count the requests count and debit your API calls credit.

<aside class="notice">
Your credit balance is updated every two minutes.

You can consult your account data at <a href="https://ui.motapi.com">https://ui.motapi.com</a>
</aside>

All requests are http `POST` request unless otherwise specified.


# Authentication

<aside class="notice">
Motapi uses API keys to allow access to the API. You can see your API key at our <a href="https://ui.motapi.com">developer portal</a>.
</aside>

Motapi expects for the API key to be included in all API requests to the server in a header that looks like the following:

`x-api-key: your-api-key`

> Make sure to replace `your-api-key` with your API key.

# Request body

All requests require an http header `Content-Type: application/json`.

All requests require a json object with a `text` property and an associated UTF-8 string value.



> example:

```shell
# With shell, you can just pass the correct header with each request
curl "https://api.motapi.com/endpoint" \
 -H "Content-Type: application/json" \
 -H "x-ap-key: <your-api-key>" \
  --request POST \
  --data '{"text":"The string to be processed."}' \
```


> Make sure to replace `your-api-key` with your API key.

<aside class="notice">
You must replace <code>your-api-key</code> with your personal API key.
</aside>

# Readability

## Get all readability scores


```shell
curl "https://api.motapi.com/readability/all" \
 -H "Content-Type: application/json" \
 -H "x-ap-key: <your-api-key>" \
  --request POST \
  --data '{"text":"The string to be processed."}' \
```

> The above command returns JSON structured like this:

```json
[
{
  "flesch": 48.04,
  "kincaid": 15.25,
  "fog": 17.43,
  "smog": 0.0,
  "ari": 21.91,
  "coleman_liau": 0.0,
  "lix": 53.57,
  "linsear_write": 0.0
}
]
```

This endpoint returns all readability scores for a given text.

### HTTP Request

`POST https://api.motapi.com/readability/all`

### Request JSON body object properties

| Property | Required | Description  |
| -------- | -------- | ------------ |
| text     | true     | UTF-8 string |



<!-- <aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside> -->
