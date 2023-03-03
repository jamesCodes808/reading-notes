# Authentication

## OAuth

- What is OAuth?

OAuth is an open-standard authorization protocol or framework that describes how unrelated servers and services can safely allow authenticated access to their assets without actually sharing the initial, related, single logon credential.

- Give an example of what using OAuth would look like.

An example of using the OAuth framework is when a user logs into or signs up for a website and it offers you the chance to use another website's log in. Like how Netlify or Render offer that you log in with github or google.

- How does OAuth work? What are the steps that it takes to authenticate the user?

First we need a user that is already signed into a website or service. And that same user is trying to access another site.

<details closed><summary>Steps to authenticate user with OAuth</summary> 

1. The first website connects to the second website on behalf of the user, using OAuth, providing the user’s verified identity.

2. The second site generates a one-time token and a one-time secret unique to the transaction and parties involved.

3. The first site gives this token and secret to the initiating user’s client software.

4. The client’s software presents the request token and secret to their authorization provider (which may or may not be the second site).
If not already authenticated to the authorization provider, the client may be asked to authenticate. After authentication, the client is asked to approve the authorization transaction to the second website.

5. The user approves (or their software silently approves) a particular transaction type at the first website.

6. The user is given an approved access token (notice it’s no longer a request token).

7. The user gives the approved access token to the first website.

8. The first website gives the access token to the second website as proof of authentication on behalf of the user.

9. The second website lets the first website access their site on behalf of the user.

10. The user sees a successfully completed transaction occurring.

11. OAuth is not the first authentication/authorization system to work this way on behalf of the end-user. In fact, many authentication systems, notably Kerberos, work similarly. What is special about OAuth is its ability to work across the web and its wide adoption. It succeeded with adoption rates where previous attempts failed (for various reasons).
</details>

- What is OpenID?

OAuth handles authorizations and OpenID handles Authentication. "OpenID is for humans logging into machines, OAuth is for machines logging into machines on behalf of humans." 
It is a one-stop authentication single sign-in service for multiple websites. This technology complements OAuth and vice versa.

## Authorized and Authentication Flows

- What is the difference between authorization and authentication?

Authentication is the process of verifying who a user is, while authorization is the process of verifying what the user has access to.

- What is Authorization Code Flow?

The Authorizaton code flow are steps that authorization moves when the user logs in and is prompted to authorize and in turn gets an authorization code.

<details closed> <summary> Authorization Code Flow </summary>

1. The user clicks Login within the regular web application.

2. Auth0's SDK redirects the user to the Auth0 Authorization Server (/authorize endpoint).

3. Your Auth0 Authorization Server redirects the user to the login and authorization prompt.

4. The user authenticates using one of the configured login options and may see a consent page listing the permissions Auth0 will give to the regular web application.

5. Your Auth0 Authorization Server redirects the user back to the application with an authorization code, which is good for one use.

6. Auth0's SDK sends this code to the Auth0 Authorization Server (/oauth/token endpoint) along with the application's Client ID and Client Secret.

7. Your Auth0 Authorization Server verifies the code, Client ID, and Client Secret.

8. Your Auth0 Authorization Server responds with an ID Token and Access Token (and optionally, a Refresh Token).

9. Your application can use the Access Token to call an API to access information about the user.

10. The API responds with requested data.

</details>

- What is Authorization Code Flow with Proof Key for Code Exchange (PKCE)?

Some apps cannot store a Client Secret, because it is either bound to the app, uses a custom url or because the client's entire source is available to the browser. So they required additional security because of this we have to add extra steps to the Authorization code flow.

<details closed><summary>How it works:</summary>


1. The user clicks Login within the application.

2. Auth0's SDK creates a cryptographically-random code_verifier and from this generates a code_challenge.

3. Auth0's SDK redirects the user to the Auth0 Authorization Server (/authorize endpoint) along with the code_challenge.

4. Your Auth0 Authorization Server redirects the user to the login and authorization prompt.

5. The user authenticates using one of the configured login options and may see a consent page listing the permissions Auth0 will give to the application.

6. Your Auth0 Authorization Server stores the code_challenge and redirects the user back to the application with an authorization code, which is good for one use.

7. Auth0's SDK sends this code and the code_verifier (created in step 2) to the Auth0 Authorization Server (/oauth/token endpoint).

