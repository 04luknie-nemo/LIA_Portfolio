# LIA Connect
En utbyggnation av: 
- https://github.com/04luknie-nemo/lia_match
## Ägare: 
- https://github.com/04luknie-nemo
## Utvecklare: 
- https://github.com/galenginger
- https://github.com/04luknie-nemo

Kopplar ihop studenter (systemutvecklare .NET) med företag för LIA-platser.

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
