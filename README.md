Gandi module for Caddy
===========================

This package contains a DNS provider module for [Caddy](https://github.com/caddyserver/caddy). It can be used to manage DNS records with Gandi accounts.

## Caddy module name

```
dns.providers.gandi
```

## Config examples

> [!CAUTION]  
> The **API Key** authentication is no longer supported and replaced by **Personal Access Token**

To use this module for the ACME DNS challenge, [configure the ACME issuer in your Caddy JSON](https://caddyserver.com/docs/json/apps/tls/automation/policies/issuer/acme/) like so:

```json
{
  "module": "acme",
  "dns": {
    "provider": {
      "name": "gandi",
      "bearer_token": "{env.GANDI_BEARER_TOKEN}"
    }
  }
}
```

or with the Caddyfile:

```
tls {
  dns gandi {env.GANDI_BEARER_TOKEN}
}
```

You can replace `{env.GANDI_BEARER_TOKEN}` with the actual auth token if you prefer to put it directly in your config instead of an environment variable.


## Authenticating

See [the associated README in the libdns package](https://github.com/libdns/gandi) for important information about credentials.
