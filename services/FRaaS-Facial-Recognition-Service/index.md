---

copyright:

  years:  2020

lastupdated: "2020-03-11"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# About FRaaS Facial Recognition Service
{: #gettingstarted}

[AIH Tech](https://aihtech.com) FRaaS solution provides functionalities and APIs for every stage of the facial recognition process including 

- face detection stage
- face extraction stage
- matching staging

Therefore the API client can decide by itself which stage to integrate with FRaaS API. These stages in the process are serial in nature.

Thick clients, such as laptops or mobile devices, can capture images then detect and extract on the client side. Once extracted the face images, client can send them up by calling FRaaS API. Since the face detection and extraction are performed on the client side, of which an amount of CPU processing is required, server is off-loaded to for faster response and increased parallelism.

{:shortdesc}

## Getting started

FRaaS support both **STOMP websocket** as well as **RESTful** APIs.

FRaaS API support [STOMP websocket](https://stomp.github.io/index.html) interface to support publisher-subscriber model. The publisher-subscription model is instrumental for use cases revolving around video/stream face detection notifications. Requests and responses in STOMP Websocket API use HTTP status code and other standard practices for maximum compatibility. 

Selective RESTful APIs are supported to faciliate client integration. Currently, Face Watcher does *NOT* support RESTful APIs as Face Watcher is heavily bi-directional, for which STOMP Websocket is best suited.

The endpoints are categorized by 

- [Face Repo](./repo/FaceRepo.md)  (WS & REST)
- [Face Watcher](./watcher/FaceWatcher.md) (WS only)
- [Face Group](./grouping/FaceGrouping.md) (WS & REST)

Please contact us to request API access token. You can reach us at our official [website](https://aihtech.com/contact.html) or by sending us an email.

Add `Authorization` request header e.g. : `Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5...`

