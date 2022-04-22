---
layout: default
title: Can we restrict JaaS to use a specific region or DC (Data Centre)?
parent: Security & Compliance
grand_parent: JaaS
---

## Can we restrict JaaS to use a specific region or DC (Data Centre)?
JaaS is using a worldwide infrastructure with datacenter's in multiple countries.
By default JaaS will always try to select the closest location to the first person entering/creating the meeting room; everyone else will then join the room setup in that location.

It is possible for you to force a specific cluster to be used instead of the ‘first-in-first-chosen’ approach, i.e. You can force the exclusive use of Frankfurt for example.
This can be done by setting the DC specific domain in the script source when you initialise the iFrame.

### Examples

The Default:
`  	<script src='https://8x8.vc/external_api.js' async></script> `
AND...
`window.onload = () => { const api = new JitsiMeetExternalAPI("8x8.vc", `

`FRANKFURT: 	<script src='https://frankfurt.8x8.vc/external_api.js' async></script>`
AND...
`window.onload = () => { const api = new JitsiMeetExternalAPI("frankfurt.8x8.vc", `

Using the approach outlined above the options currently available to you are:
* 8x8.vc (Default, closest location, First in First Chosen)
* frankfurt.8x8.vc (Germany)
* london.8x8.vc (UK)
* ashburn.8x8.vc (US-East)
* oregon.8x8.vc (US-West)
* saopaulo.8x8.vc (SA-East)
* mumbai.8x8.vc (India)
* sydney.8x8.vc (Australia)

## Important notes

There are a some important conditions surrounding this feature.
* IF the 1st participant to join the room is a PSTN participant then the room is always created in US-West (Oregon) DC.
* IF the region you chose to use is completely down for some reason (this has never happened, the whole DC (AWS/OCI) would need to be unavailable) then it will then get re-directed to another regional DC.
* For customers who absolutely cannot use a DC other than the chosen one, even in the above 2 circumstances, we are actively working to expose a new API call that will enable customers like yourself to query the DC where the conference is taking place.  By using this API call as the conference is initiated, if the conference does start in another region you can detect it and immediately end the conference.  You can then destroy the iFrame and display your own suitable message to the user/s and/or then re-attempt to create the conference in the preferred cluster location.  The logic in your app is yours to control in that regard.
