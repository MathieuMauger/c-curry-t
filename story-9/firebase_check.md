Nous avons récupéré le lien vers Firebase à partir de l'apk signé. Voici ce que l'on a obtenu : 

```xml
<string name="firebase_database_url">https://application-client-nickel.firebaseio.com</string>
```

Lorsqu'on essaie d'accéder à la base de données depuis ce lien, nous obtenons une erreur 401 Unauthorized (voir firebase-screen.png).

On peut conclure que la base de données est sécurisée.