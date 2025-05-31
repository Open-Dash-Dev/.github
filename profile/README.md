# Open Dash
![Client Progress](https://progress-bar.xyz/0/?title=client) ![Server Progress](https://progress-bar.xyz/16/?title=server)  ![NodeJS](https://img.shields.io/badge/Node.JS-v23.11.0-green?logo=nodedotjs&logoColor=white) ![Godot](https://img.shields.io/badge/Godot-v4.4.1-blue?logo=godotengine&logoColor=white) ![GD](https://img.shields.io/badge/Recreated%20GD-none-red)

## Welcome!
This organization is dedicated to the Open Dash project; a project to remake Geometry Dash in the Godot Game Engine (*Exact* version used can be downloaded from this URL: [Well, it's a placeholder while I upload it.](https://example.com/)).
Want more info? Here are some specifics about the magical bytes that made these megabytes:
- **Godot Version:** 4.4.1 *C#*
- **Primary Development Platforms:** ***Windows 11*** *24H2*
- **Server NodeJS Version:** v23.11.0

## Server
The game has its own custom server framework, built with Node.JS, check out the [server repo](https://github.com/Open-Dash-Dev/server/) for more information.
**But if you want a byte of the technical stuff, look at the bottom of this README.**

## Client
The client is the Godot part, and unfortunately, is currently **incapable** of replicating Geometry Dash version *1.0*. It's still barely developed, so what would you expect?

# Technical Overview
> [!WARNING]
> Technical Stuff with `console.log("CODE?! 🙀 (UH OH!)");`, some super brain dazzling Java-based Object Notation, and a whole world of technical HTTP wirey, JS supercode, and some Bongo Mongo for Databases, and O-SO-MUCH more, if you just want to play, go to the [client repo](https://github.com/Open-Dash-Dev/client/) and head over to releases.

## Some quick definitions
Some words will be short, here is what we mean by some stuff.
- HTTP: HyperText Transfer Protocol; used to send information from your PC to our server.
- GD: Simply Geometry Dash.
- GJ: Geometry Dash's original name; Geometry Jump, the game still uses it a *lot* internally.
- OD/OJ: Same as GD/GJ, but O means Open.
- MongoDB: The database to hold user and level info!

## A better progress marker
As you saw, the client is *0%* done so far. Here is a checklist of what we've done:
- [ ] Gameplay
- [ ] Icon Kit
- [ ] Menus
- [ ] Editor
- [ ] Start the Godot project
- [ ] GitHub Repo

Also, here's the server stuff!
- [ ] Node JS talking
- [x] Figure out GD server stuff
- [x] Plan structure
- [x] Start NodeJS Project
- [x] GitHub Repo
- [ ] Actually code it. (99% of the server, died in Ender Dragon fight, needs to respawn.)
- [ ] Rate limits
- [x] MongoDB Setup

## Server
The server, as most servers do, has MANY endpoints, as who wants to be like `www.server.info?iWantTo=uploadLevel`, if you want, here is an overview:
> [!WARNING]
> 1:
> The endpoint `CreateOJUser`, and all `gd` ones are rate limited to 5 requests/min to prevent user overpopulation (👥👥👥👥👥👥) and also RobTop's servers from melting into a blop of silicon.
> 2:
> Most of these endpoints are a pure plan. Nothing is implemented.

- **`level/`:** The level block sender 🧱
  - **`uploadOJLevel10`:** Upload a level
  - **`searchOJLevel10`:** Search for a level
  - **`downloadOJLevel10`:** You'll never guess what this does... downloads a level.
- **`user/`:** The semi-user system to express yourself with a username! 🙎‍♂️
  - **`createOJUser`:** Creates a user
  - **`downloadOJUser`:** Pretty simple, downloads user data.
- **`gd/`:** RobTop server requester. You get Open Dash + it's Geometrical inspiration.
  - **`downloadGJLevel`:** Downloads a GD level and also brings along some extra data from search!
  - **`searchGJLevel`:** Well, it searches for a GD level
  - **`convertGJLevelOJ`:** Converts a GD level to OD, it's not gonna work perfectly though.
  - **`needGJLevelData/`:** This needs GD level data stored as Base64 in the `gd` parameter.
    - **`convertGJLevelOJ`:** Does the same as the other one... but you provide the level.
- **`song/`:** 200 OK. Audio is now found.
  - **`urlGJMusicLib`:** Resolves a GD Music Library ID to a URL.
  - **`urlNGMusic`:** Resolves Newgrounds Music... and includes the GD whitelisted songs only.
  - **`urlOJMusicLib`:** Will resolve Open Dash Music Library IDs to URLs.
