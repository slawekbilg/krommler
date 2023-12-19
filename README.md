# krommler
# home assistant integration, local LAN econet

# EcoNET
  - platform: rest
    scan_interval: 60
    resource: !secret econet_host_lan_regParams
    method: GET
    name: KrommlerRegEcoNet
    verify_ssl: false
    username: !secret econet_user
    password: !secret econet_pass
    authentication: basic
    headers:
      User-Agent: Home Assistant
      Content-Type: application/json
    value_template: "OK"
    json_attributes:
    - curr
