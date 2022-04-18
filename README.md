# **ARE Dynamic : Propagation d'un feu de forêt**

### **Membres du groupe :**
- Yanis **BAOUCHE** __(21107473)__
- Rick **GAO** __(21110625)__
- Lucas **CHIMIER** __(21103839)__
- Ronista **VICTOR MANOHARAN** __(28727387)__

## Introduction :

<br>

<img src="https://qph.cf2.quoracdn.net/main-qimg-9beeb08dd2bbef7e953e276ba666417b" width=1010>
<p align="justify">
  Ces dernières années, le monde connaît de plus en plus de désastres naturels et notamment des <a href="https://en.wikipedia.org/wiki/Wildfire" target="_BLANK">feux de forêts</a>. Nous savons déjà que cette augmentation est liée au réchauffement climatique, mais nous voulons savoir comment. Et plus précisément quels facteurs influent sur leur multiplication, leur intensité ou leur propagation. En effet, outre la prévention de ces feux, intervenir rapidement et efficacement est également synonyme de vies sauvées et de forêts préservées. 

Pour cela, nous disposons d’un outil efficace et fiable qui pourrait nous permettre de modéliser et connaître l’influence de certains paramètres sur les feux et ainsi savoir lutter efficacement contre eux, c’est la modélisation informatique. 
</p>
  
<br>

## **Problématique : L'augmentation des facteurs naturels dans le monde influence t-elle une propagation de feu de forêt ?**


### Hypothèses :
- Une forêt dense est plus favorable à une propagation rapide et totale du feu de forêt.
- L'humidité influe sur la propagation du feu.
- Le vent influe sur la propagation du feu de forêt.

### Objectifs :
- [X] Montrer que les facteurs météorologique influent sur la vitesse de propagation et la direction de propagation du feu de forêt.
Modéliser cette propagation. Interpréter les données de la modélisation.
- [X] Comparer les résultats des modélisations avec et sans influence de la météo, de la densité et de l’humidité des arbres.
- [X] Interpréter graphiquement l’évolution du nombre d’arbres vivants, entrain de brûler et morts en fonction des paramètres.
- [X] Donner une argumentation quant à l’apparition des feux de forêts et les facteurs favorisant la propagation du feu.
- [X] A partir de la modélisation, comprendre l’origine de la multiplication des feux de forêt.
- [X] Proposer des solutions permettant de réduire les feux de forêt.
- [X] Proposer des outils permettant de prévenir l’apparition de feux de forêt.


