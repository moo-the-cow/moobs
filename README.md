# moobot-light

## Requirements:
Docker - Linux Containers

Docker-Compose


## Setup (based on windows environment):

modify your [appsettings.conf](appsettings.conf)

fill out everything that is marked like this `<REPLACE ME>`

put all the files into a folder

in a Terminal type:
```
docker compose up -d
```

## Features
option to send requests from twitch to obs and returning data (via whisper or normal chat message in public)

automatic scene switching on low bitrate/high rtt

persmissions on each command

## Main Command
| Object (do not modify!) | Name (alias) | Enabled | Role Permission |
| ---- | ---- | :---: | -------- |
| Obs | !obs | true |  broadcaster, moderator  |

## Sub Commands

| Object (do not modify!) | Name (alias) | Enabled | Whisper result | Role Permission |
| ---- | ---- | :---: | --- | -------- |
| GetVersion | GetVersion | true | false |  broadcaster, moderator  |
| GetStats | GetStats | true | true | broadcaster, moderator  |
| SetCurrentSceneCollection | SetCurrentSceneCollection | true | null | broadcaster, moderator |
| SetCurrentProgramScene | SetCurrentProgramScene | true | null | broadcaster, moderator |
| SetSceneItemEnabled | SetSceneItemEnabled | true | null | broadcaster, moderator |

## Usage on Twitch
`!obs GetVersion` will show

*MoobsWebsocket v1.0 on Moobot-light (OBS: <OBS_VERSION>)*

`!obs GetStats` will whisper the user who triggerd the command OBS Stats (only remaining recording diskspace for now)

*Diskspace Left: 94,26 GB*

`!obs SetCurrentSceneCollection <SCENECOLLECTION_NAME>` will switch to the scene collection with that name

`!obs SetCurrentProgramScene <SCENE_NAME>` will switch to the scene with that name

`!obs SetSceneItemEnabled <ITEM_NAME>` will switch to the Source of the current selected Scene with that name
