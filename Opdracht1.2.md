# Browser Technologies
## Assignment 1.2 - Fork your OBA

## Tested features
I tested almost all the features except the no JavaScript, because it's a client side web application; so nothing will work.

#### 1 Turn off images
When turning of images the oba logo disappears and the thumbnails for the books don't render. All the other "images" are svg's. And since the books have titles there's no need to fix anything, although I could replace the oba logo with an svg.

#### 2 Turn off custom fonts
When turning of custom fonts, the fonts: 'FontAwesome' and 'Slackey' do not load. There are no real issues because because I only use these for extra detailing. How I could keep them when turning of custom fonts is use svg instead.

#### 3 Turn off colours
The website looks fine. The colors are a bit weird, but the contrasts are clear. You can differentiate all elements, except when it's entirely grey. The entirely grey one could be fixed by adding a white border to important elements, like buttons and inputs. But overall it works fine.

#### 4 Mouse and trackpad are broken
This creates issues. For example you can tab to the add word form and actually ... add words, but trying to use the "go to genres section button" will change the positioning of everything; because some buttons are not on the page. But most important is to add a word and make a request to the API, which didn't work. I fixed this by a adding keydown event and checking for the enter key. I also added a `tabindex="-1"` to some buttons and changed the mainpotion (the svg with which you can start looking for data) from `<div>` to `<button>`.

#### 5 Turn off broadband internet
I switched the network speed to "3G slow". And the results surprised me; it wasn't all that bad. This is probably because I only have one img on the home page, all the others visuals are svg's.

#### 6 Javascript
Didn't even bother to test the "no javascript", because it's an entirely client-sided web app. Nothing is going to work. You can type words but you can't submit them really.

#### 7,8 Cookies and LocalStorage
When turning of cookies it also turned of localstorage, and when I did that, the app would break when making the api calls.

---

## Device lab and Screen reader tests
### Device lab
The older phones don't work and it's probably because of `display: grid`. But the two older phones I used both have different errors with styling. The tablets worked, don't know about the e-reader but I assume nothing is going to work.

First of, the device lab is broken af. But after switching the wifi I was able to get to my website. Some phones don't work and some do (my own).

Insights:
- The phones are outdated and the browsers don't support `display: grid`
- The phones also didn't work when I tried to hold the mainpotion down (`ontouchstart`)
- And the two phones I did test both had different issues.
- The tables worked fine (atleast two)

### Screen reader
When I tested the screen reader on my website the first `<form>` works fine. It says exactly what I want it to say. But when I get to some of the svg's the reader reads the numbers in them. This is a problem because I couldn't target the mainpotion with which I make the API request. I tried to add an `alt` but it didn't work.

## Fixes
The first problem I had to fix was that on mobile the viewport was all messed up. So I added this chunk of code: <br>
```css
html, body {
  font-family: system-ui, Arial, sans-serif;
  font-size: 16px;
  position: relative;
  margin: 0;
  border: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
}
body {
  background: #e0e0e0;
  overflow-y: scroll;
}
```

The next problem I had to fix was change the 
```html 
<div id="main-potion"> ... </div>
```
to 
```html
<button id="main-potion"> ... </button>
```
I did this to enable tabbing to it. And I also added some keyboard events, so now you can lookup a word without mouse or trackpad.

And I added events listeneres for keys and touches.
```js
function holdMouse() {
    let milis = 0;
    window.mouseHoldDown = setInterval(() => {
      milis++;

      if (milis >= 10) {
        explosion.classList.add("explode");
        
        // Added this because I wasn't able to scroll the results because the explosion blocked my touches
        setTimeout(() => {
          explosion.classList.remove("explode");
        }, 2000)
        
        clearInterval(window.mouseHoldDown)
        // API call
        app.changeHash("results");
      }
    }, 100)

    window.addEventListener("mouseup", () => clearInterval(window.mouseHoldDown));
    window.addEventListener("touchend", () => clearInterval(window.mouseHoldDown)); // Supports mobile
    window.addEventListener("keyup", () => clearInterval(window.mouseHoldDown)); 
  }

  mainPotion.addEventListener("mousedown", holdMouse);
  mainPotion.addEventListener("touchstart", holdMouse);
  
  // Only when on focus add keydown event, so pressing tab won't trigger it
  mainPotion.addEventListener("focus", focusEvent => {
    focusEvent.target.addEventListener("keydown", keyEvent => {
      if (keyEvent.keyCode === 13) { // Key is enter
        holdMouse()
      }
    })
  });
```

### Todo's
There are specific things I should fix but I could fix them all by remaking the app and use progressive enhancement. This way I can make all the important things accessible for everyone. And add layers from there.

#### Things I need to fix
- Support no javascript and no localstorage/cookies by doing all the important stuff on the server 
- Only render one section to help support tabbing
- Fix screenreader issues somehow

## Sources 
- https://stackoverflow.com/questions/826782/how-to-disable-text-selection-highlighting
- https://stackoverflow.com/questions/3682812/disabling-tab-focus-on-form-elements
- https://stackoverflow.com/questions/15073759/fixed-positioned-div-is-extending-outside-of-html-body

## Licence
MIT © [Jesse Dijkman](https://github.com/jesseDijkman1)
