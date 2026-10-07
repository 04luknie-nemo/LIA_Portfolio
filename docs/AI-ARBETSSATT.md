# Arbetssätt med AI

Det här dokumentet beskriver hur jag använder Claude (AI-assistent) i projektet. Målet är att jag ska kunna förklara varje rad i koden. Om jag inte kan det har AI:n gjort för mycket.

## Roller

| Jag | Claude |
| --- | --- |
| Skriver entiteter och regler i Domain | Förklarar mönster och begrepp innan jag skriver |
| Skriver services i Application | Granskar min kod och pekar på problem |
| Bestämmer struktur, namn och flöden | Föreslår testfall jag missat |
| Granskar och godkänner all kod från Claude | Skriver boilerplate när jag ber om det: konfiguration, DI, migrationer |

## Tre nivåer av hjälp

Jag väljer nivå för varje uppgift och säger det i början.

1. Förklara. Claude förklarar utan att skriva min lösning. Korta exempel på ett mönster är okej.
2. Granska. Jag skriver koden. Claude kommenterar men skriver inte om den.
3. Ta över. Claude skriver koden. Jag granskar den enligt checklistan nedan innan den mergas.

Nivå 1 och 2 är standard. Nivå 3 använder jag för kod jag redan förstår, eller när jag vill se ett förslag att jämföra med.

## Arbeta i små etapper

En etapp är en sak, till exempel "företag kan neka en ansökan". Varje etapp följer samma steg:

1. Jag beskriver vad som ska byggas.
2. Claude ställer frågor om regler och kantfall.
3. Koden skrivs, av mig eller av Claude beroende på nivå.
4. Koden hamnar på en egen gren och i en pull request.
5. Granskning.
6. Tester skrivs och går igenom i GitHub Actions.
7. Merge till main.

En etapp ska gå att granska på cirka 15 minuter. Blir den större delar vi upp den.

## När Claude tar över

- Claude skapar en egen gren, aldrig direkt mot main.
- Claude öppnar en pull request och beskriver vad som ändrats och varför.
- Jag granskar varje fil innan merge.
- Claude lägger till en rad i AI-loggen nedan.

## Checklista vid granskning av AI-kod

- [ ] Jag kan förklara vad varje rad gör.
- [ ] Jag kan förklara varför lösningen ser ut så här, och inte på ett annat sätt.
- [ ] Koden följer lagerstrukturen. Domain beror inte på något annat projekt.
- [ ] Reglerna ligger i entiteterna, inte i services eller endpoints.
- [ ] Det finns tester för reglerna.
- [ ] Inga nya paket har lagts till utan att jag vet varför.
- [ ] Bygget och testerna går igenom i GitHub Actions.

Om en punkt inte stämmer frågar jag Claude tills den gör det, eller skriver om koden själv.

## Bra frågor att ställa

- "Förklara utan kod hur jag borde lösa X."
- "Visa ett kort exempel på mönstret, inte min lösning."
- "Granska min kod, peka på problem men skriv inte om den."
- "Ställ frågor tills jag själv ser felet."
- "Vilka testfall saknas?"

## AI-logg

Här loggas varje gång Claude skriver kod som hamnar i repot.

| Datum | Etapp | Nivå | Vad Claude gjorde | Granskad av mig |
| --- | --- | --- | --- | --- |
| 2026-10-06 | Projektstart | Ta över | Skapade Expo-appen med reset-project och mallen för Web API | Ja |
| 2026-10-07 | Arbetssätt | Ta över | Skrev CLAUDE.md och det här dokumentet | Ja |
| 2026-10-07 | CI | Ta över | Rättade stavfel i api.yml, sökväg till lockfil i mobile.yml och bytte actions till v5 | |
