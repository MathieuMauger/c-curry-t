# Politique de Sécurité Mobile (politique_mobile)

Cette politique définit les standards obligatoires pour le développement et l'utilisation des applications mobiles au sein de l'organisation.

## 1. Développement et Protection du Code

- Interdiction des secrets en clair : Aucune clé d'API, URL de base de données ou identifiant technique ne doit être codé en dur.

- Gestion des secrets : Utilisation obligatoire de solutions de coffre-fort numérique comme KeePass.

## 2. Sécurité et Cycle de Vie

- Protection des services Cloud : Activation de Firebase App Check pour s'assurer que seules les applications authentiques peuvent interagir avec la base de données, même si l'URL est connue.

- Signature des APK : Tout APK déployé doit être signé avec une clé protégée dont la validité est contrôlée.

- Audit Régulier : Chaque version majeure doit passer par une analyse statique (via des outils comme MobSF) avant sa mise en production.