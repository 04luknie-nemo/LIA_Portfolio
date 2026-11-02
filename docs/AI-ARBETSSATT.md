# Arbetssätt med AI

Det här dokumentet beskriver hur vi använder Claude (AI-assistent) i projektet. Målet är att varje utvecklare ska kunna förklara varje rad i koden. Om vi inte kan det har AI:n gjort för mycket.

## Utvecklare

| Person | Roll |
| --- | --- |
| [@04luknie-nemo](https://github.com/04luknie-nemo) | Projektägare. Äger idén, bestämmer etapper och godkänner merge till main. |
| [@galenginger](https://github.com/galenginger) (Sebastian) | Medutvecklare. |

## Uppdelning

Varje del av projektet har en ansvarig. Den ansvariga skriver koden, den andra granskar.

| Del | Ansvarig |
| --- | --- |
| Domain: entiteter och regler | Bestäms |
| Application: services | Bestäms |
| Infrastructure: databas och inloggning | Bestäms |
| Api: endpoints | Bestäms |
| mobile: Expo-appen | Bestäms |

Fyll i tabellen när ni har bestämt er. Ändra den om uppdelningen ändras.

## Roller

| Utvecklarna | Claude |
| --- | --- |
| Skriver entiteter och regler i Domain | Förklarar mönster och begrepp innan vi skriver |
| Skriver services i Application | Granskar vår kod och pekar på problem |
| Bestämmer struktur, namn och flöden | Föreslår testfall vi missat |
| Granskar varandras kod och all kod från Claude | Skriver boilerplate när vi ber om det: konfiguration, DI, migrationer |

## Tre nivåer av hjälp

Den som arbetar med en uppgift väljer nivå och säger det i början.

1. Förklara. Claude förklarar utan att skriva lösningen. Korta exempel på ett mönster är okej.
2. Granska. Utvecklaren skriver koden. Claude kommenterar men skriver inte om den.
3. Ta över. Claude skriver koden. Den andra utvecklaren granskar den enligt checklistan nedan innan merge.

Nivå 1 och 2 är standard. Nivå 3 används för kod vi redan förstår, eller för att få ett förslag att jämföra med.

## Arbeta i små etapper

En etapp är en sak, till exempel "företag kan neka en ansökan". Projektägaren lägger upp etapper som issues på GitHub. Varje etapp följer samma steg:

1. Den ansvariga tar en issue och beskriver vad som ska byggas.
2. Claude ställer frågor om regler och kantfall.
3. Koden skrivs, av utvecklaren eller av Claude beroende på nivå.
4. Koden hamnar på en egen gren och i en pull request.
5. Den andra utvecklaren granskar.
6. Tester skrivs och går igenom i GitHub Actions.
7. Projektägaren godkänner merge till main.

En etapp ska gå att granska på cirka 15 minuter. Blir den större delar vi upp den.

## Granskning mellan utvecklarna

- Ingen mergar sin egen pull request.
- Den som granskar ska kunna förklara koden efteråt, inte bara godkänna den.
- Frågor ställs som kommentarer i pull requesten, så de syns för båda.
- Vänta på granskning innan nästa etapp som bygger på samma kod.

## När Claude tar över

- Claude skapar en egen gren, aldrig direkt mot main.
- Claude öppnar en pull request och beskriver vad som ändrats och varför.
- Den andra utvecklaren granskar varje fil innan merge.
- Claude lägger till en rad i AI-loggen nedan.

## Checklista vid granskning av AI-kod

- [ ] Jag kan förklara vad varje rad gör.
- [ ] Jag kan förklara varför lösningen ser ut så här, och inte på ett annat sätt.
- [ ] Koden följer lagerstrukturen. Domain beror inte på något annat projekt.
- [ ] Reglerna ligger i entiteterna, inte i services eller endpoints.
- [ ] Det finns tester för reglerna.
- [ ] Inga nya paket har lagts till utan att jag vet varför.
- [ ] Bygget och testerna går igenom i GitHub Actions.

Om en punkt inte stämmer frågar granskaren Claude eller utvecklaren tills den gör det.

## Bra frågor att ställa

- "Förklara utan kod hur jag borde lösa X."
- "Visa ett kort exempel på mönstret, inte min lösning."
- "Granska min kod, peka på problem men skriv inte om den."
- "Ställ frågor tills jag själv ser felet."
- "Vilka testfall saknas?"

## AI-logg

Här loggas varje gång Claude skriver kod som hamnar i repot.

| Datum | Etapp | Nivå | Vad Claude gjorde | Begärd av | Granskad av |
| --- | --- | --- | --- | --- | --- |
| 2026-10-06 | Projektstart | Ta över | Skapade Expo-appen med reset-project och mallen för Web API | @04luknie-nemo | @04luknie-nemo |
| 2026-10-07 | Arbetssätt | Ta över | Skrev CLAUDE.md och det här dokumentet | @04luknie-nemo | @04luknie-nemo |
| 2026-10-07 | CI | Ta över | Rättade stavfel i api.yml, sökväg till lockfil i mobile.yml och bytte actions till v5 | @04luknie-nemo | @04luknie-nemo |
| 2026-11-02 | Arbetssätt | Ta över | Uppdaterade CLAUDE.md och det här dokumentet för två utvecklare | @04luknie-nemo | |
| 2026-11-02 | Regler | Ta över | Skrev docs/REGLER.md utifrån besluten om roller, ansökan och kontakt med företagen | @04luknie-nemo | |
| 2026-11-02 | Regler | Ta över | Lade till statusen Stängd och tillåtna övergångar i docs/REGLER.md | @04luknie-nemo | |
