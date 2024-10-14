# Ghost on Fly.io

  [1]: https://github.com/NiklasRosenstein/headscale-fly-io
  [2]: https://github.com/NiklasRosenstein/vaultwarden-fly-io
  [Litestream]: https://litestream.io
  [GeeseFS]: https://github.com/yandex-cloud/geesefs/

This repository is inspired by my other projects, [Headscale on Fly.io][1] and [Vaultwarden on Fly.io][2]. The goal is
to create a simple deployment of the [Ghost] blogging platform that gets away without persistent storage or an external
database; just a machine and S3.

It uses an SQlite database replicated to S3 using [Litestream] and the Ghost content folder an S3 bucket mounted via
[GeeseFS].

> Disclaimer: We use `NOD_ENV=development` to allow using an SQlite database in the first place. I'm unaware of any
> consequences for production scenarios _aside_ from allowing to use SQlite, so tread carefully.

## Configuration

### Litestream & GeeseFS

GeeseFS re-uses the same S3-related environment variables as our Litestream configuration. For the variables of that
configuration, see [litestream-entrypoint.sh](https://github.com/NiklasRosenstein/headscale-fly-io/blob/main/headscale-fly-io/litestream-entrypoint.sh).
