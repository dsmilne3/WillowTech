<!-- TOC -->

- [My Laptop](#my-laptop)
- [Native Tools, Settings, & Preferences](#native-tools-settings--preferences)
- [Homebrew](#homebrew)
- [Raycast](#raycast)
- [Window Management](#window-management)
- [Break Timer](#break-timer)
- [App Switching](#app-switching)
- [Menu Bar Widgets and Utilities](#menu-bar-widgets-and-utilities)
- [Shell & Terminal](#shell--terminal)
- [Docker Desktop](#docker-desktop)
- [Web Browser](#web-browser)
- [VS Code](#vs-code)
- [Node.js](#nodejs)
- [Other Apps I Use Often](#other-apps-i-use-often)
- [Screen Recording & Demo Editing](#screen-recording--demo-editing)

<!-- /TOC -->

This repo contains info on all the apps / tools / settings I use on my Mac.

## My Laptop

I'm using a 16" Macbook Pro with Apple silicon for work at Cisco AppDynamics.

- Apple M1 Pro
- 16GB RAM
- 500GB SSD
- [Complete specs](https://everymac.com/systems/apple/macbook_pro/specs/macbook-pro-m1-pro-10-core-cpu-16-core-gpu-16-2021-specs.html)

## Native Tools, Settings, & Preferences

These are my preferred settings changes for my peripherals, Desktop, Dock, and Finder.

### System Settings -> Mouse

- Tracking speed = 3rd fastest
- Natural scrolling = Disabled
- Smart Zoom = Enabled

### System Settings -> Printers & Scanners

The Canon Pixma MX472 print drivers are preinstalled in MacOS, so the printer installation is straight forward. But I had to download the latest scanner ICA driver and IJ Scan Utility for my version of MacOS (currently 14.x). For some reason, Canon's US support site didn't have these, so I had to use [the site for Canada](https://canoncanada.custhelp.com/app/browse/a_status/published/channelRecordID/DRIVERS_AND_SOFTWARE/pageSize/25/productCategoryAnsList/RN_PRODUCT_2403%3ARN_CATEGORY_3516%3ARN_CATEGORY_318/productRecordID/RN_PRODUCT_2403/truncate/200/type/browse/session/L3RpbWUvMTczMDAxMjc2My9nZW4vMTczMDAxMjc2Mi9zaWQvZlVSeUFzX1dtMEhldzNGaTM1JTdFMWklN0VSYkRoOHVJX3B4cDZISmFqXzcxT0JVVmJ4aFVnellMYnFud1VaUWhLR1JMRzNwUG1Kc3BmTjJxRmNSSTR5SUZ4UExza2dHdXdqN0d1NXNCUU0ydSU3RW5xZHY0Sk9JMFhRQTd3JTIxJTIx).

### System Settings -> Desktop & Dock

I remove most apps from the dock except the ones I use most often so I can easily launch and switch between them. This may change as I attempt to transition to using the keyboard and Finder (or its replacement) more often.

- Dock
  - Size = Large; Magnification = Off; Position on Screen = Right; Minimize windows into application icon = Enabled; Automatically hide/show dock = Enabled; Show suggested and recent apps in Dock = Disabled
- Desktop & Stage Manager
  - Show Items: On Desktop = Enabled; In Stage Manager = Disabled
  - Click wallpaper to reveal desktop = Only in Stage Manager
- Keyboard -> Keyboard Shortcuts -> Spotlight
  - Show Spotlight search = Disabled (you'll see why in the RayCast section)

### Finder Settings and View Preferences

I like to be able to see when a device or server connection is persistent. Since I leave my desktop relatively bare, these settings help me notice that I might have some cleanup work to do. Separately, don't use tags in MacOS.

- Settings
  - General
    - Show these on the desktop: CDs, DVDs, and iPods = Disabled
    - New Finder windows show -> Home Folder
  - Tags - All disabled
  - Sidebar
    - Favorites - Recent, Movies, Music, Pictures = Disabled
    - Locations - MacBook Pro = Disabled
    - Tags - Recent Tags = Disabled
  - Advanced
    - Show warning before changing an extension = Disabled
    - Keep folders on Top: In windows when sorting by name = Enabled
    - When performing a search: Search the current folder
- View
  - Show Tab Bar
  - Show Path Bar
  - Show Status Bar

## Homebrew

[Homebrew](https://brew.sh/) is my preferred package manager for MacOS. We'll use it extensively to install tools and apps from the command line. Xcode CLI Build Tools is included in the installation. Open up the built in `Terminal` app and run the install command from the website.

**Be sure to follow the instructions in the terminal - especially any commands that are needed to complete the configuration.**

After Homebrew is done installing, we will use it (via RayCast) to install everything else we need.

## Raycast

Credit goes to CJ at CodeingGarden for introducing me to [RayCast](https://www.raycast.com/) and some other utilities. You can check out this [video of his full setup](https://youtu.be/GK7zLYAXdDs?si=pXhMJ7DuB_48x5Jt&t=427).

The built in `Spotlight` tool prioritizes web search results over local apps or folders and there's no way to modify that behavior. RayCast doesn't do that and has a ton of other features. Install it by downloading the package from the website or via Homebrew by opening a `Terminal` and running this command:

```sh
brew install raycast
```

**The first time you luanch RayCast, be sure to select the configuration option to use Spotlight's default keyboard shortcut (Command+Space)**.

### RayCast Homebrew Plugin

Install the [RayCast Homebrew Plugin](https://www.raycast.com/nhojb/brew) so we can easily install formulae and casks directly from RayCast.

## Window Management

Positioning windows with keyboard shortcuts isn't included in MacOS, so we need an app for it. RayCast has this feature, but requires a Pro subscription. So instead, I use [rectangle](https://rectangleapp.com/).

Search for `rectangle` in RayCast `brew search` or:

```
brew install rectangle
```

Launch the app to configure settings:

- Launch on login = Enabled
- Check for updates automatically = Enabled

## Break Timer

I use [Stretchly](https://hovancik.net/stretchly/) mainly because it doesn't have any in-app purchases. As of this writing, it's an unsigned app, so it needs a little special treatment to get installed...

```sh
brew install --cask --no-quarantine stretchly
```

Launch the app to configure settings:

- Start Stretchly automatically when logging in = Enabled
- Shows breaks on all monitors = Disabled
- Show breaks even in Do Not Disturb mode = Enabled
- Schedule:
  - Mini Break - 1 minute every 15 minutes
  - Long Break - 5 minutes every 60 minutes
- Theme:
  - Enable transparency = Enabled

## App Switching

The built in App switcher only shows application icons. It also only shows one icon per app regardless of how many windows of that app there are. So instead, I use an app switcher called [AltTab](https://alt-tab-macos.netlify.app/). It shows full window previews, and has an option to show a preview for every open window in all applications (even minimized ones).

Search for `alt-tab` in RayCast `brew search` or:

```sh
brew install alt-tab
```

Launch the app enable the settings that would allow it to take screenshot thumbnails , it enable it in the list of apps allowed to do Screen & System Audio Recording and control the screen. In addition, add these configuration settings to replace the default app switcher's shortcut (`Command`+`Tab`):

- Controls tab -> Shortcut 1 -> Trigger shortcut: set to Hold `Command`
- Appearance tab -> Thumbnails: Size = Small

## Menu Bar Widgets and Utilities

At this point, there are a ton of icons in the menu bar and it's missing some helpful information. There's an app for that...

### Default Widgets

These are accessed by clicking the system date/time in the Menu Bar. I'm still exploring what's available for my new laptop. More to follow as I play around with them.

### System Stats Widgets

I use [stats](https://github.com/exelban/stats) to see CPU usage / temp, RAM utilization, and network traffic at a glance.

Search for `stats` in RayCast `brew search` or:

```sh
brew install stats
```

Launch the app to configure settings:

- Start automatically when logging in = Enabled
- Select Do not share anonymous telemetry data
- Review the icon/widget settings you want to see
- I usually merge the label with the graph widget and set them with a Frame and color them based on some value so they turn yellow/red as that metric increases.

### Hidden Bar

I use [Hidden Bar](https://github.com/dwarvesf/hidden) to choose which icons should be hidden after a timeout.

Search for `hiddenbar` in RayCast `brew search` or:

```sh
brew install hiddenbar
```

## Shell & Terminal

I don't mind the default `Terminal`, but I do have some visual preferences I set in the `Ocean.terminal` file you can check out in this repo.

An ennhancement to `Zsh` is [Oh My Zsh](https://ohmyz.sh/).  Get the install command from the website.

I haven't discovered any specific settings to change yet, but I'll add those here if/when I do.

### Load dotfiles

All my dotfiles are stored on [github](https://github.com/w3cj/dotfiles).

I clone this repo to my machine and copy the files into my home directory.

## Docker Desktop

There are multiple results when you searching `docker` within `RayCast`. To be sure I'm getting Docker Desktop, I'll use `Homebrew` directly instead:

```sh
brew install --cask docker
```













## Web Browser

### Firefox

I use Firefox because it is open source and comes from the [Mozilla Foundation](https://www.mozilla.org/en-US/about/manifesto/), a non profit company that [respects my privacy](https://www.mozilla.org/en-US/firefox/privacy/).

I use Firefox Developer Edition. To install this with `brew` you will need to tap [a cask](https://github.com/Homebrew/homebrew-cask-versions) first:

```sh
brew tap homebrew/cask-versions
```

You can then install Firefox Developer Edition with brew:

```sh
brew install homebrew/cask-versions/firefox-developer-edition
```

I use the following extensions to stay productive:

- [Tabliss](https://tabliss.io/) - simple new tab page
- [OneTab](https://www.one-tab.com/) - consolidate a bunch of open tabs into a shareable list of links
- [Dark Reader](https://darkreader.org/) - turn any site into dark mode

I use the following extensions to protect my privacy while browsing the web:

- Adblocker - [uBlock Origin](https://github.com/gorhill/uBlock)
- Tracker Blocker - [Privacy Badger](https://privacybadger.org/)
  - Firefox now includes tracker blocking, but I leave Privacy Badger enabled.
- [Decentraleyes](https://decentraleyes.org/)
  - Caches CDN links locally and intercepts requests to serve from the cache. Prevents CDNs from tracking you across websites.



## VS Code

[VS Code](https://code.visualstudio.com/) - is my preferred code editor.

You can view all of my VS Code settings / extensions [here](https://github.com/CodingGarden/vscode-settings).

### Github SSH Setup

- Follow [this guide](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) to setup an ssh key for github
- Follow [this guide](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account) to add the ssh key to your github account

## Node.js

I use nvm to manage the installed versions of Node.js on my machine. This allows me to easily switch between Node.js versions depending on the project I'm working in.

See installation instructions [here](https://github.com/nvm-sh/nvm#installing-and-updating).

OR run this command (make sure v0.39.7 is still the latest)

```sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```

Now that nvm is installed, you can install a specific version of node.js and use it:

```sh
nvm install 20
nvm use 20
node --version
```

### Global Modules

There are a few global node modules I use a lot:

- lite-server
  - Auto refreshing static file server. Great for working on static apps with no build tools.
- http-server
  - Simple static file server.
- license
  - Auto generate open source license files
- gitignore
  - Auto generate `.gitignore` files base on the current project type

```
npm install -g lite-server http-server license gitignore
```

## Other Apps I Use Often

- [sublime-text](https://www.sublimetext.com/) - Note taking (I know there are better apps...)
- [slack](https://slack.com/) - Messaging
- [keka](https://www.keka.io/en/) - Can extract 7z / rar and other types of archives
- [keepingyouawake](https://keepingyouawake.app/) - Prevents my Mac from going to sleep so I don't have to keep my MacBook open all the time just to use the fingerprint scanner to unlock it.
- [vlc](https://www.videolan.org/) - I use VLC to watch videos instead of the built in QuickTime.

You can install them in one go by placing them all into a text file and then running brew install:

```
sublime-text
slack
keka
keepingyouawake
vlc
```

```sh
xargs brew install < apps.txt
```

## Screen Recording & Demo Editing

I'm currently looking into:

- [Movavi](https://www.movavi.com/screen-recorder-mac/)
- [Screen Studio](https://screen.studio/)
- [Wondershare DemoCreator](https://democreator.wondershare.com/?extra_param=eyJ0eXBlIjoid2ViX2NsaWVudF9pbmZvIiwiYnV5X3R5cGUiOiJvbmx5X3dlYiIsInNob3BwaW5nX2lkIjoiMTczMDA2ODg3NDYwM184Nzk0MDEifQ==)
- [OBS Studio](https://obsproject.com/)
