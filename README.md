# virtualtabletop

This project aims to create a virtual tabletop in the browser where you can (re)create all board, dice and card games and play them without registration over the internet.

You can host your own instance or go to [VirtualTabletop.io](https://virtualtabletop.io).

This project is inspired by [playingcards.io](https://playingcards.io).

It's still in an early state but most PCIO files should be compatible and playable already.

Come join our [Discord server](https://discord.gg/xWxz9Gd) if you want to discuss the project.

This project started after [a reddit post](https://www.reddit.com/r/PlayingCardsIO/comments/jiajth/mildly_ot_feature_requests_for_a_pcio_clone/) in our [playingcardsio subreddit](https://www.reddit.com/r/PlayingCardsIO/).

## License

The project is licensed under [GPLv3](https://www.gnu.org/licenses/gpl-3.0.en.html).

The cards in [assets/cards-default](https://github.com/ArnoldSmith86/virtualtabletop/tree/main/assets/cards-default) were [created by Adrian Kennard](https://www.me.uk/cards/) and released under CC0 Public Domain license.

The cards in [assets/cards-plastic](https://github.com/ArnoldSmith86/virtualtabletop/tree/main/assets/cards-plastic) have their own [license.txt file](https://github.com/ArnoldSmith86/virtualtabletop/blob/main/assets/cards-plastic/license.txt).

The games in the public library have their license information and attributions inside their `attribution` metadata field. You can read by adding the game to your game library and clicking `Edit`.

## Download this repository and get all dependencies

### Linux

This assumes a Debian based Linux. If you use something else, you probably know what you need to change.

```
curl -sL https://deb.nodesource.com/setup_15.x | sudo -E bash -                         # adds a repository for Node.js v15
sudo apt install -y git nodejs                                                          # installs the required software
git clone --recurse-submodules https://github.com/ArnoldSmith86/virtualtabletop.git     # downloads everything in this repository
cd virtualtabletop                                                                      # changes to the newly created directory
npm install                                                                             # uses the Node.js package manager to install all dependencies
```

### Windows

1. Install [Git](https://git-scm.com/download/win) (or the [GitHub app](https://desktop.github.com/)) and [Node.js](https://nodejs.org/en/download/current/).
2. Open the command prompt and [cd](https://www.digitalcitizen.life/command-prompt-how-use-basic-commands/) to a directory where you want the project to live.
3. Do `git clone --recurse-submodules https://github.com/ArnoldSmith86/virtualtabletop.git` which downloads the project (or use the GitHub app to do this).
4. Do `cd virtualtabletop` to get into the project directory git created.
5. Do `npm install` so Node.js downloads all the dependencies of the project.

## Starting the server

Now you can start the server by typing:

```
npm start
```

If that doesn't work, try:

```
node server.mjs
```

This will serve the project at [localhost:8272](http://localhost:8272).

## Debug

To debug client-side code, first start the server so that it doesn't compress the code:

    npm run debug

In your browser, refresh to have it re-download the client code.
Press F12 to show the developer tools.

In Chromium, select the Sources tab, then the select the file for the room.
Press Ctrl-f to search for the code you want to set a breakpoint for an step through.

## Testing

To run the unit tests (and get a coverage report):

    npm test

To run them continuously (on each save) while you develop:

    npm run test-cont
