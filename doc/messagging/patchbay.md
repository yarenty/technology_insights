# patchbay.pub


patchbay.pub is a free web service you can use to implement things like static site hosting, file sharing, cross-platform notifications, webhooks handling, smart home event routing, IoT reporting, job queues, chat systems, bots, etc, all completely serverless and requiring no account creation or authentication. Most implementations need nothing but curl and simple bash snippets.




patchbay.pub


trivial example. If you run this GET to create a consumer, it will block:

```shell

curl https://patchbay.pub/8ew3-s004
```
Until you also run this POST in another terminal to create a producer:

```shell

curl https://patchbay.pub/8ew3-s004 -d "Hi there"
```





If you use the /pubsub/ protocol, like this:

```shell

curl https://patchbay.pub/pubsub/8ew3-s004


curl https://patchbay.pub/pubsub/8ew3-s004 -d "Hi there"
```


the request uses the channel in a different mode. GETs act similarly to before, but POSTs become non-blocking, and will broadcast messages to all blocked pubsub consumers, not just the first one. As the name suggest, this models the PubSub pattern.