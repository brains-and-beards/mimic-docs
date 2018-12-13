# Project Importing

Mimic app can import projects from external file, this feature could be very useful and it is very easy to use.

Mimic doesn't import the file but only save a reference to it, so the path of the file used in this process must not change. For instance this feature if very useful is you save the JSON file with the project settings in the same folder of your project

To import a project click on _Import project_ on the menu on the top left:

![Import Project Menu](../Images/import_project_menu.png 'Import Project Menu')

The _Import Project_ popup is open and you can start to import your project:

![Import Project Popup](../Images/import_project_popup.png 'Import Project Popup')

Write a _Project Name_ and select the JSON file with your project settings.

The JSON file must have the following structure:

```
{
	"projects": [
		{
			"uuid": "new-project-123456",
			"name": "New Project",
			"endpoints": [
				{
					"uuid": "new-project-users-123456",
					"path": "/users",
					"method": "GET",
					"response": [],
					"request": { "body": {}, "params": "" },
					"statusCode": 200,
					"timeout": 0
				},
				{
					"uuid": "new-project-posts-123456",
					"path": "/posts",
					"method": "GET",
					"response": [],
					"request": { "body": {}, "params": "" },
					"statusCode": 200,
					"timeout": 0
				}
			]
		}
	]
}
```

The root label must be _projects_ and the value is an array of projects.

_Project_

Each project has _uuid_, _name_ and an array of _endpoints_

- The _uuid_ must be unique, for instance, use the project name and some number like in the example.
- The _name_ value is the project name used by Mimic.
- The _endpoints_ array has a list of endpoints.

_Endpoint_

Each endpoint has _uuid_, _path_, _method_, _response_, _request_, _statusCode_, _timeout_,

- The _uuid_ must be unique, for instance, use the project name, the endpoint path and some number like in the example.
- The _path_ is the path of the endpoint, like `/users`.
- The _method_ is the method of the endpoint, like `GET`, `POST`, `PUT`, `DELETE`, `PATCH`.
- The _response_ is the response of the endpoint, here you can set the JSON used as response.
- The _request_ is the request of the endpoint, here you can set the _body_ (JSON) and the _parameters_ of the request. Like `sortby=date`.
- The _statusCode_ is the status code of the response of the endpoint, like `200`.
- The _timeout_ is the delay (in ms) of the response of the endpoint.

The root label can contain multiple projects.

If the file is correct you can upload it and click on _Import_ button to import your project:

![Import Project Info](../Images/import_project_info.png 'Import Project Info')

Your project is imported!

You can find it in the projects list:

![Imported Project Menu](../Images/imported_project_menu.png 'Imported Project Menu')

settingsand clicking on it you will find all endpoints set on the JSON file:

![Imported Project](../Images/imported_project.png 'Imported Project')
