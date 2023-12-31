As a convenience vaultwarden image will also host static files for Vault web interface. You can disable this static file hosting completely by setting the WEB_VAULT_ENABLED variable.

```sh
docker run -d --name vaultwarden \
  -e WEB_VAULT_ENABLED=false \
  -v /vw-data/:/data/ \
  -p 80:80 \
  vaultwarden/server:latest
```
Alternatively you can override the Vault files and provide your own static files to host. You can do that by mounting a path with your files over the `/web-vault` directory in the container. Just make sure the directory contains at least `index.html` file.

```sh
docker run -d --name vaultwarden \
  -v /path/to/static/files_directory:/web-vault \
  -v /vw-data/:/data/ \
  -p 80:80 \
  vaultwarden/server:latest
```

Note that you can also change the path where vaultwarden looks for static files by providing the `WEB_VAULT_FOLDER` environment variable with the path.