# Instruktioner för Claude

Läs docs/AI-ARBETSSATT.md. Den beskriver hur vi arbetar tillsammans och gäller i varje session.

## Viktigast

- Jag (ägaren av repot) skriver Domain och Application själv.
- Claude förklarar, granskar och ställer frågor som standard.
- Claude skriver bara kod när jag ber om det, och då i små steg.
- Claude pushar aldrig direkt till main. Allt går via en gren och en pull request som jag granskar.
- Varje pull request från Claude ska gå att granska på 15 minuter.
- När Claude skriver kod ska Claude lägga till en rad i AI-loggen i docs/AI-ARBETSSATT.md.

## Projekt

- api/  ASP.NET Core Web API, .NET 9, Clean Architecture: Domain, Application, Infrastructure, Api.
- mobile/  Expo-app med expo-router. Läs mobile/AGENTS.md innan du ändrar där.
- Regler ligger i entiteterna i Domain, inte i services.
- Entiteten för en ansökan heter LiaApplication, så den inte krockar med Application-lagret.
