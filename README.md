# The Client - Website

Ontwerp en maak een website voor een opdrachtgever en bespreek het resultaat tijdens de Sprint Review.

De instructie van deze leertaak staan in de [INSTRUCTIONS.md](https://github.com/fdnd-task/the-client-website/blob/main/docs/INSTRUCTIONS.md)



## Inhoudsopgave Readme

  * [Briefing](#briefing)
  * [Schetsen](#schetsen)
  * [Bouwen](#bouwen)
  * [Sprint review](#sprintreview)

## Briefing
Debriefing ~ Oncollaboration

Achtergrondinformatie:
Het project is ontstaan naar aanleiding van een jaar verblijf in Indonesië om het land en de gezondheidszorg beter te leren kennen, en om samen met collega's onderzoek te doen. Tijdens dit verblijf werd duidelijk dat er behoefte is aan meer interactie met de internationale medische gemeenschap, met name vanwege het achterblijven van de gezondheidszorg in Indonesië. Artsen worden voornamelijk opgeleid in Jakarta en behandelen patiënten met relatief weinig ervaring.

Kernpunten en Doelstellingen:
Het project richt zich op het verbeteren van de communicatie tussen Nederland en Indonesië op het gebied van oncologie, vooral via chats en evt. calls, bijvoorbeeld om CT-scans te bespreken en kennis te delen.
Alle webinars moeten geüpload worden en makkelijk toegankelijk zijn. 
Naast de webinars wordt ook gewerkt aan het delen van artikelen en het vergemakkelijken van communicatie tussen de Nederlandse en Indonesische medische teams. Het uploaden van scans is essentieel om gezamenlijk bestralingsgebieden te kunnen bepalen.
Er moet een naslagwerk komen voor specifieke onderwerpen, waarbij gebruikers makkelijk kunnen vinden bij wie ze terecht kunnen met vragen.

Design:
Er wordt een manier gezocht om CT-scans te delen en feedback te geven.
Brainstormsessies zijn nodig om te bepalen hoe het chatsysteem tussen beide landen moet werken, zodat het aan specifieke gebruikersbehoeften voldoet, zoals waarom een bepaald gebied bestraald moet worden.
Alle communicatie moet voor iedereen zichtbaar zijn, (evt. bij het uploaden van Webinars inclusief audio-opties).
Een vertaalfunctie voor de transcripties van de Webinars en goede navigatiestructuur binnen de video's.
Het toevoegen van contactinformatie van de Webinar gever en een apart gedeelte voor artikelen die bij de Webinars horen.


Inhoudelijke punten:
Het project moet ervoor zorgen dat meer informatie over Indonesië, oncologie, het AVL en ziekenhuizen in Jakarta gemakkelijk beschikbaar wordt.
Voor nu ligt de focus op het creëren van de interface. De oplevering hiervan wordt voornamelijk individueel verwacht. 
Vergelijkbare projecten kunnen mogelijk als inspiratiebron dienen.(Al zijn deze te vinden, evt. interessant om onderzoek naar te doen)

Planning
Di 1/10: Teams meeting om 13:00 uur. -> bespreken CT scans
Do 10/10: Teams meeting om 11:00 uur. -> sprint review (bekijken/bespreken van het gemaakte werk)

 Contact: j.v.diessen@nki.nl
Contactpersoon FDND student: vdgraaf.tessa@gmail.com




## Schetsen
<!-- Bij Kenmerken staat welke technieken zijn gebruikt en hoe. Wat is de HTML structuur? Wat zijn de belangrijkste dingen in CSS? Wat is er met Javascript gedaan en hoe? Misschien heb je een framwork of library gebruikt? -->

## Bouwen

Ik begon met het plannen van de structuur van de website. Omdat de website medische professionals als doelgroep heeft, wilde ik een zeer schone en professionele layout maken, zonder afleidende elementen. Ik koos ervoor om de website in te delen in logische secties zoals een hero-sectie, webinar-lijst, en een footer met nuttige links. 

De eerste stap was het schrijven van de basis HTML voor de verschillende secties:

```html
<header>
    <div class="header-content">
        <h1>Antoni van Leeuwenhoek Hospital</h1>
        <nav>
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#">Webinars</a></li>
            </ul>
        </nav>
    </div>
</header>
```


## CSS-uitdagingen
Tijdens het stylen liep ik tegen enkele uitdagingen aan. Ik wilde een strakke, moderne uitstraling met subtiele kleuren, maar ik merkte dat het moeilijk was om een balans te vinden tussen de zakelijke en toegankelijke uitstraling. Uiteindelijk koos ik voor een blauw kleurenpalet, met accenten van wit en lichte grijstinten.

Sticky Header
Een van de uitdagingen was het maken van een sticky header die blijft hangen terwijl je door de pagina scrolt. Dit is belangrijk omdat de gebruiker altijd makkelijk toegang moet hebben tot de navigatie, ongeacht waar ze zich op de pagina bevinden. Hiervoor gebruikte ik de position: sticky CSS-eigenschap:

```css
header {
    background-color: #005a87;
    color: white;
    position: sticky;
    top: 0;
    z-index: 999;
    padding: 20px 0;
}
```
Hero Sectie
Een ander belangrijk onderdeel was de hero-sectie. Ik wilde dat de afbeelding in de achtergrond subtiel was, maar ook de tekst op de voorgrond moest goed leesbaar zijn. Dit loste ik op door een overlay toe te voegen met een transparante achtergrondkleur:

```css
.hero {
    position: relative;
    height: 600px;
    background-image: url('hospital-hero.jpg');
    background-size: cover;
    background-position: center;
    display: flex;
    justify-content: center;
    align-items: center;
}

.hero-overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 90, 135, 0.7);
    z-index: 1;
}
```
Dit gaf het gewenste effect van een visueel aantrekkelijke maar subtiele achtergrond, zonder dat de tekst verloren ging.

Probleem met Dropdown Menu's
Een andere uitdaging die ik tegenkwam was het maken van een goed werkend dropdown menu voor de navigatie van webinars. Ik ontdekte dat de dropdown niet soepel werkte, vooral op mobiele apparaten. Na wat onderzoek en experimenten met verschillende methoden, kwam ik erachter dat de hover-functie in CSS niet altijd geschikt is voor touchscreens. 

Responsief Ontwerp
De site moest ook goed werken op verschillende schermformaten, dus heb ik gebruikgemaakt van media queries om de layout aan te passen voor mobiele apparaten. Dit zorgde ervoor dat de website er zowel op desktops als op telefoons goed uitziet:

```css
@media (max-width: 768px) {
    nav ul {
        flex-direction: column;
    }

    .webinar-list {
        grid-template-columns: 1fr;
    }
}
```
Webinars Zoeken en Filteren
Om de webinars gebruiksvriendelijk te maken, heb ik een zoekveld toegevoegd waarmee gebruikers naar specifieke webinars kunnen zoeken. Ik wilde ook de mogelijkheid bieden om op categorieën te filteren, zoals 'Borstkanker' of 'Longkanker'. Hiervoor gebruikte ik eenvoudige HTML-knoppen en voegde ik later wat JavaScript-functionaliteit toe om de zoekresultaten te filteren. De basisstructuur zag er als volgt uit:

```html
<div class="webinar-categories">
    <button class="category-btn">All</button>
    <button class="category-btn">Breast Cancer</button>
    <button class="category-btn">Lung Cancer</button>
</div>
```

Later voeg ik nog een JavaScript-filterfunctie toe om de webinars op categorie te filteren.

Conclusie
Het bouwen van deze website was een leerzaam proces. Ik kwam verschillende uitdagingen tegen, maar door geduldig te experimenteren met verschillende oplossingen, heb ik een mooie en functionele website kunnen opleveren. Het gebruik van een heldere visuele hiërarchie, duidelijke navigatie, en het toepassen van goede responsieve technieken waren cruciaal voor het eindresultaat.

## Sprint review

This project is licensed under the terms of the [MIT license](./LICENSE).
