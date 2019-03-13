# Browser Technologies
## Assignment 1.1 - Break the web

### Purpose of the assignment
Purpose of this assignment is to find out you might have wrong assumptions, and to let you empathize with the enduser.

---

### Features
- Javascript (volledig)
- LocalStorage doet het niet

### Websites
1. [Lunchroom de Walvis](http://www.lunchroomdewalvis.nl/)
2. [Bij ernst](http://www.bij-ernst.nl/)
3. [Huisartsenpraktijk Walvis](https://huisartswalvis.praktijkinfo.nl/)

---

## Javascript (entirely disabled)
### What problems can they cause?
According to this [article from medium](https://medium.com/@mindfiresolutions.usa/how-important-is-javascript-for-modern-web-developers-2854309b9f52); 94.5% of all websites use JavaScript. Some even use JavaScript frameworks like React.js and Vue.js. These websites/webapps would probably have a lot of trouble when JavaScript is disabled. Also functionalities like carousels probably won't work.

### How can you test this?
Chrome has an extension which allows you to disable JavaScript among others. <br>
[Web Developer Extension](https://chrome.google.com/webstore/detail/web-developer/bfbameneiokkgbdmiekhjnmfkcnldhhm)

### Websites
Websites from around my area. 

#### Lunchroom de Walvis [Site](http://www.lunchroomdewalvis.nl/)
Carousel doesn't work, it's completely hidden when JavaScript is disabled. <br>
**Fix:** You can just display the carousel by default, but you can't go through them with a click. Just displaying them with CSS.

Search button won't expand the search input. <br>
**Fix:** Use the checkbox-label hack (CSS)

#### Bij-ernst [Site](http://www.bij-ernst.nl/)
The page is filled with scrolling transitions that are hidden by default. With JavaScript disabled they are hidden. <br>
**Fix:** Display them by default but hide them on page load with JavaScript. This way they will always be visible even without JavaScript. They are only hidden when JavaScript is enabled. 

The main menu is hidden without JavaScript. <br>
**Fix:** Also hide thme with JavaScript, or make the menu with pure CSS.

#### Huisartsenpraktijk Walvis
Search button doesn't expand the search input. <br>
**Fix:** Checkbox hack or hide the input with JavaScript.

---

## LocalStorage doesn't work
### What problems can they cause?
Localstorage allows for storing data in a users' browser.
Sites like google use localstorage to determine if user is logged in. Without it, you can't. 
I think you probably also can't add thins to a list without being logged in.

### How can you test this? 
Go to _chrome Settings > advanced > content settings > cookies_

### Websites
The websites I looked at for the JavaScript feature don't have any problems without localstorage. 

## Sources
- https://www.smashingmagazine.com/2018/05/using-the-web-with-javascript-turned-off/
- https://medium.com/@mindfiresolutions.usa/how-important-is-javascript-for-modern-web-developers-2854309b9f52
- https://blockmetry.com/blog/javascript-disabled
- https://twitter.com/philhawksworth/status/990890920672456707
