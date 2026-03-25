## Recompilation de l'APK

### Commande utilisée

```powershell
apktool b "cheminverslapk\story-4" -o "cheminverslefolderdesortie\story-7\app_recompiled.apk" 2>&1 | Tee-Object -FilePath "cheminpourlelog\story-7\build.log"
```

## Résultat

```
story-7/
├── app_recompiled.apk   # APK recompilé
└── build.log            # Log complet du build
```