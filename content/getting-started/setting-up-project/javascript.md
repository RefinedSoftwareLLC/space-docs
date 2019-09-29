---
title: "Javascript client SDK"
date: 2019-09-26T09:23:20+05:30
draft: true
weight: 2
---

Follow this guide to use javascript client SDK in your web app or any Javascript/Node.js project.

## Step 1: Install Space Cloud API
**Install via npm:**

{{< highlight bash >}}
npm install space-api --save
{{< /highlight >}}

**Or import as a stand alone library:**

{{< highlight html >}}
<script src="https://spaceuptech.com/downloads/libraries/space-api.js"></script>
{{< /highlight >}}

## Step 2: Create an API instance

An `api` instance of Space Cloud on the frontend will help you talk to `space-cloud` binary and perform backend operations directly from the frontend. 

The `API` constructor takes two parameters: 

- **PROJECT_ID:** Unqiue identifier of a project. It's derived by converting your project name to lowercase and replacing all spaces and hiphens to underscores. For example `Todo App` becomes `todo_app`.
- **SPACE_CLOUD_URL:** This is the url of your `space-cloud` binary. It's `http://localhost:4122` or `https://localhost:4126` for HTTP and HTTPS endpoints respectively.

> **Note:** Replace `localhost` with the address of your Space Cloud if you are not running it locally. 

**For ES6:**

{{< highlight javascript >}}
import { API } from 'space-api';

const api = new API('todo_app', 'http://localhost:4122');
{{< /highlight >}}

**For ES5/CommonJS:**

{{< highlight javascript >}}
const { API } = require('space-api');

const api = new API('todo_app', 'http://localhost:4122');
{{< /highlight >}}

**For stand alone:**

{{< highlight javascript >}}
var api = new Space.API("todo_app", "http://localhost:4122");
{{< /highlight >}}


## Step 3: Create a DB instance

The `api` instance created above will help you to directly use `fileStorage` and `functions` modules. However, to use `crud`, `realTime` and `auth` modules you will also need to create a `db` instance.

> **Note:** You can use multiple databases in the same project. (For eg. MongoDB and MySQL)

**For MongoDB:**

{{< highlight javascript >}}
const db = api.Mongo();
{{< /highlight >}}


**For PostgreSQL:**

> **Note:** This can also be used for any other database that is PostgreSQL compatible (For eg. CockroachDB, Yugabyte etc.)

{{< highlight javascript >}}
const db = api.Postgres();
{{< /highlight >}}

**For MySQL:**

> **Note:** This can also be used for any other database that is MySQL compatible (For eg. TiDB)

{{< highlight javascript >}}
const db = api.MySQL();
{{< /highlight >}}

## Next steps
Great! Since you have initialized the `api` and `db` instance you can start building apps with `space-cloud`. 

Feel free to check out various capabalities of `space-cloud`:

- Perform database [queries](/essentials/queries)
- [Mutate](/essentials/mutations) data
- [Realtime](/essentials/subscriptions) data sync across all devices
- Manage files with ease using [File Storage](/essentials/file-storage) module
- [Authenticate](/auth/authentication) your users
- Write [custom business logic](/essentials/custom-logic)
- [Secure](/auth/authorization) your apps