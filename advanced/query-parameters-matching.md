# Query parameters matching

Sometimes we have to provide auto-generated query parameters to our API call, for example if we would like to receive the data based on a timestamp value or if we have to pass the access token for security reasons. Those parameters are changing dynamically which means providing the mocked endpoint for them can be quite difficult and inconvenient. Fortunately Mimic is able to detect those query parameters and forward the request to the mocked endpoint if possible. The logic which detects the parameter matching is the following:

If the original request you send from your app has some query parameters specified Mimic is checking if all the parameters and values of the mocked endpoint match all the parameters and values of the original request. If yes, it means the original request will be redirected to the mocked endpoint. 

For example if you have the following mocked endpoints:
- (1) *https://restcountries.eu/rest/v2/all?fields=name&capital=Budapest*
- (2) *https://restcountries.eu/rest/v2/all?fields=name*

and you're sending the following requests:

1. *https://restcountries.eu/rest/v2/all?fields=name&timestamp=1545390653* the request **will be** forwarded to the mocked **endpoint (2)** because the parameters (*fields = fields*) and values (*name = name*) are matching.
2. *https://restcountries.eu/rest/v2/all?fields=capital&timestamp=1545390653* **will not  be** forwarded because there are no endpoints available where the parameters and the values are matching
3. *https://restcountries.eu/rest/v2/all?fields=name&capital=Budapest&timestamp=1545390653* the request **will be** forwarded to **endpoint (1)** because all the parameters and values are matching
4. *https://restcountries.eu/rest/v2/alpha* **will not  be**  forwarded because there are no endpoints available where the parameters and the values are matching

## Handling multiple matches

In some cases one request can be forwarded to multiple mocked endpoints, for example if you have the following mocked endpoints:
- (1) *https://restcountries.eu/rest/v2/all*
- (2) *https://restcountries.eu/rest/v2/all?fields=name*

and the request is
*https://restcountries.eu/rest/v2/all?fields=name&capital=Budapest*

then both mocked endpoints will be matched because *fields* parameter and the related value match **endpoint (2)** and also match **endpoint (1)** because it's considered as an extra parameter. In this case the following log message will be displayed on the UI:

![Multiple matching endpoints found](../Images/multiple_matches.png 'Multiple matching endpoints found')

## Checking HTTP body

If you'd like to use the parameter matching method for **POST** or **PUT** requests too, you have to make sure the sent HTTP body is the same as the mocked endpoint's. 
For example if you have the following mocked endpoint:
- *https://restcountries.eu/rest/v2/all*
```
BODY:    {"body": "value"}
```
only the exactly matching bodies will be accepted:  
```
{"body": "value"} or {body: value}
```

