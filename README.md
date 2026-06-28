# HTTP HA

Custom Home Assistant integration for calling HTTP endpoints from automations and scripts.

## Usage

```yaml
action:
  - service: http_ha.request
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

If the response has a JSON content type, the service returns parsed JSON in `http_result.body`.
