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

[OpenWebif](https://github.com/E2OpenPlugins/e2openplugin-OpenWebif) is an open-source web interface for Enigma2 based set-top boxes.

### Prerequisites

Your device needs to have the OpenWebif plugin installed. On most devices it is installed by default, if not, it is available via the Plugins menu within your Enigma2 distribution.

Please beware that the OpenWebif setting "Require client cert for HTTPS" is not supported.

{% include integrations/config_flow.md %}

{% configuration_basic %}
Host:
    description: "The IP address or hostname of your device."
Port:
    description: "The port of the OpenWebif service running. Defaults to 80."
Username:
    description: "The username, if HTTP(S) Authentication is enabled."
Password:
    description: "The password, if HTTP(S) Authentication is enabled."
Uses an SSL certificate:
    description: "Whether HTTPS is enabled."
Verify SSL certificate:
    description: "Whether the SSL certificate should be verified."
{% endconfiguration_basic %}

## Configuration options

The integration provides the following configuration options:

{% configuration_basic %}
Turn off to deep standby:
    description: "Shuts the device down (called Deep Standby) on turning off the device.
                Beware that the device can no longer be reached when shut down! Turning on the device is only possible via Wake on LAN, the power button on the device or the remote control!"
Bouquet to use as media source:
    description: "Sets the bouquet to use for the source list."
{% end configuration_basic %}

## Entities

Currently, the following entity is exposed:

### Media player

The following actions are supported: Play, Pause, Channel up and down (represented by previous and next track), setting volume, switching the channel via the source list.

The bouquet for the source list can be configured via the Configure button of the device entry on the [integration page](https://my.home-assistant.io/redirect/integration/?domain=enigma2).

## Data updates

My integration fetches data from the device every 15 seconds by default.

## Troubleshooting

### Getting a 403.6 IP address rejected error on setup

#### Description

OpenWebif has a protection by default, so that only devices in the same subnet can connect to the device.

#### Resolution

There are two solutions: You can either enable HTTP(S) Authentication or enable the setting "Enable access from VPNs"

## Remove integration

This integration follows standard integration removal, no extra steps are required.

{% include integrations/remove_device_service.md %}
