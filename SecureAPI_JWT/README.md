# SecureAPI_JWT

API REST ASP.NET Core 8 sécurisée avec ASP.NET Core Identity et JWT.

## Fonctionnalités
- Inscription (`POST /api/Auth/register`)
- Connexion et génération de token (`POST /api/Auth/token`)
- Attribution de rôle (`POST /api/Auth/addrole`)
- Endpoints protégés par `[Authorize]` et `[Authorize(Roles = "Admin")]`
- Swagger avec bouton Authorize

## Prérequis
- .NET 8 SDK
- SQL Server LocalDB (ou SQL Server Express)

## Lancer le projet
1. Cloner le dépôt
2. Vérifier la chaîne de connexion dans `appsettings.json`
3. Appliquer la migration : `Update-Database`
4. Lancer avec F5 et ouvrir Swagger

## Scénario de test
1. Register, puis récupérer le token
2. GET /WeatherForecast sans token : 401
3. Authorize avec `Bearer <token>` : 200
4. Avec le rôle Admin requis : 403 pour un simple User
5. addrole avec l'Id de l'utilisateur, puis nouveau token : 200

## Auteur
Votre nom, classe