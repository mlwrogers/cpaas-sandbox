---
layout: default
title: Does JaaS support breakout rooms?
parent: JaaS_FAQ
grand_parent: JaaS
---

## Does JaaS support breakout rooms?

Yes!

Jitsi Breakout Rooms enables a moderator to split a Jitsi meeting into smaller groups.  A moderator can bring particpants back into the main room at any time.

Each breakout room is a completely unique room they are completely separate from each other and from the main room in terms of audio/video.  There is no audio/media "leak" or interference between rooms.

Breakout Rooms can be created at any time before or during a meeting. A Moderator can either assign participants to specific rooms or participants can join & leave rooms themselves.

## What do they look like in UI?

Take 2 mins to watch Saghul doing a quick run through of how participants and Moderators can use Breakout rooms.

<iframe width="560" height="315" src="https://www.youtube.com/embed/ubYYZ0daw10" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Can i pre-create and control breakout rooms using the iFrame API?

Yes!  
The following iFrame API controls are available to you.

### Functions
- listBreakoutRooms

### Commands
- addBreakoutRoom
- autoAssignToBreakoutRooms
- closeBreakoutRoom
- joinBreakoutRoom
- removeBreakoutRoom

### Events
- The `videoConferenceJoined` event includes a new boolean value to indiciate if the room is a breakout room or not.

You can read more details on the API in the [Jitsi handbook here.](https://jitsi.github.io/handbook/docs/dev-guide/dev-guide-iframe/#addbreakoutroom)

## Can i disable breakout rooms?

Yes.
There are several options for controlling breakout room features by using configOverWrite, [documented here.](https://github.com/jitsi/jitsi-meet/blob/master/config.js#L1102)

If you you are not yet familiar with using configOverWrite and customising your meetings, [take a look at our faq](https://mlwrogers.github.io/cpaas-wiki/docs/jaas/faq_customise/) to help get you started.

## 📘  Notes
{: .text-blue-000 }

 Some noteworthy points for the current implementation of Breakout Rooms

- Only Moderators can create Breakout Rooms.
- The Breakout Room names are currently not editable.
- Call recording _currently_, only works in the main room. Individual breakout rooms cannot be recorded.
- In a password-protected meeting, participants will need to re-enter the password to get back into the main room.
  - Breakout Rooms can be individually password-protected
- A Moderator can call all particpants back to the main room just by closing the breakout room.
  - To close a breakout room the Moderator cannot be in that room, i.e. the Moderator needs to be in a different breakout room or the main room.
- For the Moderator to perform an action on a participant (move/kick/mute) they must be in the same room as that participant.
- It is possible to create Breakout rooms before other participants join the meeting, but participants can only be assigned after they join the meeting. This is because (amongst other things), guest users don’t exist in the Jitsi ecosystem until they join the meeting (since there’s no registration of any kind), so there’s no way of assigning them.
