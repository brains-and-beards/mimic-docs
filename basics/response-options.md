---
description: Response
---

# Response options

The response panel allows you to specify the response details of your endpoint:

![New Endpoint](../Images/newendpoint_details_values.png 'New Endpoint')

In this section you can specify the following options:

- HTTP Status Code
- Delay
- Body type
- Body content

In the **HTTP Status Code** input you can specify the HTTP status code of your response, the example above is showing a successful request with status code **200**.

In the **Delay** input you can specify the delay (in milliseconds) of your response, the example above doesn't use any delay and the value is **0**.

This feature can come in handy if you would like to simulate network problems or test out race conditions in your app.

You can choose between **JSON** or **RAW** as body type of the response.

The **JSON** body must be a valid JSON, you can use the body editor to write and validate the JSON. When the JSON is valid you will see the green tick as the image above. The green icon will be hidden if the JSON is not valid. The validation is automatic, the editor checks the content every second (with a delay during typing).

In a **RAW** body you can put anything else that JSON, like formatted text

`<h1>File not found</h1>`

or just some error string

`403 Forbidden`
