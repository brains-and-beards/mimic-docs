# Create first project

Read on to learn how to set up your first project on Mimic:

- **[Create Project](#create-project)**
- **[Mock Server](#mock-server)**
- **[Create Endpoint](#reate-endpoint)**
- **[Test](#test)**

## Create Project

To create your first project click on **Projects** Button and then on **Create new Project** :

![Create new Project](../Images/createnewproject.png 'Create new Project')

You will see the details Project popup:

![Create new Project](../Images/projectdetails.png 'Create new Project')

here you can set the **name** of your project and the **URL prefix** for your API service.

This data will be used to forward any unmocked requests directly to your API service. _This data is confidential and never leaves your computer_.

Clicking on **Add Project** the project will be created.

## Mock Server

Once the project is created you can see on the **Status Bar** that the server is working and its url. This is the base url used by all endpoints you will create.

![Server working](../Images/statusbar_serverworking.png 'Server Working')

As you can see the base url includes also the name of the project (_myproject_ in the image above).
Clicking on the **Status Bar** the base url will be copied to the clipboard.

You can manage the mock server through the **Server Button** of the **Action Bar**, clicking on this button you can start/stop the server and the current server status will be shown on the **Status Bar**

## Create Endpoint

Let's create your first endpoint. To do it click on yellow plus button on the **Action Bar**

![Add Endpoint](../Images/actionbar_createendpoint.png 'Add Endpoint')

Now you can see the new endpoint on the _Endpoints_ list, click on the row to add more details. Clicking on the endpoint row, you will see the **Endpoint Details Section** on the right.

![New Endpoint](../Images/newendpoint_details.png 'New Endpoint')

in this panel you can set the _path_ of the endpoint, the details of the request and of the response.

In the top bar you can see the current path of this endpoint, at the moment it is the default value set automatically.

You will see all details of this panel on the next sections: **Sending Api Request** and **Response options**.

Now let's set only a simple endpoint to complete our first project:

Our endpoint will be:

`GET /demo`

and the response will be:

`{label: 'my first endpoint'}`

To do that, please follow these steps:

- Type a path on Path input to set the path of the endpoint.
- put `demo`
- Click Enter or click the yellow save button on the top.
- The HTTP method is already set to `GET`
- Click on Response
- Set the JSON response: `{label: 'my first endpoint'}`

Now your endpoint details panel should be like the following image:

![New Endpoint](../Images/newendpoint_details_values.png 'New Endpoint')

Your first endpoint is ready!

## Test

Let's test our first endpoint.

the full url of the endpoint is:

`http://localhost:3000/[project name]/[endpoint path]`

in this case it is:

`http://localhost:3000/myproject/demo`

You can open it using the browser or you can test it on the Terminal using `curl`:

`curl http://localhost:3000/myproject/demo`

Is the response like the JSON you have set before?

`{label: 'my first endpoint'}`

Yes! your first project is ready and works great!
