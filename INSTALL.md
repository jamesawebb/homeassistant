# Profile

- Multi-factor Authentication Modules
- Themes: [Dark Cyan](https://community.home-assistant.io/t/dark-cyan-theme/28594)

# Add-ons

## Official

Repository at https://home-assistant.io/addons.

### Duck DNS

- Browse http://www.duckdns.org/
- Sign in with GitHub
  * jamesawebb@gmail.com
  * Chrome password
- Create token

```json
{
  "lets_encrypt": {
    "accept_terms": true,
    "certfile": "fullchain.pem",
    "keyfile": "privkey.pem"
  },
  "token": "!secret let_encrypt_token",
  "domains": ["famidamily.duckdns.org"],
  "seconds": 300
}
```

### Mosquitto broker

Used with Zigbee2mqtt.  

1. Create new user `mqtt`
2. Configure with:

```yaml
{
  "logins": [
    {
      "username": "mqtt",
      "password": "!secret master2"
    }
  ],
  "anonymous": false,
  "customize": {
    "active": false,
    "folder": "mosquitto"
  },
  "certfile": "fullchain.pem",
  "keyfile": "privkey.pem"
}```

## Community

Repository at https://github.com/hassio-addons/repository.

- Visual code
- Portainer
- Pi-hole
- InfluxDB

## Third-part Repositories

- [Google Drive Backup](https://github.com/sabeechen/hassio-google-drive-backup)
- [Zigbee2mqtt](https://github.com/danielwelch/hassio-zigbee2mqtt)
- [ESPHome](https://github.com/esphome/hassio)

# Integrations

- [Google Hangouts](https://www.home-assistant.io/components/hangouts/#steps-to-obtain-authorization-code)
  * Sign in with:
    - famidamily.hassio@google.com
    - !secret: basic
    - Grab Oauth code from Javascript console.  [Link](https://accounts.google.com/o/oauth2/programmatic_auth?scope=https%3A%2F%2Fwww.google.com%2Faccounts%2FOAuthLogin+https%3A%2F%2Fwww.googleapis.com%2Fauth%2Fuserinfo.email&client_id=936475272427.apps.googleusercontent.com&device_name=hangups) bookmarked for that account.

# Custom Components

- [HACS](https://custom-components.github.io/hacs/installation/manual/)

Add the following to `configuration.yaml` and restart:

```yaml
hacs:
  token: !secret my_github_access_token
```

- [Zigbee2mqtt network map](https://github.com/rgruebel/ha_zigbee2mqtt_networkmap)
- Zigbee [device pairing instructions](https://www.zigbee2mqtt.io/devices/MCCGQ01LM)
