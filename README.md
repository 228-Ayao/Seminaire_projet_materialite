# Sommaire :
1. [Présentation du projet de recherche](#paragraph1) <br>
2. [Présentation du corpus](#paragraph2) <br>
3. [Méthodologie :](#paragraph3) <br>
4. [Résultats de recherche](#paragraph4) <br>
5. [Limites au projet de recherche, pistes envisagées pour la suite](#paragraph5) <br>
6. [Conclusion](#paragraph6)  <br>
7. [Annexes](#paragraph7)  <br>

## Présentation du projet de recherche <a name="paragraph1"></a>

À l’ère du numérique, il est essentiel de nous intéresser sur la question de la matérialité des objets beaux-arts. En effet, il est impossible de retranscrire sur des écrans ce que l’on ressent quand on voit une œuvre d’art physiquement : la symbolique, la matière, les dimensions, la perception de l’objet-même est totalement différente selon la façon dont on le visualise. Quand on entre dans un musée, on peut ressentir toute une palette d’émotions à la vue de tableaux ou de sculptures, par leur étendue et leur beauté. À l’inverse, la matérialité de l’œuvre d’art sur des interfaces web se réduit simplement à une chaîne de caractères.
Dans le cadre du séminaire « Explorations numériques des archives de l’INA et de l’INHA », organisé en collaboration avec l’EUR ArTec, nous avons utilisé le jeu de données « Les collections Rothschild dans les institutions publiques françaises », provenant de l’Institut National de l’Histoire de l’Art. <br>
À partir de celui-ci, nous proposerons de montrer **comment l’analyse du jeu de données permet-elle de mettre en avant la matérialisation des œuvres d’art en fonction d’une approche historique.** <br>
De cette problématique en a découlé 4 autres sous-questions de recherche, qui sont les suivantes : <br>
1 - Est-ce que le type d’œuvre collectionné par la famille Rothschild évolue en fonction de l’époque ? <br>
2 - Est-ce que le type de peinture utilisé est différent en fonction des dimensions ? Et en fonction de la date de création ? <br>
3 - Est-ce que l’époque influe sur les dimensions des œuvres d’art léguées par la famille Rothschild ? <br>
4 - Peut-on représenter numériquement une œuvre d’art à partir d’un objet du quotidien ? <br>
Tout au long de ce billet de recherche, des tâcherons de répondre à ces questions en y apportant le plus de réponses concrètes possibles, notamment en intégrant des datavisualisations.

Dès le début de ce projet, il a été primordial pour nous de nous interroger sur la notion de « matérialité ». Le CNRTL la définit de la façon suivante : « caractère de ce qui est matière ». Cette définition nous a particulièrement aidé dans notre processus créatif car elle a engendré d’autres recherches sur le terme de « matière ». Nous avons ainsi recensé plusieurs mots-clés pour catégoriser notre projet, naturellement liées à la notion de matérialité : « représentation spatiale », « dimensions », « matière », « symbolique », « temporalité ».

## Présentation du corpus <a name="paragraph2"></a>
Le jeu de données que nous avons utilisé comporte les données liées aux collections de la famille Rothschild, dont les œuvres ont été léguées aux institutions publiques françaises. Ce n’est pas le seul jeu de données de l’INHA, en effet il y avait également la possibilité d’en utiliser deux autres : celui du répertoire des tableaux italiens des collections publiques françaises (RETIF) et celui du musée des monuments français d’Alexandre Lenoir. 
Le choix du jeu de données de la famille Rothschild est lié au fait que l’on connaissait un peu le nom et l’histoire de cette famille. Nous pensions également que la collection d’œuvres d’arts lui appartenant était assez conséquente. Après discussions, nous avons rassemblé plus d’informations sur le jeu de données et nous avons appris que ce dernier était constitué de tous les lègues de cette famille à l’état français. 
Le jeu de données de la famille Rothschild est composé de 1364 données. Au sein de ce corpus, nous trouvons des champs (des colonnes) qui caractérisent un objet, ces champs pouvant prendre des caractères comme : 
-	artwork -TITRE qui est le titre 
-	artwork -HAUTEUR qui est la hauteur
-	artwork- LARGEUR qui est la largeur de l’œuvre 
-	artwork – UNIQUE_KEY qui est l’ID de l’œuvre
-	artwork – DISPLAY_DATE_EXE_TXT qui est la date de l’œuvre
-	artwork – DISPLAY_MATIERE qui est la matière de l’objet
-	artwork -  URL qui est le lien URL de l’œuvre
-	artwork – DISPLAY_LIEU_CONSERV qui est le lieu de conservation de l’œuvremi
-	artwork -  IMG_DIRECT_ACCESS qui est l’URL de la vignette de l’objet
-	artwork – DISPLAY_DENOMINATION qui est le type d’œuvre
-	artwork – DISPLAY_PERSONNE_AUTEUR qui est l’auteur de l’oeuvre
-	artwork – DISPLAY_TECHNIQUE qui est la technique de l’objet 
-	artwork -DISPLAY_ROLE_AUTEUR qui est le rôle de l’auteur par rapport à l’œuvre
Ces champs composent le jeu de données de la famille Rothschild et sont aussi présents dans les autres jeux de données. Ces informations dans les champs sont issues de la base de données des collections Rothschild dans les institutions publiques françaises se trouvant sur AGORHA. Ce site permet de consulter en ligne l’ensemble des données au sujet desquelles l’INHA travaille. 

## Méthodologie : <a name="paragraph3"></a>
## Travaux sur le jeu de données

Pour pouvoir répondre à notre problématique ainsi qu’à nos sous-questions de recherche, il a fallu travailler sur le jeu de données et créer des datavisualisations. Pour modifier le jeu de données, nous avons utilisé l'outil OpenRefine pour nettoyer, ajouter et optimiser les données du corpus. Cet outil, qui est un « Excel aux hormones », permet de faire du data wrangling pour préparer les données avant les visualisations. En effet, en regardant le jeu de données sur OpenRefine, nous avons vu des erreurs comme : <br>
–	Le nommage des enregistrements de valeur des caractéristiques des œuvres d'art dans les champs (erreurs d'orthographe, valeurs non identiques dans le champ des dates) <br>
–	Des données manquantes dans les champs notamment dans le champ artwork -HAUTEUR (et donc la hauteur), le champ artwork- LARGEUR (et donc la largeur) de l’œuvre. <br>
–	Des imprécisions au niveau de l’utilisation des unités de mesure pour la représentation des œuvres d’art (les dimensions de certaines œuvres d’art étaient indiquées en mètres, d’autres en centimètres. Nous avons dû homogénéiser les données en utilisant uniquement les centimètres.) <br>

Nous avons donc nettoyé les données comme les données du champs artwork – DISPLAY_DATE_EXE_TXT qui correspond à la date de l’œuvre (qui était soit une date précise, soit un siècle, soit une « fourchette » de date). Pour optimiser ce champ, nous avons créé un nouveau champ « Date de l’œuvre » en mettent les dates au format numérique, puis créé un champ « Siècle » avec les dates du champ « Date de l’œuvre ». Cette action a permis d’optimiser les dates pour les visualisations en créant des siècles.
 

Nous avons modifié l’orthographe des enregistrements de certains champs, ajouté la majuscule sur les enregistrements et modifié certains titres de champs. Le travail, le plus long de ces 3 jours d’action sur OpenRefine a été de faire du data wrangling sur le champ « artwork -HAUTEUR » qui est la hauteur de l’œuvre et le champ « artwork- LARGEUR » qui est la largeur de l’œuvre d’art. La première action de ce travail a consisté à modifier certaines valeurs de ces champs en les convertissant de mètres à centimètres. Ce travail a été réalisé pour toutes les valeurs comprises entre 0.00 et 10 qui étaient majoritairement en mètres. Ces valeurs ont été vérifiées manuellement. La deuxième action sur ces champs était de compléter certaines valeurs des champs de la HAUTEUR et de La LARGEUR qui étaient absentes, comme le montre la photo ci-dessous.
 

Pour ajouter les valeurs manquantes, après discussion avec les encadrants (Dario Campagno, Benjamin Barbier, Nicolas Sauret et Antoine Courtin), la solution trouvée est la suivante : nous avons créé un ratio moyen des œuvres d’art en utilisant la formule suivante sur OpenRefine : cells["artwork - HAUTEUR"].value * 1.0 / cells["artwork - LARGEUR"].value * 1.0 (Hauteur * Largeur) et en créant un nouveau champs « Ratio ». Cependant pour bien ajouter des valeurs sur des données manquantes, il fallait respecter le siècle et le type de l’œuvre pour avoir une meilleure cohérence dans l’enrichissement des données, ce qui est passé par la mise en place d’un tableau Excel présentant les ratios calculés selon les œuvres d’art.
 

Ensuite, nous avons appliqué le ratio sur les données manquantes dans le champ « artwork – LARGUEUR » et en appliquant soit la formule suivante sur OpenRefine : cells["artwork - HAUTEUR"].value * 1.0 / 4.1666 ( Hauteur *1.0 / le ratio moyen = largeur ) soit en utilisant le diamètre de l’œuvre d’art (notamment pour la porcelaine), selon le type de l’objet et le siècle. Pour les données manquantes dans le champ « artwork – HAUTEUR », nous avons pris les données de la page URL de l’œuvre d’art et si on ne trouvait pas la donnée après discussion avec les encadrants, nous avons décidé d’éliminer du corpus les œuvres d’art dont la hauteur était absente, afin d’avoir des visualisations de données plus claires et avec toutes les données nécessaires.
Pour finir sur le data wrangling, nous avons créé un champs supplémentaire : celui de la « Surface », permettant de visualiser l’aire des œuvres d’arts en utilisant une formule sur OpenRefine : cells["artwork - HAUTEUR"].value * cells["artwork - LARGEUR"].value (Hauteur * Largeur). 
 

Pour terminer sur la structuration des données sur OpenRefine, les données qui n’avaient pas suffisamment de données exploitables dans nos visualisations étaient au nombre de 270. Pour répondre à la problématique et à nos sous-questions de recherche, notre corpus final a donc été composé de 1094 enregistrements sur le jeu de données de la collection Rothschild. 

 
Après ce travail de data wrangling, nous avons pu passer à l’étape de la visualisation de l’information et à la réalisation des tests sur les formes de visualisations possibles. Les visualisations ont été réalisées sur l’outil Flourish qui permet de faire du storytelling et de mettre en avant les données pour répondre aux sous-problématiques.

La visualisation des données des collections Rothschild consiste à la représentation avec l’outils « flourish » d'informations et de données obtenues après le nettoyage des données initiales sur OpenRefine. À l'aide d'éléments visuels comme les graphiques cette visualisation de données permet de voir et de comprendre des tendances ou des valeurs inhabituelles dans les données, de manière très explicite.

## Résultats de recherche <a name="paragraph4"></a>
**1.	Est-ce que le type d'œuvre collectionnée par la famille Rothschild évolue en fonction de l’époque ? <br>**
<script src="https://public.flourish.studio/resources/embed.js">
Le XVIIIème siècle est le siècle phare de la collection Rothschild. 
Une première analyse du graphique, permet de déduire que la grande majorité de la collection est alimentée par des œuvres datant du XVIIIe siècle. Il y a 869 œuvres au total avec une majorité d’objet d’art européen (651), ou encore 146 meubles domestiques. Cette collection du XVIIIème est complétée en minorité par les autres types d’œuvres tels que les peintures, les dessins et les sculptures.
À l'inverse, on peut voir que la plupart des œuvres d'art collectionnées datant du XVe siècle et du XVIe siècle sont des sculptures et des peintures.
Il commence à y avoir une grande de plus large diversification des types d'œuvre à partir du 18e siècle.
Les siècles les moins prolifiques en termes de collections sont respectivement le XXe, XIVe et le XVIIe siècle. 

**2.	 Est-ce que le type de peinture utilisé est différent en fonction des dimensions ? <br>**
<div class="flourish-embed flourish-scatter" data-src="visualisation/6068286"><script src="https://public.flourish.studio/resources/embed.js">
Les variables prises en compte dans cette visualisation sont la surface de chaque œuvre notée ici en centimètre carré (cm²) ainsi que la technique de peinture utilisée. 
Une vingtaine de techniques sont utilisées dans la réalisation des œuvres de la collection Rothschild à savoir le polychrome qui offre de diverses couleurs, la céramique, la marqueterie qui utilise des placages de bois en plus d’autres matières, le ciselé, etc.
Il en ressort à partir du graphique que la grande majorité des peintures ont été peintes à l'huile. Les peintures les plus proéminentes sont environ au nombre de deux. Il y a 2 peintures à fresque et un autre de type peinture à l’huile.
Cependant il est difficile d’établir à partir de ces 2 types de peinture que ce sont celles qui ont les plus grandes dimensions car on ne possède pas assez de données. Par conséquent, on ne peut pas établir un constat général. À partir du corpus étudié, le type de technique utilisé pour la peinture n'influence pas vraiment leur dimension.

**3.	Est-ce que l’époque influe sur les dimensions des œuvres d’art léguées par la famille Rothschild ? <br>**
<div class="flourish-embed flourish-scatter" data-src="visualisation/6069072"><script src="https://public.flourish.studio/resources/embed.js">
Pour répondre à cette problématique nous avons croisé trois variables telles que la surface de l’œuvre, la période de création avec le siècle, en fonction du type d’œuvre. L’objectif est de mettre en exergue la concentration des d’œuvres selon les siècles.
L’analyse du graphique montre que les œuvres de grande taille se situent principalement dans les siècles de grandes collections comme le XVIIIe siècle et les autres collections moins conséquentes sont composées des œuvres de petite taille.
On peut en déduire que les dimensions dépendent de la quantité des collections au cours des siècles et n’influe à aucun moment le choix des œuvres à travers les siècles. 
Mais les siècles les moins prolifiques en termes de collection sont constitués essentiellement des œuvres de petites tailles. 

## Limites au projet de recherche, et pistes envisagées pour la suite <a name="paragraph5"></a>
Le manque d’outils et de temps sont principalement les deux limites que nous avons rencontré dans la réalisation de ce projet de recherche.

**1.	Le manque d’outils de visualisions <br>**
**Peut-on représenter numériquement une œuvre d’art à partir d’un objet du quotidien ?**
L’objectif de cette sous-problématique est d’apporter une plus-value à l’expérience visiteur en jouant sur les dimensions, en permettant au visiteur d’avoir une idée sur la taille de l’œuvre présentée sur un écran.
Le but n’est pas de permettre aux visiteurs de deviner la taille exacte mais de lui permettre d’avoir une idée approximative sur la taille.
L’objet de la vie quotidienne utilisée sert d’unité de mesure ou de baromètre. 
Il n’existe pas encore d’outils de visualisation approprié pour traduire ou expérimenter cette idée mais une maquette faite manuellement permet d’avoir une présentation expérimentale.
On a pris une bouteille d’Evian de 1.5 litre qui mesure un peu plus de 30 cm, et placé à coté de chaque œuvre affichée de manière identique sur un écran.
Cet exemple permet de deviner les tailles approximatives des œuvres présentées sur la maquette, qui sont respectivement d’environ 30 cm, 100 cm et 60 cm. 

**2.	Le manque de temps <br>**
L’objectif de départ était de faire le même traitement sur un deuxième jeu de données qui était celui de la collection d’Alexandre Lenoir, en le mettant en commun avec celui de la collection de la famille Rothschild. 
Ce travail avait pour but de répondre à la problématique suivante : « Est-ce que l’identité des détenteurs des œuvres d’art à une influence sur leurs dimensions ? », que nous pourrions étudier dans un futur proche.

## Conclusion <a name="paragraph6"></a>
Nous avons trouvé ce projet de recherche très intéressant et enrichissant d’un point de vue manipulation de données et d’étude de corpus sur les objets beaux-arts. Cependant, pour approfondir davantage l’analyse et pour répondre avec plus de précisions à nos problématiques, il nous aurait fallu plus de temps pour aller plus en profondeur dans nos recherches. 

## Annexes <a name="paragraph7"></a>
[Cliquez ici pour accéder aux modifications réalisées sur OpenRefine.](URL)





  

