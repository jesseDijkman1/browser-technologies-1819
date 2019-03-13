# Browser Technologies
## Opdracht 1.1 - Breek het web
Het Web laten 'breken' door features van het platform bewust uit te zetten. Images, custom fonts, JavaScript, kleur, breedband internet.

### Doel van deze opdracht
Het doel van deze opdracht is om erachter komen dat je misschien aannames hebt die niet kloppen, en om je in te laten leven in de eindgebruiker.

### Uitleg
Onderzoek minimaal twee features. Dat betekent uitvogelen wat het voor impact heeft op de sites die je kent en normaal gebruikt. Kies sites in je directe omgeving: van je werkgever, lokale vereniging, de cafetaria om de hoek, en/of eerdere projecten die je zelf gedaan hebt. Gebruik onderstaande artikelen bij je onderzoek.

1. Afbeeldingen uitzetten
2. Custom fonts uitzetten
3. Javascript (volledig)
4. Kleur uitzetten & kleurenblindheid instellen
5. Breedband internet uitzetten
6. Cookies
8. localStorage doet het niet
9. Muis/Trackpad werkt niet

Optioneel mag je ook één van deze features onderzoeken:
- a. Wifi hotspots/HTTPS
- b. Content blockers
- c. CDN’s
- d. Ad blockers (privacy)
- e. Browser detect


Lezen
- [The Web I Want](https://dev.to/quii/the-web-i-want-43o)
- [The Role of Enhancement in Web Design
by Raluca Budiu](https://www.nngroup.com/articles/enhancement/)



### Criteria
Je krijgt 2 features van de 8
- Zoek uit welke problemen ze kunnen veroorzaken (verzamel cijfers, meningen, ervaringen)
- Zoek uit hoe je dit kunt testen (hoe kun je een feature ‘uitzetten’)
- Vind een aantal sites waar dit ook problemen oplevert (uit je directe omgeving)
- Beschrijf hoe je dit kan fiksen
- Maak hierover een presentatie en neem die woensdag mee, dan gaan we de resultaten bespreken

---

### Features
- Javascript (volledig)
- LocalStorage doet het niet

### Websites
1. [Lunchroom de Walvis](http://www.lunchroomdewalvis.nl/)
2. [Kanovereniging Argonauten](http://www.kvargonauten.nl/)
3. [Huisartsenpraktijk Walvis](https://huisartswalvis.praktijkinfo.nl/)

---

## Javascript (volledig)
### What problems can they cause?
According to this [article from medium](https://medium.com/@mindfiresolutions.usa/how-important-is-javascript-for-modern-web-developers-2854309b9f52); 94.5% of all websites use JavaScript. Some even use JavaScript frameworks like React.js and Vue.js. These websites/webapps would probably have a lot of trouble when JavaScript is disabled. Also functionalities like carousels probably won't work.

### How can you test this?
Chrome has an extension which allows you to disable JavaScript among others. <br>
[Web Developer Extension](https://chrome.google.com/webstore/detail/web-developer/bfbameneiokkgbdmiekhjnmfkcnldhhm)

#### Lunchroom de Walvis
#### Kanovereniging Argonauten
#### Huisartsenpraktijk Walvis

## LocalStorage doet het niet
### What problems can they cause?
Localstorage allows for storing data in a users' browser.
Sites like google use localstorage to determine if user is logged in. Without it, you can't. 
I think you probably also can't add thins to a list without being logged in.

### How can you test this? 
Go to _chrome Settings > advanced > content settings > cookies_

#### Lunchroom de Walvis
#### Kanovereniging Argonauten
#### Huisartsenpraktijk Walvis


## Sources
- https://www.smashingmagazine.com/2018/05/using-the-web-with-javascript-turned-off/
- https://medium.com/@mindfiresolutions.usa/how-important-is-javascript-for-modern-web-developers-2854309b9f52
- https://blockmetry.com/blog/javascript-disabled
- https://twitter.com/philhawksworth/status/990890920672456707
