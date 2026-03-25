# 1. Analyse d'Intégrité et Préparation

L'analyse a débuté par l'identification unique du fichier et la préparation de l'environnement d'audit.


- Empreinte Numérique (SHA256) : `F01F08C8B6E2FE4612E81BC7E3A3BA9440DAD0D7A962F4E67640390DD721D528.`

- Analyse Statique Automatisée : Utilisation de MobSF via Docker pour une première évaluation globale.

- Décompilation : Utilisation d'Apktool pour extraire les ressources et le code source de l'APK.

# 2. Analyse des Vulnérabilités (Findings)

- `google_api_key` : Clé API exposée. Risque : Abus de quota et accès services Google.
- `firebase_database_url` : URL Firebase. Risque : Accès direct DB si règles permissives.
- `ACCOUNT_ENDPOINT` : Route API. Risque : Fuzzing et attaques ciblées sur endpoints bancaires.
- `ENVIRONMENT` : "production". Risque : Confirmation de la cible pour l'attaquant.

# 3. Recommendations 
- Révoquer les clés immédiatement et migrer vers **GCP Secret Manager**.
- Implémenter le **Certificate Pinning** et activer **Firebase App Check**.
- Supprimer tout secret en clair du fichier `strings.xml` (lisible après décompilation).

- Stocker les clés via des variables d'environnement ou un système de gestion de secrets (ex: Android Keystore, variables CI/CD).