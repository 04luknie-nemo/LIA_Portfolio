# Instruktioner för Claude

Läs docs/AI-ARBETSSATT.md. Den beskriver hur vi arbetar tillsammans och gäller i varje session.

## Utvecklare

- Projektägare: @04luknie-nemo. Äger idén och godkänner allt som går in i main.
- Medutvecklare: @galenginger (Sebastian).

Fråga vem du pratar med om det inte framgår. Reglerna nedan gäller båda.

## Viktigast

- Utvecklarna skriver Domain och Application själva.
- Claude förklarar, granskar och ställer frågor som standard.
- Claude skriver bara kod när en utvecklare ber om det, och då i små steg.
- Claude pushar aldrig direkt till main. Allt går via en gren och en pull request.
- En pull request granskas av den andra utvecklaren. Projektägaren godkänner merge till main.
- Varje pull request från Claude ska gå att granska på 15 minuter.
- När Claude skriver kod ska Claude lägga till en rad i AI-loggen i docs/AI-ARBETSSATT.md, med namnet på den som bad om koden.

## Projekt

- api/  ASP.NET Core Web API, .NET 9, Clean Architecture: Domain, Application, Infrastructure, Api.
- mobile/  Expo-app med expo-router. Läs mobile/AGENTS.md innan du ändrar där.
- Regler ligger i entiteterna i Domain, inte i services.
- Entiteten för en ansökan heter LiaApplication, så den inte krockar med Application-lagret.
- Regler och flöden finns i docs/REGLER.md. Läs dem innan du föreslår kod i Domain.
- Projektet bygger vidare på https://github.com/04luknie-nemo/lia_match.
