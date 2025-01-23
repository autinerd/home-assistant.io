---
title: Enigma2 (OpenWebif)
description: Instructions on how to integrate an Enigma2 based box running OpenWebif into Home Assistant.
ha_category:
  - Media player
ha_release: '0.90'
ha_iot_class: Local Polling
ha_codeowners:
  - '@autinerd'
ha_domain: enigma2
ha_config_flow: true
ha_platforms:
  - media_player
ha_integration_type: device
---

The **Enigma2** {% term integration %} allows you to control a Linux based set-top box which is running [Enigma2](https://github.com/oe-alliance/oe-alliance-enigma2) with the OpenWebif plugin installed.

[OpenWebif](https://github.com/E2OpenPlugins/e2openplugin-OpenWebif) is an open source web interface for Enigma2 based set-top boxes.

### Prerequisites

Your device needs to have the OpenWebif plugin installed. On most devices it is installed by default, if not it is available via the Plugins menu within your Enigma2 distribution.

{% include integrations/config_flow.md %}

## Entities

Currently, the following entity is exposed:

### Media player

The following actions are supported: Play, Pause, Channel up and down (represented by previous and next track), setting volume, switching the channel via the source list.

The bouquet for the source list can be configured via the Configure button of the device entry on the [integration page](https://my.home-assistant.io/redirect/integration/?domain=enigma2).

## Remove integration

This integration follows standard integration removal, no extra steps are required.

{% include integrations/remove_device_service.md %}
