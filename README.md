<img src="Synchmod/Assets.xcassets/AppIcon.appiconset/icon_128x128@2x.png" alt="Synchmod icon" width="64px" style="vertical-align: middle; margin-right: 8px;" />

# Synchmod

Synchmod is a batChmod-clone but for Apple Silicon instead.
It's only for changing file/folder ownership and permissions, with no other options found in the OG app.
Uses SMJobBless privileged helper tool.

## Disclaimer + TOS

Please use this at your own risk. It works for me, but I can’t guarantee it’ll work perfectly on every setup.
By using Synchmod, I assume no responsibility if it messes up your system.

## Usage

#### 1) Clone the repo

```bash
git clone https://github.com/ilovedoumiao/synchmod.git
```

#### 2) Open in Xcode

Project file: `Synchmod.xcodeproj`

#### 3) Signing

Change the targets' Team and Signing Certificate with your Apple Developer account/team as `SMJobBless` requires proper signing.


## Elevated Privileges

Synchmod will ask for your password on first launch first apply. This is to install the helper tool in so that it can makes your changes if `sudo` is required (i.e. changing owner from `root`, etc)

They will be installed in the following locations:
```
\Library\PrivilegedHelperTools
\Library\LaunchDaemons
```

### Notes

You may need to run the included `SMJobBlessUtil.py` after building to update the `Info.plist` identifier if your changes don't apply.

I've set the project to build for only `arm64` so change accordingly if you need a Universal version.

[Credits: mikeyh](https://gist.github.com/mikeyh/89a1e2ecc6849ff6056b7391c5216799)