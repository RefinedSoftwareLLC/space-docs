---
title: "Event Triggers"
date: 2019-10-19T10:46:59+05:30
draft: true
weight: 1
---

Space Cloud can be used to create event triggers on database or custom events. The in-built eventing queue in Space Cloud **reliably** invokes webhooks to carry out any custom logic.

## Why use event triggers?

Event triggers enable:

- **Improved performance**: Due to the **async** nature, event creators don't have to wait. 
- **Better reliability**: Configurable retry logic.
- **Simplified decoupling**: Change business logic without changing event data.   

## Use cases

Event triggers are excellent for carrying out asynchronous business logic. Following are a few use cases of event triggers:

- Updating search index (e.g., Elasticsearch or Algolia) or a caching system on CRUD operations in your primary database.
- Performing mutations on any event.
- Sending out a welcome email on new signup.


## How it works

You add an event trigger to Space Cloud via Mission Control. Each event trigger has `type`, webhook and other configurable parameters.

Events can be of the following types:

- `CRUD_CREATE`: When a row/document gets created.
- `CRUD_UPDATE`: When a row/document gets updated.
- `CRUD_DELETE`: When a row/document gets deleted.
- `<CUSTOM>`: Whenever you queue a custom event to Space Cloud.

Whenever an event takes place (e.g., insert mutation via Space Cloud or a custom event), Space Cloud invokes the webhook with the event payload. If the webhook responds with a `2xx` status code, Space Cloud marks the event to be `processed`. Otherwise, it retries the webhook, a certain number of times (configurable) before finally marking it as `failed`. 

Space Cloud stores the events log in `event_logs` table in the eventing database (both of them are configurable). The primary database that you selected while creating a project is selected as the eventing database by default.