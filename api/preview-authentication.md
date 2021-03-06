---
layout: "api-page2"
title: Authentication
published: true
excerpt: "Uset authentication in Europeana REST API"
---

Europeana API supports three kinds of user authentication that are used in three different application scenarios. To perform general API calls, like [search](http://labs.europeana.eu/api/preview-search), [object](http://labs.europeana.eu/api/preview-object) or [provider/collection](http://labs.europeana.eu/api/preview-provider), which do not involve user-specific information, the most basic authentication scheme is used. For accessing user-specific data stored on MyEuropeana accounts using [MyData](http://labs.europeana.eu/api/preview-myeuropeana) calls, a caller application is to be identified by the user credentials. Finally, for applications wishing to get 3rd party access on behalf of a registered user, OAuth2 authentication scheme is supported.

### Basic Authentication

This is the simplest form of authentication which does not involve accessing user-specific information. To perform a call using this authentication every API call must be provided a special authentication parameter _wskey_. This value of this parameter should be the public key that you got during the API user registration process. We use these keys to anonymously gather interesting statistics about API usage. If you forget your API key or need to generate a new one, login to [My Europeana](http://europeana.eu/portal/myeuropeana#login).


### User Authentication

This form of authentication is used when an application wishes to access MyEuropeana data of a specific user. Either the user’s username and password, or public and private keys can be used. The pair of credentials used determines which base API endpoint to use in subsequent API calls, either `http://beta.europeana.eu/v2/user` when using the username/password or `http://beta.europeana.eu/v2/mydata` when using the public/private keys.

    POST http://beta.europeana.eu/login.do

|Parameter|Either|Or|
|:----------|:--------------|:--------------------|
|j_username | Your USERNAME | Your PUBLIC apikey  |
|j_password | Your PASSWORD | Your PRIVATE apikey |

The initial response header is a `HTTP/1.1 302 Moved Temporarily` that contains a cookie with the key/value pair, `JSESSIONID=<your-session-value>`. That cookie will need to be sent with every subsequent API call that requires authentication. Unsuccessful authentication will redirect to `http://europeana.eu/api/login?form=user`. Successful authentication will redirect to `http://beta.europeana.eu/`.


### OAuth2 Authentication

For applications that wish to access MyEuropeana data of a specific end-user on his behalf, we use the standard [OAuth2](http://oauth.net/2/) authentication scheme. This scheme works by redirecting the application to a dedicated login page provided by the server and issuing to the application an authenticating token with a limited lifetime when the login is succesful. The token can be refreshed later on by the application. To use this kind of authentication the application should first access the URL

    http://beta.europeana.eu/oauth/authorize

and further on the URL

    http://beta.europeana.eu/oauth/token


to refresh the token.

There are many open source libraries available for various languages to help you implement this authentication scheme in your project. For more information, consult the [OAuth2 reference page](http://oauth.net/2/).
