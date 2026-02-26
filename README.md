# 🪞 Container Image Mirror

A GitHub Action that periodically mirrors third-party Docker/OCI images to Docker Hub — purely as a **backup**. Nothing is modified, repackaged, or redistributed for commercial gain. All original licenses apply in full.

> ⚠️ **Heads up:** This repo is a personal/infra backup tool. If you own one of the mirrored images and want it removed, just [open an issue](../../issues) or send a PR — it'll be done promptly, no questions asked.

---

## 🤔 What does it do?

1. Reads `images.json` for the list of source → target image pairs.
2. Every 6 months (Jan 1 & Jul 1) — or on manual trigger — it checks whether each source image has changed using a manifest fingerprint (SHA-256).
3. If something changed, it copies the image (all platforms) to Docker Hub using [`skopeo`](https://github.com/containers/skopeo).
4. Caches digests in `.cache/digests.json` so unchanged images are skipped.

**Images are copied as-is. No layers are modified. No proprietary content is added or stripped.**

---

## ⚖️ Disclaimer

- 🔒 This is a **backup mirror only** — not a redistribution or alternative registry.
- 🛠️ Images are **not altered** in any way.
- 🏷️ All original **licenses remain in effect** — see the table below.
- 💰 These images are **not commercialized** here. Do not use this mirror to bypass upstream licensing terms.
- 📬 If you are a maintainer and want your image removed, [open an issue](../../issues).

---

## 📦 Mirrored Images & Licenses

### 🟢 Currently Mirrored (`images.json`)

| Image | Upstream | License |
|---|---|---|
| `portainer-ce` | [portainer/portainer-ce](https://github.com/portainer/portainer) | [zlib](https://github.com/portainer/portainer/blob/develop/LICENSE) |
| `n8n` | [n8nio/n8n](https://github.com/n8n-io/n8n) | [Sustainable Use License](https://github.com/n8n-io/n8n/blob/master/LICENSE.md) ⚠️ |
| `ollama` | [ollama/ollama](https://github.com/ollama/ollama) | [MIT](https://github.com/ollama/ollama/blob/main/LICENSE) |
| `open-webui` | [open-webui/open-webui](https://github.com/open-webui/open-webui) | [MIT](https://github.com/open-webui/open-webui/blob/main/LICENSE) |
| `mariadb` | [MariaDB](https://github.com/MariaDB/server) | [GPL v2](https://github.com/MariaDB/server/blob/main/COPYING) |
| `bitnami-wordpress` | [bitnami/containers](https://github.com/bitnami/containers) | [Apache 2.0](https://github.com/bitnami/containers/blob/main/LICENSE.md) / WordPress: [GPL v2](https://wordpress.org/about/license/) |
| `ghost` | [TryGhost/Ghost](https://github.com/TryGhost/Ghost) | [MIT](https://github.com/TryGhost/Ghost/blob/main/LICENSE) |
| `postgres` | [postgres](https://github.com/postgres/postgres) | [PostgreSQL License](https://www.postgresql.org/about/licence/) |
| `umami` | [umami-software/umami](https://github.com/umami-software/umami) | [MIT](https://github.com/umami-software/umami/blob/master/LICENSE) |
| `swagger-ui` | [swagger-api/swagger-ui](https://github.com/swagger-api/swagger-ui) | [Apache 2.0](https://github.com/swagger-api/swagger-ui/blob/master/LICENSE) |
| `node-red` | [node-red/node-red](https://github.com/node-red/node-red) | [Apache 2.0](https://github.com/node-red/node-red/blob/master/LICENSE) |
| `mongo-express` | [mongo-express/mongo-express](https://github.com/mongo-express/mongo-express) | [MIT](https://github.com/mongo-express/mongo-express/blob/master/LICENSE.md) |
| `bitnami-mongodb` | [bitnami/containers](https://github.com/bitnami/containers) | Apache 2.0 / MongoDB: [SSPL v1](https://www.mongodb.com/licensing/server-side-public-license) ⚠️ |
| `mongodb` | [mongodb-community-server](https://github.com/mongodb/mongo) | [SSPL v1](https://www.mongodb.com/licensing/server-side-public-license) ⚠️ |
| `grav` | [getgrav/grav](https://github.com/getgrav/grav) | [MIT](https://github.com/getgrav/grav/blob/develop/LICENSE.txt) |
| `wiki` (Wiki.js) | [requarks/wiki](https://github.com/requarks/wiki) | [AGPL v3](https://github.com/requarks/wiki/blob/dev/LICENSE) |
| `traefik` | [traefik/traefik](https://github.com/traefik/traefik) | [MIT](https://github.com/traefik/traefik/blob/master/LICENSE.md) |
| `nextcloud` | [nextcloud/server](https://github.com/nextcloud/server) | [AGPL v3](https://github.com/nextcloud/server/blob/master/COPYING) |
| `redis` | [redis/redis](https://github.com/redis/redis) | [BSD 3-Clause](https://github.com/redis/redis/blob/unstable/COPYING) ⚠️ newer versions use RSALv2+SSPLv1 |
| `nodejs` | [nodejs/node](https://github.com/nodejs/node) | [MIT / various](https://github.com/nodejs/node/blob/main/LICENSE) |
| `memcached` | [memcached/memcached](https://github.com/memcached/memcached) | [BSD 3-Clause](https://github.com/memcached/memcached/blob/master/LICENSE) |
| `prometheus` | [prometheus/prometheus](https://github.com/prometheus/prometheus) | [Apache 2.0](https://github.com/prometheus/prometheus/blob/main/LICENSE) |
| `influxdb` | [influxdata/influxdb](https://github.com/influxdata/influxdb) | [MIT](https://github.com/influxdata/influxdb/blob/master/LICENSE) |
| `haproxy` | [haproxy/haproxy](https://github.com/haproxy/haproxy) | [GPL v2 / LGPL v2.1](https://github.com/haproxy/haproxy/blob/master/LICENSE) |
| `caddy` | [caddyserver/caddy](https://github.com/caddyserver/caddy) | [Apache 2.0](https://github.com/caddyserver/caddy/blob/master/LICENSE) |
| `dockge` | [louislam/dockge](https://github.com/louislam/dockge) | [MIT](https://github.com/louislam/dockge/blob/master/LICENSE) |
| `yacht` | [SelfhostedPro/Yacht](https://github.com/SelfhostedPro/Yacht) | [MIT](https://github.com/SelfhostedPro/Yacht/blob/master/LICENSE) |
| `medusajs` | [medusajs/medusa](https://github.com/medusajs/medusa) | [MIT](https://github.com/medusajs/medusa/blob/develop/LICENSE) |

---

### 🗄️ Previously Mirrored (`old-images.json`)

These were mirrored at some point and may still exist on Docker Hub, but are no longer actively synced.

| Image | Upstream | License |
|---|---|---|
| `neko-chromium` / `neko-firefox` / `neko-tor` | [m1k1o/neko](https://github.com/m1k1o/neko) | [Apache 2.0](https://github.com/m1k1o/neko/blob/master/LICENSE) |
| `rabbitmq` | [rabbitmq/rabbitmq-server](https://github.com/rabbitmq/rabbitmq-server) | [MPL 2.0](https://github.com/rabbitmq/rabbitmq-server/blob/main/LICENSE) |
| `elasticsearch` | [elastic/elasticsearch](https://github.com/elastic/elasticsearch) | [Elastic License 2.0 / SSPL v1](https://github.com/elastic/elasticsearch/blob/main/LICENSE.txt) ⚠️ |
| `strapi` | [strapi/strapi](https://github.com/strapi/strapi) | [MIT (v4) / SEE LICENSE (v5)](https://github.com/strapi/strapi/blob/develop/LICENSE) |
| `drupal` | [drupal/drupal](https://github.com/drupal/drupal) | [GPL v2+](https://www.drupal.org/about/licensing) |
| `joomla` | [joomla/joomla-cms](https://github.com/joomla/joomla-cms) | [GPL v2+](https://github.com/joomla/joomla-cms/blob/5.2-dev/LICENSE.txt) |
| `directus` | [directus/directus](https://github.com/directus/directus) | [BSL 1.1](https://github.com/directus/directus/blob/main/license) ⚠️ |
| `payload` | [payloadcms/payload](https://github.com/payloadcms/payload) | [MIT](https://github.com/payloadcms/payload/blob/main/LICENSE) |
| `prestashop` | [PrestaShop/PrestaShop](https://github.com/PrestaShop/PrestaShop) | [OSL 3.0](https://github.com/PrestaShop/PrestaShop/blob/develop/LICENSE.md) |
| `odoo` | [odoo/odoo](https://github.com/odoo/odoo) | [LGPL v3](https://github.com/odoo/odoo/blob/17.0/LICENSE) |

---

> ⚠️ **Note on non-OSI licenses:** A handful of images (n8n, MongoDB, Elasticsearch, Directus, newer Redis) use licenses that are **source-available but not OSI-certified open source**. They are included here solely as infrastructure backups. Please review their upstream license terms before any production or commercial use.

---

## 🔧 Setup (if you want to fork this)

1. Fork the repo.
2. Add two repository secrets:
   - `DOCKERHUB_USERNAME` — your Docker Hub username.
   - `DOCKERHUB_TOKEN` — a Docker Hub access token (read/write).
3. Edit `images.json` with your own image list.
4. Trigger the workflow manually or wait for the schedule.

---

## 📄 License

The **workflow code and configuration in this repository** is licensed under the [MIT License](./LICENSE).

The mirrored images themselves remain under their own respective licenses — see the table above.
