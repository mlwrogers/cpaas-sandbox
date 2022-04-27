---
layout: default
title: Does JaaS support a waiting lobby?
parent: JaaS_FAQ
grand_parent: JaaS
---

## Does JaaS support a waiting lobby?

Yes!

JaaS supports both a Prejoin page as well as a lobby.

## Lobby

The lobby can be enabled using the [SETTINGS_PROVISIONING webhook.](https://developer.8x8.com/jaas/docs/webhooks-payload#settings_provisioning)

When the lobby is enabled, participants will be 'on hold' before joining a meeting, and moderators will be able to select and approve who can participate in the meeting.

In addition to enabling/disabling a passcode there are two types of lobby.
WAIT_FOR_APPROVAL or WAIT_FOR_MODERATOR

- If WAIT_FOR_APPROVAL is returned (or the lobbyType filed is missing) all non-moderator participants must 'knock on the door' / 'ask to join' and be approved by a moderator from the room.
- if WAIT_FOR_MODERATOR is returned the lobby is automatically disabled after the first moderator joins.

## Prejoin Screen
The prejoin page is displayed AFTER the lobby but BEFORE joining a meeting.It allows participants to enter a display name and select certain video/audio devices in addition to mute/unmute device options.

[Read more on the Prejoin page](https://developer.8x8.com/jaas/docs/jaas-prefs-prejoin)

## Customisation
Both the lobby and the prejoin screen can have a level of customisation through using the [advanced branding feature, documented here.](https://developer.8x8.com/jaas/docs/jaas-prefs-advanced-branding)
