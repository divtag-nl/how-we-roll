[← Terug](/)

# Data en veiligheid

Bij Divtag hechten wij veel waarde aan het waarborgen van de veiligheid op het gebied van klantdata. Deze data is meestal voor onze klanten van levensbelang en bevat ook vaak privacy gevoelige informatie. Daarnaast is natuurlijk de privacywetgeving (AVG) van toepassing op persoonsgegevens. 

Om op een goede en veilige manier te kunnen werken hebben we een aantal richtlijnen opgesteld, je vindt ze hieronder. 

## Awareness aka "De Pizza Policy"
Oké, eerst nog even dit… We streven allemaal naar een zo veilig mogelijke omgeving, maar dat gaat verder dan goede code schrijven en rechten op omgevingen inrichten. Als je bij Divtag je werkplek of je laptop verlaat, dan lock je deze natuurlijk door hem in slaap modus te zetten of dicht te klappen. Doe je dat niet dan is de kans groot dat een van je collega's via jou mailadres verteld dat jij deze week bij de vrijdagmiddagborrel de pizza verzorgt. Op die manier proberen we iedereen binnen Divtag een stukje awareness bij te brengen.

## Veilig omgaan met klantdata
Voorkomen is beter dan genezen, als divtagger heb je daarom nooit een goede reden om op je lokale omgeving klankdata op te slaan. Bij de ontwikkeling van nieuwe software schrijven we seeders die je gebruikt voor het dagelijks werken binnen je ontwikkelomgeving. De klant heeft een testomgeving waarin voorbeeld data staat, gebruik een van deze omgevingen als je iets wilt testen of uitproberen. Toegang tot de productieomgevingen is enkel voorbehouden aan senior ontwikkelaars / technisch eindverantwoordelijke voor een project.

## Bewerkersovereenkomst
Afspraken over de verantwoordelijkheden bij het werken met privacy gevoelige informatie leggen we vast in een bewerkersovereenkomst met onze klanten indien van toepassing. Divtag heeft hier een standaard overeenkomst voor. Dit gebeurd bij de intake van een nieuw project maar het kan ook zijn dat de informatie behoefte van onze klanten wijzigt. In dat geval kan het zo zijn dat er op een later moment alsnog een bewerkersovereenkomst getekend dient te worden.  Mocht je vermoedens hebben dat de behoefte van een klant wijzigt en dit raakt privacy gevoelige informatie? Maak dit dan bespreekbaar bij je collega's.

## Hoe we handelen in een geval van datalek
Als je het vermoeden hebt dat er een datalek heeft plaats gevonden, of kan vinden dan meld je dit bij een van de senior ontwikkelaars. Samen met hen wordt gekeken naar een correct oplossing en de procedure melden datalek in werking gesteld. 

Voorbeelden van datalekken zijn bijvoorbeeld een e-mail die naar de verkeerde adressen wordt gestuurd, een e-mail met een verkeerd bestand of document als bijlage, een usb-stick die verloren raakt, of een laptop die wordt gestolen. 

## Veiligheid webapplicaties
Bij Divtag bouwen we veilige webapplicaties. Dit wil zeggen dat je als ontwikkelaar gedwongen wordt om na te denken over veiligheidsrisico's bij de ontwikkeling (privacy by design). We hebben ons proces zo ingericht dat iedere code wijziging wordt gecontroleerd door een collega, en middels [Scrutinizer CI](https://scrutinizer-ci.com/) wordt beoordeeld. Zo zorgen we er gezamenlijk voor dat we betere en veiligere software ontwikkelen. Daarnaast ben je natuurlijk bekend met de [OWASP top 10](https://www.owasp.org/index.php/Category:OWASP_Top_Ten_Project).

## Deployement van nieuwe releases
Als we een nieuwe versie hebben ontwikkeld van een van onze projecten dan zorgen we er voor dat we deze in de regel niet op vrijdag deployen naar de productieomgeving. Ook aan het einde van de dag of net voor een druk moment proberen we dit natuurlijk te voorkomen. Afhankelijk van het project kan het zijn dat de rechten op de masterbranche alleen beschikbaar zijn voor de senior ontwikkelaars.
