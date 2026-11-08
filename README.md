# skin-authlib-injector

A minecraft launcher-ready fork of **authlib-injector** that only proxies skins & capes and keeps the original Minecraft authentication, used by Syanic Launcher itself.

## Credits & Acknowledgement
- [@yushijinhun](https://github.com/yushijinhun) Creator of **authlib-injector**
- Contributors & Developers of [yushijinhun/authlib-injector](https://github.com/yushijinhun/authlib-injector/graphs/contributors)

## Changes
- Commit [chg: Disable the auth server and add the session server filter](https://github.com/syaniclauncher/skin-authlib-injector/commit/8303f3c4bd542955df3250ef4ee57d24b0586ccd)
    * Removed proxy for `authserver.mojang.com` (uses original servers)
    * Limited proxy for `sessionserver.mojang.com` to skins only (auth goes to original servers)
- Commit [add: Allow launching the game offline when the server is unreachable](https://github.com/syaniclauncher/skin-authlib-injector/commit/53f083d4245543aa8d8822dbff32e56490afa74b)
    * Loads the game in offline mode (“Offline” serverName) if the server is unreachable, instead of crashing the game like the original authlib.

> If you want to use this in your own project or minecraft launcher, I completely promote it, as I rather support communities instead of companies. ~@xsyanic

## Wiki
The wiki for implementing the server can be found [here](https://yushijinhun.github.io/authlib-injector/en/yggdrasil-server-technical-specification.html)

You can skip all the authentication related endpoints. 

## Download
You can download the latest authlib-injector build from [here](https://github.com/syaniclauncher/skin-authlib-injector/releases).

Or use the API url to download the latest release.

#### Request: 

`GET https://skinauthlibinjector.syanic.org/artifact/latest.json`

`GET https://syaniclauncher.github.io/skin-authlib-injector/artifact/latest.json`

#### Example Response: 
```json
{
  "build_number": 4,
  "version": "1.2.8",
  "release_time": "2026-11-08T22:46:05Z",
  "download_url": "https://github.com/syaniclauncher/skin-authlib-injector/releases/download/v1.2.8/skin-authlib-injector-1.2.8.jar",
  "checksums": {
    "sha256": "6a3a25a6cc665a619c89e5f4a411dd4de1ecec1b82877825d5e0556871a7961d"
  }
}
```

## Build
Dependencies: Gradle, JDK 17+. The target Java platform version is 8.
I reccomend to use [Termurin JDK 17](https://adoptium.net/temurin/releases?version=17&os=any&arch=any) to compile this project.

Run:
```
gradle 
```
(or `./gradlew` on Windows)

Build output can be found in `build/libs`.

## Deploy
Configure Minecraft server with the following JVM parameter:
```
-javaagent:{/path/to/skin-authlib-injector.jar}={Server URL}
```

## Options
They are same as [yushijinhun/authlib-injector](https://github.com/yushijinhun/authlib-injector/blob/develop/README.en.md#options), nothing new :)

## License
Files in the `wiki` subdirectory are licensed as [CC BY-SA 4.0](CC-BY-SA-4.0.txt) as the [orignal repo](https://github.com/yushijinhun/authlib-injector/blob/develop/README.en.md#license) is licensed.

All other files are licensed under the GNU Affero General Public License v3.0 or later, with the "AUTHLIB-INJECTOR" exception. The full text of the AGPLv3, including the authlib-injector exception, is available in [AGPLv3-with-authlib-injector-exception.txt](AGPLv3-with-authlib-injector-exception.txt).

> **"AUTHLIB-INJECTOR" EXCEPTION TO THE AGPL**
>
> As a special exception, using this work in the following ways does not cause your program to be covered by the AGPL:
> 1. Bundling the unaltered binary form of this work in your program without statically or dynamically linking to it; or
> 2. Interacting with this work through the provided inter-process communication interface, such as the HTTP API; or
> 3. Loading this work as a Java Agent into a Java Virtual Machine.
