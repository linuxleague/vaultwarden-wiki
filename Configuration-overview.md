## Configuration methods

In bitwarden_rs, you can perform configuration either via environment variables or an [[admin page|Enabling-admin-page]] (which writes settings to a `config.json` file under your data directory). It's important to note that each setting in `config.json` overrides the corresponding environment variable setting (if it exists). For example, if you set the environment variable `DOMAIN=https://bitwarden.example.com`, but your `config.json` includes `"domain": "https://bw.example.com"`, then bitwarden_rs will generate various links based on what's in the config file (`https://bw.example.com`).

A common source of confusion is enabling the admin page (which creates the `config.json` file), changing some settings via the admin page (which sets the corresponding values in `config.json`), then later trying to change those settings via environment variable (which doesn't work because `config.json` overrides env vars). To avoid this confusion, it's highly recommended to stick to one configuration method or the other; that is, configure entirely via environment variables, or entirely via `config.json` (whether using the admin page or editing `config.json` directly).

## Setting the domain URL

Make sure to set the `DOMAIN` environment variable (or `domain` in the config file) properly. If you don't, it's likely that various functionality will break mysteriously. Some examples:

* `https://bitwarden.example.com`
* `https://bitwarden.example.com:8443` (non-default port)
* `https://host.example.com/bitwarden` ([[subdir hosting|Using-an-alternate-base-dir]] -- avoid URL-rewriting tricks whenever possible)