# Contributor Guide

`cfp.io` is a multi-tenant application, running on Google Compute Engine as Docker containers.

- [Backend](https://github.com/cfpio/callForPapers) is a spring boot application, offering REST services to frontend
- [Auth](https://github.com/cfpio/auth) do manage users authentication, based on proven email.
- [Front](https://github.com/cfpio/front) is a _rebuild-from-scracth_ web frontend, as the legacy one was spaghetti code.

## multi-tenancy

All Call for Papers instances do run on the same backend application, using a multitenant approach. Based on requested URL https://xxx.cfp.io we filter database requests using `xxx` event ID. If not obtained from `Referer` header, this event ID can also be passer as custom `X-Tenant-Id` header.

## authentication

The [Auth](https://github.com/cfpio/auth) do generate a Json Web Token with proven user email. 
TODO contributor guide

## backend

The [Backend](https://github.com/cfpio/callForPapers) is a spring-boot application. It contains significant legacy code. We made some clenaup, but still need some. For this reason, the exposed REST API is versionned as `/v0/*` as we plan to expose a sanityzed one as `/v1/*`.
TODO contributor guide

## Front

[Front-legacy](https://github.com/cfpio/front-legacy) do contain the legacy front-end, to be replaced at some time by 
[Front](https://github.com/cfpio/front). The later is an angular application, which can rely during development on `demo` tenant hosted on production server https://demo.cfp.io.
TODO contributor guide
