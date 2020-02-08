Pour démarrer un nouveua projet, créer une carcasse d'installer IONIC :

Dans ce répertoire, initaliser le projet : 
```bash
npm init
```
puis installer IONIC :
```bash
npm i ionic
```
et enfin, générer le nouveau projet :
```bash
./node_modules/.bin/ionic start
```
avec comme options : Angular et blank project.



Fermer la fenêtre et mettre le projet ainsi généré dans VSC.
A noter que ce répertoire peut être sorti de sa coquile et sa coquille peut-être jetée ; on gagne de la place.

Afin d'installer des "dependancies" faire :
```bash
npm i ionic --save-dev
```

Editer package.json et insérer :
```bash 
"ionic" : "ionic", 
"start": "ionic serve",
```

 dans les scripts.

 Installer CORDOVA :
 ```bash
 npm install cordova --save-dev
 ```
puis
```bash
npm run ionic cordova prepare android
```
Modifier config.xml en remplaçant le name, l'auteur, description, mail....

installer native-run par :
```bash
npm i native-run --save-dev
```

Afin de tester sur le device android, faire :
```bash
npm run ionic cordova run android --device
```

Supprimer Home et app-routing-module et toutes ses références.

Git init

git add filename

git commit -m "Nouveau projet IONIC" 