8. Your Auth0 Authorization Server verifies the code_challenge and code_verifier.

9. Your Auth0 Authorization Server responds with an ID token and access token (and optionally, a refresh token).

10. Your application can use the access token to call an API to access information about the user.

11. The API responds with requested data.

</details>

- What is Implicit Flow with Form Post?

The Implicit Flow is intended for public clients or applications that are unable to securely store client secrets. This is no longer considered best practice when requesting for Access Tokens. Here is how it works:

<details closed><summary>How it works </summary> 

1. The user clicks Login in the app.

2. Auth0's SDK redirects the user to the Auth0 Authorization Server (/authorize endpoint) passing along a response_type parameter of id_token that indicates the type of requested credential. It also passes along a response_mode parameter of form_post to ensure security.

3. Your Auth0 Authorization Server redirects the user to the login and authorization prompt.

4. The user authenticates using one of the configured login options and may see a consent page listing the permissions Auth0 will give to the app.

5. Your Auth0 Authorization Server redirects the user back to the app with an ID Token.
</details>


- What is Client Credentials Flow?

The client credentials flow is used when typical username+password or social logins don't make sense to use. It is when we need to use machine to machine authentications. 

<details closed> <summary>How it works: </summary> 

1. The application authenticates with the Auth0 Authorization Server using its Client ID and Client Secret (/oauth/token endpoint).

2. Auth0 Authorization Server validates the Client ID and Client Secret.

3. Auth0 Authorization Server responds with an Access Token.

4. The application can use the access token to call an API on behalf of itself. For more information on this process, see Validate JSON Web Tokens.

5. The API responds with requested data.

</details>

- What is Device Authorization Flow?

With device authorization flow, we authenticate the user indirectly by asking the user to go to a link on their computer or mobile device to authorize the device. 

<details closed> <summary>How it works: </summary> 

1. The user starts the app on the device.

2. The device app requests authorization from the Auth0 Authorization Server using its Client ID (/oauth/device/code endpoint).

3.  The Auth0 Authorization Server responds with a device_code, user_code, verification_uri, verification_uri_complete expires_in (lifetime in seconds for device_code and user_code), and polling interval.

4.  The device app asks the user to activate using their computer or smartphone. The app may accomplish this by:

5.  asking the user to visit the verification_uri and enter the user_code after displaying these values on-screen

6.  asking the user to interact with either a QR Code or shortened URL with embedded user code generated from the verification_uri_complete

7.  directly navigating to the verification page with embedded user code using verification_uri_complete, if running natively on a browser-based device

8.  The device app begins polling your Auth0 Authorization Server for an Access Token (/oauth/token endpoint) using the time period specified by interval and counting from receipt of the last polling request's response. The device app continues polling until either the user completes the browser flow path or the user code expires.

9.  When the user successfully completes the browser flow path, your Auth0 Authorization Server responds with an Access Token (and optionally, a Refresh Token). The device app should now forget its device_code because it will expire.

10.  Your device app can use the Access Token to call an API to access information about the user.

11. The API responds with requested data.

</details>

- What is Resource Owner Password Flow?

Not recommended but highly-trusted applications can use the Resource Owner Password Flow, which requests that users provide credentials (username and password), typically using an interactive form. The Resource Owner Password Flow should only be used when redirect-based flows

<details closed><summary> How it works </summary> 

1. The user clicks Login within the application and enters their credentials.

2. Your application forwards the user's credentials to your Auth0 Authorization Server (/oauth/token endpoint).

3.  Your Auth0 Authorization Server validates the credentials.

4.  Your Auth0 Authorization Server responds with an Access Token (and optionally, a Refresh Token).

5.  Your application can use the Access Token to call an API to access information about the user.

6.  The API responds with requested data.

</details>

## things I want ot know more about

- Using OAuth in my code, is it for the front end or back end or both?


>References
>
>[What is OAuth? How the open authorization framework works](https://www.csoonline.com/article/3216404/what-is-oauth-how-the-open-authorization-framework-works.html)
>
>[Authentication and Authorization Flows](https://auth0.com/docs/get-started/authentication-and-authorization-flow)
>
>[Authentication vs. Authorization](https://auth0.com/docs/get-started/identity-fundamentals/authentication-and-authorization)