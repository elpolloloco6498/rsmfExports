# rsmfExports

## A propos
Cet outil permet de télécharger des fichiers automatiquement sans avoir à parcourir l'interface RSMF. 
Il suffit de spécifier les écrans que l'outil doit parcourir et les champs d'exportation qui nous intéresses.

## Installation de l'outil
### Installation de Gecko driver
Gecko driver est indispensable, il permet de faire le lien entre le code python et le navigateur.
Gecko driver "geckodriver.exe" se trouve dans le repertoire Github, vous pouvez le copier dans n'importe quel dossier. Il faudra spécifier son emplacement dans le fichier de configuration de l'outil.

### Installation de Firefox
Si ce n'est pas deja fait un faut installer le navigateur Firefox sur votre ordinateur.

### Installation de Python
Depuis le centre logiciel installer Python 3.9

### Installation des modules Python requis
Tapez dans le terminal:\
`pip3 install selenium, keyring, eel`\
Puis encore dans le terminal, nous allons configurer votre mot de passe RSMF:\
Tapez\
`python3`\
`keyring.set_password("darwin", "username", "password")`\
Votre mot de passe a été enregistré par le système.
L'outil est prêt a être utilisé.

## Configuration
Il faut maintenant configurer l'outil.
Dans le fichier config.json vous trouverez toutes informations qu'il faut renseigner. En particulier le nom d'utilisateur RSMF et le lien de l'éxecutable Geckodriver.\
config.json\
```
{
  "selenium": {
    "geckodriver": "C:/Produits/GeckoDriver/geckodriver.exe",
    "report": "readme.txt"
  },
  "app": {
    "name": "rsmf",
    "url": "http://lxre0017pv.unix-int.intra-int.bdf-int.local:8080/e360/mdm/entity360view/?wstate=(%27$ws%27:DASHBOARD)",
    "version": "1.0",
    "username": "ishaml"
  }
}
```
Le fichier de configuration ui.json permet de configurer les différents écrans de l'application RSMF. Pour chaque écran il faut expliciter les différents champs d'exportation.\
ui.json\
```
{
  "screens": {
    "Ecran Assurance": {
      "export-fields": [
        "Assurance",
        "Dénomination",
        "Dérogation",
        "Données CV",
        "Obligations Déclaratives"
      ]
    },
    "Ecran Agent financier": {
      "export-fields": [
        "Agent financier",
        "Obligations déclaratives",
        "Reporting SSM"
      ]
    }
  }
}
```

## Lancement
Dans un terminal dans le repertoire de l'outil, tapez:\
`python3 main.py`
