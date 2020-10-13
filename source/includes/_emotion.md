# Emotion

## Get all emotions score intensities


```shell
curl "https://api.motapi.com/emotion/intensity" \
 -H "Content-Type: application/json" \
 -H "x-api-key: <your-api-key>" \
  --request POST \
  --data '{"text":"The string to be processed."}' \
```

> The above command returns JSON structured like this:

```json
{
  "anger": 0.0,
  "anticipation": 0.0,
  "disgust": 0.0,
  "fear": 0.0,
  "joy": 0.083333336,
  "sadness": 0.073,
  "surprise": 0.0,
  "trust": 0.29933333
}
```

This endpoint returns all emotions score intensities for a given text.

### HTTP Request

`POST https://api.motapi.com/emotion/intensity`

### Request JSON body object properties

| Property | Required | Description                                       |
| -------- | -------- | ------------------------------------------------- |
| text     | true     | UTF-8 string                                      |
| language | false    | ISO 639-1 2 letters language code. example : "fr" |