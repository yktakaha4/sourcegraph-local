# sourcegraph-local

## Usage

```
$ openssl genrsa 2048 > data/sourcegraph/config/sourcegraph.key
$ openssl req -new -x509 -nodes -sha256 -days 3650 -key data/sourcegraph/config/sourcegraph.key -out data/sourcegraph/config/sourcegraph.crt
$ chmod 400 data/sourcegraph/config/*.{key,crt}
$ ll data/sourcegraph/config/*.{key,crt}
-r-------- 1 tkhs tkhs 1245  5月 11 01:56 data/sourcegraph/config/sourcegraph.crt
-r-------- 1 tkhs tkhs 1675  5月 11 01:55 data/sourcegraph/config/sourcegraph.key

$ docker-compose up
# https:localhost:7080
```

- [ ] https://localhost:7080/site-admin/configuration
  - `https://localhost:7080` を指定
- [ ] https://localhost:7080/site-admin/external-services/new?id=github
  - token と orgs を指定
