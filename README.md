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

Ik begon met het plannen van de structuur van de website. Omdat de website medische professionals als doelgroep heeft, wilde ik een professionele layout maken, zonder afleidende elementen. Ik koos ervoor om de website in te delen in duidelijke secties zoals een hero-sectie, webinar-lijst, en een footer met bepaalde links. 

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
Tijdens het stylen liep ik tegen enkele uitdagingen aan. Ik wilde een strakke, moderne uitstraling met subtiele kleuren, maar ik merkte dat het moeilijk was om een balans te vinden tussen de professionele en toegankelijke uitstraling. Uiteindelijk koos ik voor een blauw kleurenpalet, met accenten van wit en lichte grijstinten.

### Sticky Header
Een van de uitdagingen was het maken van een sticky header die blijft hangen terwijl je door de pagina scrolt , dit was een uitdaging omdat ik nog nooit zoiets hebt gebouwd. Dit is belangrijk omdat de gebruiker altijd makkelijk toegang moet hebben tot de navigatie, ongeacht waar ze zich op de pagina zijn. Hiervoor gebruikte ik de position: sticky CSS-eigenschap:

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
### Hero Sectie
Een ander belangrijk onderdeel was de hero-sectie. Ik wilde een subttiele achtergrond , met een tekst op de voorgrond die goed leesbaar was maar niet teveel informatie in een keer gaf , meer een simpele intro .

```css
.hero {
    position: relative;
    height: 600px;
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
Dit gaf het gewenste effect van een visueel subtiele achtergrond, en een korte kleine tekst.

Probleem met Dropdown Menu's
Een andere uitdaging die ik tegenkwam was het maken van een goed werkend dropdown menu voor de navigatie van webinars. Ik ontdekte dat de dropdown niet soepel werkte, vooral op mobiele apparaten. Ik heb daardoor die functie voor nu verwijdert omdat ik anders in tijdsnood kwam , maar ga hiermee veder in de volgende sprint.

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
Om de webinars gebruiksvriendelijk te maken, heb ik een zoekveld toegevoegd waarmee gebruikers naar specifieke webinars kunnen zoeken. Ik wilde ook de mogelijkheid bieden om op categorieën te filteren, zoals 'Borstkanker' of 'Longkanker'. Hiervoor gebruikte ik eenvoudige HTML-knoppen en ga ik later wat JavaScript-functionaliteit toevoegen om de zoekresultaten te filteren. De basisstructuur zag er als volgt uit:

```html
<div class="webinar-categories">
    <button class="category-btn">All</button>
    <button class="category-btn">Breast Cancer</button>
    <button class="category-btn">Lung Cancer</button>
