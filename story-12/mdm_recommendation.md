# Choix d'une solution MDM

Pour encadrer l'usage des terminaux accédant aux ressources d'une application, une solution de Mobile Device Management (MDM) est indispensable.

# Tableau Comparatif des Solutions

| Critère | Microsoft Intune | Jamf Pro / Workspace ONE |
| :--- | :--- | :--- |
| **Intégration Écosystème** | Intégration native avec Azure AD et Microsoft 365, idéale pour gérer les accès aux endpoints de production. | Jamf est spécialisé Apple ; Workspace ONE est une solution agnostique très complète. |
| **Gestion des Secrets** | Permet d'isoler les applications professionnelles pour éviter la fuite des clés API et URLs exposées. | Offre un contrôle granulaire sur les permissions des applications et le chiffrement des données. |
| **Accès Conditionnel** | Bloque l'accès aux APIs si l'appareil est compromis ou non conforme. | Politiques de conformité automatisées permettant de verrouiller le terminal en cas de détection de menace. |
| **Déploiement d'Apps** | Facilite la distribution sécurisée d'APK signés et la gestion de leur cycle de vie. | Supporte des flux de déploiement complexes pour les flottes mixtes (iOS/Android). |
| **Coût et Adoption** | Souvent déjà inclus dans les licences entreprises existantes, réduisant les coûts de mise en œuvre. | Nécessite généralement un investissement supplémentaire par licence utilisateur. |

# Recommandation : Microsoft Intune

### Justification :

Au vu des vulnérabilités de configuration trouvées (endpoints de production et clés API exposés), Microsoft Intune est recommandé pour sa capacité à imposer des politiques d'accès conditionnel.

- **Conteneurisation :** Permet d'isoler les données de l'application Nickel des applications personnelles sur le téléphone de l'utilisateur.

- **Conformité :** Bloque l'accès aux endpoints de production (api.nickel.eu) si le téléphone est rooté ou si l'intégrité de l'OS est compromise, complétant ainsi les vérifications de hash (SHA256) effectuées manuellement lors de l'audit.