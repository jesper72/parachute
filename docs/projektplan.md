# Projektplan
*Grupp Parachute*

**Innehåll:**
<a href="#intro">Introduktion och beskrivning</a>
<a href="#users">Målgrupp och användare</a>
* <a href="#mainuser">Huvudanvändare </a>
* <a href="#secondaryuser">Sekundära användare</a>
<a href="#visualization">Visualisering av koncept och dataflöde</a>
<a href="#tech">Teknikval</a>
* <a href="#backend">Backend </a>
* <a href="#frontend">Frontend </a>

## Problembeskrivning<a id="intro"></a>
Appen som ska utvecklas är till för att lösa problemet med dålig kommunikation mellan hantverkare och kunder.
Kommunikationen anses ofta vara bristande från hantverkares sida och kunder känner att de inte har någon koll.
Problemet leder till att kunder uppfattar hantverkare som oseriösa och ett hantverkarbranschen ges ett dåligt rykte.
Appen ska säljas till kund som en SaaS-lösning.

## Målgrupp och användare<a id="users"></a>
Appens målgrupp är hantverksföretag som vill förbättra kommunikation och hantering av arbetsorder.

### Huvudanvändare<a id="mainuser"></a>
Huvudanvändare av appen är byggföretags ansvariga (chefer) och byggföretags hantverkare.
**Ansvariga användare** kommer att ha tillgång till administratörsfunktionalitet, t ex lägga in ordrar, uppdatera tidsrapportering och hantera fakturering.
**Hantverkare** kommer att ha tillgång till en mer avskalad sida efter inloggning. Hantverkare kommer att rapportera tider och ta del av tidsplanering.

### Sekundära användare<a id="secondaryuser"></a>
Byggföretagens kunder kommer att få någon slags notifikation om tidsplanering.

## Visualisering av koncept och dataflöde<a id="visualization"></a>
![Visualisering av app](https://github.com/webbprojekt1-parachute/parachute/blob/master/docs/parachuteapp.png)

1. **Fort Nox REST-API end-points.**
HTTP-transport.
2. **Lokal databas.**
MySQL.
3. **Lokalt REST-API och proxy server.**
Apache2 + PHP 5.6. HTTP-transport mellan [Fort Nox](https://fortnox.se) (1) och Klient (4).
4. **Klient.**
Foundation for Apps [(AngularJS)](https://angularjs.org). Arbetar med REST mot lokalt API (3).
5. **Notifikation-service.**
Meddelar kund (6), chef (7), hantverkare (8). _(E-post, SMS?)_
6. **Kund.**
Ringer upp byggföretags chef (7), får notifikationer pushade till sig.
7. **Chef.**
Arbetar mot klient (4) via inloggning som administratör. Fulla rättigheter för ändringar och tillägg i arbetsordrar. Hanterar kunder, skapar fakturor, hanterar tidsplanering.Får push-notifikationer från service (5).
8. **Hantverkare.**
Arbetar mot klient (4) via inloggning som hantverkare. Rapporterar in tid om arbetad tid till arbetsordrar.

## Teknikval<a id="tech"></a>
Beskrivning och information om de teknikval som gjorts för webbappen.

### Backend<a id="backend"></a>
**Server:** Apache2
**Språk:** PHP 5.6
**Databas:** MySQL
**Transport:** REST-API, HTTP

### Frontend<a id="frontend"></a>
**CSS/SASS:** Foundation for Apps
**JavaScript:** AngularJS (ingår i Foundation for Apps)
**Statiska sidor:** HTML5, Single Page Application