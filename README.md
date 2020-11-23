![](RackMultipart20201123-4-144y2zl_html_6d7521e4a3fe0f2f.png) ![](RackMultipart20201123-4-144y2zl_html_2703074ba6c5b93e.jpg)

# **Projet Machine Learning et Systèmes multi-agents**

Réalisée par :

EL KTIBI El hassane
 CHAOUKI Mouad

![](RackMultipart20201123-4-144y2zl_html_649c9586e4691459.png)

Encadrée par :

Mr. Lotfi Aachak

Mr. Ennaimi

_2ème année Cycle Ingénieur Logiciels et Système Intelligents [2019-2020]_

**[Introduction générale](#_1ejn6ue8fzm7) 2**

[Objectif de projet](#_1fwdww5gcofe) 3

[Conception de projet](#_y1tb56qkbtt9) 3

[La couche intelligente](#_k1mk6kx3mttr) 3

[La couche MAS](#_7cvzoktik8e0) 4

[La couche SPA](#_d8ee82zijv10) 4

**[Chapitre 1 : La partie Smart Layer](#_x2t6rg6so9le) 4**

[Introduction](#_5cds5bkxvecx) 4

[Environnement de développement](#_705jfd26bwuk) 4

[VS code](#_9eyopvf6nop0) 4

[Mongodb](#_xdssscuamxtc) 5

[Flask](#_t7vixlo4o2iy) 5

[Libraries](#_78jflfc4o34w) 5

[Architecture du projet](#_4szzydft8dlm) 5

[Description de l&#39;API](#_7zfv8eafbtqi) 6

[Scraping](#_iyb5d5ulslj8) 7

[Preprocessing](#_ml8tevey83hh) 9

[Loading to database](#_1anlw32590pe) 10

[Sentiment analysis](#_tof21vdgokwn) 11

[Clustering](#_unpdrps6n9u3) 12

[Prediction](#_6h1x8a9jsv1p) 13

[Conclusion](#_l5kn1pseg5gx) 15

**[Chapitre 2 : La partie Backend-SMA: Spring Boot, JADE](#_fmzpvdsoduic) 15**

[Introduction](#_hupmkvy31iqy) 15

[Environnement de développement et frameworks](#_1ety7m5r1wsr) 15

[Spring](#_ylpisri2rzr7) 15

[JADE](#_v4asjeq57chf) 15

[Postman](#_wymp4zvtqp5h) 16

[Spring Boot](#_pql2gi2lm4u3) 16

[API Rest](#_i1fvm0lr2ilp) 16

[Architecture du projet](#_y6vonzqrzzm1) 17

[SentimentAnalyzerAgent](#_h6lpusdlo2ji) 19

[ScrapingAgent](#_xta80ui7ni9b) 21

[PreprocessingAgent](#_v4786gagzj9w) 22

[LoadingAgent](#_7mpmeu87meyb) 23

[PredictionAgent](#_55zqylqt0dmj) 24

[DataVisualizationAgent](#_7ixstcug91or) 25

[ClusteringAgent](#_65t22ljzgceu) 26

[Conclusion](#_stqt8gbs12pd) 26

**[Chapitre 3 : La partie Frontend](#_o55ilnd9l2n0) 27**

[Introduction](#_crpgjr6rp173) 27

[Le Navigateur web](#_ee0gtec1a9h2) 27

[HTML (Hyper Text Markup Language)](#_3mxlaawr84m) 27

[CSS (Cascading Styles Sheets)](#_4m2qb75x2y15) 28

[Javascript](#_jt6y2684zgk8) 28

[Frameworks](#_wxlvgr6voar4) 28

[Bootstrap](#_mya8n6cujwam) 28

[Angular](#_6c5weziaions) 28

[Angular Materials](#_wkpg0j9d0urr) 29

[Charts.js](#_xi4tv2uljfnr) 29

[Mise en œuvre](#_6zecr5f7c8pk) 29

[Partie Visualisation](#_egz9ia9voa46) 30

[Partie Scrapping](#_z15e98ay9dkv) 30

[Partie Clusters](#_5buj1ncuep00) 31

[Partie Prédiction](#_omwd6lmnd2rg) 32

[Conclusion](#_b7pio5g0mzzk) 32

**[Conclusion générale](#_utu6p9wmlfez) 33**

# Introduction générale

L&#39;informatique est aujourd&#39;hui au centre de toutes les activités de l&#39;homme. Que ce soit un simple achat dans un magasin, le règlement d&#39;une facture, un appel téléphonique, une transaction bancaire ou un partage de données entre filiale d&#39;une entreprise, un système d&#39;information simple ou complexe intervient toujours. Quel que soit le domaine, (télécommunications, commerce, entreprise ou médecine), nous avons toujours besoin d&#39;un système de traitement automatique de l&#39;information. Il y a quatre ans, l&#39;Université de Maroua fut créée et par la même occasion un centre de santé chargé du suivi médical de chaque individu de la communauté universitaire : le Centre Médico-Social.

## Objectif de projet

L&#39;objectif principal du projet est la réalisation d&#39;un système multi-agents intelligents basé sur plusieurs algorithmes d&#39;apprentissage supervisé et non supervise, le système sera composé de plusieurs agents intelligents et interactifs, d&#39;où chaque agent effectue une tâche spécifique. En plus d&#39;une application Single page Application qui va interagir avec le système.

## Conception de projet

![](RackMultipart20201123-4-144y2zl_html_bfeec248fc0264cf.png)

Le projet est constitué de 3 couches distinctes qui peuvent être déployé sur plusieurs machines.

### La couche intelligente

C&#39;est une api REST basée sur Flask contenant tous les scripts nécessaires pour scrapper, prétraiter et charger les données dans une base de données mongodb

en plus de tous les modèles que nous avons développés pour faire des clusters, des prédictions, des analyses sentimentales et des visualisations

### La couche MAS

C&#39;est une api REST basée sur SpringBoot contenant JADE Framework avec tous nos agents, et leurs comportements et comment ils communiquent entre eux et comment ils servent la couche frontend SPA.

### La couche SPA

C&#39;est la partie front qui contient des pages pour chaque agent(analyse des sentiments, clustering, prediction, data visualisation), chaque page communique directement avec l&#39;agent approprié.

# Chapitre 1 : La partie Smart Layer

## Introduction

Dans cette partie, nous avons développé une API (REST) en utilisant le framework Flask, elle contient tous les scripts nécessaires pour les agents, et aussi pour le grattage, le prétraitement et le chargement des données dans une base de données mongodb.

Nous l&#39;avons appelée couche intelligente car elle contient tous les modèles d&#39;apprentissage machine qui peuvent être consommés par les agents à l&#39;aide de requêtes HTTP.

## Environnement de développement

### VS code

Visual Studio Code est un éditeur de code extensible développé par Microsoft pour Windows, Linux et macOS. Les fonctionnalités incluent la prise en charge du débogage, la mise en évidence de la syntaxe, la complétion intelligente du code, les snippets, la refactorisation du code et Git intégré. Les utilisateurs peuvent modifier le thème, les raccourcis clavier, les préférences et installer des extensions qui ajoutent des fonctionnalités supplémentaires.

### Mongodb

MongoDB (de l&#39;anglais humongous qui peut être traduit par « énorme ») est un système de gestion de base de données orienté documents, répartissable sur un nombre quelconque d&#39;ordinateurs et ne nécessitant pas de schéma prédéfini des données. Il est écrit en C++.

### Flask

Flask est un framework open-source de développement web en Python. Son but principal est d&#39;être léger, afin de garder la souplesse de la programmation Python, associé à un système de templates. Il est distribué sous licence BSD.

## Libraries

Pymongo, pandas, numpy, sklearn, matplotlib, BeautifulSoup, flair

Pour exécuter correctement cette couche, assurez-vous de lire le fichier &quot;requirement.txt&quot; et d&#39;installer tous ces libraries.

## Architecture du projet

![](RackMultipart20201123-4-144y2zl_html_a581c6047e7f7e63.png)

Cette couche est structurée en différents fichiers dont chacun contient des fonctions spécifiques et un fichier principal app.py qui est exécuté et contient notre API.

## Description de l&#39;API

@app.route(&#39;/api/v1/scrapNews&#39;, methods=[&#39;GET&#39;]) :

nécessite un paramètre &quot;nombre de pages&quot; pour commencer à scraper les titres des actualités du site web source &quot;maroc world news&quot;.

@app.route(&#39;/api/v1/preprocessing&#39;, methods=[&#39;GET&#39;])

lance le prétraitement et le nettoyage des données collectées

@app.route(&#39;/api/v1/scrapCovData&#39;, methods=[&#39;GET&#39;])

nécessite un paramètre &quot;type de data&quot;, pour commencer à collecter les données correctes de covid19 au maroc selon le type de données que nous voulons.

@app.route(&#39;/api/v1/loadToDB&#39;, methods=[&#39;GET&#39;])

nécessite un paramètre &quot;type&quot;, pour charger les données collectées dans la collection mongodb appropriée.

@app.route(&#39;/api/v1/startAnalysis&#39;, methods=[&#39;GET&#39;])

il commence à analyser les titres de l&#39;actualité recueillis et enregistre les résultats.

@app.route(&#39;/api/v1/analyzeSentiment&#39;, methods=[&#39;POST&#39;])

nécessite un paramètre &quot;text&quot;, pour commencer à analyser le texte passé en paramètres et renvoie le sentiment, et la confiance de model pour ce résultat.

@app.route(&#39;/api/v1/getNews&#39;, methods=[&#39;GET&#39;])

nécessite les paramètre &quot;number&quot; et &#39;sentiment&#39; , et renvoie le nombre d&#39;actualités correspondent au sentiment passé en paramètres.

@app.route(&#39;/api/v1/statAnalysis&#39;, methods=[&#39;GET&#39;])

renvoie des statistiques sur les titres de l&#39;actualité, le nombre de titres, le nombre de titres positifs et négatifs.

@app.route(&#39;/api/v1/marocData&#39;, methods = [&quot;GET&quot;])

renvoie les données covid19 marocaines pour la visualisation.

@app.route(&#39;/api/v1/getClusters&#39;, methods = [&quot;GET&quot;])

renvoie les régions regroupées &quot;clusters&quot; du maroc en ce qui concerne les données de la covid 19.

@app.route(&#39;/api/v1/prediction&#39;, methods = [&quot;GET&quot;])

nécessite un paramètre &quot;number&quot;, c&#39;est le nombre des cas confirmés pour prédire et renvoie le nombre des mort.

## Scraping

![](RackMultipart20201123-4-144y2zl_html_ab3466fd3b34b351.png)

Comme vous le voyez, nous supprimons trois types de données :

- les titres d&#39;actualités au maroc, source: &quot;moroccoworldnews&quot;

![](RackMultipart20201123-4-144y2zl_html_958295735162c928.png)

- données de la covid 19 par régions au maroc

![](RackMultipart20201123-4-144y2zl_html_cb6060aba11692e.png)

- données de la covid 19 pour chaque jour au maroc

![](RackMultipart20201123-4-144y2zl_html_b64cfb43b2e3cd8c.png)

note : pour les données marocaines, nous avons utilisé une source &#39;updated&#39; quotidiennement, de sorte que nous n&#39;avons pas besoin de scraper les données manuellement et d&#39;exécuter le script chaque jour.

## Preprocessing

![](RackMultipart20201123-4-144y2zl_html_64bf9ce03e415575.png)

Voici un exemple de preprocessing et cleaning de data des titres d&#39;actualités: suppression des colonnes non utilisé (colonne: url), suppression des titre répétés

## Loading to database

![](RackMultipart20201123-4-144y2zl_html_10a38d2e6e424083.png)

Chargement des données collectées (en fichiers .csv) dans la base de données mongodb appropriée.

## Sentiment analysis

![](RackMultipart20201123-4-144y2zl_html_6401abfd5b6dbdb6.png)

pour analyser la polarité des sentiments dans les titres des actualités, nous avons utilisé un modèle préformé &quot;pretrained model&quot; du &quot;Flair&quot; qui est le meilleur modèle que nous puissions trouver accessible à l&#39;utilisation, et il est considéré comme l&#39;état de l&#39;art de l&#39;analyse sentimentale.

![](RackMultipart20201123-4-144y2zl_html_8c6f4f712ef4f7cf.png)

![](RackMultipart20201123-4-144y2zl_html_291e65a1a6c80376.png)

## Clustering

![](RackMultipart20201123-4-144y2zl_html_60111cfd2fc5e485.png)

dans ce modèle, nous avons utilisé la bibliothèque sklearn pour entraîner l&#39;algorithme K-means sur des données non étiquetées afin d&#39;obtenir des clusters (régions) basés sur le nombre de cas confirmés et de décès, il est à noter que nous avons utilisé la &quot;elbow method&quot; pour déterminer le nombre de clusters

## Prediction

![](RackMultipart20201123-4-144y2zl_html_a23cb549d2c46fe1.png)

dans ce modèle, nous avons utilisé la bibliothèque sklearn pour entraîner un algorithme de régression linéaire sur des données étiquetées (apprentissage supervisé) afin d&#39;obtenir des prédictions sur le nombre de décès en fonction du nombre de cas confirmés, il convient de mentionner que ce modèle n&#39;est pas précis, car les données ne sont pas linéaires et il est impossible de prédire un tel phénomène quel que soit le modèle utilisé

![](RackMultipart20201123-4-144y2zl_html_4b6ff2e023af3aae.png)

Voici la différence entre les nombres prédits et les nombre réels de dataset de test.

![](RackMultipart20201123-4-144y2zl_html_e7a82c5fe7c9e5a6.png)

## Conclusion

Dans cette partie, nous avons appris et appliqué différents concepts et méthodes, dont le scraping, le nettoyage et le prétraitement des données, en plus de certains algorithmes et techniques classiques de ML et de la manière dont tout cela peut être déployé dans une api REST à l&#39;aide de Flask.

# Chapitre 2 : La partie Backend-SMA: Spring Boot, JADE

## Introduction

Le « backend » est un peu comme la partie immergée d&#39;un iceberg. On ne la voit pas en tant que simple Internaute mais elle représente une très grande partie d&#39;un projet web.

- Le Backend se compose généralement de trois éléments :
- Un serveur (hébergement web)
- Une application (site web, administration)
- Une base de données (sorte de feuille de calcul pour organiser les données)

## Environnement de développement et frameworks

### Spring

Spring est un framework open source pour construire et définir l&#39;infrastructure d&#39;une application Java, dont il facilite le développement et les tests.

### JADE

JADE (Java Agent DEvelopment Framework) est un framework logiciel entièrement implémenté dans le langage Java. Il simplifie la mise en œuvre de systèmes multi-agents grâce à un middleware conforme aux spécifications du FIPA et à un ensemble d&#39;outils graphiques qui prennent en charge les phases de débogage et de déploiement

### Postman

Postman est un outil de test API évolutif qui s&#39;intègre rapidement dans le pipeline CI/CD. Il a été lancé en 2012 en tant que projet parallèle par Abhinav Asthana pour simplifier le flux de travail des API dans les tests et le développement. API signifie Application Programming Interface (interface de programmation d&#39;applications), qui permet aux applications logicielles de communiquer entre elles par le biais d&#39;appels API.

### Spring Boot

Un Framework ou kit de développement est un espace de travail modulaire, c&#39;est à dire une suite d&#39;outils et de bibliothèques qui facilitent et accélèrent le développement d&#39;un logiciel. Il contient toutes les fonctions de base utiles au développement d&#39;un type de programme, et permet donc de ne pas avoir besoin de réécrire les mêmes fonctions à chaque programme créé. Il en existe dans tous les langages de programmation.

Parmi les Framework Web, nous somme plus particulièrement intéressée aux Framework Spring boot. Dans leur grande majorité, elle est conçue sur le modèle MVC, ce qui permet de structurer les données. Ils imposent un cadre et des normes de développement qui permettent une programmation propre et modulaire. Une autre motivation pour ce choix est le fait que nous les membres de cette équipe nous avons déjà travaillé avec cette Framework. Il est aussi important de mentionner que Maven a été utilisé pour faire la gestion des dépendances du projet. De cette façon, il a été assez facile d&#39;inclure plusieurs modules nécessaires pour l&#39;application web. Ces modules auront permis de grandement réduire le code écrit grâce aux annotations fournies par le module permettant l&#39;intégration avec Jade. De plus, il est assez facile d&#39;implémenter de nouvelles routes avec les annotations fournies par Spring Boot.

### API Rest

Pour rendre accessible des données via un site, il existe les méthodes dites REST(representational state transfer). Il s&#39;agit d&#39;un ensemble de conventions et de bonnes pratiques à respecter et non d&#39;une technologie entière. L&#39;information de base, dans une architecture REST, est appelée ressource. Toute information qui peut être nommée est une ressource : la description d&#39;un bâtiment, la liste des arrêts de bus ou n&#39;importe quel concept. Dans un système hypermédia, une ressource est tout ce qui peut être référencé par un lien. L&#39;interface entre les composants est simple et uniforme. En HTTP, cette interface est implantée par les verbs GET, PUT, POST, DELETE, . . . qui permettent aux composants de manipuler les ressources de manière simple.

## Architecture du projet

Le backend de ce projet se compose de quatre parties, soit la partie service, contrôleur, agents plus l&#39;application main Spring boot.

![](RackMultipart20201123-4-144y2zl_html_edcca9f3d9322315.png)

**agent** : ce package contient tous les agents, les agents interagissent directement avec leurs pages SPA et consomment leur besoin de la couche intelligente de Flask

**container** : ce package contient tous les containers des agents et le main conainer

**controller** : c&#39;est un contrôleur pour démarrer les agent depuis l&#39;extérieure avec une requête http.

**service** : pour consommer l&#39;api de la couche intelligente de Flask.

![](RackMultipart20201123-4-144y2zl_html_fec76ac657de58d7.png)

Nous avons ajouté les capacités REST à nos agents en utilisant l&#39;annotation @RestController de Springboot alors nos agents sont capables de consommer la couche inteligennt et aussi de communiquer avec la couche SPA de frontend.

## SentimentAnalyzerAgent

![](RackMultipart20201123-4-144y2zl_html_f84b3fd5c1f9c330.png)

cet agent envoie une demande à l&#39;agent de scrapping (requête REQUEST), l&#39;agent de scraping collecte les données et envoie une demande à l&#39;agent de prétraitement pour nettoyer les données et les prétraiter, puis l&#39;agent de prétraitement envoie une demande à l&#39;agent de chargement pour que ce dernier charge les données dans la base de données mongodb, puis l&#39;agent de chargement envoie une requête INFORM à SentimentAnalyzerAgent pour qu&#39;il puisse lancer une analyse sentimentale sur les données scrappées.

Voici le code source de l&#39;agent:

![](RackMultipart20201123-4-144y2zl_html_2ed300ee798db1c6.png)

![](RackMultipart20201123-4-144y2zl_html_4bfcd90c5a4923fd.png)

## ScrapingAgent

![](RackMultipart20201123-4-144y2zl_html_38b7ad9cab9d6c0f.png)

Cet agent lance des requêtes de scraping selon le type de données qu&#39;on veut scraper et envoie une demande à l&#39;agent de prétraitement

## PreprocessingAgent

![](RackMultipart20201123-4-144y2zl_html_e78468a03fbf120e.png)

Cet agent lance des requêtes de preprocessing selon le type de données et envoie une demande à l&#39;agent de chargement.

## LoadingAgent

![](RackMultipart20201123-4-144y2zl_html_ae767b09c7f9921f.png)

Cet agent lance des requêtes de chargement selon le type de données et envoie une requête INFORM à l&#39;agent approprié.

## PredictionAgent

![](RackMultipart20201123-4-144y2zl_html_e753f86c7dcd9a44.png)

La même manière de travail que celle de l&#39;agent SentimentAnalyzerAgent.

## DataVisualizationAgent

![](RackMultipart20201123-4-144y2zl_html_e0ba0ec60c30fd85.png)

La même manière de travail que celle de l&#39;agent SentimentAnalyzerAgent.

## ClusteringAgent

![](RackMultipart20201123-4-144y2zl_html_473ba5e10b7ed2d4.png)

La même manière de travail que celle de l&#39;agent SentimentAnalyzerAgent.

## Conclusion

Cette section du rapport a présenté la partie du développement Backend du projet, c&#39;est la partie du code qui est exécutée par le serveur, il s&#39;agit du aussi de la partie des systèmes multi agents .

Ainsi on a expliqué dans cette partie le choix de technologies utilisés et ses fonctionnements.

# Chapitre 3 : La partie Frontend

## Introduction

La partie frontend est la partie du code qui est reçue par le client. Le client c&#39;est notre navigateur Web. Il s&#39;agit des éléments du site web que l&#39;on aperçoit à l&#39;écran et avec lesquels on pourra interagir. Ces éléments sont développés en utilisant trois langages ; HTML, CSS et Javascript.

## Le Navigateur web

Notre navigateur est l&#39;outil qui va nous permettre de voir notre application. Les navigateurs les plus connus sont : Chrome, Firefox, Safari, Internet Explorer, etc. On peut le voir comme une sorte de traducteur, c&#39;est-à-dire qu&#39;il va recevoir du code et nous le montrer sous forme visuelle, il va afficher nos pages Web. D&#39;ailleurs, ils n&#39;ont pas tous la même façon de traduire ce code et lorsque l&#39;on codera, on devra faire attention aux spécificités de certains navigateurs web.

Le code client que votre navigateur peut comprendre est composé de 3 langages différents : HTML, CSS et Javascript.

![](RackMultipart20201123-4-144y2zl_html_fde04a9ca20cb0ef.png)

## HTML (Hyper Text Markup Language)

HTML – Hyper Text Markup Language – est un langage composé de tags, balises en Français. Il va nous permettre de représenter la structure, le squelette de nos pages Web. Par exemple : un titre, un paragraphe, une image ou une liste.

## CSS (Cascading Styles Sheets)

Le langage CSS – Cascading Styles Sheets – est un langage qui va mettre en forme nos pages Web et les décorer. Il va désigner nos éléments HTML à l&#39;aide de sélecteurs et va leur appliquer un style CSS. C&#39;est ce langage CSS qui est responsable des couleurs, des tailles, de la mise en page, etc.

## Javascript

Un site Web peut être composé uniquement d&#39;HTML et de CSS, mais si on veut lui insuffler un peu de vie on aura besoin de Javascript, qui lui, est un vrai langage de programmation, avec des boucles, des conditions…II sera responsable de l&#39;interactivité et de la logique qu&#39;il y a derriere nos pages web. Par exemple, si on veut ouvrir un menu en cliquant sur un bouton particulier, on le fera avec du Javascript.

## Frameworks

### Bootstrap ![](RackMultipart20201123-4-144y2zl_html_8a401be301cc990.png)

Il y a aussi Bootstrap qui est un framework HTML, CSS et Javascript, c&#39;est-à-dire une structure qui contient de nombreux composants prêts à l&#39;emploi: boutons, listes déroulantes, menus, etc.

### Angular ![](RackMultipart20201123-4-144y2zl_html_a56b28f8793eb5fa.png)

Angular est un framework JavaScript Open Source basé sur Typescript et développé par Google. Il utilise l&#39;architecture MVM (Modèle Vue Modèle), proche du modèle MVC. Cela va permettre de structurer le code et bien séparer la vue (l&#39;interface) des modèles (fonctionnement).

Il est considéré comme un langage « côté client », ceux-ci permettent de gérer l&#39;interface utilisateur de chaque page (affichage, interactions…) de façon dynamique et viennent en complément aux langages côté serveur.

En général, Angular récupère des données du back-end, les affiche à l&#39;utilisateur via interface contenant des boutons, des formulaires… et ces boutons et ces formulaires permettent de déclencher des modifications côté back-end. On pourrait donc dire que Angular fait l&#39;intermédiaire entre l&#39;utilisateur et le back-end.

### Angular Materials

![](RackMultipart20201123-4-144y2zl_html_1ff3df549c6bf187.png)

Material est un module d&#39;Angular, c&#39;est un module d&#39;intégration qui permet d&#39;obtenir facilement une interface responsive harmonieuse et unie dans le style &#39;flat&#39; de Google. La documentation de Angular Material se trouve ici material.angularjs.org/latestest et elle est très bien faite.

### Charts.js

![](RackMultipart20201123-4-144y2zl_html_dbe9bd01a1b5237f.jpg)

Chart.js, la bibliothèque JavaScript de représentation des données sous forme de graphes statistiques vient d&#39;être publiée sur le site officiel de son créateur Nick Downie. D&#39;une utilisation très simple avec plusieurs options de personnalisation, l&#39;outil offre une prise en charge du HTML5 et ne nécessite pas de dépendance tierce.

## Mise en œuvre

La partie front end est divisée en 4 sous-parties selon les membres du groupe :

- Partie Visualisation
- Partie Clusters
- Partie Prédiction
- Partie Scrapping

### Partie Visualisation

Cette partie permettra la visualisation totale des données en se basant sur des graphes.

![](RackMultipart20201123-4-144y2zl_html_58c60f657cc900fc.png)

### Partie Scrapping

Après un Scrapping des news, on peut vérifier si les news sont positifs ou bien négatifs en utilisant l&#39;analyse des sentiments.

On peut aussi entrer une chaîne de caractères et voir si est-elle dans le sens positif ou bien négatif.

![](RackMultipart20201123-4-144y2zl_html_5156d2abc71a113a.png)

### Partie Clusters

Après un clustering des régions du Maroc, on projette leurs statistiques des cas, déçus et rétablies.

![](RackMultipart20201123-4-144y2zl_html_49b57e90b7b71951.png)

D&#39;autre part on affiche les villes qui ont un nombre de déçus et cas en commun se forme d&#39;un graphe de clusters.

![](RackMultipart20201123-4-144y2zl_html_f061110b605b4611.png)

### Partie Prédiction

Pour cette partie, on peut savoir approximativement le nombre des déçus en se basant sur le nombre des cas entré en paramètre.

![](RackMultipart20201123-4-144y2zl_html_35d3d59229bb5df2.png)

## Conclusion

Ce chapitre de projet s&#39;intéresse à la réalisation de la partie Frontend, c&#39;est l&#39;ensemble des interfaces que l&#39;utilisateur peut, en utilisant le Framework Angular qui est basé sur le modèle MVC qui donne lui-même une architecture simplifiée et bien organisée.

# Conclusion générale

Dans ce projet, nous avons essayé d&#39;apprendre beaucoup de choses en science des données et en particulier comment prétraiter les données, de les transformer, de les charger de manière utile qui nous aidera à faire des analyses, nous avons également appris à faire des système multi agents dans des environnements compliquées, ainsi on a appliquer et déployer des algorithmes ML en combinaison avec un système multiagent.

_Département Génie Informatique_
