Usually, password hints are sent by email. But as bitwarden_rs is made with small or personal deployment in mind, hints are also available from the password hint page, so you don't have to configure an email service. If you want to disable this feature, you can use the `SHOW_PASSWORD_HINT` variable:

```sh
docker run -d --name bitwarden \
  -e SHOW_PASSWORD_HINT=false \
  -v /bw-data/:/data/ \
  -p 80:80 \
  mprasil/bitwarden:latest
```