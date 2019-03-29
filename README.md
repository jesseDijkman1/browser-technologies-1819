![Server rendered ball and pad](https://raw.githubusercontent.com/jesseDijkman1/browser-technologies-1819/master/images/server-sided-ball-and-pad-rendering.gif)
Server sided pong-game

## Table of Contents 🗃
* [Description](#description-)
* [Installing](#installing-)
  * [Packages and Technologies](#packages-and-technologies)
* [How It Works](#how-it-works-️)
  * [Core functionalities](#core-functionalities)
* [Sources](#sources-)
  * [Honourable Mentions](#honourable-mentions)
* [Licence](#licence-)

## Description 📝
A server side pong-game. For this course we had to implement progressive enhancement in a project. I chose pong, which was the most difficult, and I basically started this Monday. The first two weeks I had my eye on socket.io, but Monday I heard that it **MUST** work without client-side javascript. I actually got it working without it, but multiplayer seems to be impossible.

## Installing 🔍
To install this application enter the following into your terminal:
```
git clone https://github.com/jesseDijkman1/pong-game.git

cd pong-game
```

### Packages and Technologies
There are some important packages that I need to address:
- [express-session](https://www.npmjs.com/package/express-session)
- [ejs](https://www.npmjs.com/package/ejs)

And I used a meta tag in some which I didn't even know existed before this course:
```html
<meta http-equiv="refresh" content="delay;url=http://example.com" />
```

## How It Works 🛠️
#### Pad movement
To make the pads move without the entire page refreshing. I used an iframe

#### Ball movement
To make the ball move I also used an iframe, which uses keyframes and meta resfresh

#### Lobby
To keep track of the players I used express-session and stored all the session-ids.

### Core functionalities
Because the app needed to be progressively enhanced, I had some core functionalities.
- The lobby
- Being able to move a pad
- Being able to move the ball
- Keep track of the score (which isn't really a core functionality, but it works for singleplayer)

## Sources 📚
- [Readme-template](https://baspieren.github.io/readme-template/)

### Honourable Mentions
- ⭐️ Bas Pieren

## Licence 🔓
MIT © [Jesse Dijkman](https://github.com/jesseDijkman1)
