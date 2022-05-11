[![kaindlglobalnetwork.de](https://raw.githubusercontent.com/kgncloud/docker-template/main/KAINDL_LogoDesign_B_orange_rgb.png)](https://kaindlglobalnetwork.de)

# mautrix-twitter

The [Kaindl Network](https://kaindlglobalnetwork.de) team brings you another container release featuring:

* Regular application & security updates
* Built-in Healthcheck
* bringing a container as close as possible to linuxserver.io releases
* We track the upstream source changes and publishes fast new versions of this image.
* Bringing you Linuxserver.io Image Quality
* Using Alpine Base Image

## 🔧 How to Install

### 🐳 Docker

#### Docker CLI
```bash
docker run -d --restart=unless-failed -v ./data:/data ghcr.io/kgncloud/mautrix-twitter:main
```
#### Docker-Compose

### Build the Image locally

```bash
git clone https://github.com/kgncloud/mautrix-twitter/
cd mautrix-twitter
docker build Dockerfile
```

## What is needed to launch this Container

- Matrix Server with access to register bots
- Whatsapp Account
- Server(Linux preferred) to launch this Container 

## How does this Container work



## Version Tags

This image provides various versions that are available via tags. `main` tag usually provides the latest stable version. Others are considered under development and caution must be exercised when using them.

| Tag | Description |
| :----: | --- |
| main | Latest Release Version of this Container |

## Volumes

| Volumes | Description |
| :----: | --- |
| data | Here are the Registration Files, Bride Configuration Files (and SQLite File if configured) |

## 🩺 Healthcheck

This image has already a healtcheck included :D

## System Requirements

This Image was test for the use of one person

| Ressources | Description |
| :----: | --- |
| CPU | Low usage maximum 2 Threads needed |
| RAM | 1GB                                |
| Disk| No prediction possible, depends on user|

## Enviromental Variables
The Deveolper of the software generates a Configuration and a Registration File. We want to make your setup even easier by giving you the choise to input the configuration via Enviromental Variables. This would also allow an easier launch on Docker Swarm withut the need to expose your Filesystem.

| Variable | Description| Required Variable? | Standard Variable |
| :----: | --- | --- | --- |
| homeserver_adress | The address that this appservice can use to connect to the homeserver. | yes | https://example.com
| homeserver_domain | The domain of the homeserver (for MXIDs, etc).                         | yes | example.com
| asmux             | Is the homeserver actually mautrix-asmux?                              | no  | false
| status_endpoint   | The URL to push real-time bridge status to. If set, the bridge will make POST requests to this URL whenever a user's whatsapp connection state changes. The bridge will use the appservice as_token to authorize requests. | no | null
| message_send_checkpoint_endpoint | Endpoint for reporting per-message status. | no | null
| async_media | Does the homeserver support https://github.com/matrix-org/matrix-spec-proposals/pull/2246? | no | false
| bridge_adress | The address that the homeserver can use to connect to this appservice. | yes | http://localhost:80
| bridge_hostname | The hostname and port where this appservice should listen. | yes | 0.0.0.0
| bridge_port | The hostname and port where this appservice should listen.     | yes | 80
| database_type | The database type. "sqlite3" and "postgres" are supported.   | yes | sqlite3
| database_uri | | yes | mautrix-whatsapp.db
| database_max_open_conns | Maximum number of connections. Mostly relevant for Postgres. | no | 20
| database_max_idle_conns | Maximum number of connections. Mostly relevant for Postgres. | no | 2
| database_max_conn_idle_time | Maximum connection idle time and lifetime before they're closed. Disabled if null. | no | null
| database_max_conn_lifetime | Maximum connection idle time and lifetime before they're closed. Disabled if null. | no | null
| provisioning_api_prefix | Prefix for the provisioning API paths. | no | /_matrix/provision |
| provisioning_api_shared_secret | Shared secret for authentication. If set to "generate", a random secret will be generated, or if set to "disable", the provisioning API will be disabled. | no | generate
| provisioning_api_segment_key | Segment API key to enable analytics tracking for web server endpoints. Set to null to disable. Currently the only events are login start, QR code retrieve, and login success/failure. | no | null
| matrix_bridge_id | The unique ID of this appservice. | no | whatsapp |
| matrix_bridge_username | Username of the appservice bot. | no | whatsappbot
| matrix_bridge_displayname |Display name and avatar for bot. Set to "remove" to remove display name/avatar, leave emptyto leave display name/avatar as-is. | no | WhatsApp bridge bot
| matrix_bridge_avatar | Display name and avatar for bot. Set to "remove" to remove display name/avatar, leave empty to leave display name/avatar as-is. | no | mxc://maunium.net/NeXNQarUbrlYBiPCpprYsRqr
| matrix_protocol_ephemeral_events | Whether or not to receive ephemeral events via appservice transactions. Requires MSC2409 support (i.e. Synapse 1.22+). You should disable bridge -> sync_with_custom_puppets when this is enabled. | no | false
| matrix_protocol_as_token | Authentication tokens for AS <-> HS communication. Autogenerated; do not modify. | NO!!! | This value is generated when generating the registration
| matrix_protocol_hs_token | Authentication tokens for AS <-> HS communication. Autogenerated; do not modify. | NO!!! | This value is generated when generating the registration
| metrics_enabled | Enable prometheus metrics? | no | false
| metrics_listen | IP and port where the metrics listener should be. The path is always /metrics | no | 127.0.0.1:8001
| whatsapp_os_name | Device name that's shown in the "WhatsApp Web" section in the mobile app. | no | Mautrix-WhatsApp bridge
| whatsapp_browser_name | Browser name that determines the logo shown in the mobile app. Must be "unknown" for a generic icon or a valid browser name if you want a specific icon. List of valid browser names: https://github.com/tulir/whatsmeow/blob/8b34d886d543b72e5f4699cf5b2797f68d598f78/binary/proto/def.proto#L38-L51 | no | unknown
| whatsapp_debug_decode_before_send | Decode outgoing binary XML payloads to try to make sure they're valid before sending to WhatsApp. | no | false
| 

## Licence

Our Images are always having the Unlicence if possible. The Developer of this Image did use the GNU Affero General Public License v3.0 . This Licence gives us the requirement to passthrough the same Licence to be compliant.

### Permissions

- Commercial use
- Modification
- Distribution
- Patent use
- Private use

### Limitations

- Liability
- Warranty

### Conditions

- License and copyright notice
- State changes
- Disclose source
- Network use is distribution
- Same license

docker pull ghcr.io/kgncloud/mautrix-twitter:main
