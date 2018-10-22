# Configuration

Mimic is a fully-configurable app. It allows you to configure a JSON file with the port settings and your projects' details.

The file is called `apimocker.json` and you can find it in the app package content. The config has a JSON structure.

Example Config:

```
{
  "httpPort": "3000",
  "projects": [
    {
      "uuid": "8f63d210-d2fe-11e8-a311-1b5d7ae5a1b9",
      "name": "project",
      "endpoints": [
        {
          "uuid": "d9e21a40-d2fe-11e8-a311-1b5d7ae5a1b9",
          "path": "/show",
          "method": "GET",
          "response": {},
          "request": { "body": {}, "params": "" },
          "statusCode": 200,
          "timeout": 0,
        }
      ],
      "fallbackUrlPrefix": "https://your.api.host/api/v2/"
    }
  ],
  "version": "1.0"
}
```

File Structure:

- `httpPort` - HTTP port the server is listening on.
- `projects` - Array which represents projects.
- `version` - Config version.

Project Structure:

- `uuid` - Project id should be unique and not empty.
- `name` - Project name.
- `endpoints` - Array which represents a list of endpoints in the project.
- `fallbackUrlPrefix` - String which represents the address of a server with a real API to be used for [mocking](../basics/collections.md) purposes

Endpoint structure:

- `uuid` - Endpoint id, should be unique and not empty.
- `path` - Endpoint path should start with `/`.
- `method` - Endpoint REST method type, should be: GET, POST, PUT, PATCH, DELETE
- `response` - Endpoint response, must be a string or json.
- `request` - Endpoint options. Represents an object with two fields: `body` which must be json and `params` (URL parameters), which must be a string.
- `statusCode`- Endpoint HTTP status code [more info](https://www.restapitutorial.com/httpstatuscodes.html).
- `timeout` - API timeout.

If you need some help with your custom configuration you can contact us or find more info in the related documentation sections:

- [Create First Project](../basics/create-first-project.md)
- [Sending Api Request](../basics/sending-api-request.md)
- [Response Options](../basics/response-options.md)
