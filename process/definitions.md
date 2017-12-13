[← Terug](/)

# Definities

Bij Divtag scrummen we. Bij Scrum horen bepaalde spelregels en rituelen. Op deze pagina staan de richtlijnen beschrijven waar een taak aan moet voldoen voordat hij een bepaalde status kan krijgen.

## Definition of Ready

Hieronder staat een lijst met de punten waar een taak moet voldoen voordat hij “ready” is en kan worden opgepakt in het ontwikkelproces. Afhankelijk van wat voor taak het is, bijvoorbeeld een bug of een nieuwe feature zijn sommige punten wel of niet van toepassing.

**Titel**: Als {type gebruiker} wil ik {iets doen} zodat ik {er iets aan heb}.

**Beschrijving**: Hier kan uitgebreid beschreven worden hoe en waarom de klant iets wil. Dit moet duidelijk genoeg zijn, dat iemand zonder kennis van het systeem snapt wat de bedoeling is. Indien nodig hoort hier ook een wireframe of grafisch ontwerp bij. Of als het bijvoorbeeld een complexe berekening is misschien een flow diagram.

**Aantal storypoints**: Hoeveel storypoints kost het om het punt te verwerken (planningpoker).

**Acceptatiecriteria**: Waarop dient het punt getest te worden, voordat het goedgekeurd wordt?

**Afhankelijkheden**: Waarvan is het punt afhankelijk? Moeten eerst andere punten verwerkt zijn voor dit punt opgepakt kan worden? Of moet er bijvoorbeeld rekening worden gehouden met externe systemen of API’s voor dit punt? Moet er contact zijn met een externe partij?

**Developer**: Is het belangrijk dat het punt verwerkt wordt door een bepaalde developer?

**Branch**: In welke branch moet dit punt verwerkt worden?

**Terugkoppelen**: Aan wie dient er teruggekoppeld te worden als het punt verwerkt is. (Optioneel)

**WBSO**: Kan dit punt worden toebedeeld aan een WBSO deel project? Zoja: Welke?

**Epic**: Aan welk onderdeel van de applicatie kan dit punt worden toebedeeld?

**Prioriteit**: Welke prioriteit heeft deze taak? 

**Indien het een Bug betreft zijn er nog een 3-tal extra zaken benodigd:**

**Versies**: Met welke versies van de software, de software door Divtag ontwikkeld of bijvoorbeeld de browser versie doet het probleem zich voor.

**Stappen om te reproduceren**: Welke stappen moeten er doorlopen worden om het probleem te reproduceren.

**Uitkomst momenteel**: Wat gebeurd er momenteel volgens de klant als de stappen om reproduceren gevolgd worden?

## Definition of Staging

Hieronder staat een lijst met de punten waar een taak aan moet voldoen  voordat hij “staging” is en kan worden beschouwd als klaar om door een klant getest te worden. Afhankelijk van wat voor taak het is, bijvoorbeeld een bug of een nieuwe feature zijn sommige punten wel of niet van toepassing.

**Peer reviewed**: De code is gecontroleerd en goedgekeurd door een collega- developer.

**Codesniffer**: De code is gecontroleerd door Codesniffer en geeft geen foutmeldingen.

**Code documentatie**: Is er een doc block gedefinieerd? 

**Acceptatiecriteria**: Aan de acceptatiecriteria moet zijn voldaan volgens 2 developers (Ontwikkelaar + reviewer).

## Definition of Done

Hieronder staat een lijst met de punten waar een taak aan moet voldoen voordat hij “done” is en kan worden beschouwd als volledig afgerond. Afhankelijk van wat voor taak het is, bijvoorbeeld een bug of een nieuwe feature zijn sommige punten wel of niet van toepassing.

**Acceptatiecriteria**: Aan de acceptatiecriteria moet zijn voldaan volgens de product owner.

**Terugkoppelen**: Indien aangegeven in de taak, dient er teruggekoppeld te zijn aan de juiste persoon.

**Deployed**: Er moet gedeployed zijn in de productieomgeving.

**Documentatie**: Is de klant documentatie (handleiding) bijgewerkt indien van toepassing?
