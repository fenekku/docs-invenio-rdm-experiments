# Install for preview

**Intended audience**

The guide is intended for assessors to try InvenioRDM on their _local machine_ in a fully containerized environment.

- Container (good for quick preview): The application is built inside a Docker image.


## [1. Install CLI tool](cli.md)

Install the InvenioRDM CLI tool (see [reference](../reference/cli.md)), e.g. via [`pip`](https://pip.pypa.io/en/stable/):

```shell
pip install invenio-cli
```

## [2. Initialize project](scaffold.md)

Scaffold your InvenioRDM instance on your filesystem.

```shell
invenio-cli init rdm
```

You can add `-c <version>` to specify the version you want to install.

```shell
invenio-cli init rdm -c <version>
# e.g:
invenio-cli init rdm -c v12.0
```

As of writing:

- LTS release (for production systems): ``v12.0``
- STS release (for feature previews): ``v11.0``

You will be asked several questions. If in doubt, choose the default.

## 3. Run

```shell
invenio-cli containers start --lock --build --setup
```

## [4. Explore InvenioRDM](run.md)

Go and explore your InvenioRDM instance on:

- Container: [https://127.0.0.1](https://127.0.0.1)

!!! warning "Self-signed SSL certificate"

    Your browser will display a big warning about an invalid SSL certificate. This is because InvenioRDM generates a self-signed SSL certificate when you scaffold a new instance and because InvenioRDM requires that all traffic is over a secure HTTPS connection.

    All major browsers allow you to bypass the warning (not easily though). In Chrome/Edge you have to click in the browser window and type ``thisisunsafe``.

To create a new administrator account:

In a fully containerized context, connect to a container first e.g. the web-api container: `docker exec -it my-site-web-api-1 /bin/bash`. Then run the commands from within the container as-is.

**Steps**
The following command creates an activated and confirmed user (assuming you have email verification enabled as is the default).

```shell
invenio users create <EMAIL> --password <PASSWORD> --active --confirm
```

Then, allow the user to access the administration panel:

```shell
invenio access allow administration-access user <EMAIL>
```

#### [6. Stop it](destroy.md)

When you are done, you can stop your instance and optionally destroy the containers:

To just stop the containers:

```shell
invenio-cli containers stop
```

To destroy them:

```shell
invenio-cli containers destroy
```
