# HA HTTP Request

A custom Home Assistant integration that allows automations and scripts to send HTTP requests to external services.

## Features

* Supports `GET`, `POST`, `PUT`, `PATCH`, and `DELETE`
* Custom headers
* JSON and text request bodies
* Returns the HTTP response to a variable
* Automatic JSON parsing when the response content type is `application/json`

## Installation

Copy the `custom_components/HTTP_Request_HA` folder into your Home Assistant `custom_components` directory and restart Home Assistant.

## Example

```yaml
action:
  - service: http_request.request
    data:
      method: POST
      url: https://example.com/api
      headers:
        Content-Type: application/json
        Authorization: Bearer token
      body:
        foo: bar
    response_variable: http_result
```

If the response is JSON, it will be available as:

```yaml
{{ http_result.body }}
```

You can also access:

* `http_result.status`
* `http_result.headers`
* `http_result.body`

## Use Cases

* Trigger webhooks
* Control external devices
* Send notifications to third-party services
* Integrate with REST APIs
* Exchange data with custom applications

## License

MIT License.
