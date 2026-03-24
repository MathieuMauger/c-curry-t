## Vulnérabilités
- `google_api_key` : Clé API exposée. Risque : Abus de quota et accès services Google.
- `firebase_database_url` : URL Firebase. Risque : Accès direct DB si règles permissives.
- `ACCOUNT_ENDPOINT` : Route API. Risque : Fuzzing et attaques ciblées sur endpoints bancaires.
- `ENVIRONMENT` : "production". Risque : Confirmation de la cible pour l'attaquant.

## Solutions
1. Révoquer les clés immédiatement et migrer vers **GCP Secret Manager**.
2. Implémenter le **Certificate Pinning** et activer **Firebase App Check**.
3. Supprimer tout secret en clair du fichier `strings.xml` (lisible après décompilation).