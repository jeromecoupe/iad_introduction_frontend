## Introduction au développement web front-end (HTML/CSS/JS)

Nous allons aborder ici les 3 langages principaux utilisés pour créer les pages et sites Internet que vous utilisez chaque jour.

Lorsque vous naviguez sur Internet, votre navigateur interprète du code HTML / CSS / Javascript pour générer et afficher les pages avec lesquelles vous interagissez.

_Exemple: view source sur gmail, view source sur le site de l'IAD_

A l'aide de ces trois langages et armés d'un simple éditeur de texte, vous pouvez créer des sites Internet au contenu sémantique, des mises en pages et layout complexes et une interactivité poussée. Rien de plus n'est nécessaire, vous pouvez publier pour le monde entier.

_Exemple: site webstoemp_

Chacun de ces langages possède un rôle bien particulier:

- **HTML** sert à structurer vos contenus de façon sémantique (afin qu'il ait un sens pour les machines comme pour les humains)
- **CSS** sert à créer des mises en pages (macro) et à appliquer des styles graphiques à vos éléments HTML (micro)
- **Javascript** sert à ajouter de l'interactivité (des comportements) à vos pages web (depuis de simples animations et effets jusqu'à de la géo-localisation).

Le [World Wide Web Consortium](http://www.w3.org) W3C est la structure qui créé et maintient ces langages ou standards. Tous les fabricants de navigateurs participent aux discussions et groupes de travail, avec d'autres experts venus d'autres horizons.

## HTML

HTML (pour Hypertext Markup Language) est, comme son nom l'indique, un langage de markup (servant à marquer des éléments de contenu pour leur donner une valeur sémantique) et capable de lier entre-eux divers documents par le biais de liens hypertextes.

Proposé en 1989 par [Tim Berners-Lee](https://en.wikipedia.org/wiki/Tim_Berners-Lee) et [Robert Calliau](https://en.wikipedia.org/wiki/Robert_Cailliau), le HTML était à la base destiné à permettre aux scientifiques et chercheurs du [CERN](http://home.cern/) de partager leurs documents et découvertes et faire des liens entre les documents qu'ils partageaient.

Le World Wide Web à connu une croissance fulgurante et est aujourd'hui bien plus large que le seul monde de la recherche scientifique. De simples "documents" nous sommes passés à des oeuvres d'art interactives ou à des applications en ligne. Le HTML a évolué avec le web et reste la base de tous les sites que vous utilisez.

### Structure de document: Emboitement hiérarchisé

Si vous vous penchez sur la structure de documents HTML, vous constaterez qu'ils fonctionnent à la manière de poupées russes, par emboitements hiérarchisés. Cette structure devient observable si vous utilisez des outils de développement tels que ceux présents dans tous les navigateurs modernes.

Voici un document HTML minimal:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <title>Hello Internet</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="My first HTML document">
  </head>
  <body>
    <p>Hello Internet</p>
  </body>
</html>
```

_Exercice: visualiser la structure du DOM (Document Object Model) avec les outils de développement dans Chrome (onglet elements)_

### Doctype, character encoding, langage

La première ligne du document est ce que l'on appelle le doctype. Comme le nom l'indique, cette ligne spécifie que le document est de type HTML. Cette ligne est nécessaire pour un rendu standardisé dans les différents navigateurs.

L'attribut `lang`du tag `<html>` permet de spécifier la langue dans laquelle le document est écrit. Cet attribut est particulièrement important pour le référencement ainsi que pour la synthèse vocale par exemple.

Vient ensuite le `charset` qui indique au navigateur quel est l'encodage de caractères utilisé par le document. De façon générale, le charset recommandé est "UTF-8" qui permet de gérer la plupart des caractères, y compris des caractères un peu plus exotiques pour nos yeux occidentaux (chinois, cyrillique, etc).

### <meta> viewport

Ce tag demande au navigateur d'afficher le document en considérant que la largeur de celui-ci est égale à la largeur de l'appareil utilisé, avec un niveau de zoom de 1 (pas de zoom).

### Document structure: `<head>` and `<body>`

Tout document HTML est séparé en deux parties distinctes: `<head>` et `<body>`

- `<head>`: les méta-données liées au document (title, description, langue principale, charset, feuille de styles et scripts liés, etc)
- `<body>`: les éléments de contenu du document (textes, références vers les fichiers images vidéos, son et document, canvas, tags, etc.)

_Exercice: créer un document de base "hello world" en HTML et le visualiser dans un navigateur_

### Attributs et tags

Outre le contenu texte lui même, un fichier html est composé de tags et d'attributs. Ceux-ci définissent les rôles et les attributs des éléments de contenu qui composent le fichier.

#### Tags

Les tags définissent le rôle des éléments qui composent la page. Par exemple, certains mots d'un texte peuvent devenir un lien hypertextes ou encore former un titre.

```html
<p>
  Lorem ipsum dolor sit amet, consectetur adipisicing elit. Impedit voluptates
  et deserunt, recusandae obcaecati culpa in aperiam. Non libero, fuga eligendi
  labore voluptate voluptatum totam itaque accusantium mollitia quasi! Sit.
</p>
```

```html
<h1>Voici un magnifique titre de niveau 1</h1>
```

Nous verrons quelques-uns des tags principaux lors de cette introduction. [Pour une liste exhaustive, je vous recommande Mozilla Developer Network](https://developer.mozilla.org/fr/docs/Web/HTML/Element).

##### Tags pairs et self closing tags

La plupart des tags HTML fonctionnent par paires et entourent leur contenu.

```html
<p>
  Un paragraphe avec un peu de texte sur lequel nous voulons
  <strong>attirer l'attention</strong>
</p>
<a href="http://www.webstoemp.com">Delicious websites from Brussels</a>
```

Cependant, il existe des tags qui fonctionnent seuls. Bien souvent il s'agit de tags n'ayant pas de contenu textuel.

```html
<meta charset="utf-8">
```

```html
<img src="images/monimage.png">
```

```html
<input type="text">
```

```html
<link rel="stylesheet" href="css/screen.css" media="screen">
```

#### Attributs

Les attributs sont liés aux tags et précisent certains aspects de ceux-ci. Voici deux exemples liés aux liens.

- L'attribut `href` d'un lien renseigne l'URL vers laquelle ce lien établi une connexion.
- Son attribut `title` fourni une description complémentaire au texte de ce lien.

```html
<a href="http://www.monsite.com/mon-dernier-blogpost.html" title="Tout ce qu'il faut savoir sur être professeur à l'IAD">En savoir plus</a>
```

#### Bonnes pratiques

HTML est un langage assez pragmatique et qui "pardonne" beaucoup d'erreurs de syntaxe et de style. Néanmoins, il est important de suivre certaines règles. Lorsque vous débutez, valider votre code peut s'avérer intéressant.

Outre cette validation, voici une série de bonnes pratiques qui rendront votre code plus lisible.

##### Bonne imbrication et fermeture des tags

Vos tags doivent être bien imbriqués. Les ouvertures et les fermetures de tags doivent se faire niveau par niveau ainsi que dans le bon ordre.

**Incorrect**

```html
<p>Lorem ipsum dolor sit amet, consectetur <a href="fake.html">adipisicing elit</p></a>.
```

**Correct**

```html
<p>Lorem ipsum dolor sit amet, consectetur <a href="fake.html">adipisicing elit</a>.</p>
```

##### Utiliser des minuscules partout

Bien que des majuscules soient valides en HTML, votre code sera plus lisible si vous tags et attributs sont écrits en minuscules.

**Pas terrible**

```html
<p>Mon paragraphe contenant <a href="https://www.iad-arts.be">un lien hypertexte</a></p>
```

**Mieux**

```html
<p>Mon paragraphe contenant <a href="https://www.iad-arts.be">un lien hypertexte</a></p>
```

##### Toujours placer vos attributs entre guillemets

Encore une fois, HTML ne vous y oblige pas mais placer les valeurs de vos attributs entre guillemets augmente grandement la lisibilité de votre code HTML.

**Pas terrible**

```html
<p>Un paragraphe contenant <a href=https://www.iad-arts.be>un lien hypertexte</a></p>
```

**Mieux**

```html
<p>Un paragraphe contenant <a href="https://www.iad-arts.be">un lien hypertexte</a></p>
```

##### Gestion des caractères spéciaux dans les déclarations CSS et JavaScript

La meilleure solution consiste à placer tout votre code CSS ou de JavaScript dans des fichiers externes et pas dans votre fichier HTML.

##### Encodage des caractères "&" dans les URLs

Le validateur HTML générera une erreur lorsque un caractère "&" n'est pas encodé dans une URL. Veillez donc à y remédier en encodant cette dernière.

Invalide:

```html
<a href="index.php?a=1&b=2">Latest News</a>
```

Valide:

```html
<a href="index.php?a=1&amp;b=2">Latest News</a>
```

_Exercice: créer une version texte d'un CV minimaliste: nom, prénom, adresse, quelques paragraphes_

### Différents types de tags

En HTML, la plupart des tags sont soit des tags de type "block", soit des tags de type "inline". En fait ces tags se distinguent principalement au niveau de leurs modes d'affichage. Il existe d'autres types de tags mais ce sont les deux principaux.

#### Tags de type "block"

[Les tags de type "block"](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements) sont principalement utilisés pour marquer des blocs de contenu relativement importants dans vos documents. Un exemple type de ce genre de tags est le paragraphe `<p>`

Les éléments de type "block":

- sont affichés sur une nouvelle ligne
- prennent toute la place disponible en largeur dans leur bloc conteneur
- peuvent contenir d'autres éléments de type block ou "inline"

Exemples:

`<p>`: utilisé pour marquer un paragraphe

```html
<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Iusto assumenda quam illum ducimus. Odio reiciendis eligendi, repellendus beatae, tempora laboriosam suscipit quam velit! Culpa sunt commodi animi, ullam temporibus. Inventore.</p>
```

`<h1>` > `<h6>`: utilisé pour marquer les niveau de titres (il n'y à que six niveaux de titres en HTML)

```html
<h1>Level one title</h1>
<h2>Level two title</h2>
...
<h6>Level six title</h6>
```

`<ul>` et `<ol>`: utilisés pour marquer des listes (en conjonction avec `<li>`)

Les listes non ordonnées ou listes à puces avec `<ul>`

```html
<ul>
  <li>farine</li>
  <li>oeufs</li>
  <li>sucre</li>
  <li>lait</li>
</ul>
```

Les listes ordonnées ou numérotées avec `<ol>`

```html
<ol>
  <li>premier élément</li>
  <li>deuxième élément</li>
  <li>troisième élément</li>
</ol>
```

`<blockquote>`: utilisé pour marquer les citations (en conjonction avec `<cite>`)

```html
<blockquote>
  <p>If you don't know where you are going, any road will get you there.</p>
  <footer>
    <cite>Lewis Caroll</cite>
  </footer>
</blockquote>
```

_Exercice: ajouter quelques paragraphes, listes et titres à votre document de travail_

#### Tags de type "inline"

L'autre grande famille d'éléments sont les éléments de type "inline". Ils sont utilisés pour marquer des ensembles de contenus plus petits dans vos documents. Deux semples types sont les tags `<em>` et `<strong>` utilisé pour marquer certains éléments importants.

Les éléments de type "inline":

- ne commencent pas sur une nouvelle ligne
- sont d'une largeur égale à leur contenu
- peuvent contenir d'autres éléments de type "inline" mais ne peuvent pas contenir d'élément de type "block"

`<img>`: utilisé pour référencer les images et que nous verrons plus poins dans notre chapitre consacré aux media.

`<em>`: utilisé pour mettre de l'emphase dans un texte. Est affiché par défaut affiché en italique par les navigateurs.

```html
<p><em>J'adore</em> vraiment Bruxelles</p>
```

`<strong>`: utilisé pour insister sur l'importance d'un élément dans un texte. Est par défaut affiché en gras par les navigateurs

```html
<p><strong>Attention</strong> aux chutes de pierres</p>
```

`<sup>` et `<sub>`: utilisés pour mettre du texte en exposant ou en indice

```html
<p>La formule chimique de l'eau est H<sub>2</sub>O</p>
```

```html
<p>La superficie de la Belgique est de 30 528 km<sup>2</sup></p>
```

Nous ne les aborderons pas cette année, mais pas mal d'éléments servant à construire des formulaires en HTML sont également de type "inline". C'est le cas des éléments `<button>`, `<input>`, `<label>`, `<select>` et `<textarea>` par exemple.

_Exercice: ajouter quelques tags `<strong>` et `<em>` à votre document de travail avant de le visualiser dans un navigateur._

### Element de type table

`<table>`: utilisé pour marquer les tableaux (en conjonction avec `<th>`, `<tr>`, `<td>`,)

```html
<table>
  <tr>
    <th>Name</th>
    <th>Rank</th>
    <th>Mood</th>
  </tr>
  <tr>
    <td>Yoda</td>
    <td>Jedi master</td>
    <td>Worried</td>
  </tr>
  <tr>
    <td>Darth Vador</td>
    <td>Sith Lord</td>
    <td>Implacable</td>
  </tr>
  <tr>
    <td>Luke Skywalker</td>
    <td>Jedi Knight</td>
    <td>Impatient</td>
  </tr>
</table>
```

### Les liens `<a>`

L'un des éléments les plus important du langage HTML, le lien, est lui aussi un élément de type inline. Cet élément `<a>` permet de créer des liens entre différents documents HTML, avec une adresse email ou encore avec des fichiers d'autres types (PDF, Images, etc.).

Pour transformer du texte ou une image en un lien, il suffit d'utiliser le tag `<a>`:

```html
<p><a href="http://en.wikipedia.org/wiki/Brussels">Bruxelles</a> est la capitale de la Belgique et de l'Europe.</p>
```

#### Liens relatifs et absolus

Ce lien est "absolu" dans la mesure où son attribut `href` référence une URL complète, qui peut être résolue indépendamment de son contexte.

```html
<a href="index.html"><img src="img/logo.png" alt="webstoemp"></a>
```

Ce lien est "relatif" dans la mesure où son attribut `href` référence une URL relative au contexte du document établissant le lien. Par exemple, si le domaine est *www.webstoemp.com*, le navigateur interprètera ce lien comme *http://www.webstoemp.com/index.html*.

#### Liens vers adresses email

```html
<a href="mailto:jercoupe@gmail.com">Contacter Jérôme Coupé</a>
```

Les liens peuvent également renvoyer vers une adresse email, il suffit que cette dernière soit précédée de `mailto:`.

#### Ancres

Il est également possible d'établir des liens vers d'autres parties d'un même document, par exemple pour renvoyer les utilisateurs en haut de page ou vers une section bien définie dans un document très long.

```html
<h1 id="top">Titre de la page</h1>
... beaucoup de contenu ...
<a href="#top">Retour en haut de page</a>
```

_Exercice: expérimenter avec les liens et les ancres dans votre document de travail_

### Divisions avec `<div>` et `<span>`

Le tag `<div>` est un tags de type "block" utilisé pour créer des division dans les documents. Ces divisions n'ont aucune valeur sémantique et sont principalement utilisées pour des raisons stylistiques et pour appliquer une mise en page et des styles CSS à ces éléments.

Avant l'avènement de HTML5 et des nouveaux tags sémantiques que nous allons voir ci-dessous, le tag `<div>` était utilisé partout pour grouper des éléments, les mettre en page et réaliser des layouts. `<div>` est encore utilisé comme cela de nos jours mais HTML5 nous propose maintenant quelques éléments dont la valeur sémantique est plus importante et qui peuvent avantageusement le remplacer dans certains cas.

Le tag `<span>` peut être vu comme l'équivalent "inline" du `<div>`, permettant de créer des groupes plus petits auxquels des styles peuvent être appliqués. `<span>`est également neutre, avec une valeur sémantique proche de zéro.

### Un peu plus de sémantique

HTML comprend également quelques éléments sémantiques visant à permettre une meilleure définition des contenus des pages Internet.

#### `<nav>`

Cet élément est utilisé pour marquer les interfaces de navigation du site ou de la page. Il s’agit d’une section de la page contenant les liens utilisés pour la navigation. Tous les groupes de liens ne sont pas forcément des interfaces de navigation, seuls ces derniers peuvent être marqués à l’aide de l’élément `<nav>`.

#### `<article>`

Est utilisé pour marquer une partie d'un document, d'une page, d'un site qui fait sens prise indépendamment: un post sur un forum, un article de magazine ou de journal, un billet sur un blog, un commentaire soumis par un utilisateur ou n'importe quel autre élément de contenu indépendant. Une bonne question à se poser pour l’utilisation d’article est: pourriez vous inclure ce contenu dans un flux RSS (ou un mur Facebook). Ce contenu ferait-il sens pris isolément? Si oui, il s’agit probablement d’un bon candidat.

##### `<section>`

Section générique d'un document ou d'une application. Section sert à marquer un groupement thématique de contenus, typiquement il comporte un `<header>` et parfois un `<footer>`. Exemples: les chapitres d'un livre, les sections d'une thèse, les différentes sections d'une page d'accueil: introduction, news, portfolio, information de contact, etc. Attention à ne pas utiliser section en lieu et place de `<div>` ou `<article>`, par exemple pour séparer le contenu principal d'une page de son contenu secondaire. A part de rares exceptions, n'utilisez pas `<section>` si cet élément ne possède pas naturellement un titre. [Un article détaillé sur le sujet est disponible sur HTML5 Doctor](http://html5doctor.com/the-section-element/).

##### `<aside>`

Est utilisé pour marquer du contenu qui est lié de façon indirecte au parent de l'élément `<aside>`. Une bonne question à se poser pour l’utilisation de ce élément: pourriez-vous le supprimer du document sans que celui-ci perde un aspect important de son contenu.

##### `<main>`

L’élément `<main>` représente le contenu principal d’un document. Il ne peut être utilisé qu’une seule fois au sein d’un document HTML et ne peut jamais être le descendant de `<article>`, `<aside>`, `<footer>`, `<header>` ou `<nav>`.

##### `<header>`

Typiquement utilisé pour contenir les métas informations (titre, logo, date de publication, etc) d’un document ou d’une partie d’un document. L'élément `<header>` peut être utilisé plusieurs fois dans le cadre d'un même document. Suivant le contexte dans lequel il est placé (`<body>`, `<article>`, `<section>`, etc.) il aura un statut différent.

##### `<footer>`

Typiquement utilisé pour contenir les métas informations (auteur, lien vers des documents liés) d’un document ou d’une partie de document. L'élément `<footer>` peut être utilisé plusieurs fois dans le cadre d'un même document. Suivant le contexte dans lequel il est placé (`<body>`, `<article>`, `<section>`, etc.) il aura un statut différent. Notons que les coordonnées de contact mentionnées dans un `<footer>` devraient êtres marqués à l'aide de l'élément `<address>`

##### `<time>`

Est utilisé pour marquer des données temporelles (dates, heures etc.) de façon à ce qu'elles soient lisibles et exploitables par des machines ou programmes. Un attribut `datetime` peut également être ajouté afin de préciser les choses si le texte marqué n'est pas une date grégorienne valide.

```html
<time datetime="2007-10-05">5 Octobre</time>
<p>I usually have a snack at <time datetime="2019-05-15T16:00">16:00</time>.</p>
<p>posted on <time datetime="2009-04-12">12 April 2009</time> by Jérôme Coupé</p>
```

### Media

Les media tels que les images, les vidéos ou les fichiers audio ne sont pas inclus mais seulement référencés dans les documents HTML.

#### Images

Nous avons déjà parlé des images en HTML. Celles-ci sont référencées dans les documents HTML via le tag `<img>`qui est un tag "self closing" et pas une paire.

L'image a intégrer est renseignée via l'attribut `src` qui est obligatoire et renseigne l'URL de l'image (celle-ci peut être renseignée de façon relative ou absolue). HTML supporte différents formats d'images. Voici le plus utilisés: JPEG, GIF, PNG et SVG.

La taille de l'image peut être spécifiée à l'aide des attributs `width` et `height`. Si ceux-ci ne sont pas spécifiés, l'image sera affichée à sa taille effective. L'attribut `alt` est utilisé pour donner une représentation textuelle de l'image aux navigateurs qui ne les supportent pas.

```html
<img src="img/apple_watch.jpg" alt="apple watch modèle sport" width="200" height="355">
```

Il existe encore bien d'autres attributs, dont certains sont très utiles dans le cadre du responsive web design mais vous connaissez maintenant les principaux d'entre eux.

Les tags `<figure>` et `<figcaption>` peuvent être utilisés pour ajouter une légende à vos images, vos graphiques, etc.

```html
<figure>
  <img src="img/apple_watch.jpg" alt="apple watch modèle sport" width="200" height="355">
  <figcaption>
    <p>L'Apple watch, annoncée le 9 Septembre 2014 par Apple</p>
  </figcaption>
</figure>
```

#### Vidéo et Audio

HTML permet également d'intégrer facilement des fichiers audio ou vidéo à vos documents, et ce à l'aide de tags nommés (de façon fort surprenante) `<video>` et `<audio>`.

##### Vidéo

Voici le tag `<video>` dans son utilisation la plus simple:

```html
<video src="videos/videofile.mp4" poster="posterimage.jpg" controls>
  <p>Votre navigateur ne supporte pas les vidéos intégrées. Vous pouvez néanmoins <a href="videos/videofile.mp4">télécharger la vidéo</a> et utiliser votre lecteur préféré.</p>
</video>
```

L'attribut `poster` sert à spécifier une image d'attente pour la vidéo. [Mozilla Developer Network](https://developer.mozilla.org/fr/docs/Web/HTML/Element/video) vous donnera des informations exhaustives sur l'élément `<video>` et son utilisation en HTML5.

Le problème est que les différents navigateurs ne supportent pas tous les mêmes formats vidéo. Il vous faudra donc spécifier différents fichiers pour les différents navigateurs et utiliser l'élément `<source>`.

```html
<video poster="posterimage.jpg" controls>
  <source src="videos/videofile.webm" type="video/webm">
  <source src="videos/videofile.mp4" type="video/mp4">
  <p>Votre navigateur ne supporte pas les vidéos intégrées. Vous pouvez néanmoins télécharger la vidéo en format <a href="videos/videofile.webm">WebM</a> ou <a href="videos/videofile.mp4">MP4</a>.</p>
</video>
```

##### Audio

Voici le tag `<audio>` dans son utilisation la plus simple:

```html
<audio src="audios/audiofile.mp3" controls>
  <p>Votre navigateur ne supporte pas les fichiers audio intégrées. Vous pouvez néanmoins <a href="audios/audiofile.mp3">télécharger le fichier audio</a> et utiliser votre lecteur préféré.</p>
</audio>
```

En utilisant différents formats et l'élément `<source>`:

```html
<audio controls>
  <source src="audios/audiofile.mp3" type="audio/mpeg">
  <source src="audios/audiofile.ogg" type="audio/ogg">
  <p>Votre navigateur ne supporte pas les fichiers audio intégrés. Vous pouvez néanmoins télécharger le fichier audio en format <a href="audios/audiofile.mp3">MP3</a> ou <a href="audios/audiofile.ogg">OGG</a> et utiliser votre lecteur préféré.</p>
</audio>
```

### Formulaires

Les formulaires forment une partie importante des applications web. La balise `<form>` indique le début d'un formulaire. Les deux attributs les plus couramment utilisés sont `action` (l'URI du programme qui traitera les informations entrées dans le formulaire) et `method` qui spécifie si ces données sont envoyées dans l'URL (valeur `get`) ou si elles sont inclues dans le corps du formulaire et envoyées au serveur (valeur `post`).

Voici un [petit guide sur MDN sur l'utilisation des formulaires](https://developer.mozilla.org/fr/docs/Web/Guide/HTML/Formulaires). Il existe de nombreux types de champs et d'attributs qui y sont liés. Les plus courants sont les balises `<label>` ([labels](https://developer.mozilla.org/fr/docs/Web/HTML/Element/label) d'un champ de formulaire) et `<input>` ([champs](https://developer.mozilla.org/fr/docs/Web/HTML/Element/input)).

Pour lier un label à un champ de formulaire, le label doit posséder un attribut `for` dont la valeur doit être identique à celle de l'attribut `id` du champ.

Voici un formulaire de base.

```html
<form action="register.php" method="post">
  <div>
    <legend for="userName">Name *</legend>
    <input type="text" name="user-name" id="userName" required>
  </div>
  <div>
    <legend for="userEmail">Email *</legend>
    <input type="email" name="user-email" id="userEmail" required>
  </div>
  <div>
    <input type="submit" value="Send">
  </div>
</form>
```

### Scripts

Avec des sites de plus en plus orientés vers des applications et interactifs, JavaScript est une part importante du web actuel.

Les scripts javascripts sont habituellement des fichiers chargés par le document HTML comme le sont les images, les fichiers CSS et autres assets. Tout comme les CSS, les scripts peuvent être placés directement dans le code HTML. Tout comme avec vos styles CSS, la bonne pratique est de plutôt charger un fichier externe.

Généralement, la balise `<script>` est placée juste avant le tag de fin de `</body>`dans un document HTML afin que les scripts soient chargés après le reste du document HTML (ce qui permet au script de manipuler des éléments du DOM) et que le chargement des scripts ne bloquent pas le rendu de la page.

```html
<script src="js/main.min.js"></script>
```

### Exercice: création d'un document de base

Essayons de créer ensemble un document plus élaboré et sémantiquement correct. Je vous propose ici de créer votre CV en HTML.

_Exercice: créer un CV complet en HTML: commencer par écrire votre contenu et ajoutez ensuite les tags HTML._

## CSS

Le langage CSS (Cascading Style Sheets) est un langage utilisé pour mettre en page et attacher des styles graphiques à vos documents HTML. Nous verrons ici les bases de CSS et réservons les réalisation de layout complexes, d'animations et de sites responsives aux cours suivants.

Les navigateurs possèdent une CSS par défaut. Lorsque vous visualisez un document HTML dans votre navigateur, cette CSS par défaut est appliquée. Nous allons voir ensemble comment écrire la nôtre.

### Lier CSS et HTML

Il existe plusieurs façons de lires des styles CSS à vos documents HTML. Nous allons ici nous concentrer sur la plus utilisées d'entre-elles: l'élément `<link>` et l'attribut `media`.

```html
<link rel="stylesheet" href="css/screen.css" media="screen">
```

Cette simple ligne de code va lier un fichier CSS (screen.css) à votre document HTML. L'attribut `media` spécifie pour quels media les styles devront êtres appliqués. Il existe de nombreuses valeurs possibles pour cet attribut mais les deux plus utilisés sont `screen` et `print`.

- `screen`: les styles seront uniquement appliqués si le document HTML est visualisé sur un écran.
- `print`: les styles ne seront appliqués que si vous imprimez le document HTML.

_Exercice: créer une feuille de style externe (css/screen.css) et la lier à votre document HTML de travail_

_Exercice: expérimenter avec l'attribut media et les valeurs screen et print_

### Sélecteurs, propriétés, valeurs

Les règles CSS sont composées de sélecteurs, de propriétés et de valeurs.

- **sélecteur**: permet, comme son nom l'indique, de sélectionner les éléments auxquels les styles vont s'appliquer. Comme nous le verrons plus loin, il existe différents types de sélecteurs.
- **propriété**: permet de spécifier les propriétés dont il faut modifier les valeurs pour les éléments visés par le sélecteur
- **valeurs**: permet de spécifier les valeurs à appliquer aux propriétés des éléments visés par le sélecteur

_Exercice: changer la couleur de fond de votre page_

```css
body {
  background-color: red;
}
```

```css
body {
  background-color: red;
  color: blue;
}
```

Il existe différents types de sélecteurs CSS, nous en verrons quelques exemple simples lors de cette introduction. Pour ce qui est des propriétés et des valeurs, nous en aborderons quelques unes lors de cette introduction également, mais seulement un petit nombre. Pour une [référence complète des propriétés CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference), vous pouvez vous référer à Mozilla Developer Network ou encore à [Codrops](http://tympanus.net/codrops/css_reference/).

#### Sélecteurs de type

Les sélecteurs les plus simples à comprendre sont les sélecteurs de type. Ces sélecteurs permettent de cibler tous les éléments d'un certain type présents dans le document HTML. Tout élément HTML peut donc être ciblé par un sélecteur de type.

```css
body {
  background: red;
}
```

```css
p {
  color: blue;
}
```

#### Sélecteurs de classes

Les sélecteurs de classes sont le moyen le plus répandu d'appliquer des styles à un ou plusieurs éléments HTML. Il suffit d'ajouter un attribut `class` à n'importe quel éléments dans votre code HTML et d'ensuite cibler les éléments possédant cet attribut à l'aide d'un sélecteur de classe. Ces sélecteurs s'écrivent avec un "." devant le nom de la classe visée: `.maclasse`.

```html
<div class="message">
  <p>Voici un message</p>
  <p>Comportant plusieurs paragraphes</p>
</div>
```

```css
.message {
  border: 1px solid #cacaca;
  background-color: #e4e4e4;
}
```

Les sélecteurs de classes sont parmi les plus répandus dans la mesure où les classes:

- rendent vos styles CSS indépendants de la structure de votre HTML
- peuvent être réutilisées au sein d'un document
- peuvent être combinées de manière efficace
- ont une spécificité basse

```html
<div class="message message-warning">
  <p>Voici un message</p>
  <p>Comportant plusieurs paragraphes</p>
</div>
```

```css
.message {
  border: 1px solid #cacaca;
  background-color: #e4e4e4;
}

.message-warning {
  border-color: #d35400;
  background-color: #f1eae6;
}
```

#### Sélecteurs d'ID

Ces sélecteurs permettent de sélectionner des éléments en fonction de leurs attributs ID. Ces sélecteurs s'écrivent avec un "#" devant le nom de la classe visée: `#monid`.

```html
<div id="sitefooter">
  <p>&copy; Jérôme Coupé - la casa productions</p>
</div>
```

```css
#sitefooter {
  background: #242424;
  color: #f9f9f9;
}
```

##### Différence entre classes et ids

- une `id` ne peut être utilisée qu'une et une seule fois par document HTML. Les `id` ne sont donc pas idéales pour créer des systèmes de composants réutilisables.
- nous verrons plus loin qu'une `id` possède une spécificité très élevée. Elles ne sont donc pas idéales pour créer un système d'éléments combinables.

La bonne pratique est d'utiliser des sélecteurs dont la spécificité est aussi basse que possible. Certains développeurs recommandent de suivre une règle simple: ne jamais utiliser d'ID comme hooks pour vos styles CSS.

Les sélecteurs d'ID existent, mais ma recommandation est de ne pas les utiliser en CSS dans la mesure du possible.

#### Sélecteurs descendants

Les sélecteurs descendants permettent de rendre vos sélecteurs plus spécifiques en prenant en compte leur contexte. Ces sélecteurs s'écrivent en combinant plusieurs sélecteurs avec un espace.

```html
<nav>
  <ul class="mainnav">
    <li><a href="index.html">Home</a></li>
    <li><a href="work.html">Work</a></li>
    <li><a href="blog.html">Blog</a></li>
    <li><a href="about.html">About</a></li>
  </ul>
</nav>
```

```css
.mainnav a {
  color: red;
}
```

Les sélecteurs se lisent de droite à gauche. Celui-ci peut donc se traduire en français par: sélectionner tous les liens qui sont des descendants de `.mainnav`, à n'importe quel niveau dans l'arbre du document.

#### Sélecteurs chainés

Les sélecteurs peuvent également être chainés pour ne cibler que les éléments auxquels plusieurs classes sont appliquées.
Le sélecteur suivant ne ciblera que les éléments auxquels à la fois les classes `one` et `two` sont appliquées.

```css
.one.two {
  color: red;
}
```

#### Sélecteurs d'enfants

Les sélecteurs d'enfants permettent de rendre vos sélecteurs encore plus spécifiques. Ces sélecteurs s'écrivent en combinant plusieurs sélecteurs avec un `>`.

```html
<nav>
  <ul class="mainnav">
    <li><a href="index.html">Home</a></li>
    <li><a href="work.html">Work</a></li>
    <li><a href="blog.html">Blog</a></li>
    <li><a href="about.html">About</a></li>
  </ul>
</nav>
```

```css
.mainnav > li {
  color: red;
}
```

Les sélecteurs se lisent de droite à gauche. Celui-ci peut donc se traduire en français par: sélectionner tous les `li` qui sont des enfants directs de `.mainnav`.

#### Liens et pseudo-classes

Certains [sélecteurs de la famille des pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes) permettent de cibler les différents états de vos liens.

```css
a:link {
  text-decoration: underline;
}

a:visited {
  color: purple;
}

a:hover {
  text-decoration: none;
}

a:focus {
  color: green;
}

a:active {
  color: red;
}
```

_Exercice: expérimenter avec les pseudo-classes liées aux liens dans votre document de travail_

#### Autres sélecteurs

Il existe bien d'autres sélecteurs que vous pouvez utiliser dans le cadre de vos CSS.

Vous pouvez vous faire une idée de la diversité des sélecteurs CSS en consultant les spécifications du W3C ([CSS 2.1](http://www.w3.org/TR/CSS2/selector.html) and [Selectors Level 3](http://www.w3.org/TR/css3-selectors/)) ou [cette référence de Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference). 30 sélecteurs parmi les plus utilisés sont expliqués dans [cet article sur Nettuts](http://code.tutsplus.com/tutorials/the-30-css-selectors-you-must-memorize--net-16048).

Nous aborderons et utiliserons un grand nombre de sélecteurs CSS en détail l'année prochaine et dans la suite de votre cursus.

#### Grouper les sélecteurs

Il est important de noter que, dans le cadre de vos fichiers CSS, vous pouvez appliquer les mêmes propriétés et valeurs à des sélecteurs différents en séparant ces derniers par une virgule. C'est une manière de ne pas vous répéter dans vos fichiers CSS en groupant vos sélecteurs.

```css
.message,
.infobox {
  border: 1px solide #ccc;
  background: #e6e6e6;
}
```

Cela veut simplement dire que les mêmes règles CSSs seront appliquées aux éléments auxquels la classe `message` est appliquée, et également aux éléments auxquels la classe `infobox` est appliquée.

Les espaces sont importants dans les sélecteurs.

```css
.one .two {
  /* règles CSS */
}
```

Est un sélecteur descendant qui cible les éléments de classes `two` qui sont les descendants (à n'importe quel degré dans le DOM) des éléments de classe `one`.

Tandis que

```css
.one.two {
  /* règles CSS */
}
```

Est un sélecteur de classes chaînées qui cible les éléments auxquels sont appliquées à la fois les classes `.one` et `.two`

### Cascade et Spécificité

Cascade et spécificité sont les deux mécanismes par lesquels un navigateur décide quels styles doivent être appliqués en cas de conflit.

#### Cascade

Les règles CSS s'appliquent en cascade, en commençant pas les règles spécifiées en début de fichier et en terminant par les dernières. En cas de conflit, le navigateur applique la dernière règle spécifiée dans le document.

```css
body {
  color: red;
  color: green;
}
```

```css
p {
  background: red;
}

p {
  background: green;
}
```

#### Spécificité

Le calcul de la spécificité prend le pas sur la cascade. Vos sélecteurs les plus spécifiques prendront le pas sur les sélecteurs les moins spécifiques, quel que soit l'ordre de la cascade.

```css
body p {
  background: green;
}

p {
  background: red;
}
```

La règle de base est que plus votre sélecteur à l'air complexe, plus sa spécificité sera grande. Le calcul de spécificité se fait en réalité de façon un peu plus complexe:

A-B-C

- A: Nombre d’ID référencées dans le sélecteur
- B: Nombre de classes et de pseudo-classes référencées dans le sélecteur
- C: Nombre d’éléments référencés dans le sélecteur
- Ne pas tenir compte des pseudo éléments.

La spécificité n'est pas spécifiée en base 10. Un sélecteur avec une spécifié de 1-0-0 l'emportera toujours sur un élément dont la spécificité est 0-3-0 et ce dernier l'emporte sur un sélecteur dont la spécificité est 0-0-6. Andrew Clarke nous propose [une analogie avec Star Wars](http://www.stuffandnonsense.co.uk/archives/css_specificity_wars.html) qui vous aidera à comprendre les choses.

```css
body > a:hover
```

La spécificité de ce sélecteur est de 0-1-2.

_Exercice: déterminer la spécificité de divers sélecteurs_

#### Poids

Une directive `!important` permet de passer outre la spécificité. A utiliser le moins possible en production.

```css
body p {
  background: green;
}

p {
  background: red !important;
}
```

### Modèles de boites avec width, height, border, padding et margin

Chaque élément en HTML génère une boite. Ces boites ont différentes caractéristiques et sont de différents types suivant l'élément utilisé (`block`, `inline`, `inline-block`, etc.).

Les dimensions de ces boites peuvent être spécifiées à l'aide des propriétés `width`, `height`, `border`, `padding` et `margin`.

A l'aide des différentes valeurs spécifiées, les navigateurs calculent la taille de toutes ces boites à l'écran. [C'est ce que l'on appelle le Box Model en CSS](https://developer.mozilla.org/fr/docs/Apprendre/CSS/Building_blocks/Le_modele_de_boite#Le_Mod%C3%A8le_Standard_de_Bo%C3%AEte_CSS) qui est affiché dans les outils de dévelopement de votre navigateur.

- Par défaut, la largeur totale d’une boîte se calcule de la façon suivante : largeur du contenu (width) + padding + borders + margin.
- Par défaut, la hauteur totale d’une boîte se calcule de la façon suivante : hauteur du contenu (height) + padding + borders + margin.

Il est posible de modifier le box model à l'aide de la propriété `box-sizing`. Par exemple, `box-sizing: border-box;` modifie le Box Model afin que les dimensions spécifiées pour padding et border soient includes dans `width` et `height`.

Les dimensions de ces boites peuvent être spécifiées avec des unités absolues (`px` par exemple) ou relatives (`%`, `rem`, `em`, `vh`, `vw`, `ch` etc.).

`width` et `height` exprimées en pourcentages sont toujours relatives au block conteneur de la boite visée. Par exemple, un `<div>` ayant une largeur de 50% placé dans un `<div>` ayant lui même une largeur de 50% ne fera que 25% de la largeur totale de la page.

`margin` et `padding` exprimés en pourcentages sont toujours calculées par rapport à la largeur (`width`) de leur élément parent.

Les propriétés `width`et `height` ne prennent qu'une seule valeur.

```css
.content-primary {
  width: 66%;
}

.content-primary {
  width: 750px;
}
```

La propriété `border`peut soit être spécifiée en une seule propriété courte, soit décomposées en différentes propriétés distinctes: `border-width`, `border-style`, `border-color`.

Il est également possible de spécifier les caractéristiques de chaque border individuellement en utilisant les propriétés: `border-top`, `border-bottom`, `border-left`, `border-right`,

```css
body {
  margin: 0;
  padding: 0;
  border: 1em solid red;
}

body {
  border-top: 3px double aqua;
}
```

Les propriétés `margin` et `padding` sont spécifiées à l'aide 4 valeurs distinctes. Ces valeurs correspondent à chacun des côtés de la boite, en commençant par le haut et dans l'ordre des aiguilles d'une montre (top, right, bottom, left).

Si des valeurs sont manquantes, le navigateur les complètes automatiquement en doublant les valeurs deux par deux (top et bottom, left et right). Ces propriétés courtes peuvent également être spécifiées séparément à l'aide de `padding-top`, `padding-bottom`, `padding-left`, `padding-right`, `margin-top`, `margin-bottom`, `margin-left` et `margin-right`.

```css
body {
  margin: 0;
}

.myclass {
  padding: 2em 0;
  /* same as padding: 2em 0 2em 0 */
}

.myclass {
  padding-top: 5%;
}

.myclass {
  margin: 2em 0 1em;
  /* same as margin: 2em 0 1em 0 */
}

.myclass {
  margin-left: 1em;
  margin-bottom: 1em;
}

.myclass {
  padding-right: 20px;
  padding-left: 1em;
  padding-bottom: 2em;
}
```

Des marges latérales automatiques combinées à une largeur (`width`) spécifiée sont également utilisées comme moyen simple de centrer un bloc dans une page.

```css
.mypage {
  width: 80%;
  margin: 0 auto;
}
```

### Couleurs

#### propriétés color et background

Les propriétés `color` et `background` vous permettent de changer les couleurs de vos textes ou les fonds appliqués à vos boites.

```css
body {
  magin: 0;
  padding: 2em;
  background: #f0f0f0;
  color: #171717;
  border: 1em solid #d35400;
}
```

#### Différentes façons de spécifier des couleurs

Il existe [différentes façons de spécifier les couleurs en CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value): mots-clef, notation hexadécimale, notation rgb, notation rgba sont certaines d'entre elles. La notation rgba se distingue des autres dans la mesure où elle vous permet de spécifier l'opacité d'une couleur.

```css
.myclass {
  color: red;
}

.myclass {
  color: #ff0000;
}

.myclass {
  color: rgb(255, 0, 0);
}

.myclass {
  color: rgba(255, 0, 0, 0.5);
}
```

La plupart des programmes de design vous permettent de facilement trouver et convertir les valeurs correspondant aux couleurs que vous souhaitez utiliser.

#### Utilisation d'images de background

Il est également possible d'utiliser des images comme fonds pour vos boites. Vous devez pour cela utiliser les propriétés suivantes:

- `background-image:url(../img/monimage.png)` pour spécifier l'image à utiliser comme image de fond.
- `background-position:50% 50%` pour spécifier la position de l'image dans la boite visée. Vous pouvez soit utiliser des unités (pourcentages, pixels, em, rem, etc.) soit des mots-clefs comme `top`, `bottom`, `left` et `right`.
- `background-repeat:no-repeat` pour spécifier si l'image va se répéter et comment. Les valeurs possibles sont `no-repeat`, `repeat`, `repeat-x` et `repeat-y`.
- `background-size` spécifie comment le navigateur doit traiter l'image par rapport au bloc dans lequel elle se trouve. Les valeurs les plus simples à comprendre sont `cover` et `contain`. `cover` spécifie que l'entièreté du bloc conteneur doit être couverte par l'image. `contain` spécifie que l'ensemble de l'image doit toujours être affichée dans les limites du bloc conteneur. Dans les deux cas, l'image sera resizée par le navigateur pour se conformer aux directives reçues.

Tout cela peut être géré via la propriété courte `background` dont vous trouverez une [explication complète sur MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/background).

```css
.banner {
  background: #cccccc url(../image/framboises.jpg) 50% 50% / cover no-repeat;
}
```

#### Dégradés en CSS

En CSS, les [dégradés](https://css-tricks.com/css3-gradients/) se gèrent via la propriété `background-image`. Commençons par les [gradients linéaires](https://developer.mozilla.org/fr/docs/Web/CSS/linear-gradient).

```css
.linear-gradient {
  background-image: linear-gradient(blue, white);
}

.linear-gradient {
  background-image: linear-gradient(to right, blue, white);
}

.linear-gradient {
  background-image: linear-gradient(to bottom, blue, white);
}

.linear-gradient {
  background-image: linear-gradient(45deg, blue, white, yellow);
}
```

Vous pouvez également spécifier à quel moment chaque couleur doit commencer dans le gradient. Dans l'exemple ci-dessous, le vert commence à 20%, tandis que le jaune commencera pour sa part à 70%.

```css
.linear-gradient {
  background-image: linear-gradient(to right, blue, green 20%, yellow 70%);
}
```

Vous pouvez également utiliser des [gradients radiaux](https://developer.mozilla.org/fr/docs/Web/CSS/radial-gradient):

```css
.radial-gradient {
  background-image: radial-gradient(circle, blue, green 70%);
}

.radial-gradient {
  background-image: radial-gradient(ellipse, blue, green 70%);
}
```

```css
background-image: radial-gradient(
  ellipse farthest-corner at 45px 45px,
  #00ffff 0%,
  rgba(0, 0, 255, 0) 50%,
  #0000ff 95%
);
```

_Exercice: expérimenter avec les couleurs et les images de fond dans votre fichier de travail_

### Propriétés CSS liées au texte

CSS vous offre également de nombreux outils pour contrôler les aspects typographiques de votre design. Nous verrons ici les propriétés les plus utilisées: `font-family`, `font-size`, `font-weight` et `line-height`. Nous aborderons également les propriétés `font-variant` et `font-style`.

`font-family`: permet de gérer la police utilisée. S'utilise en général avec plusieurs fontes ([font-stack](http://www.smashingmagazine.com/2009/09/22/complete-guide-to-css-font-stacks/)) de façon à avoir des polices de rechange au cas où l'une ou plusieurs d'entre-elles ne sont pas disponibles sur l'ordinateur client.

```css
h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: Helvetica, Arial, sans-serif;
}
```

`font-size`: permet de gérer la taille de police. Peut être spécifiée en unités absolues (px) ou relatives (pourcentages, em, etc)

```css
h1 {
  font-size: 200%;
}
```

`font-weight`: permet de spécifier la graisse de la police. Peut être spécifiée à l'aide de mots-clefs (normal, bold) ou de valeurs numériques (400, 600, 800).

```css
h1 {
  font-weight: 600;
}
```

`line-height`: permet de spécifier une hauteur de ligne pour vos textes. C'est une des rares propriété qui ne prend pas d'unité en CSS. La hauteur de ligne est relative à la taille de police.

```css
body {
  line-height: 1.5;
}
```

`font-style`: permet de gérer l'aspect d'une police. Les valeur les plus utilisées sont `italic` et `normal`

```css
body {
  font-style: italic;
}
```

Toutes ces propriétés peuvent être utilisées dans le cadre d'une seule propriété courte: `font`.

```css
body {
  font: normal italic 100%/1.5 Helvetica, Arial, sans-serif;
}
```

`text-transform`: permet de gérer les transformations à appliquer sur une police. Les valeurs les plus utilisées sont: `capitalize`, `uppercase`, `lowercase` et `none`.

```css
body {
  text-transform: uppercase;
}
```

`text-align`: permet d'aligner votre texte

#### Utilisation de polices non-standard

Depuis que les principaux navigateurs supportent la propriété `@font-face`, il est possible d'utiliser des polices non-standard. Au lieu de se reposer sur les polices présentes sur l'ordinateur de vos visiteurs, vous pouvez spécifier des polices personnalisées que les visiteurs téléchargent en même temps que le contenu de votre site. Nous verrons cela en détail dès l'année prochaine.

Etant donné les complexités techniques de la typographie sur écran, de nombreux services ont vu le jour pour vous proposer des polices optimisées et en permettre une utilisation simple dans vos designs: Typekit, Fontdeck, Google fonts.

Nous nous concentrerons ici sur l'utilisation de Google Fonts, un service gratuit offrant des fontes de qualité. Voici [quelques](http://femmebot.github.io/google-type/) [exemples](http://hellohappy.org/beautiful-web-type/) de ce qu'il est possible de réaliser en se concentrant uniquement sur la typographie.

_Exercice: utiliser des fontes standard avec un font-stack_

_Exercice: utiliser des fontes non-standard avec Google Fonts_

### Texte en colonnes avec CSS

Vous pouvez utiliser CSS pour disposer vos textes en colonnes de manière dynamique en utilisant les [colonnes en CSS3](https://developer.mozilla.org/fr/docs/Web/CSS/Colonnes_CSS3). Pour ce faire, vous devrez utiliser les propriétés suivantes: `column-count`, `column-gap`, `column-rule` et `column-width`. Les navigateurs ne comprenant pas ces propriétés vont simplement les ignorer.

```css
.columns2 {
  column-count: 2;
  column-gap: 40px;
  column-rule: 1px solid red;
}
```

ou

```css
.columns-small {
  column-width: 20em;
}
```

### Images et videos

Voyons maintenant deux façons simples de positionner les images dans votre document.

#### Images et text-align

Par défaut les images sont des éléments de type `inline`. La propriété `text-align` va donc avoir le même effet sur elles que sur du texte.

Pour aligner des images à gauche ou à droite ou pour les centrer dans un bloc conteneur, il suffit d'utiliser cette propriété sur ce dernier.

```html
<p class="img-container"><img src="../img/myimage.png" alt="alt text"></p>
```

```css
.img-container {
  text-align: center;
  /*text-align:right;*/
  /*text-align:left;*/
}
```

#### Images et Floats

CSS peut également être utilisée pour positionner vos images relativement à votre texte.

Les propriétés `float:left;` et `float:right;` permettent au texte de contourner une image.

```html
<p>
  <img src="img/monimage.png" class="imgleft" width="200" height="112" alt="représentation alternative">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Sit cum corporis
  fugiat labore explicabo mollitia est saepe in minima porro neque ipsam
  voluptates, natus voluptatum! Animi commodi corporis ducimus natus!
</p>
<p>
  Aspernatur excepturi aut tempora, a beatae rerum molestias fuga architecto
  enim officia libero, voluptates vitae? Iusto itaque possimus, repudiandae!
  Distinctio cum velit vel voluptatum dolor, magni, nam doloremque unde minus.
</p>
```

```css
.imgleft {
  float: left;
  margin: 0 0 0.5em 1em;
}

.imgright {
  float: right;
  margin: 0 1em 0.5em 0;
}
```

#### Images et Videos fluides

Si vous avez des conteneurs spécifiés en pourcentage, il peut être utile de faire en sorte que vous images rétrécissent avec ces derniers. Pour cela, il suffit de spécifier que vos images ne peuvent jamais être plus larges que leur élément parent. Cette technique fonctionne pour les images comme pour les players videos et audio HTML5.

```css
.imgfluid {
  max-width: 100%;
}
```

Une technique différente doit être utilisée pour les `iframe` (Youtube / Vimeo / Soundcloud). Un `iframe` étant une sorte de fenêtre vers un autre site, elle ne se comporte pas comme un élément `audio` ou `video`.

```html
<div class="videocontainer">
  <iframe src="https://www.youtube.com/embed/IjHgzkQM2Sg"></iframe>
</div>
```

```css
.videocontainer {
  padding-top: 56.25%; /* ratio fluide de 16/9 (100%/16*9=56.25%) */
  background-color: #000;
  position: relative; /* contexte de positionnement pour l'iframe */
}

.videocontainer > iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border: none;
}
```

_Exercice: Mettre en page votre CV avec HTML et CSS_
