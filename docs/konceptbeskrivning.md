
**Bakgrund**

Hantverksbranchen har ett par saker gemensamt:
-	De hanterar ofta planeringen offline, på whiteboards eller liknande
-	De vill lägga så lite tid som möjligt på administration såsom fakturering och bokföring
-	Deras kunder upplever att de får bristfällig information

**Aktörer**

-	Chefen, admin för hantverkarföretaget. Sitter uteslutande och arbetar på sin dator eller tablet. I undantagsfall även på mobilen.
-	Hanterkaren, anställd på hantverkarföretaget. Accessar i de allra flesta fallen applikationen via sin mobil eller tablet.
-	Kunden, uppdragsgivaren som interagerar med chefen med mail och blir notifierad via SMS och e-post

**Integrationer**

-	Cellsynt - SMS-tjänst (håller på att bli kund, strax klart)
-	Fortnox API - Affärssystem
-	Google - för att logga in med google konto
-	SMTP-server för mailskickning


**Funktionalitet**

Chefen
-	Chefen väljer att bli kund och registrerar sitt företag och sitt google konto - blir därmed admin
-	Ställa in företagsinställningar inkl API-nycklar till Fortnox
-	Lägga till, uppdatera och inaktivera en anställd - som också loggar in med ett googlekonto
-	Ställ in notifieringsinställningarna på den anställde SMS eller e-post eller båda och också vid vilka händelser den anställde vill bli notifierad
-	Lägg upp arbetsschema på anställd
  -	t ex 7-16 varje dag, förutom torsdagar då hen hämtar på dagis vid 15.
  -	Lägg upp semesterperioder och annat
-	Planeringsvy för alla anställda och Planeringsvy per anställd
  -	här lägger man ut jobben grafiskt i ett schema


*En kund ringer och beställer ett jobb*

-	Chefen lägger upp kunden - som sparas i Fortnox system
  -	Notifieringsinställningarna sparas i vårt system, dvs om kunden vill bli kontaktad via SMS eller e-post eller båda delarna och också vid vilka händelser en kund vill bli notifierad
-	Chefen skapar en offert till kunden lokalt i systemet och väljer att skicka den till kunden via e-post
  -	Offerten inehåller:
    -	Kundinformation
    -	Information om vad som ska göras
    -	Ett antal artiklar och timmar som har ett pris plus moms kopplade till sig
-	Chefen skapar en arbetsorder lokalt i systemet
  -	En arbetsorder innehåller:
    -	Kundinformation
    -	Vad som ska göras
    -	Evetuellt artiklar som ska användas (hämtas från Fortnox) t ex 1st skruv, 4st badkar
-	Nu går chefen in i planeringsvyn och tilldelar arbetsordern till en specifik anställd på en specifik dag


Hantverkaren
-	Loggar in i webbappen och ser sin att-göra-lista för dagen
  -	Hen kan även navigera till dagar framåt och bakåt i tiden (swipe ftw!)
  -	Finns det ett jobb från tidigare dagar som är tilldelat hen och inte är avslutat syns det också här och man kan navigera till det
-	Välj ett jobb
  -	Läs om vad som ska göras och vilka artiklar som ska tas med
  -	Eventuellt checka av vilka artiklar som har tagits med
  -	Länk till en vägbeskrivning i förslagsvis google maps, eller annat fiffigt förslag?
-	När jobbet är gjort:
  -	Registrera utförd arbetstid
  -	Registrera använda artiklar 
  -	Skriv fritext t ex 
  -	Ta ett eller flera kort med mobilkameran som kopplas till jobbet
  -	Markera jobbet som slutfört alternativt flagga det för chefen att det krävs ytterligare insatser

Chefen igen
-	Chefen ser tydligt att det finns arbetsordrar som kräver hans uppmärksamhet
-	Färdiga arbetsordrar
  -	Godkänn, komplettera informationen, se datan och bilderna som hantverkaren skickade in
  -	Fakturera
    -	Utgå från de artikelrader som finns i arbetsordern
    -	Chefen kan modifiera raderna
    -	Skapa fakturan som skapas i Fortnox
      -	Fakturan ska bokföras i Fortnox
      -	Fakturan ska skickas till kunden via e-post via Fortnox
-	Arbetsordrar som kräver ytterligare insatser
  -	Planera om på ny dag och ny hantverkare


**Notifieringar**
-	Systemet ska skicka e-post och SMS till kunder och hantverkare vid vissa händelser i systemet, förslagsvis:
  -	Arbetsordern tilldelas en hantverkare
  -	Arbetsordern avslutas
  -	Fakturan skickas


**Ickefunktionellt**
Systemet ska byggas som en eller flera single page webappar på ett PHP backend och en mySQL-databas. 
Webapparna ska byggas i lämpligt ramverk såsom angular. Backend i lämpligt MVC-ramverk. 
Backend ska exponera ett REST-api för frontendapparna. Snacka JSON.
Vi använder Git för versionshantering.


**Referenser**
http://developer.fortnox.se
Fortnox tillhandahåller ett REST-api med all funktionalitet vi behöver kring fakturering, artiklar och kunder. 

https://www.cellsynt.com/pdf/Cellsynt_SMS_gateway_HTTP_interface_(Swedish).pdf
Cellsynt tillhandahåller ett api för att skicka SMS. Förhandling pågår-


