---
title: "Manual (using binary)"
date: 2019-09-26T12:40:33+05:30
draft: true
weight: 2
---

This guide helps you set up Space Cloud quickly on your local machine via its binary executable. It lets you explore the Space Cloud APIs on MongoDB without having to set up any project.

If you instead want to start a project from scratch using Space Cloud, then check out the [getting started](/docs/getting-started) guide.

## Prerequisites

- [MongoDB Database](https://docs.mongodb.com/manual/installation/)

> **Note:** MongoDB is not a dependency of Space Cloud. We are using MongoDB in this guide for ease of use because of its schemaless nature.

## Step 1: Download Space Cloud

The first step is to download the binary. You need to download the binary for your operating system, or you could build it directly from its source code. You need to have go version 1.13.0 or later to build it from source.

Download the binary for your OS from here:

- [Mac](https://spaceuptech.com/downloads/darwin/space-cloud.zip)
- [Linux](https://spaceuptech.com/downloads/linux/space-cloud.zip)
- [Windows](https://spaceuptech.com/downloads/windows/space-cloud.zip)

You can unzip the compressed archive.

**For Linux / Mac:** `unzip space-cloud.zip && chmod +x space-cloud`

**For Windows:** Right-click on the archive and select `extract here`.

To make sure if the binary is correct, type the following command from the directory where the binary is downloaded:

**For Linux / Mac:** `./space-cloud -v`

**For Windows:** `space-cloud.exe -v`

It should show something like this:

{{< highlight bash>}}
space-cloud-ee version 0.13.0
{{< /highlight >}}

## Step 2: Start Space Cloud

> **Note:** Make sure your MongoDB is up and running before this point

To start Space Cloud in `dev` mode, copy-paste the following command and hit enter:

**For Linux / Mac:** `./space-cloud run --dev`

**For Windows:** `space-cloud.exe run --dev`

You should see something like this when Space Cloud starts:

{{< highlight bash>}}
Creating a new server with id auto-1T5fA9E1B2jeNUbV8R0fOPubRng
Starting http server on port: 4122

   Hosting mission control on http://localhost:4122/mission-control/

Space cloud is running on the specified ports :D
{{< /highlight >}}

> **Note:** The `--dev` flag tells Space Cloud to run in dev mode (so that the admin UI does not ask for a username and password)

## Step 3: Configure Space Cloud

As you would have noticed, `space-cloud` generates a `config.yaml` file in the working directory.

Space Cloud needs this config file to function. The config file is used to load information like the database to be used, its connection string, security rules, etc. 

Space Cloud has it's own Mission Control (admin UI) to configure all of this quickly. 

### Open Mission Control

Head over to `http://localhost:4122/mission-control` to open Mission Control.

> **Note:** Replace `localhost` with the address of your Space Cloud if you are not running it locally. 

### Creating a project

Click on `Create a Project` button to open the following screen:

![Create a project screen](/images/screenshots/create-project.png)

Give a `name` to your project. MongoDB is selected as your database by default. Keep it as it is for this guide.

Hit `Next` to create the project.

### Configuring DB config

Head over to the `Database` section:

As you can see, the `Overview` tab shows the connection status (i.e. whether Space Cloud is connected or not to your database). 

If it shows disconnected, then click on the edit button to enter the correct connection string of your database:

![Edit connection details](/images/screenshots/edit-connection.png)

That's all that is required to configure Space Cloud for this guide!

## Step4: Let us try it out 

Our backend is up and running, configured to expose APIs on MongoDB. Time to explore its awesome powers. 

[Explore GraphQL APIs](/getting-started/quick-start/explore-graphql) of Space Cloud using GraphiQL.