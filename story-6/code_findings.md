## Vulnérabilité

**Localisation :** `Source Code/com/fpe.comptenickel/BuildConfig`

Des endpoints et identifiants sensibles sont exposés en clair directement dans le code de l'application, ce qui les rend accessibles à toute personne décompilant l'APK.

```java
package com.fpe.comptenickel;

public final class BuildConfig {
    public static final String ACCOUNT_ENDPOINT                  = "https://api.nickel.eu/customer-banking-api";
    public static final String CUSTOMER_AUTHENTICATION_ENDPOINT  = "https://api.nickel.eu/customer-authentication-api";
    public static final String PERSONAL_SPACE_API_ENDPOINT       = "https://api.nickel.eu/personal-space-api";
    public static final String GCM_PROJECT_NUMBER                = "246766419677";
    public static final String PUSHWOOSH_APPID                   = "DDF11-D1BF9";
    public static final String ENVIRONMENT                       = "production";
    public static final String BUILD_TYPE                        = "release";
    public static final int    VERSION_CODE                      = 150;
    public static final String VERSION_NAME                      = "2.12.0";
}
```

**Risques :**
- Exposition des endpoints d'API de production
- Possibilité d'usurpation ou d'abus des services bancaires
- Identifiant Pushwoosh (notifications push) extractible et réutilisable

**Recommandation :** Stocker les clés via des variables d'environnement ou un système de gestion de secrets (ex: Android Keystore, variables CI/CD).

---

## Mauvaise Pratique 

Dans le dossier `pushwoosh/`

Les fichiers dans ce dossier sont nommés avec des lettres simples sans signification (`a`, `aa`, `b`, `c` ... jusqu'à `z`), ce qui rend le code **illisible et non maintenable**.

**Risques :**
- Difficulté d'audit et de maintenance
- Obfuscation volontaire ou involontaire du comportement de l'app
- Impossible de comprendre le rôle de chaque fichier sans les lire un par un

**Recommandation :** Adopter une convention de nommage explicite.