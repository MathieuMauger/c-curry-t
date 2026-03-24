Nous avons unzip le fichier app.apk. Grâce à cela, nous avons obtenu un dossier que vous retrouverez sous ./app/.

Ensuite, nous avons exécuté les commandes

```bash
Get-FileHash .\app\classes.dex -Algorithm SHA256
Get-FileHash .\app\AndroidManifest.xml -Algorithm SHA256
```
et avons obtenu les hashs suivants suivants: 

.\app\classes.dex : 57898C5978715DA96560ED2692B4A8FA1A8E914B37988DCF369CC59951F6C429

.\app\AndroidManifest.xml : 80B9B101E3BF02F03EEC4F2C9C9CCF4D61403612E1435949B51CEC8B85D7A276