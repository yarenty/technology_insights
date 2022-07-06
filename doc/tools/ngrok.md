# NGrok - Free Firewall Tunnel



https://dashboard.ngrok.com/get-started/setup



If you are hosting a server on a home network with a dynamic IP address, it can be hard or impossible to accept incoming web requests. NGrok provides local workstations with a *.ngrok.io web address for exposing local servers to the Internet. It also provides HTTPS/TLS support, which is pretty cool!

Ngrok is especially useful when you want to experiment with third-party APIs that use WebHooks.


to run:
```shell
ngrok http 80
```



## Tip 1: Auth in 5 Seconds
Building auth into your apps is important but sometimes it gets in the way. We have a simpler mindset:

```shell
ngrok http 8000 --basic-auth="katelibby:rooftoppool"
```

Whether you use HTTP Basic Auth, OAuth 2.0, OpenID Connect, or even SAML, ngrok has you covered out of the box. 


### Using ngrok for HTTP Basic Authentication
The simplest form of authentication is HTTP Basic Auth. In ngrok, you can set it up as easily as:

```shell
ngrok http 3001 --basic-auth="katelibby:reallyrocks"
```
and that gives you a simple login box:

HTTP Basic Auth with ngrok

Basic auth creates a single username and password in front of your ngrok tunnel. This is ideal for those one-off customer demos where you only need to protect your application for a brief period of time. Under no circumstances should you launch a production application onto the public internet with just Basic Auth.

### Using ngrok for OAuth 2.0
If we want to really launch an application with authentication, we need to get more serious. At minimum, we want individual users to have their own credentials and - ideally - we don’t want to get involved in the complexity of user and password management. Luckily, that is exactly what OAuth 2.0 is designed for.



In this case, we’ll shift our command slightly to leverage Google’s login flow:
```shell
ngrok http 3001 --oauth=google
```
Now when we attempt to access our tunnel, we’ll get redirected to Google, complete the authentication flow, and get redirected back to our application. That’s all it takes to put a simple OAuth front end on your most ancient, arcane, untouchable applications. To date, we haven’t modified the application.

That said, if we have the ability or need to modify the application, as part of the flow, ngrok will collect specific fields from your identity provider and pass them along as headers. Specifically, it includes:
```text
Ngrok-Auth-User-Email: keith@ngrok.com
Ngrok-Auth-User-Id: 102528612345998048947
Ngrok-Auth-User-Name: Keith Casey
Referer: https://accounts.google.com/
```
Now we have the ability to use these fields for logging, profile and preference management, or even to bootstrap a more complex user/authentication object for downstream applications.

But most of the time, we still don’t want anyone with a Google account logging into our application. Let’s make sure only our team can access our application:

```shell
ngrok http 3001 --oauth=google --oauth-allow-domain=company.com
```
While this works, we forgot our customer! Let’s make one tweak:

```shell
ngrok http 3001 --oauth=google --oauth-allow-domain=company.com,customer.com
```
And we can even let in our outside contractor who doesn’t have a company email:
```shell
ngrok http 3001 --oauth=google --oauth-allow-domain=company.com,customer.com –oauth-allow-email=first.last@contractor.com
```
Now we have all the flexibility of using OAuth for effectively zero effort, still without modifying our application.

### Using ngrok for OpenID Connect
While using a public OAuth provider is powerful, it’s likely we’ll want to connect to a corporate or internal identity provider. In that case, we can shift to a more fine-grained approach like OpenID Connect (OIDC) with a custom provider.

OIDC is an open protocol so we could use any provider but we’ll use Okta for simplicity. In this case, we have two steps.

First, on the Okta side, we have to set the redirect URL where the ID token is sent after a successful login flow. Within the Okta Admin Dashboard, we create an OpenID Connect application and specify the Authorization Code flow. Once created, we copy the Client ID and Client Secret for the next step and add this as a "Sign-in redirect URI":

https://idp.ngrok.com/oauth2/callback
Configure Okta's OpenID Connect for ngrok

Then on the command line we specify our Okta organization and the Client ID and Client Secret from the previous step:
```shell
ngrok http 3001 --oidc=https://mycompany.okta.com --oidc-client-id=myclientid --oidc-client-secret=myclientsecret
```
Now our application is protected by our corporate identity provider with marginally more effort than it took to use HTTP Basic Auth.



## Debugging

Testing code is a tedious task that takes a lot of time, especially if certain conditions are required – such as trigger webhooks, API requests, or web pages with specific cookies/headers/session context.

Three months ago, I developed a webhook listener that updates my database anytime a user signs a contract in DocuSign. While the initial coding was easy due to DocuSign's great doc, I spent the entire day tweaking my code logic to grab various fields from the JSON payload.

That happened because I spent 10+ minutes on each test cycle tweaking my code and then uploading and eSigning docs, and waiting for the webhook.

That was before I joined ngrok and learned about the Request Inspector and the Replay functionality — which is one of the coolest tools to save some time ❤️:

Time savings using request replays

### Request Inspector
When you launch ngrok, you can see two links: One for the tunnel to your app (it ends up in ngrok.io unless you're using custom domains) and a local URL (http://localhost:4040) for the Request Inspector.

The Request Inspector shows all the requests made through your tunnel. When you click a request, you can see details of both requests and responses.

Seeing requests are an excellent way for validating the data sent to and retrieved by your app via the ngrok tunnel. That alone can save you some time dissecting and logging HTTP request and response headers, methods, bodies, and response codes within your app just to confirm you are getting what you expect.

Request Replays (with and without modifications)
For each request, the dashboard also gives you a replay button with two options:

You can replay your requests without any modification by just clicking Replay

### Request Replay

This takes the entire request - both payload and headers - and replays it directly into your application. It does not mimic requestor IP address or recreate signing information — especially important for verifying webhooks — but the payload and headers will be intact for your code to use as you need.

Alternatively, you can also click the down arrow > Replay with Modifications. This allows you to use the same request as a template and make adjustments in the request method, header, and body:

### Request Replay Modified

Ready to get started?
Request introspections and replays are available to any ngrok user. To get it going, launch your tunnel (i.e., ngrok http 80) and then go to your introspection address (i.e., http://localhost:4040).