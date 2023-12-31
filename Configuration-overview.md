## Configuration methods

> ⚠️**NOTE:** The `config.json` file is _**NOT**_ the recommended way to configure your settings!
> Either use environment variables which you can configure in several ways for your container environment (Docker, Docker-Compose, K8s etc..)
> Or, if using a standalone binary (not distributed by Vaultwarden it self) use a `.env` file located in your current work directory.
> The `config.json` file is created and overwritten when saving the settings within the Admin interface!
>

<br>

In vaultwarden, you can perform configuration either via environment variables or an [[admin page|Enabling-admin-page]] (which writes settings to a `config.json` file under your data directory). It's important to note that each setting in `config.json` overrides the corresponding environment variable setting (if it exists). For example, if you set the environment variable `DOMAIN=https://bitwarden.example.com`, but your `config.json` includes `"domain": "https://vw.example.com"`, then vaultwarden will generate various links based on what's in the config file (`https://vw.example.com`).

A common source of confusion is enabling the admin page (which creates the `config.json` file), changing some settings via the admin page (which sets the corresponding values in `config.json`), then later trying to change those settings via environment variable (which doesn't work because `config.json` overrides env vars). To avoid this confusion, it's highly recommended to stick to one configuration method or the other; that is, configure entirely via environment variables, or entirely via `config.json` (whether using the admin page or editing `config.json` directly).

Note that config settings under the `Read-Only Config` section of the admin page can only be set via environment variables, so you must restart vaultwarden to make changes to them.

## Loading environment variables from a file

If you want to keep environment variables in a file (customarily named `.env`), you can load them as follows:

* With standalone vaultwarden, by putting `.env` in the current working directory. vaultwarden will attempt to load this file on startup. Note that Vaultwarden looks only for an env file named `.env`; it will not know how to find env files with other names.
* With Docker, by using `docker run --env-file <env-file> ...` (to have Docker load the env file) or `docker run -v /path/to/.env:/.env` (to have vaultwarden load the `.env` file from inside the container). If you use `--env-file`, note that Docker does not unquote values, so make sure to use `key=val` rather than `key="val"` or `key='val'`.
* With Docker Compose, by using the [`env_file`](https://docs.docker.com/compose/environment-variables/#the-env_file-configuration-option) directive.

## Configuration options

You can find the list of environment variables you can set at

https://github.com/dani-garcia/vaultwarden/blob/main/.env.template

If you enable the [[admin page|Enabling-admin-page]], that will also show the full list of config options.

In case there are any errors or omissions, the source of truth is

https://github.com/dani-garcia/vaultwarden/blob/main/src/config.rs (search for `make_config! {`)

Or you can use this direct link if your (Chromium-based) browser supports text fragments:

https://github.com/dani-garcia/vaultwarden/blob/main/src/config.rs#LC290:~:text=make_config!%20%7B,-folders

## Setting the domain URL

Make sure to set the `DOMAIN` environment variable (or `domain` in the config file) to the URL you use to access your vaultwarden instance. If you don't, it's likely that various functionality will break mysteriously. Some examples:

* `https://bitwarden.example.com`
* `https://bitwarden.example.com:8443` (non-default port)
* `https://host.example.com/bitwarden` ([[subdir hosting|Using-an-alternate-base-dir]] -- avoid URL-rewriting tricks whenever possible)