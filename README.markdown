# DynMap 1.16.4 modded block renders

I wanted to create a DynMap For my All The Mods 6 (ATM6) server. It's been a bit of a journey. I thought I'd share some of my resources along the way.

## Installing DynMap for ATM6

DynMap for Forge for Minecraft 1.16.4 isn't officially released yet, but I pulled the snapshot off of [the build server](https://dynmap.us/builds/dynmap/) (Dynmap-3.1-SNAPSHOT-forge-1.16.4.jar), and it's working well for me so far!

I had to up my `max-tick-time` to 999999 in `server.properties` to give DynMap enough time to initialise on first boot. This is probably overkill and bad practice, but it's worked.

## Modded Block Rendering

That works great, except it only renders vanilla minecraft blocks, leaving whole swaths of black where modded blocks (particularly those from BYG) should be.

I could not find any Model or Texture files that seem to have been generated for ATM6, so I have started generating them. I'll tell you how to use mine, and then explain how I went about making them in case you want to contribute.

### Install mine

Download everything (or the mods you are interested in) in the `renders` folder of this repository, and put them in the `dynmap/renderdata` folder of your minecraft server (this folder should be generated the first time you run DynMap)

### Generate your own

To create these, I found @Lumrenion's fork of DynmapBlockScan, which [has a branch where they are getting it to work for 1.16.4](https://github.com/Lumrenion/DynmapBlockScan/tree/1.16.4). There is no documentation for this, so I `git clone`d it, ran `./gradlew clean build` to compile it, and then used my compiled version to follow [these instructions](https://www.reddit.com/r/feedthebeast/comments/f9gker/howto_add_missing_mod_textures_to_dynmap_112/).

I tried running it alongside the whole of ATM6, but I set it off running, and after several hours it had not completed, and I couldn't tell if it was working or errored, so I'm going to selectively run it for the mods I need. I will be generating more as I need for my server, but if there are any that I've missed, let me know in the issues of this github repo and I'll see if I can generate them.
