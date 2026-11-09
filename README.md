# 🚇 Metrocraft 2036

**Multiplayer online post-apocalyptic game set in the Moscow metro.** Java client and server on a custom engine, microservices, a website with accounts and payments, a launcher, an admin panel and player support.

🌐 [metrocraft36.com](https://metrocraft36.com) · ▶️ [YouTube](https://www.youtube.com/@metrocraft36) · 💬 [Discord](https://discord.com/invite/xSgCwrWRVk)

> Source code is private (Interactive Game Studio). This repository describes the project and my role.

## At a glance
| | |
|---|---|
| My role | **Project Lead / CTO**, Apr 2024 – present |
| Team | 20–40 people: developers, game designers, narrative designers, artists, QA |
| Audience before open beta | 700 pre-registrations · 300 peak concurrent players in tests · 5,000 Discord members |
| Milestones | Closed beta in spring 2025 · open beta in preparation |
| My code | ~2,100 commits, ~2M lines added; author of over half of all server commits |

![screenshot](https://github.com/user-attachments/assets/1fffe260-2922-4315-8eee-2f5df9e3d327)

## Leading the project
- Run the backlog and releases in Jira, with separate version lines for the engine and the game. Assign and accept work across all disciplines.
- Confluence documentation: design docs for game mechanics, quest-authoring guides for narrative designers, technical docs, patch notes.
- Hiring through the careers page and the admin panel; sourcing and accepting 3D assets from contractors.
- Closed beta operations (whitelists, daily fixes from reports), open beta preparation, Bug Bounty and a media program.

## Engine and gameplay (Java)
- Moved the project from its Minecraft/Forge legacy to **our own engine**: LWJGL3, PBR rendering with lighting and shadows, NanoVG and then Noesis UI, FMOD audio, Jolt physics, PopcornFX effects.
- **Custom UDP networking** (RakNet, io_uring): chunk streaming, preloading, texture streaming, network metrics.
- Modular architecture with about 70 modules on each side, a packet registry and a shared client-server config format.
- Gameplay systems: inventory and equipment, trading and barter, perks, clans and faction wars, outposts, weapons and shooting, anti-cheat logs, voice chat.
- **World editor for the team:** roles and permissions, edit history, prefabs, interactive objects, an NPC and quest editor, visual graphs (State Tree, Event Graph), Google Sheets import and export, and an **MCP server that lets Claude drive the editor**.

![screenshot](https://github.com/user-attachments/assets/d2b41876-860f-4452-8749-9ad89bca3296)

## Backend and web
- Java/Spring Boot microservices with gRPC, Kafka and Eureka: characters, inventory, quests, factions, realms, anti-cheat.
- Website backend moved from NestJS to seven Java services behind a gateway, with Keycloak SSO (social login, Twitch, Telegram linking).
- Payments: PayPal, YooMoney, Enot, UnitPay.
- Next.js website in two editions (RU and global), a Flarum forum with SSO and an admin panel (players, punishments, mailings, auction).
- Tauri launcher with versioning, 2FA, telemetry and S3/CDN plus peer-to-peer delivery.

![screenshot](https://github.com/user-attachments/assets/a56b709e-c2ca-409c-b10c-ac2c56daf587)

## Infrastructure
- Docker Compose for dev, staging and production; GitHub Actions pipelines with obfuscation, asset encryption and automated releases.
- Game-server containers behind a Quilkin proxy, an nginx TCP firewall in front of the microservices.
- PostgreSQL, MongoDB, ClickHouse, Redis, MariaDB; incremental backups to S3; player analytics in ClickHouse.
- Self-hosted studio tooling: Keycloak SSO with one role matrix, Jira, Confluence, Mattermost, GitHub and Bitbucket with Git LFS, Sentry, Prometheus, Grafana, Loki, Wazuh, CrowdSec, Vault, a FreeScout helpdesk linked to Jira, VPN access.

## Tech stack
| Area | Stack |
|---|---|
| Game | Java 21/25, Gradle, LWJGL3, OpenGL, NanoVG, ImGui, Noesis, FMOD, Jolt, PopcornFX, Recast/Detour, Netty, RakNet |
| Services | Spring Boot, gRPC, Protobuf, Kafka, Eureka, Flyway, Maven; Node.js, NestJS, TypeORM |
| Frontend | Next.js, React, TypeScript, Tauri |
| Data | PostgreSQL, MongoDB, ClickHouse, Redis, MariaDB, S3 |
| Infrastructure | Docker, Docker Compose, GitHub Actions, nginx, Caddy, Cloudflare, Portainer, Quilkin, Linux |
| Observability and security | Sentry, Prometheus, Grafana, Loki, Wazuh, CrowdSec, Vault, Keycloak |

## More screenshots
![](https://github.com/user-attachments/assets/30daf6ba-04c9-4f9e-bdc4-680b8c461c12)
![](https://github.com/user-attachments/assets/962e49b3-eb22-42b5-a776-c6e38dffd1d0)
![](https://github.com/user-attachments/assets/08021d96-987f-4c51-bdb7-8e69b7478087)
![](https://github.com/user-attachments/assets/02b28f50-ecc2-4f01-b153-c3e8ceb00390)
![](https://github.com/user-attachments/assets/2054d7de-e6ba-463d-ad07-0bba1a3e7af6)
![](https://github.com/user-attachments/assets/dca67561-cee5-4a0d-84ba-e2bf8e994830)
