Discogs HTML Table
=================
Create an HTML table using Python and OAuth of a Discogs record collection.<br>

The discogs-oauth-example repo was created to provide a very basic but functioning example of how a developer may utilize the python oauth2 library to download images and make authenticated calls against the Discogs API.

Changes or suggestions are welcomed. Please log an issue or pull request via github.

Based on [https://github.com/jesseward/discogs-oauth-example](https://github.com/jesseward/discogs-oauth-example)

Requirements
============
* The python oauth2 library (pip install oauth2).
* A [discogs.com](https://www.discogs.com/login) user account 

To use OAuth
===================

1. Obtain consumer keys : The application developer registers their new application at [https://www.discogs.com/settings/developers](https://www.discogs.com/settings/developers) . Discogs assigns a consumer_key and consumer_secret for the application. This is a one-time action required on behalf of the developer and their application. Each application is assigned a unique value.

2. Request a token : The application sends the consumer_key and consumer_secret to the request_token endpoint ([http://api.discogs.com/oauth/request_token](http://api.discogs.com/oauth/request_token)). Discogs returns a request_token and secret

3. Request user access : Request the user to grant  access to your application. This is done by directing the user to a URL. The URL is generated by your application, it simply appends the request_token and secret returned in step 2 to [http://www.discogs.com/oauth/authorize](http://www.discogs.com/oauth/authorize). If the user accepts this request, discogs will return a verification code. Store this verification code for the next request (step 4).

4. Request token verification : The application sends the request_token and request token secret along withe the verification code to the Discogs api. If the API validates your request, you're returned an access_token and an access token secret. You must store or persist this access_token for the user.

5. Fetching data via your access_token: You're now able to fetch data using the OAuth process. For all authenticated requests, you pass the access_token and access_token secret.
