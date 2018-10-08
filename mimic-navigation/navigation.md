# Navigating Mimic

Mimic is a single-window application. The interface is divided into four main parts:

- **Action Bar**
- **Routes**
- **Logs**
- **Status bar**

Every part of the application was designed to give you enough space for showing information.

## Action Bar

![alt text](../Images/actionbar.png 'Action bar')

On the Action Bar, the following options are available:

- **Projects** Button - Create a new project, switch between projects.

- **Edit** Icon - Edit the project name.

- **Start Server** Button - Start the server, stop the server.

- **Plus(+)** Button - Add a route to the project.

- **Menu** Button - Projects settings, delete all routes, delete project.

## Routes

![alt text](../Images/routes.png 'Routes')

The user can see a list of routes. Every route contains a description, method, type and endpoint path.

### Routes Details

When the user clicks on an item in the routes' list, the Side Bar is shown with details about the selected endpoint.

### Side Bar - Endpoints Details

![alt text](../Images/endpointdetails.png 'Endpoints Details')

The Side Bar has four main parts:

- **Endpoint Details Action Bar** - Settings for the endpoint.
- **Path** - Input where the user can set an endpoint path.
- **Request/Response** - Two buttons let the user switch between Request and Response options.
- **Methods and Body** - Depends on the **Request/Response** buttons.

#### Endpoint Details Action Bar

![alt text](../Images/detailsoptions.png 'Endpoints Details')
The Action Bar contains:

- **Menu Button** - Allows the user to delete an endpoint.
- **Save Icon** - Allows the user to save endpoint details, making it active after every change.
- **Close Icon** - Closes the endpoint details.

#### Path

An user can type the endpoint path and save it using _Enter_ or _Save Icon_.

#### Request

The Request content contains the method buttons - GET, POST, PUT, PATCH and DELETE.

Three methods - POST, PUT and PATCH - allow the user to set the **Body**:

- JSON - The JSON body automatically saves and checks for valid syntax.
- RAW - The RAW request body can be saved using the _Save Icon_.

![alt text](../Images/request.png 'Request')

Two methods - GET and DELETE - allow the user to set **URL Parameters**.

![alt text](../Images/requestGET.png 'Request GET')

#### Response

The user can set the following on a response:

- **HTTP Status Code** (more info: [HTTP Status Codes](https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html)).
- **Delay** - Set a response delay (in milliseconds).
- **Body type** - Switch body type (JSON or RAW).

![alt text](../Images/response.png 'Response')

## Logs

![alt text](../Images/logs.png 'Logs')

The Logs section contains a list of the server's logs. Each log has a timestamp, server status, and possibly endpoint details.

Clicking the _Garbage Icon_ will clear all logs.

## Status Bar

The Status Bar represents the **Server Status**.
