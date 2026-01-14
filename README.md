# jhenkens' Home Assistant Blueprints

This repository contains a collection of Home Assistant blueprints, including both original creations and enhanced versions of blueprints forked from other repositories.

## Forked Repositories

This collection includes blueprints forked and enhanced from the following repositories:

### alexdelprete/ha-blueprints
Originally forked from [alexdelprete/ha-blueprints](https://github.com/alexdelprete/ha-blueprints)
- **Linked Entities** - Enhanced version for keeping multiple entities in sync

### edwardtfn/ha_auto_update_scheduled  
Forked from [edwardtfn/ha_auto_update_scheduled](https://github.com/edwardtfn/ha_auto_update_scheduled)
- **Auto Update Scheduled** - Automated Home Assistant updates on schedule
- **Auto Hide Updates** - Companion blueprint to hide updates until scheduled update

### gregmac/HomeAssistant-ZoozBlueprints
Forked from [gregmac/HomeAssistant-ZoozBlueprints](https://github.com/gregmac/HomeAssistant-ZoozBlueprints)  
- **ZEN Series Device Controllers** - Complete collection of Zooz Z-Wave device blueprints

## Original Blueprints

### Temperature Deviation Alert
Monitor temperature sensors and send alerts when they exceed configurable high temperature thresholds. Features dual-level alerting with different delays, repeated notifications with configurable frequency, and automatic clearing notifications when temperature returns to normal.

Exampe:
```
- id: '1636174329335'
  alias: Temperature Deviation - Fridge
  description: ''
  use_blueprint:
    path: jhenkens/temperature_deviation_alert.yaml
    input:
      temperature_sensor: sensor.sntmp_1_temperature
      helper_boolean: input_boolean.fridge_alert_helper
      alert_high_delay_2: 5
      alert_high_delay_1: 45
      alert_high_temperature_1: 41
- id: '1636174329335'
  alias: Temperature Deviation - Freezer
  description: ''
  use_blueprint:
    path: jhenkens/temperature_deviation_alert.yaml
    input:
      temperature_sensor: sensor.sntmp_2_temperature
      helper_boolean: input_boolean.freezer_alert_helper
      alert_high_delay_2: 5
      alert_high_temperature_1: 10
      alert_high_temperature_2: 20
```

### Confirm iOS Action  
Add confirmation prompts to iOS companion app actions before executing Home Assistant automations. Includes support for destructive action warnings with red highlighting for more serious operations.

### Integrated Motion Night Light
Automation for night light devices with integrated motion sensors. Designed to work with devices that have both motion detection and lighting capabilities on the same unit.


### Linked Entities
This blueprint allows you to easily create/maintain an automation that links the state of multiple entities:
  - turn ANY linked entity ON, it will turn ON ALL linked entities.
  - turn ANY linked entity OFF, it will turn OFF ALL linked entities.
  - set the brightness of any light entity, it will set the same brightness of ALL linked light entities.
  - set the color temp of any light entity, it will set the same color temperature of ALL linked light entities.
  - set the speed (percentage) of any fan entity, it will set the speed of ALL linked fan entities.

**NOTE**: You can select any entity with an ON/OFF state (switches, lights, etc.), lights with brightness or color temperature attributes, and Fans with speed (percentage) attributes.

### Auto Hide Updates
Auto-skip new updates when they become available. Use this to hide updates from the settings page until your scheduled auto-update runs, reducing visual clutter while maintaining control over when updates are applied.

### Auto Update Scheduled
Update Home Assistant automatically on a schedule when new updates are available. Includes safety features and customizable scheduling options. **Use at your own risk** - Home Assistant may restart automatically as part of the update process.

### ZEN Series Device Controllers
Collection of blueprints for Zooz ZEN series Z-Wave devices:
- **ZEN32 Controller** - Basic scene controller functionality
- **ZEN32 Controller - Cover Control** - Specialized for controlling covers/blinds
- **ZEN32 Controller - Custom Scene** - Advanced scene control with custom actions
- **ZEN51/52 Relay Controllers** - Single and dual relay automation
- **ZEN76 S2 Switch** - Smart switch automation 
- **ZEN77 S2 Dimmer** - Smart dimmer with advanced control features

**Source:**
[![jhenkens - ha-blueprints](https://img.shields.io/static/v1?label=jhenkens&message=ha-blueprints&color=blue&logo=github)](https://github.com/jhenkens/ha-blueprints "Go to GitHub repo")
