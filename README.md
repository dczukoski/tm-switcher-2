In progress code based on the MIT Licensed TM-Switcher by Brendan McGuire

# TM Switcher

TM Switcher will automatically manage robotics competition livestreams that use VEX Tournament Manager and OBS. It has been used successfully at dozens of events across multiple seasons.

Features:
- Integrates with OBS to automatically change scenes when matches are queued or started
- Record timestamps for when each match starts and its timestamp in the livestream
- Create recordings for every match
- Support for events with multiple fieldsets and multiple divisions. This software assumes that _each_ fieldset has its own livestream, so you will need to run an instance of the switcher for every livestream you wish to control.

## Install

Download the most recent build for your OS from [releases](https://github.com/dczukoski/tm-switcher-2/releases/), and run!

## Running at Events

Some key implementation details to be aware of when deploying this at your event.

- Make sure your LAN allows connections between devices! Typically, as an Event Partner, I will deploy our own router attached to the upstream network for our events. This is strongly recommended if you use tablet scoring or multiple computers in your tournament. Additionally, make sure that connections at the following ports are allowed between devices on your network: `80`, `4455`

- DWAB's Third Party API requires that integrations have an internet connection. This means that the
  device running the switcher must have access to the internet. Currently, the tokens DWAB issues
  have a lifetime of around 2 hours, and TM Switcher requests a new token every hour. This means
  that if your device running the switcher loses access to the internet, you have at least an hour
  to regain the connection before TM rejects the integration.

- You will need to supply an API Key from Tournament Manager. This can be obtained from `Tools > Options > Web Publishing`.

- When using Audience Display Automation, you likely want to select a relatively neutral scene transition effect, like a fade. Wipes or other lateral motion can interact poorly with how TM Switcher sequences audience display commands and scene changes. 

If your event has trouble with this tool, please get in touch with me!


## Disclaimer

This software is not officially supported by DWAB, VEX Robotics, Global Robotics and Science Foundation, Robot Revolution or the REC Foundation. Event Partners utilizing TM Switcher are doing so at their own risk. This software is licensed under the MIT License, which permits commercial and non-commercial uses. The author and all contributors disclaim all liability for running this software at your events.
