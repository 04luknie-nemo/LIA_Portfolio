# LIA Connect

Kopplar ihop studenter (systemutvecklare .NET) med företag för LIA-platser.

## Om projektet

- Idé och projektägare: [@04luknie-nemo](https://github.com/04luknie-nemo)
- Medutvecklare: Sebastian

Att hitta LIA i dag sker mest via mejl. Mejl missas, ansökningar kommer bort och det är svårt för skolan att se vilka elever som saknar plats. LIA Connect samlar LIA-ansökningar på ett ställe, för tre roller:

- Elev: profil med CV, pitch och kompetenser.
- Företag: ser ansökningar och deras status.
- Skola: ser alla elever och om de har fått LIA-plats.

Projektet är i ett tidigt skede. Funktioner och flöden är inte bestämda än.

## Struktur

- mobile/  Expo-app (React Native, expo-router)
- api/LiaConnect.Api/  ASP.NET Core Web API (.NET 9)

## Kom igång

Mobil:

    cd mobile
    npm install
    npx expo start

API:

    cd api/LiaConnect.Api
    dotnet run

## Arbetssätt med AI

Projektet byggs med Claude som assistent. Se [docs/AI-ARBETSSATT.md](docs/AI-ARBETSSATT.md) för hur vi delar upp arbetet och granskar kod.
