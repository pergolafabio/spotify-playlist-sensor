# Spotify Playlist Sensor

[![GitHub Release][releases-shield]][releases]
[![GitHub Activity][commits-shield]][commits]
[![License][license-shield]](LICENSE.md)

![Project Maintenance][maintenance-shield]


_Component that pulls playlist data from your Spotify accounts. To integrate with [Spotify Playlist Card][Spotify-Playlist-Card]. Requires a Spotify Premium account._


**This component will set up the following platforms.**

Platform | Description
-- | --
`sensor` | Show Spotify playlist data from Spotify user.

![header][headerimg]

## Installation

1. Setup Spotify Developer account and follow directions from the Prerequisite section of [Spotify Media Player component](https://www.home-assistant.io/components/media_player.spotify/) to create a Spotify app specifically for this sensor. Don't forget to fill out the redirect URI.
- Do not use the same client ID and secret from your existing Spotify media player component as they may conflict.
2. Using the tool of choice open the directory (folder) for your HA configuration (where you find `configuration.yaml`).
3. If you do not have a `custom_components` directory (folder) there, you need to create it.
4. In the `custom_components` directory (folder) create a new folder called `spotify-playlist`.
5. Download _all_ the files from the `custom_components/spotify-playlist/` directory (folder) in this repository.
6. Place the files you downloaded in the new directory (folder) you created.
7. Add the sensor in your `configuration.yaml`
```yaml
sensor:
  - platform: spotify-playlist
    client_id: 'your_id'
    client_secret: 'your_secret'
```
8. Restart Home Assistant.
9. Check the Notifications tab in Lovelace UI to finish Spotify authorization.
10. Locate the sensor in the Home Assistant UI, view ``more info`` and confirm your playlists are loaded.
11. (Optional) Setup the [Spotify-Playlist-Card](https://github.com/dnguyen800/Spotify-Playlist-Card) to make use of this sensor.


Using your HA configuration directory (folder) as a starting point you should now also have this:

```text
custom_components/spotify-playlist/__init__.py
custom_components/spotify-playlist/manifest.json
custom_components/spotify-playlist/sensor.py
```

## Example configuration.yaml

```yaml
sensor:
  - platform: spotify-playlist
    client_id: 'your_id'
    client_secret: 'your_secret'
```


### Configuration options for `sensor` list

Key | Type | Required | Default | Description
-- | -- | -- | -- | --

`client_id` | `string` | `True` |  `test` | The Spotify client ID for the Spotify app you created during instructions.
`client_secret` | `string` | `True` | `test` | The Spotify client secret for the Spotify app you created during instructions.
`name` | `string` | `False` | `SpotifyPlaylist` | Name of the sensor, such as `playlists`.
`playlists` | `integer` | `False` | 6 | Selects the top x number of recent playlists. Most recent playlists start from the top to bottom in the Spotify app.


## FAQ
- How often does the sensor refresh?

I set it to two minutes. You can change the SCAN_INTERVAL in the ``sensor.py`` file to whatever you like.

- After I finish authorizing in the Home Assistant UI, a blank screen pops up.

Authorization should be complete and the sensor should be pulling data from Spotify now.

## Support
I am studying Python as a hobby and this is my first public project. Some fixes/requests may be out of my scope but I'll try my best. I hope you find it useful!

## Credits
  - [Spotify Media Player Home Assistant component](https://www.home-assistant.io/components/media_player.spotify/) - I re-used the token authorization code.
  - [Feed Parser component](https://github.com/custom-components/sensor.feedparser) - Used as a starting point to write the playlist sensor. Thanks!
  - [Blueprint component](https://github.com/custom-components/blueprint) - Used to standardize HA component and card documentation.


## Contributions are welcome!

If you want to contribute to this please read the [Contribution guidelines](CONTRIBUTING.md)

***
[Spotify-Playlist-Card]: https://github.com/dnguyen800/Spotify-Playlist-Card
[spotify-playlist]: https://github.com/dnguyen800/Spotify-Playlist-Sensor

[commits-shield]: https://img.shields.io/github/commit-activity/y/dnguyen800/Spotify-Playlist-Sensor.svg
[commits]: https://github.com/dnguyen800/Spotify-Playlist-Sensor/releases/commits/master
[headerimg]: header.png
[license-shield]: https://img.shields.io/github/license/dnguyen800/Spotify-Playlist-Sensor.svg?style=for-the-badge
[maintenance-shield]: https://img.shields.io/badge/maintainer-Dan%20Nguyen%20%40dnguyen800-blue.svg?style=for-the-badge
[releases-shield]: https://img.shields.io/github/release/dnguyen800/Spotify-Playlist-Sensor.svg?style=for-the-badge
[releases]: https://github.com/dnguyen800/Spotify-Playlist-Sensor/releases





