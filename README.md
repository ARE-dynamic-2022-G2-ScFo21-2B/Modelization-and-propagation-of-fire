# **ARE Dynamic : Propagation d'un feu de forêt**

### **Membres du groupe :**
- Yanis **BAOUCHE** __(21107473)__
- Rick **GAO** __(21110625)__
- Lucas **CHIMIER** __(21103839)__
- Ronista **VICTOR MANOHARAN** __(28727387)__

## Introduction :

<br>

![Ceci est une image](https://upload.wikimedia.org/wikipedia/commons/d/d8/Deerfire_high_res_edit.jpg)

<img src="https://qph.cf2.quoracdn.net/main-qimg-9beeb08dd2bbef7e953e276ba666417b" width=1010></img>

  Ces dernières années, le monde connaît de plus en plus de désastres naturels et
notamment des [feux de forêts](https://en.wikipedia.org/wiki/Wildfire). Nous savons déjà que cette augmentation est liée au
réchauffement climatique, mais nous voulons savoir comment. Et plus précisément quels facteurs influent sur leur multiplication, leur intensité ou leur
propagation. En effet, outre la prévention de ces feux, intervenir rapidement et efficacement est également synonyme de vies 
sauvées et de forêts préservées. 

 Pour cela, nous disposons d’un outil efficace et fiable qui pourrait nous permettre de modéliser et connaître
l’influence de certains paramètres sur les feux et ainsi savoir lutter efficacement contre eux,
c’est la modélisation informatique. 

<br>

## **Problématique : L'augmentation des facteurs naturels dans le monde influence t-elle une propagation de feu de forêt ?**


### Hypothèses :
- Une forêt dense est plus favorable à une propagation rapide et totale du feu de forêt.
- L'humidité influe sur la propagation du feu.
- Le vent influe sur la propagation du feu de forêt.

### Objectifs :
- [X] Montrer que les facteurs météorologique influent sur la vitesse de propagation et la direction de propagation du feu de forêt.
Modéliser cette propagation. Interpréter les données de la modélisation.
- [ ] Comparer les résultats des modélisations avec et sans influence de la météo, de la densité et de l’humidité des arbres.
- [ ] Interpréter graphiquement l’évolution du nombre d’arbres vivants, entrain de brûler et morts en fonction des paramètres.
- [ ] Donner une argumentation quant à l’apparition des feux de forêts et les facteurs favorisant la propagation du feu.
- [ ] A partir de la modélisation, comprendre l’origine de la multiplication des feux de forêt.
- [X] Proposer des solutions permettant de réduire les feux de forêt.
- [X] Proposer des outils permettant de prévenir l’apparition de feux de forêt.


### Librairies :
- [**Matplotlib**](https://matplotlib.org/) : Matplotlib est une librairie Python permettant de tracer et visualiser des données avec des graphiques.
- [**Numpy**](https://numpy.org/) : Numpy est une librairie Python permettant de faciliter la manipulation de matrices, de tableaux multidimensionels et des fonctions mathématiques.
- [**PyGame**](https://www.pygame.org/) : Pygame est un ensemble de modules Python conçus pour écrire des jeux vidéo.

<br>

### Facteurs influençant la propagation d'un feu :

**Le vent**:

Les vents ont peut-être la plus grande influence sur le comportement des feux de forêt et sont également le facteur le plus imprévisible. Le vent alimente le feu en oxygène supplémentaire, séchant davantage les matériaux et poussant le feu à travers la terre à un rythme plus rapide.

Les vents affectent non seulement la façon dont un incendie se déclare mais aussi comment il se propage. Plus le vent souffle fort, plus le feu se propage rapidement. Les vents peuvent également changer la direction du feu.

**La température**:

La température affecte le déclenchement des incendies de forêt, car la chaleur est l'un des trois coins du triangle du feu (combustible, comburant, chaleur) .Les restes d'arbres et de plantes au sol reçoivent la chaleur du soleil, qui chauffe et sèche les matériaux. Des températures plus chaudes permettent au carburant de s'enflammer et de brûler plus rapidement, ce qui augmente le taux d'incendies de forêt. 

**Humidité**:

Alors que le vent aide à propager le feu, l'humidité agit contre le feu. L'humidité (sous forme d'humidité ou de précipitations) peut ralentir un incendie et réduire son intensité. Les matériaux peuvent être difficiles à enflammer s'ils contiennent des niveaux élevés d'humidité, car l'humidité absorbe la chaleur d'un incendie. Plus l'humidité est élevée, moins le matériau risque de se dessécher et de s'enflammer.
Étant donné que l'humidité peut réduire les risques d'incendie de forêt, les précipitations ont un impact direct sur la prévention des incendies.

<br>

### Raisonnement et observation :
- Nous avons commencé par trouver un algorithme permettant tout d'abord de modéliser la propagation d'un feu de forêt sans nécessairement avoir de paramètre. Pour cela, il nous a fallu commencé par les bases : modéliser une forêt par une liste de liste sur Python, créer une fonction permettant de mettre le feu à un arbre de la forêt, programmer une fonction de propagation, etc...
- Pour propager un forêt, il nous a fallu programmer un "jeu de la vie" suivant un certain nombre de voisins. Pour déterminer le nombre de voisin, il existe deux types de voisinage : le voisinage de Von Neumann considère qu'un point possède 4 voisins (haut, bas, gauche, droite) tandis que le voisinage de Moore considère qu'un point en possède 8 (haut, bas, gauche, droite, ainsi que les diagonales). Dans notre cas, nous utilisons le voisinage de Von Neumann plutôt que le voisinage de Moore puisque cela illustre mieux la réalité.
- Pour rendre ce programme visible, nous avons utilisé les fonctions de Pygame pour modéliser cette propagation. Nous avons utilisé la bibliothèque Pygame plutôt que Tkinter ou Matplotlib pour des raisons d'efficacité et de simplicité.

Densité : 90% d'arbre

![Propagation d'un feu de forêt](https://s7.gifyu.com/images/enregistrement-de-lecran-2022-04-15-a-181849-v1u5zifc_iKGJvaBP.gif)

- A partir de ce modèle, nous avons essayé de créer des variantes dépendant de paramètre : densité, météo, ...

- La variante dépendant de l'humidité se base sur le même principe que la modélisation précédente, la seule différence est l'ajout de probabilité lors de la propagation du feu. Pour chaque voisin, nous générons une probabilité en fonction du taux d'humidité (compris entre 0 et 1). Ainsi, plus le taux d'humidité est élevé, plus les probabilités de propager le feu aux voisins est faible.

Humidité : 30% d'humidité & 90% d'arbre

![Propagation d'un feu de forêt + Humidité](https://s7.gifyu.com/images/enregistrement-de-lecran-2022-04-15-a-184205-iqlvjjrh_8FlyrZkK.gif)

- La variante dépendant de l'humidité se base sur le même principe que la modélisation précédente, la seule différence est l'ajout de probabilité lors de la propagation du feu. Ici, on va définit un unique sens (droite), la probabilité de propager le feu aux voisin du haut et du bas et de 0.5 (1 chance sur 2) tandis que la propabilité de propager le feu au voisin de gauche est de 10% (contre 90% pour le voisin de droite).

Vent : vers la droite & 90% d'arbre

![Propagation d'un feu de forêt + Vent](https://s7.gifyu.com/images/enregistrement-de-lecran-2022-04-15-a-185258-gmrxkyjx-rqgxjywc_hMuIZXZE.gif)

- Ainsi, nous avons réussi à modéliser la propagation d'un feu de forêt en fonction de paramètres tels que la densité et la météo. Cependant, cela ne se base que sur le hasard.
- Nous allons donc simuler la propagation sur un grand nombre d'expérience afin d'obtenir une moyenne.

Simulation : 10 expériences, forêt de taille 10x10, 90% d'arbre

![Simulation feu de forêt + Humidité](https://gcdnb.pbrd.co/images/maWlsNWkc7ww.png?o=1)

Simulation : 10 expériences, forêt de taille 10x10

![Simulation feu de forêt + Densité](https://gcdnb.pbrd.co/images/SYA26Es7VcpY.png?o=1)

<br>

### Interprétation :
### Fiabilité:

Afin de tester la fiabilité de notre modèle nous l’avons comparé à un modèle déjà existant, celui du logiciel universitaire NetLogo.
En effet, NetLogo est un logiciel Développé par l'université Northwestern (université américaine située à Evanston) et financé par la National Science Foundation. Il propose aux utilisateurs de créer des modélisations mais également d’utiliser des modèles fournis avec le logiciel et développé par des chercheurs, c’est ce que nous avons fait.

Ici, on peut voir notre modèle pour une densité de 50%, et à droite celui développé par Netlogo :

<p float="left" align="middle">
  <img src="https://s7.gifyu.com/images/enregistrement-de-lecran-2022-04-18-a-134402-oacu7rc4_h3dxcTpb.gif" width="400" />
  <img src="https://s7.gifyu.com/images/NetLogo-fire-modele0646378e91d97588.gif" width="400" /> 
</p>

On observe une similarité dans les deux modèles, on peut en conclure que notre modèle est cohérents avec la réalité. Ainsi, cela nous assure la fiabilité de notre modèle que nous pouvons donc exploiter pour étudier l’impact de différents facteurs naturels sur la propagation du feu de forêt

Egalement, on peut visualiser la modélisation avec l'influence du vent:
![Propagation avec vent (Densité 100% Force 50% Proba 50%): ](https://s7.gifyu.com/images/Propagation_avec_vent.gif)

On observe que les carrés rouges (représentants le feu), se propage maitenant de manière uniforme et beaucoup plus rapide.
<br>

### Conclusion :

A partir de nos modélisations, nous avons pu constater que :
- Plus une forêt est dense, plus le feu de forêt se propage vite.
- Plus le taux d'humidité est élevé, moins le feu de forêt se propage vite.
- Plus le vent est fort, moins le feu de forêt se propage vite.

**Par conséquent, nous pouvons conclure que l'augmentation des facteurs naturels influe sur la propagation d'un feu de forêt.**

Bien qu’on ai vu que la nature pouvait être la cause du déclenchement du feu de forêt et favoriser sa propagation. Un facteur humain, peut également déclencher des feux de forêt. 


**Pour prévenir ces incendies, nous pouvons par exemple :**
- Placer des capteurs permettant de mesurer les différents facteurs naturels : humidité, température, vent, ... et informer en cas de variation anormale de ces derniers
- Construire des bouches d'incendie près des forêts pour accélérer l'extinction du feu
- Prévoir des distances de plantation entre les arbres
- Placer des arrosoir automatique (dans les zones à risque) permettant ainsi de garder l'environnement humide 
- Planter des cyprès méditerranéens, des arbres résistants aux incendies


**Quelques règles à respecter pour éviter tous risque de feux de forêt :** 

- Ne pas faire de feu/barbecue près des forêts et des espaces végétalisés.
- Respecter les interdictions d’accès aux forêts en période de risques (sécheresse, vent fort, …) 
- Ne pas fumer de cigarette en forêt, ou en pleine nature en période de sécheresse, et ne pas jeter les mégots au sol ou par la fenêtre de la voiture.
- Ne pas faire de travaux ou de petits bricolages provoquant des étincelles (soudure, scie, ...) durant les jours de risque d'incendie (sécheresse, canicule, vent fort) à proximité de végétaux.


**Comme dans tout autre cas d’urgence, la première chose à faire est :**

- Alerter les secours en composant le 18 ou le 112
- Essayer de localiser le feu
- Essayer d’éteindre le feu avec de la terre, du sable ou de l’eau sans se mettre en danger


### Markdown


```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

### Bibliographie :
- Abibi, L. « Modélisation et simulation d’incendie de forêt par automate cellulaire ». Revue Marocaine des Sciences Agronomiques et Vétérinaires, vol. 1, no 2, 2013, p. 52‐63. https://www.agrimaroc.org/index.php/Actes_IAVH2/article/view/325
- Wu, Zechuan, et al. « Simulation of Forest Fire Spread Based on Artificial Intelligence ». Ecological Indicators, vol. 136, mars 2022, p. 108653. ScienceDirect, https://doi.org/10.1016/j.ecolind.2022.108653
- Wilensky, U. (1999). NetLogo. http://ccl.northwestern.edu/netlogo/. Center for Connected Learning and Computer-Based Modeling, Northwestern University, Evanston, IL.

<br><br>

<p align="middle">Made with ♥  by Yanis, Rick, Lucas & Ronista :) </p>

