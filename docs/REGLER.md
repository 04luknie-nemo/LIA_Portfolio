# Regler och flöden

Det här dokumentet samlar besluten om hur appen ska fungera. Reglerna blir grunden för entiteterna i Domain. Ändra dokumentet när ett beslut ändras, så kod och dokument stämmer överens.

Status: utkast, 2026-11-02.

## Roller

| Roll | Använder | Gör |
| --- | --- | --- |
| Elev | Expo-appen | Ser LIA-platser, skickar ansökningar, följer status |
| Skola (lärare, LIA-samordnare) | Expo-appen | Lägger in företag och platser, sköter kontakten med företagen, ser alla elever |
| Företag | Mejl och en enkel webbsida | Svarar på ansökningar med ett klick. Inget konto. |

## Företag och LIA-platser

- Skolan lägger in företag, kontaktperson och LIA-platser. Företaget gör ingenting för att komma med.
- En LIA-plats har:
  - antal platser
  - stack, till exempel .NET, Azure, React
  - inriktning, till exempel backend, frontend eller fullstack
- Eleven ser antalet lediga platser.
- En LIA-plats stängs automatiskt när alla platser är tillsatta.

## Övriga företag

- Företag som inte är anslutna visas i en egen lista som eleven kan dölja och visa.
- Eleven söker dem på egen hand, men loggar ansökan i appen.
- Skolan ser även de ansökningarna, så överblicken blir komplett.

## Ansökan

- En elev får söka obegränsat antal LIA-platser.
- Eleven har en uppsättning dokument: CV, pitch och eventuella LIA-dokument. Samma dokument används i alla ansökningar.
- En ansökan har en av följande statusar:

| Status | Betyder |
| --- | --- |
| Skickad | Eleven har skickat ansökan |
| Granskad | Företaget har öppnat ansökan |
| Intervju | Företaget vill boka intervju |
| Accepterad | Eleven har fått platsen |
| Nekad | Företaget har tackat nej |
| Inget svar | Inget har hänt på 14 dagar |

Öppna frågor om status:
- Vilka övergångar är tillåtna? Får till exempel en nekad ansökan öppnas igen?
- Vad händer med elevens övriga ansökningar när en ansökan blir accepterad?

## Kontakt med företagen

Mejl används bara som avisering. All data och all status ligger i appen.

1. När en elev ansöker får företagets kontaktperson ett mejl: "Ny ansökan från [elev] till er LIA-plats", med en knapp.
2. Knappen öppnar en enkel webbsida utan inloggning. Sidan visar elevens CV, pitch och portfolio.
3. Sidan har knapparna "Intressant", "Boka intervju" och "Nej tack". Ett klick ändrar status i appen.
4. Har inget hänt efter 7 dagar skickas en påminnelse.
5. Har inget hänt efter 14 dagar blir statusen "Inget svar".
6. Företaget kan välja ett samlat mejl en gång i veckan i stället för ett mejl per ansökan.

Telefon fungerar som reserv. Svarar företaget per telefon eller vanligt mejl uppdaterar skolan statusen i appen.

## Länken i mejlet

Förslag, inte beslutat:

- Länken gäller i 30 dagar.
- Länken är kopplad till en kontaktperson och visar bara ansökningar till det företaget.
- En utgången länk går att förnya till samma mejladress.
- Vidarebefordran går inte att stoppa helt. Korta giltighetstider och en länk per kontaktperson begränsar risken.

## Personuppgifter

- CV och profil är personuppgifter och omfattas av GDPR.
- Eleven godkänner, när profilen skapas, att dokumenten delas med de företag eleven söker till.

## Skolans vy

- Lista med alla elever i klassen.
- Totalsummor överst, till exempel antal elever med plats, utan plats och antal ansökningar.
- Klick på en elev visar elevens ansökningar och status på varje.
- Skolan kan ändra status åt ett företag.