### Librairies :
- [**Matplotlib**](https://matplotlib.org/) : Matplotlib est une librairie Python permettant de tracer et visualiser des données avec des graphiques.
- [**Numpy**](https://numpy.org/) : Numpy est une librairie Python permettant de faciliter la manipulation de matrices, de tableaux multidimensionels et des fonctions mathématiques.
- [**PyGame**](https://www.pygame.org/) : Pygame est un ensemble de modules Python conçus pour écrire des jeux vidéo.

<br>

### Facteurs influençant la propagation d'un feu :

**Le vent**:

<p align="justify">
Les vents ont peut-être la plus grande influence sur le comportement des feux de forêt et sont également le facteur le plus imprévisible. Le vent alimente le feu en oxygène supplémentaire, séchant davantage les matériaux et poussant le feu à travers la terre à un rythme plus rapide.

Les vents affectent non seulement la façon dont un incendie se déclare mais aussi comment il se propage. Plus le vent souffle fort, plus le feu se propage rapidement. Les vents peuvent également changer la direction du feu.
</p>

**La température**:

<p align="justify">
La température affecte le déclenchement des incendies de forêt, car la chaleur est l'un des trois coins du triangle du feu (combustible, comburant, chaleur). Les restes d'arbres et de plantes au sol reçoivent la chaleur du soleil, qui chauffe et sèche les matériaux. Des températures plus chaudes permettent au carburant de s'enflammer et de brûler plus rapidement, ce qui augmente le taux d'incendies de forêt. 
</p>
  
**Humidité**:

<p align="justify">
Alors que le vent aide à propager le feu, l'humidité agit contre le feu. L'humidité (sous forme d'humidité ou de précipitations) peut ralentir un incendie et réduire son intensité. Les matériaux peuvent être difficiles à enflammer s'ils contiennent des niveaux élevés d'humidité, car l'humidité absorbe la chaleur d'un incendie. Plus l'humidité est élevée, moins le matériau risque de se dessécher et de s'enflammer.
Étant donné que l'humidité peut réduire les risques d'incendie de forêt, les précipitations ont un impact direct sur la prévention des incendies.
</p>
  
<br>

### Raisonnement et observation :

<p align="justify">
Pour modéliser notre forêt, nous allons considérer une forêt comme étant une liste de liste où chaque élément possédera des coordonnées (x,y)
Nous allons utiliser la fonction random.choice de la bibliothèque Numpy pour créer une matrice contenant que des 0 et des 1 en fonction de la probabilité (ici densité)
</p>
  
```py
def create_database(x,y,p):
    return np.random.choice([0,1],size=(x,y),p=[1-p,p]) #Créer une liste de liste de 1 et 0
```

<br>

<p float="left" align="justify">
Pour programmer le vent, nous avons essayé que le feu se propage de la façon présente sur le schéma ci-dessous. Nous avons fait une seule direction de vent car comme la forêt est tirée aléatoirement, il n'y a pas de réel intérêt à faire plusieurs possibilités de directions. Nous avons donc choisit la direction de "haut en bas" sur l'animation. Nous avons donc ajouté un coefficient lié au vent à chaque case voisine de l'arbre en feu. Ainsi, plus le vent est élevé, plus la probabilité de brûler les arbres en sens inverse au vent est faible. De plus la probabilité de brûler les arbres voisins dans le sens du vent est augmenté. Le vent 3/4 face et 3/4  dos est aussi prit en compte. Enfin, nous avons ajouté la possibilité qu'un arbre qui brûle peut brûler un arbre situé à deux cases dans le sens du vent. En effet, dans la vraie vie, le vent peut pousser les braises et ainsi enflammer des arbres plus éloignés !
</p>
<p align="middle"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/0f/Propagation_model_wildfire_%28French%29.svg/800px-Propagation_model_wildfire_%28French%29.svg.png" width="300"></p>

<p float="left" align="justify">
Pour programmer l'humidité nous nous sommes aidé du graphique ci-joint. En effet, on remarque que l'humidité influence la durée de combustion d'un arbre en feu. Ainsi, nous avons approché la courbe du graphique par une fonction constitué de morceau de fonctions affines pour plus de précision. Ainsi, en fonction de la variable humidité choisit en entrée, nous définissant un nombre d'étape correspondant à la durée qu'un arbre commençant à brûler soit encore entrain de brûler. Ici tout est question de proportion et non de statistique exacte, nous avons donc décidé que 0.1s sur le graphique correspondrait à une étape sur l'animation et dans le programme.
</p>
<p align="middle"><img src="https://user-images.githubusercontent.com/66788498/163872701-2347d5d2-2878-41ab-97b8-339f014b4fce.png" width="300"></p>

<p align="justify">
Pour animer ces étapes, nous avons programmer une fonction permettant d'ouvrir une fenêtre Pygame et de mettre-à-jour cette fenêtre en vérifiant le numéro associé au point de coordonnées (x,y)
</p>
  
```py
def draw(screen,data):
    x=0 #Initialise le point de départ en haut à gauche
    y=0
    unit=500/len(data) #Initialise le pas entre chaque case
    for i in range(len(data)): #Pour chaque ligne
        for j in range(len(data[0])): #Pour chaque colonne
            if(data[i][j]==1): #Si la case est un arbre
                pygame.draw.rect(screen,(71, 252, 80), pygame.Rect(x, y, x+unit, y+unit)) #Afficher une case verte
                x+=unit
            if(data[i][j]==0): #Si la case est de la terre
                pygame.draw.rect(screen,(247, 213, 143), pygame.Rect(x, y, x+unit, y+unit)) #Afficher une case grise
                x+=unit  
            if(data[i][j]==2): #Si la case est un arbre en feu
                pygame.draw.rect(screen,(255, 64, 67), pygame.Rect(x, y, x+unit, y+unit)) #Afficher une case rouge
                x+=unit
            if(data[i][j]==3): #Si la case est un arbre brulé
                pygame.draw.rect(screen,(33, 13, 4), pygame.Rect(x, y, x+unit, y+unit)) #Afficher une case noire
                x+=unit
        y+=unit
        x=0

    pygame.display.flip() #Mettre-à-jour la fenêtre
```

<br>

**Représentation graphique du nombre d'arbres restants et du nombre d'arbres brulés en fonction des étapes : **

Taille 100, Densité 50%, 10 Expériences :
- Sans paramètre (1)
- Force du vent à 60% (2)
- Humidité à 60% (3)
<p float="left" align="middle">
  <img src="https://user-images.githubusercontent.com/66788498/163839664-cc3cfd1a-a407-4a55-ad47-e9482adbc225.png" width="305" />
  <img src="https://user-images.githubusercontent.com/66788498/163865759-0bfa1bf7-6634-4e2f-bb19-dabc8a7c9f54.png" width="320" />
  <img src="https://user-images.githubusercontent.com/66788498/163865902-0b84aaae-c87b-40f5-a31a-5338f10cf248.png" width="305" /> 
</p>

Taille 100, Densité 80%, 10 Expériences :
- Sans paramètre (1)
- Force du vent à 60% (2)
- Humidité à 60% (3)
<p float="left" align="middle">
  <img src="https://user-images.githubusercontent.com/66788498/163840203-faaee438-7c18-4844-8219-da44da3aa096.png" width="305" />
  <img src="https://user-images.githubusercontent.com/66788498/163840453-303d6361-ac9f-4fed-81d3-5a197a66f357.png" width="312" />
  <img src="https://user-images.githubusercontent.com/66788498/163866152-5a578be7-5323-4681-bce3-b376e120c4ee.png" width="330" /> 
</p>


<br>

### Interprétation :
**Fiabilité de l'interprétation:**

<p align="justify">
Afin de tester la fiabilité de notre modèle nous l’avons comparé à un modèle déjà existant, celui du logiciel universitaire NetLogo.
En effet, NetLogo est un logiciel Développé par l'université Northwestern (université américaine située à Evanston) et financé par la National Science Foundation. Il propose aux utilisateurs de créer des modélisations mais également d’utiliser des modèles fournis avec le logiciel et développé par des chercheurs, c’est ce que nous avons fait.

Ici, on peut voir notre modèle pour une densité de 50%, et à droite celui développé par Netlogo :
</p>
  
<p float="left" align="middle">
  <img src="https://s7.gifyu.com/images/enregistrement-de-lecran-2022-04-18-a-134402-oacu7rc4_h3dxcTpb.gif" width="400" />
  <img src="https://s7.gifyu.com/images/NetLogo-fire-modele0646378e91d97588.gif" width="400" /> 
</p>

<p align="justify">
On observe une similarité dans les deux modèles, on peut en conclure que notre modèle est cohérents avec la réalité. Ainsi, cela nous assure la fiabilité de notre modèle que nous pouvons donc exploiter pour étudier l’impact de différents facteurs naturels sur la propagation du feu de forêt
</p>


**Egalement, on peut visualiser la modélisation avec l'influence du vent:**

<p align="middle">Propagation avec vent (Densité 100% Force 50% Proba 50%) :</p>
<p align="middle">
  <img src="https://s7.gifyu.com/images/Propagation_avec_vent.gif" width="400"/> 
</p>

<p align="justify">
On observe que les carrés rouges (représentants le feu), se propagent maitenant de manière uniforme et beaucoup plus rapide. De plus, on peut observer que des carrés rouges apparaissent de l'autre coté de la fenêtre. Cela montre donc que le vent à une influence sur les départs de feux car le vent fait s'envoler des branches enflammés qui déclenche à leur tour des feux. De plus, il joue un rôle dans la vitesse de propagation du feux, qui est multiplié avec celui-ci.
</p>

<br>

**Interprétation quant à l'apparition des feux de forêts et les facteurs favorisant leur propagation :**

<p align="justify">
Les données fournis par notre modélisation ainsi que les graphiques du nombre d'arbres brulés selon le taux d'humidité, nous permettent de dire que de hautes températures, qui influencent la sécheresse des arbres, favorisent l'apparition de feux de forêts et entrainent une plus grande propagation de ceux-ci.
</p>
  
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

<br>

### Annexes :

**Quelques règles à respecter pour éviter tous risque de feux de forêt :** 

- Ne pas faire de feu/barbecue près des forêts et des espaces végétalisés.
- Respecter les interdictions d’accès aux forêts en période de risques (sécheresse, vent fort, …) 
- Ne pas fumer de cigarette en forêt, ou en pleine nature en période de sécheresse, et ne pas jeter les mégots au sol ou par la fenêtre de la voiture.
- Ne pas faire de travaux ou de petits bricolages provoquant des étincelles (soudure, scie, ...) durant les jours de risque d'incendie (sécheresse, canicule, vent fort) à proximité de végétaux.


**Comme dans tout autre cas d’urgence, la première chose à faire est :**

- Alerter les secours en composant le 18 ou le 112
- Essayer de localiser le feu
- Essayer d’éteindre le feu avec de la terre, du sable ou de l’eau sans se mettre en danger

<br>

### Bibliographie :
- Abibi, L. « Modélisation et simulation d’incendie de forêt par automate cellulaire ». Revue Marocaine des Sciences Agronomiques et Vétérinaires, vol. 1, no 2, 2013, p. 52‐63. https://www.agrimaroc.org/index.php/Actes_IAVH2/article/view/325
- Wu, Zechuan, et al. « Simulation of Forest Fire Spread Based on Artificial Intelligence ». Ecological Indicators, vol. 136, mars 2022, p. 108653. ScienceDirect, https://doi.org/10.1016/j.ecolind.2022.108653
- Wilensky, U. (1999). NetLogo. http://ccl.northwestern.edu/netlogo/. Center for Connected Learning and Computer-Based Modeling, Northwestern University, Evanston, IL.
- D. MORVAN, A. LAMORLETTE « Effet de la teneur en eau sur la propagation d’un feu de surface à travers une strate de végétation homogène » http://documents.irevues.inist.fr/bitstream/handle/2042/52763/a_H834PX32.pdf;sequence=1?msclkid=2da3b51bbe8911ec8be2bcdab8811de3

<br><br>

<p align="middle">Made with ♥  by Yanis, Rick, Lucas & Ronista :) </p>

