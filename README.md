# moobot-obs

# Announcement: this should be stable by now - I will write an update after a successful stream

## Requirements:
- Docker - Linux Containers

- Docker-Compose

- Streaming Setup from https://github.com/moo-the-cow/streaming MINUS the noalbs version, which this bot will replace. I will properly add this here in time


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
| NginxStats | !br | true |  broadcaster, moderator  |

## Sub Commands

| Object (do not modify!) | Name (alias) | Arguments | Enabled | Whisper result | Role Permission
| ---- | ---- | ---- | :---: | --- | -------- |
| GetVersion | version | (none) | true | false |  broadcaster, moderator  |
| GetStats | stats | (none) | true | true | broadcaster, moderator  |
| SetCurrentSceneCollection | SetCurrentSceneCollection | (string name of scene collection) | true | null | broadcaster, moderator |
| SetCurrentProgramScene | scene | (string name of scene) | true | null | broadcaster, moderator |
| StartStream | start | (none) | true | null | broadcaster, moderator |
| StopStream | stop | (none) | true | null | broadcaster, moderator |
| StartRecord | StartRecord | (none) | true | null | broadcaster, moderator |
| StopRecord | StopRecord | (none) | true | null | broadcaster, moderator |
| SetRtt | SetRtt | (number) | true | null | broadcaster, moderator |
| SetBitrate | SetBitrate | (number) | true | null | broadcaster, moderator |
| Autoswitch | Autoswitch | (false/true) | (string name of scene collection) | true | null | broadcaster, moderator |
| SendTwitchMessages | twitchmessages | (false/true) | true | null | broadcaster, moderator |

### Group Roles
(attribute `group`)

broadcaster, moderator, vip, subscriber, turbo, partner, staff, everyone

### User Role
Requires the attribute `username` and then the username value `<USERNAME>`

example (non-working) entry for a user
```
"DummyCommand": {"name":"DummyCommandName", "enabled":true, "permission":[{"group":"moderator","cooldown":0},{"username":"m_o_o_","cooldown":0}]},
```

## Usage on Twitch
`!obs version` will show

*MoobsWebsocket v1.0 on Moobot-Obs (OBS: <OBS_VERSION>)*

`!obs stats` will whisper the user who triggerd the command OBS Stats (only remaining recording diskspace for now)

*Diskspace Left: 94,26 GB*

`!obs SetCurrentSceneCollection <SCENECOLLECTION_NAME>` will switch to the scene collection with that name

`!obs scene <SCENE_NAME>` will switch to the scene with that name

`!obs twitchmessages false` will disable/enable twitch messages for autoswitch (in case of spam)

`!obs Autoswitch false` will disable/enable autoswitch on bad connections completely (so you have to set it manually!)