</div>
```


Conclusie
Het bouwen van deze website is een leuke uitdaging voor mij. Naast dat ik nog nooit zo een website heb gebouwd vind in de opdracht ook heel leuk en belangrijk, ik ben nog lang niet klaar met bouwen maar ben al trots op wat ik tot nu toe heb gemaakt.

## Sprint review

### Plan van Aanpak voor de Sprint Review

#### 1. **Doel van de Sprint Review**
Het hoofddoel van deze Sprint Review is om feedback te verzamelen op de huidige versie van de website die is gebouwd voor artsen uit Nederland en Indonesië, zodat zij toegang hebben tot webinars over kankerbehandelingen. Het doel is om inzicht te bieden in de voortgang en om specifieke feedback te ontvangen over de functionaliteiten, het ontwerp en de gebruikerservaring. 

Doelen:
- Beoordeling van de look-and-feel van de website, inclusief de subtiele verwijzingen naar de Nederlandse en Indonesische identiteit.
- Testen van de functionaliteiten zoals de webinar-sectie, zoekfunctie, en de gebruiksvriendelijkheid.
- Feedback verzamelen over verbeteringen die kunnen worden doorgevoerd in de volgende sprint.

#### 2. **Demonstratie van het Werk**

##### Wat wil ik laten zien?
1. **Website Structuur**  
   Laat de opdrachtgever zien hoe de website is opgebouwd, van de header tot de footer. Begin met het tonen van de **hero section**, die verteld waar deze website voor gebouwd is : wereldwijde samenwerking op het gebied van kankerzorg.

   **Codevoorbeeld Hero Section**:
   ```html
   <section class="hero">
       <div class="hero-overlay"></div>
       <div class="hero-content">
           <h2 class="hero-title">World-Class Cancer Care & Global Collaboration</h2>
           <p class="hero-subtitle">Join cutting-edge webinars led by top specialists and collaborate worldwide.</p>
       </div>
   </section>
   ```

2. **Webinars Functionaliteit**  
   Demonstreer hoe artsen kunnen zoeken naar en filteren op verschillende webinars, zoals "Breast Cancer" en "Lung Cancer". Laat de zoekbalk zien die gebruikers helpt snel webinars te vinden.

   **Codevoorbeeld Webinars-sectie**:
   ```html
   <div class="webinar-search">
       <input type="text" placeholder="Search for a webinar..." id="webinar-search-input">
   </div>

   <div class="webinar-categories">
       <button class="category-btn">Breast Cancer</button>
       <button class="category-btn">Lung Cancer</button>
   </div>
   ```

3. **Responsiviteit van de Website**  
   Laat zien dat de website op verschillende apparaten goed werkt (desktop, tablet, mobiel). Dit kan bijvoorbeeld door een Chrome DevTools-sessie te openen en de verschillende schermformaten te tonen.

   **CSS Voorbeeld voor Responsiviteit**:
   ```css
   @media (max-width: 768px) {
       .hero-title {
           font-size: 2em;
       }
   }
   ```

##### Volgorde van de Demonstratie:
1. Begin met een uitleg over de **hero section**, waarin de essentie van de website wordt gepresenteerd.
2. Laat de **webinar-sectie** zien, inclusief de categorieën en zoekfunctie.
3. Toon de website op verschillende apparaten om te laten zien dat hij **responsive** is.

#### 3. **Faciliteren van Feedback**
Tijdens de demonstratie wil ik de opdrachtgever actief betrekken en aanmoedigen om specifieke feedback te geven. Ik zal de volgende vragen stellen:

- Voldoet de visuele uitstraling van de website aan uw verwachtingen, vooral met betrekking tot de subtiele Nederlandse en Indonesische elementen?
- Vindt u de navigatie en zoekfunctie voor de webinars gebruiksvriendelijk genoeg?
- Zijn er specifieke elementen die verbeterd of toegevoegd moeten worden?
- Heeft u feedback over de gebruikerservaring op verschillende apparaten?

#### 4. **Beoordelen van de Feedback**
Na de Sprint Review zal ik de gegeven feedback beoordelen en deze in concrete taken vertalen voor de volgende sprint. Elke feedback wordt gedocumenteerd in het project board, met specifieke verbeterpunten. Enkele mogelijke feedbackpunten zouden kunnen zijn:
- Verbeteringen in het design (meer kleurvariatie, betere lay-out van de webinars).
- Verbeteringen in functionaliteit (zoals filteropties voor de zoekfunctie).
- Toevoegingen die het gebruiksgemak bevorderen.

#### 5. **Voorbereiding voor de Demo**
Om goed voorbereid te zijn op de demo:
- Test ik de website op verschillende apparaten om te laten zien dat de site responsive is.
- Zorg ik dat alle functionaliteiten (zoals de zoekfunctie en de webinars) zonder problemen werken.
- Oefen ik de demo met een medestudent of mentor en vraag ik hen om feedback.

Met deze aanpak kan ik een gestructureerde Sprint Review houden en waardevolle feedback ontvangen voor de volgende sprint!

This project is licensed under the terms of the [MIT license](./LICENSE).
