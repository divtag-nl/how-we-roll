[← Terug](/)

# Gebruikte technieken

Divtag maakt gebruik van diverse standaard componenten en diensten voor de ontwikkeling van online software. Door dit te doen maken wij kwalitatief goede software die toekomstbestendig en veilig is. Hieronder treft u de meest belangrijke aan:

## Framework (Laravel)

Divtag ontwikkelt online software op basis van het PHP framework [Laravel](https://laravel.com/). Door te kiezen voor een framework zijn er een hoop zaken die standaard goed geregeld zijn. Denk hierbij aan generieke functies voor database bewerkingen, rechtenbeheer, loginmodule, etc, etc. Deze voorsprong geeft u als klant de mogelijkheid om direct de focus te leggen op de specifieke functionaliteiten van uw applicatie.

Dit framework is ontwikkelt onder de MIT Open Source Licentie. Meer informatie over deze licentievorm is te vinden op https://nl.wikipedia.org/wiki/MIT-licentie en https://opensource.org/licenses/MIT.

De gedachte achter Open Source is dat de broncode van de software open en vrij beschikbaar is voor iedereen. Zo kunnen gebruikers voortbouwen op de software, fouten herstellen of delen hergebruiken. Laravel heeft een zeer actieve community van ontwikkelaars en staat bekend als een van de meest vooruitstrevende PHP frameworks die er op dit moment bestaan.

## Versie beheer (GIT)

Alle door Divtag ontwikkelde broncode wordt in ons versiebeheer systeem [Beanstalk](https://beanstalkapp.com/) bewaard. Zo kan op ieder moment terug gekeken worden welke wijziging door wie is doorgevoerd. Dit versiebeheer systeem bevat tevens op broncode niveau de documentatie van het systeem. Afhankelijk van het soort project kan er worden gekozen voor om code reviews in te stellen alvorens aanpassingen in productie geplaatst kunnen worden.

## Code kwaliteit (Scrutinizer CI)

Middels [Scrutinizer CI](https://scrutinizer-ci.com/) vinden er geautomatiseerd kwaliteitscontroles plaats op de ontwikkelde broncode. Zo worden eventuele fouten sneller gevonden en voldoet de broncode aan de gestelde opmaak eisen. Tevens voorziet deze controle software in het onderscheppen van beveiligingsrisico's en is het mogelijk om eigen tests te ontwikkelen waaraan de software moet blijven voldoen.

Dit laatste staat beter bekend als Test Driven Development en is een steeds populairder wordende vorm van ontwikkelen. Door het uitvoeren van deze tests kan bijvoorbeeld worden gegarandeerd dat software na iedere update op dezelfde wijze blijft werken. Als de test faalt kan de software niet in productie worden genomen.

## Monitoring (Sentry)

Toch kan het, ondanks bovenstaande maatregelen, gebeuren dat een applicatie een foutmelding geeft. Deze worden middels de monitoring software van [Sentry](https://sentry.io/) centraal opgeslagen. Onze developers krijgen hier direct een melding van. Zo kan er op zeer efficiëntie wijze worden gezocht naar de oorzaak van de foutmelding.  
