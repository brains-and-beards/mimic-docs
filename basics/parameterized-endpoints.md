# Parameterized Endpoints

Mimic app allows you to use parameterized endpoints. If in your project there is an endpoint with a parameter in the path (like an ID) you can use _parameterized endpoints_ to intercept all the requests to this endpoint using different values for that parameter.

Let's see an example:

the project has an endpoint to get a post, in the path of this endpoint the `post_id` represent the ID of the post object:
`GET http://www.example.com/posts/{post_id}`

In Mimic you can create a _parameterized endpoint_ using `*` in the path to represent the parameter of the endpoint, in this case the `post_id`.

To summarize, if you want to intercept all requests to:

`GET http://www.example.com/posts/{post_id}`

In your endpoint path you have to set:

`posts/*`

![Parameterized Endpoint](../Images/parameterized_endpoint.png 'Parameterized Endpoint')

You can even specify multiple parameters, for example the endpoint:

`GET http://www.example.com/posts/{post_id}/comments/{comment_id}`

become in Mimic:

`posts/*/comments/*`
