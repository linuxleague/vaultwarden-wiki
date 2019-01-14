bitwarden_rs only provides the API (server) side implementation, so users still rely on clients from upstream. (mobile apps, desktop apps and web Vault) This is a lot of work that is done upstream by 8bit Solutions LLC. At the same time bitwarden_rs supports some paid features and offers that functionality for free. This raises some [questions about sustaining and supporting upstream](https://github.com/dani-garcia/bitwarden_rs/issues/331) development. Many users raised this issue and were asking how they can support upstream while using bitwarden_rs. Unfortunately as of now, there is no donation option, but this wiki is trying to find some ways users can support upstream development.

## Buying a licence

Many users just buy appropriate licence for their deployment and leave it unused. It's kind of donation because bitwarden_rs can't use the licence in any way.

## Help translating the apps

There are [projects on Crowdin](https://crowdin.com/profile/kspearrin) for each of the apps. If you're fluent in any language other than english, you can help traslating the apps.

## Testing, reporting bugs in clients

**Please, always report any bugs found here first.** Chances are these aren't upstream bugs, but bugs in our implementation or in your configuration. [We don't want to waste Kyle's time](https://github.com/dani-garcia/bitwarden_rs/issues/336) troubleshooting bugs with 3rd party server. In very rare cases there is a bug upstream, but at this stage we would have any other reason ruled out and the bug confirmed on the upstream server. So the takeaway here is to _not_ report bugs in upstream, but report it here instead even if you think it is client issue. We can work together to see where the problem is.