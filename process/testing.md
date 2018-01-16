[← Terug](/)

# Testen

In het ontwikkelproces worden er functionele aanpassingen beschreven in een user story. Deze user story bevat “acceptatie criteria”, dit is een beschrijving waaraan de aanpassing moet voldoen voordat deze in een productieomgeving wordt doorgevoerd.

De volgende tests vinden altijd plaats:

- Interne test: Intern wordt er door een andere ontwikkelaar gecontroleerd of er aan de acceptatie criteria wordt voldaan en technisch geen fouten in de code zitten. Dit wordt handmatig op regelniveau gecontroleerd. Hierin wordt extra aandacht besteed aan veiligheidsrisico’s zoals reeds als “Best practice” bekend. (o.a. op basis van OWASP top 10)
- Product owner test: Als de interne test is geslaagd wordt de code in de staging (test) omgeving geplaatst en door de product owner getest op functionele werking en of er aan de acceptatie criteria wordt voldaan.

Afhankelijk van de complexiteit en hoe kritiek de functionaliteit is wordt er eventueel een [unittest](https://nl.wikipedia.org/wiki/Unittesten) taak opgenomen in de user story.

Met een unittest waarborgen we dat de functionaliteit correct werkt en blijft werken in de toekomst. Deze unit tests worden geautomatiseerd uitgevoerd tijdens het ontwikkelen. Indien een test faalt kan de code niet worden opgenomen in de release.

Iedere wijziging kan middels een roll-back uit het versiebeheer systeem worden terug gedraaid. Iedere database aanpassing die wordt uitgevoerd bevat een ‘up’ en ‘down’ procedure. Indien nodig kunnen eventuele structuur wijzigingen hiermee ongedaan worden gemaakt.
