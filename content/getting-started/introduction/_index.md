---
title: "Introduction"
date: 2019-09-20T06:42:20+05:30
draft: true
weight: 1
---

Space Cloud is an **open-source, self hosted backend as a service**.  It provides **GraphQL** and **REST** APIs that can be consumed directly from your frontend apps in a secure manner. 

You can read more about it's [features here](/getting-started/introduction/features).

## About Space Cloud

Space Cloud is primarily a web server that automatically integrates with an existing or a new database to provide instant realtime APIs over GraphQL and REST. Written in Golang, it provides a high throughput data access layer which can be consumed directly from the frontend. It's completely unopinionated and works with the tech stack of your choice.

![Space Cloud Architecture](https://spaceuptech.com/icons/space-cloud-basic.png)

In a nutshell, Space Cloud provides you with all of the following without having to write a single line of backend code:

- **Powerful CRUD**: Flexible queries, transactions and cross-database joins
- **Realtime**: Make live queries to your database
- **File storage**: Upload/download files to scalable file stores (e.g., Amazon S3, Google Cloud Storage)
- **Extensible**: Access your custom HTTP services via the unified APIs of Space Cloud
- **Event-driven**: Trigger webhooks or serverless functions on database or custom events
- **Fine-grained access control**: Dynamic access control that integrates with your auth system (e.g., auth0, firebase-auth)
- **Scalable**: Written in Golang, it follows cloud-native practices and scales horizontally

## How it works

Space Cloud is meant to replace any backend php, nodejs, java code you may write to create your endpoints. Instead, it _exposes your database over an external API_ that can be consumed directly from the frontend. In other words, it **allows clients to fire database queries directly**.

However, it's important to note that **the client does not send database (SQL) queries** to Space Cloud. Instead, it sends an object describing the query to be executed. This object is first **validated** by Space Cloud (using security rules). Once the client is authorized to make the request, **a database query is dynamically generated and executed**. The results are sent directly to the concerned client.

We understand that not every app can be built using only CRUD operations. Sometimes it's necessary to write business logic. For such cases, Space Cloud allows you to write your custom HTTP services. These custom services can be invoked from the frontend or by other services using the unified APIs of Space Cloud. You can even **perform joins on your database and services** via the GraphQL API of Space Cloud!

<div style="text-align: center">
<img src="https://spaceuptech.com/icons/space-cloud-detailed.png"  style="max-width: 80%" alt="Detailed Space Cloud architecture" />
</div>

Apart from these, Space Cloud also integrates with tons of cloud technologies to give you several other features like `realtime database` (changes in the database are synced with all concerned clients in realtime), `file storage`, `event-triggers`, etc.
