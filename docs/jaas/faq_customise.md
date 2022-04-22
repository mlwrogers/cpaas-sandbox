---
layout: default
title: Can i still customise and brand the JaaS meeting experience?
parent: JaaS_FAQ
grand_parent: JaaS
---

## Can i still customise and brand the JaaS meeting experience?

Yes, absolutely!

We support a number of different ways for you to do that, from a quick and easy _watermark_ and custom meeting URL to a more bespoke user interface and/or layout.
The different options are covered by; Branding, Advanced Branding and Customising your meetings UI.

### Branding

The easiest, but most basic option; JaaS supports a high-level _branding_ capability that allows you to easily customise the meeting experience from within the [JaaS console.](https://jaas.8x8.vc/), no extra coding required.

This Branding page enables you to brand all meetings that run on your AppID with your own:

* Custom meeting invite URL
* Enterprise Logo or symbol
* Company website link
* UI background image or color
* Custom DID list URL

For complete information on this please refer to the [Branding page](https://developer.8x8.com/jaas/docs/jaas-console-branding)

### Advanced Branding

Taking things a little further is our Advanced Branding capability; this allows you to configure elements on your meeting's UI on a _per-room_ basis.

📘 It's important to note that as soon as you setup an advanced branding URL your basic/global Branding settings (detailed above) will be ignored... This is true also in the event your advanced branding endpoint fails to respond or responds with an error.
{: .text-blue-000 }

Configuring the advanced branding capabilities consists of setting up an endpoint on your backend which will serve the branding data payload.

For complete information on this please refer to the [Advanced branding page](https://developer.8x8.com/jaas/docs/jaas-prefs-advanced-branding)

For quick reference, here is an example of an advanced branding payload.
```
{
  "backgroundColor":"#FFF",
  "backgroundImageUrl":"https://mycompany.com/images/background.png",
  "didPageUrl":"https://mycompany.com/dids",
  "inviteDomain":"https://mycompany.com/invite",
  "logoClickUrl":"https://mycompany.com",
  "logoImageUrl":"https://mycompany.com/images/logo.png",
  "avatarBackgrounds": ["#12A378", "linear-gradient(125.83deg, #000 0%, #FFF 99.09%)"],
  "premeetingBackground": "url(https://mycompany.com/images/premeetingBackground.png)",
  "virtualBackgrounds": ["https://my.img01.jpg", "https://my.img02.jpg"],
  "labels": {
    "en": "https://myenglishlabels.json",
    "fr": "https://myfrenchlabels.json",
    "ptBR": "https://mybrazilianlabels.json"
  },
  "customTheme": {
    "palette": {
      "ui01": "orange !important",
      "ui02": "maroon",
      "surface02": "darkgreen",
      "ui03": "violet",
      "ui04": "magenta",
      "ui05": "blueviolet",
      "field02Hover": "red",
      "action01": "green",
      "action01Hover": "lightgreen",
      "action02Disabled": "beige",
      "success02": "cadetblue",
      "action02Hover": "liceblue"
    },
    "typography": {
      "labelRegular": {
        "fontSize": 25,
        "lineHeight": 30,
        "fontWeight": 500
      }
    }
  }
}
```

### Customising your meetings UI

The meeting's UI can be further customised through the configOverwrite and interfaceConfigOverwrite objects which are part of the JitsiMeetExternalAPI's options object.

This enables you to choose the video layout (gallery, focus etc.) as well as which buttons are displayed or even to remove the Jitsi toolbar completely and create your own buttons using the API, and many other elements.

For a complete list of all possible values, please refer to :

[config.js](https://github.com/jitsi/jitsi-meet/blob/master/config.js) for possible configOverwrite object values.
[interface_config.js](https://github.com/jitsi/jitsi-meet/blob/master/interface_config.js) for possible interfaceConfigOverwrite object values.

📘  Note that not all options found in the two config files are overwritable.
{: .text-blue-000 }

Please see below a snippet on how to use the config and interface config overwrites in your application:
```
const domain = '8x8.vc';
const options = {
    ...
    configOverwrite: { startWithAudioMuted: true },
    interfaceConfigOverwrite: { DISABLE_DOMINANT_SPEAKER_INDICATOR: true },
    ...
};
const api = new JitsiMeetExternalAPI(domain, options);
```

There is a wide array of configurable things for the conference, some of which are described in the main JaaS documentation website such as:
[How to manage the UI buttons](https://developer.8x8.com/jaas/docs/customize-ui-buttons)
[How to set the default language](https://developer.8x8.com/jaas/docs/customize-ui-default-language)
