To enable YubiKey authentication, you must set the `YUBICO_CLIENT_ID` and `YUBICO_SECRET_KEY` env variables.

If `YUBICO_SERVER` is not specified, it will use the default YubiCloud servers. You can generate `YUBICO_CLIENT_ID` and `YUBICO_SECRET_KEY` for the default YubiCloud [here](https://upgrade.yubico.com/getapikey/).

Note: In order to generate API keys or use a YubiKey with an OTP server, it must be registered. After configuring your key in the [YubiKey Personalization Tool](https://www.yubico.com/products/services-software/personalization-tools/use/), you can register it with the default servers [here](https://upload.yubico.com/).

```sh
docker run -d --name bitwarden \
  -e YUBICO_CLIENT_ID=12345 \
  -e YUBICO_SECRET_KEY=ABCDEABCDEABCDEABCDE= \
  -v /bw-data/:/data/ \
  -p 80:80 \
  mprasil/bitwarden:latest
```