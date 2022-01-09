# Eda Nettside
 Nettside for musikkgruppen Eda.
 
 ### [https://edamusic.no/](https://edamusic.no/)
 
 *Hostet hos [domeneshop](https://domene.shop/).*


### Tutorial: Hvordan oppdatere nettsiden på webhotellet automatisk.
**Før du starter:**

    - Sørg for at Git koden din er strukturert riktig. Er det en www mappe i master folderen?
    - Er de andre nettsidene under www mappen? (www/søknad)
1. Finn fram til Git repoet ditt, e.g https://github.com/Zylvian/Eda-Nettside.
2. Gå til 'Settings' -> 'Secrets', og legg inn FTP passordet ditt som "FTP_PASSWORD".
3. Gå til 'Actions' -> 'New Workflow'.
4. Lim inn denne koden, og bytt ut "username" med passordet du ble tilsendt av domeneshop:
```
on: push
name: 🚀 Deploy website on push
jobs:
  web-deploy:
    name: 🎉 Deploy
    runs-on: ubuntu-latest
    steps:
    - name: 🚚 Get latest code
      uses: actions/checkout@v2
    
    - name: 📂 Sync files
      uses: SamKirkland/FTP-Deploy-Action@4.2.0
      with:
        server: ftp.domeneshop.no
        username: BRUKERNAVN
        password: ${{ secrets.FTP_PASSWORD }}
    ```
    *(Dokumentasjon: https://github.com/marketplace/actions/ftp-deploy)*

5. Nettsiden din skal nå oppdatere seg hver gang du pusher ny kode til Git! 
```

---

## Laget av:

![Mac and cheese te beste pris](/www/mac_cheese.webp?raw=true "Mac and cheese te beste pris")

### Mac - [@GMRMac](https://github.com/GMRMac)

<!-- ![Dilettant e på g e det mulig](/www/jarleglasses.jpg?raw=true?width=250 "Dilettant e på g e det mulig")` -->
<img src="/www/jarleglasses.jpg" alt="drawing" width="250"/>

### Dilettant - [@Zylvian](https://github.com/Zylvian) 
