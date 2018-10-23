# API Forwarding

In this section is described the **API forwarding** feature of Mimic and how you can easily mock a real endpoint of your API service.

To use this feature you must set the information about your real API service in the project details.
You can set them during project set up or, if the the project already exists, opening the project details clicking on the menu icon on the top of the window and selecting _project settings_

![Project Setting](../Images/project_settings.png 'Project Setting')

The project settings popup allows you to set the information about your real API service:

![Project Details](../Images/edit_project.png 'Project Details')

We can use the following API service as example to explain how the API forwarding feature of Mimic works:

[restcountries.eu](https://restcountries.eu/)

It is a free and open source REST service to get informations about countries of the World.

Let's create our project to mock that service API. Create a new project called **countries**:

![API Forwarding Exampre Project](../Images/api_forwarding_example_project.png 'API Forwarding Exampre Project')

During the set up process you must add the information about the real API service, in this case you can set:

- _Domain_ : restcountries.eu
- _Path_ : /rest/v2/

You can leave empty the **port** field becasue there is not any information about it. The **path** is set to `/rest/v2/` because all the endpoints have this path in their URLs.

Clicking on **Add Project** your _countries_ project is ready and it is running.

## API Forwarding

Your project hasn't any endpoints but it is connected to a real API service. As you know the url of your mock server is:

`http://localhost:3000/countries`

and the real API service has the `all` endpoint to get all data of all countries:

`GET https://restcountries.eu/rest/v2/all`

Let's try to do a request to the mock server for this endpoint using the following command on your Terminal:

`curl http://localhost:3000/countries/all`

Because the `countries` project doesn't have the `all` endpoint, this request is forwarded to the real API service using the data you set in the project details. You will receive the response from the real API service proxied through Mimic.

## Mock Button

Your forwarded request is shown in the logs panel of Mimic, and in its row it is present also a green button, **Mock**, as shown in the next image:

![Mock button](../Images/log_row_with_mock_button.png 'Mock button')

The **Mock** button create instantly a new endpoint of the project with the same url and response of the request forwarded to the real API service.

In this case, you will have a new `all` endpoint with the same information and response of

`GET https://restcountries.eu/rest/v2/all`

After clicking on **Mock** button you can see the new `all` endpoint in the endpoints list. If you open the details of this endpoint you will find the same response of the real endpoint:

![Mocked Endpoint](../Images/endpoint_created_from_mock_button.png 'Mocked Endpoint')

## Conclusions

**API Forwarding** feature allows Mimic to forward requests to real API services when the current project hasn't the requested endpoint and all the information of the real API service (domain, path and port) are set in the project details.

In addition when a request is forwarded, the **Mock Button** allow the user mock the endpoint with a single click.

A common use case of these feature could be to create a mock of the own API service and use it even when there is not internet connection.
