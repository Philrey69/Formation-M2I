
# Introduction à l'utilisation du README.md
## Sous-titre


> introduction ou citation


* Myliste Item
* Myliste subitem

A téléchager
* [NPM](https://nodejs.org/en/) 
* [VSCODE](https://code.visualstudio.com/)
* [Gitbash](https://gitforwindows.org/)
* Xampp

# Utilisation de VSC

Pour ouvrir le projet, glisser le dossier racine dans la fenêtre de VSC.

RACCOURCIS VSC
* Auto-indenter : alt+shift+f
* Commentaires : ctrl + :
* Terminal : ctrl + %
* Supprimer une ligne : shift + suppr
* Dupliquer une ligne : shift + alt + flèche haute ou basse
* Déplacer : alt + flèche haute ou basse
* remplacer : ctrl + h


## Déclarer un projet

Avant tout, il faut obligatoirement déclarer le projet.
Pour déclarer un projet :
```bash
npm init
```
dans terminal à l'endroit racine du projet puis répondre aux questions. Pour ouvrir le terminal : "CTRL+%" dans VSC


Dans le doc HTML, la balise script se place en dernière position du BODY en précisant le chemin relatif ( par rapport à où est Index.html.).

Pour le projet : Faire un MCD et un dictionnaire de données.
MVC : Model Vue Controler 

## Les variables

JVS : Variable en camelCase : let maVariable=0;

Une valeur contient un type

* Primitives
    * string
    * boolean
    * number
    * undefined (quand le "let var" n'est pas suivi du = ; ne pas utiliser et préférer = null; )
* Non primitives
    * Object
    * Array
    * ....


JVS est un langage dynamiquement typé.

pour le string : 
    \ pour mettre une apostrophe dans du string : 'j\'ai';
    préférer le "back-stick" : alt-gr + 7 (`)


const : constante avec obligation d'affecter une valeur et accessible uniquement en lecture.

Tableau : lors de la déclaration, il vaut mieux terminer par une virgule :
```js
    let variable[1, 2, 3,];
```

Déclaration d'un objet auto-construit :
    let myObject = {}; ou ,  pour un tableau :
    let myObject{name : `Paris`,
                 temperature : 7   };



Dans un objet, pas de "const", de "let", de ";" ; les propriétés sont séparées par une virgule et on leur définit une valeur avec ":".


Variables métasyntaxiques : foo, bar, ba2, qux


### Les opérateurs


Concaténation

Ne pas utiliser le +  :
```js
    const someVar = `Hello`;
    const someVar2 = `World`;
    console.log(someVar + someVar2)
```
Mais : 
```js  
    console.log(`Hello ${someVar2}`); /* c'est de l'interpolation */
```

% : modulo : c'est le reste d'une division.


Foo[`bar`] ou Foo.bar

###DOM
de 1995 à 2008 il n'existait que a pour manipuler l'affichage.

Attention : Faille de sécurité de type XSS : Cross-Site Scripting

Document Object Model ("DOM" --> affichage sur page HTML)

* Ajouter un élément : 
   * 1 - Créer la balise
   ```js
        let childElement = document.createElement(`h1`);
   ```
   * 2 - Mettre le contenu dans la balise
        Bad practice (La faille de sécurité [@see XSS](https://www.owasp.org/index.php/Cross-site_Scripting_(XSS)) mais c'est comme ça : 
   ```js  
        childElement.innerHTML = `<p>Some <i>content</i></p>`;
   ```
   * 3 - Mettre dans la balise dans le document
        Positionner un élément en dernière position dans la balise manipulée
   ```js
        parentElement.appendChild(childElement);
   ```
      la méthode appenChild existe pour toutes les balises HTML ; Insert child dans h1 en dernière position.


* Récupérer un élément HTML

```js
    document.body
```


### LES FONCTIONS

> Ne pas déclarer les fonctions comme ça :

European Computer Manufactoring Association (ECMA) décide des normes des langages script.
Cancel bad parts: **es6** 2015 (es6 (ECMA Script version 6) version de jsc)
```js
function foo(){
    console.log(this)
};
```
Ce type de déclaration possède un contexte d'exécution instable et remontée de portée à cause de la 1ère passe de la précompilation (càd une fonction dclarée en toute fin sera utilisable ce qui n'est pas lisible). Le contexte d'exécution c'est "this".

Les déclarer comme ça, plutôt dans des ```const``` :
```js
const foo =(arg1) => {
    /* contexte stable */
    console.log(arg1)
};

foo("John");
```

Usage, siganture must be respected

```js
const addition =(a,b) => { return a + b }
let toto = 1;
let toto = 2;
addition(toto, titi);
```

[@see high cohesion](https://en.wikipedia.org/wiki/GRASP_(object-oriented_design)#High_cohesion)




#### Portée des variables

{} crée un scope.

Les varables du scope supérieur sont accessibles au scope inférieur.

Hoisting : remontée de portée (par exemple l'utilisation d'une fonction avant qu'elle ne soit déclarée)

> nome des fonctions : action (verbe) ou question (isValid, ...)

Cohésion forte vs cohésion faible

La cohésion faible consiste à appeler les fonctions à patir d'un point unique.
La cohésion forte est l'appel d'une fonction qui appelle une autre fonction qui appelle une autre fonction......


# Dépendances 

**Visiter npm web-site**

[Materialize](https://materializecss.com/)

```bash
npm i materialize-css
```

[Material design](https://material.io/)

```bash
npm i material-design-icons
```

A chaque installation d'une librairie, modification du fichier package.json rubrique "dependencies".


## Quelle librairie ?


* Bootstrap (basé sur twitter ; mauvaise intégration sur mobile)
* Materialize (respecte le material design ; inspiré de Google) 
* Foundation (from Adobe)
* Material design lite (google) pas de doc
* Material Design Components (google + Angular)
* Bulma





## Installation de la librairie Materialize

Analyser la librairie avant.
voir la page [Materialize npm](https://www.npmjs.com/package/materialize-css).
Dessus il y a comment l'installer (taper "npm i materialize-css" dans la console) :

PS C:\Users\Administrateur\Desktop\formation-javascript\procedural> npm i materialize-css
npm notice created a lockfile as package-lock.json. You should commit this file.
npm WARN procedural@1.0.0 No repository field.

+ materialize-css@1.0.0
added 1 package from 1 contributor and audited 1 package in 0.434s
found 2 moderate severity vulnerabilities
  run `npm audit fix` to fix them, or `npm audit` for details
PS C:\Users\Administrateur\Desktop\formation-javascript\procedural>


Installer ensuite les icônes de Google. Pour voir comment on fait rechercher "npm google maerials icons"
Donc faire npm i material-design-icons sur la console


Consulter le forum [stackoverflow](https://stackoverflow.com/).


Implémenter les lignes qu'il faut dans le fichier HTML.

Tester ensuite l'installation.


>Préinstaller les librairies :
```npm install ```


** Intégration dans le code HTML
```html
  <link rel="stylesheet" type="text/css" href="./node_modules/material-design-icons/iconfont/material-icons.css" />
  <link rel="stylesheet" type="text/css" href="./node_modules/materialize-css/dist/css/materialize.css" />


  <script type="text/javascript" src="./node_modules/materialize-css/dist/js/materialize.js"></script>


```




# TIPs

> forcer la prise en compte d'un paramètre en CSS 
: mettre !important; derrière le paramètre
```cs
witdh: 60% !important;
```


> récupérer un élément affiché :

```js
const elem= document.querySelector(CSS selector)
``` 
CSS selectors : 
```js
.myClass
#myId
a
div a
```

> récupérer TOUS les éléments en fonction d'un sélecteur CSS :
```
const elem = querySelectorAll(CSS selector)
```

> Récupérer la valeur d'une touche

```js
inputCity.addEventListener("keyup", (e) =>{
    onKeyPressValid(e);
});


const onKeyPressValid = (e) =>{
 
    if (13 === e.keyCode){
        onBlurCloseSidenav();
    } else if (27 === e.keyCode) {
        const input = document.querySelector("#city_name");
        input.value = "";
        onBlurCloseSidenav();
    }

};
```




> Liste cliquable

```js

const div = document.queryselector(".city_list");
div.innerHTML = ``;
cities.forEach((value) => {
    const li = docuement.createElement(`li`);
    li.innerHtml = `<a>${value}</a>`;
    div.appendChild(li);
    li.addEventListener("click", ) => { onClic=kCity(value)});

});



# Evènements

Actions du user ou du système

User :
* MouseEvent
    * MouseOver
    * MouseClick
    * Scroll

* KeyboardEvent
    * KeyPress

* BatteryEvent

* LocationEvent

Système :
* ProgressEvent


Les balises HTML possèdent des attributs évènementiels.

>A ne pas faire !!!
```html
<input onblur="...." (instructions Javascript)>
```
Plus généralement avec "on" quelquechose (onBlur, onClick,...). 

En JavaScript : element.attribut évènementiel
```js

element.onblur = ()=>{

}

```

Jusqu'en 2008, on ne pouvait assigner qu'une seule fonction à un évènements.
Maintenant, nous pouvons en assigner plusieurs (uniquement dans le cas d'un navigateur WEB) :

```js
element.addEventListener ("type de l'évènement", fonction());
element.addEventListener ("click", function());


main.addEventListener("click", () =>{
   console.log("clicked")
});
```

# Les conditions

```js
If (condition) {
    true
} else{
    false
}

```

Opérateur ternaire

? délimite le premier opérateur, le  deuxième opérateur s'exécute si condition est vraie, délimitée par ":". Le troisième opérateur s'exécute si la condition est fausse.

```js


const toto = condition ? "true" : "false"

```



# Aller chercher des informations

Cela se fait par requêtes HTTP et on attend une réponse.

Un request est composé de :
* url
* méthod (POST(create), GET(read), PUT (update), DELETE) (Creation Retrieve, Update et Delete ou "CRUD")
* headers (entête (format) peut qualifer la langue, l'unité de calcul, etc...)
* body

format JSON : Java Script Object Notation, XML (Extensible Markup Language)

```js

const xtr = XMLHttpRequest();

xhr.open(method, url);
xhr.setRequesHeader(name, value);
xhr.send(body);


A gérer :
xhr.onlaod (réponse arrivée)
xhr.onerror (avec erreur)
xhr.onabort (quand annulé)

```


# Démarrer un serveur

Vérifier que l'on est on bon endroit (là où il y a l'index.html).
puis taper
```bash

php -S localhost:8000     (attention "S" majuscule)
```

si php non reconnu :
soit changer de terminal, soit ajouter PHP à la variable d'environnement.

taper dans la barre de recherche windows "Envir"
puis variables d'environnement puis "path" dans variables système
puis faire nouveau mettre le chemin où il y  PHP d'installé.


Ensuite taper "localhost:8000" dans la barre de navigation web.
La page est en auto-refresh.



AJAX  Asynchronous Javascript And XML.


Status de la réponse Http


1   information
2   success
3   provoque des redirections 
4   erreur logique
5   server error (erreur matérielle probable)



# La compilation JAVASCRIPT

permet d'utiliser les import / export qu'on ne peut pas utiliser nativement dans JavaScript.

Dossier dist

2 principaux frameworks : 
* Angular (google + Microsoft) utilise le compiler TypeScript
* React Vue (facebook) utilise le compiler Babel (compilation en ligne de commandes)

Ce ne sont pas de vrais compilateurs (au sens traduction en langage machine) mais plutot des agrégateurs.

Ill ya des outils qui facilitent : 
* GRUNT
* GULP
En fait, se sont des lanceurs de tâches automatiques (task runner);

Sont apparus des modules bundler (webpack par exemple)

Webpack + babelloader +  sassloader + Fileloader + BrowserSyncPlugin
