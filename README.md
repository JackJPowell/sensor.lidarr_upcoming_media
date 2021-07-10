# sensor.lidarr_upcoming_media
Lidarr component to feed Upcoming Media Card.

Home Assistant component to feed [Upcoming Media Card](https://github.com/custom-cards/upcoming-media-card) with
Lidarr's upcoming releases.</br>
This component does not require, nor conflict with, the default Lidarr component.</br></br>
### Issues
Read through these two resources before posting issues to GitHub or the forums.
* [troubleshooting guide](https://github.com/custom-cards/upcoming-media-card/blob/master/troubleshooting.md)
* [@thomasloven's lovelace guide](https://github.com/thomasloven/hass-config/wiki/Lovelace-Plugins).

## Installation:

1. Install this component by copying [these files](https://github.com/custom-components/sensor.lidarr_upcoming_media/tree/master/custom_components/lidarr_upcoming_media) to `/custom_components/lidarr_upcoming_media/`.
2. Install the card: [Upcoming Media Card](https://github.com/custom-cards/upcoming-media-card)
3. Add the code to your `configuration.yaml` using the config options below.
4. Add the code for the card to your `ui-lovelace.yaml`. 
5. **You will need to restart after installation for the component to start working.**

| key | default | required | description
| --- | --- | --- | ---
| api_key | | yes | Your Lidarr API key
| host | localhost | no | The host Lidarr is running on.
| port | 8686 | no | The port Lidarr is running on.
| urlbase | / | no | The base URL Lidarr is running under.
| days | 7 | no | How many days to look ahead for the upcoming sensor.
| ssl | false | no | Whether or not to use SSL for Lidarr.
| max | 5 | no | Max number of items in sensor.
</br>

**Do not just copy examples, please use config options above to build your own!**
### Sample for configuration.yaml:

```
sensor:
  - platform: lidarr_upcoming_media
    api_key: YOUR_API_KEY
    host: 127.0.0.1
    port: 8686
    days: 7
    ssl: false
    max: 10
```

### Sample for ui-lovelace.yaml:

    - type: custom:upcoming-media-card
      entity: sensor.lidarr_upcoming_media
      title: Upcoming Music
      
      
### Card Content Defaults:

| key | default | example |
| --- | --- | --- |
| title | $title | "Under the Table and Dreaming" |
| line1 | $studio | "Dave Matthews Band" |
| line2 | $release | "Mon, 10/31 9:00pm" if it's more than a week away or "Monday, 9:00pm" if it's within a week.|
| line3 | $runtime | "45 min" |
| line4 | $genres | "Rock"
| icon | mdi:music | https://materialdesignicons.com/icon/music