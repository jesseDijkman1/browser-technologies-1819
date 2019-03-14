# Browser Technologies
## Opdracht 1.2 - Fork je OBA

## Tested features
I tested almost all the features except the no JavaScript, because it's a client side webapplication so nothing will work.

#### 1 Turn off images
When turning of the images, the app won't render the thumbnails from the results. This is the only "problem". Luckily there's a title so there's no need to fix it.

#### 2 Turn off custom fonts
When turning of custom fonts, FontAwesome won't load and Slackey won't load. There are no real issues because

#### 3 Turn off colours
The website looks fine. The colors are a bit weird but the contrasts are right. You can differentiate all elements, except when it's entirely grey. The entirely grey one could be fixed by adding a white border to important elements, like buttons and inputs. 

#### 4 Mouse and trackpad are broken
This creates issues. For example you can tab to the add word form and add things, but trying to enter the go to genres section button will change the positioning of everything. But most important is to add a word and make a request to the API. I fixed this by adding keydown event and checking for the enter key. I also added a `tabindex="-1"` to some buttons and changed the mainpotion (the svg with which you can start looking for data) from `<div>` to `<button>`.

#### 5 Turn off broadband internet
I turned the internet to 3G slow. And the results surprised me; it wasn't all that bad. This is probably because I only have one img, all the others visuals are svg's.

#### 6 Javascript
Didn't even bother to test the "no javascript", because it's an entirely client-sided webapp. Nothing is going to work.

#### 7,8 Cookies and LocalStorage
When turning of cookies it also turned of localstorage, and when I did that, the app broke.

## Device lab and Screen reader tests
### Device lab
The older phones don't work and it's probably because of `display: grid`. But the two older phones I used both have different errors with styling. The tablets worked, don't know about the e-reader but I assume nothing is going to work.

### Screen reader
When I tested the screen reader on my website the first `<form>` works good. It says exactly what I want it to say. But when I get to some of the svg's the reader reads the numbers in them.

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

## Sources 
- https://stackoverflow.com/questions/826782/how-to-disable-text-selection-highlighting
- https://stackoverflow.com/questions/3682812/disabling-tab-focus-on-form-elements
- https://stackoverflow.com/questions/15073759/fixed-positioned-div-is-extending-outside-of-html-body
