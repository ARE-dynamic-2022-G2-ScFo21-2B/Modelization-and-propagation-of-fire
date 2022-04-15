# **ARE Dynamic : Propagation d'un feu de forêt**


**Membres du groupe :**
- Yanis **BAOUCHE** __(21107473)__
- Rick **GAO** __(21110625)__
- Lucas **CHIMIER** __(21103839)__
- Ronista **VICTOR MANOHARAN** __(28727387)__


## Introduction :

![Ceci est une image](https://upload.wikimedia.org/wikipedia/commons/d/d8/Deerfire_high_res_edit.jpg)

  Ces dernières années, le monde connaît de plus en plus de désastres naturels et
notamment des [feux de forêts](https://en.wikipedia.org/wiki/Wildfire). Nous savons déjà que cette augmentation est liée au
réchauffement climatique, mais nous voulons savoir comment. Et plus précisément quels facteurs influent sur leur multiplication, leur intensité ou leur
propagation. En effet, outre la prévention de ces feux, intervenir rapidement et efficacement est également synonyme de vies 
sauvées et de forêts préservées. 

  Pour cela, nous disposons d’un outil efficace et fiable qui pourrait nous permettre de modéliser et connaître
l’influence de certains paramètres sur les feux et ainsi savoir lutter efficacement contre eux,
c’est la modélisation informatique. 


## **Problématique : L'augmentation des facteurs naturels dans le monde influence t-elle une propagation de feu de forêt ?**


### Hypothèses :
- Une forêt dense est plus favorable à une propagation rapide et
totale du feu de forêt.
- L'humidité influe sur la propagation du feu.
- Le vent influe sur la propagation du feu de
forêt.


### Objectifs :
- Montrer que les facteurs météorologique influent sur la vitesse de
propagation et la direction de propagation du feu de forêt.
Modéliser cette propagation. Interpréter les données de la
modélisation.
- Comparer les résultats des modélisations avec et sans influence
de la météo, de la densité et de l’humidité des arbres.
- Interpréter graphiquement l’évolution du nombre d’arbres vivants,
entrain de brûler et morts en fonction des paramètres.
- Donner une argumentation quant à l’apparition des feux de forêts
et les facteurs favorisant la propagation du feu.
- A partir de la modélisation, comprendre l’origine de la
multiplication des feux de forêt.
- Proposer des solutions permettant de réduire les feux de forêt.
- Proposer des outils permettant de prévenir l’apparition de feux de
forêt.


### Librairies :

- [**Pandas**](https://pandas.pydata.org/) : Pandas est une librairie Python permettant la manipulation et l'analyse de données.
- [**Matplotlib**](https://matplotlib.org/) : Matplotlib est une librairie Python permettant de tracer et visualiser des données avec des graphiques.
- [**Numpy**](https://numpy.org/) : Numpy est une librairie Python permettant de faciliter la manipulation de matrices, de tableaux multidimensionels et des fonctions mathématiques.
- [**PyGame**](https://www.pygame.org/) : Pygame est un ensemble de modules Python conçus pour écrire des jeux vidéo.

### Facteurs inflent sur la propagation d'un feu:

**Le vent**:

Les vents ont peut-être la plus grande influence sur le comportement des feux de forêt et sont également le facteur le plus imprévisible. Le vent alimente le feu en oxygène supplémentaire, séchant davantage les matériaux et poussant le feu à travers la terre à un rythme plus rapide.

Les vents affectent non seulement la façon dont un incendie se déclare mais aussi comment il se propage. Plus le vent souffle fort, plus le feu se propage rapidement. Les vents peuvent également changer la direction du feu.

**La température**:

La température affecte le déclenchement des incendies de forêt, car la chaleur est l'un des trois coins du triangle du feu (combustible, comburant, chaleur) .Les restes d'arbres et de plantes au sol reçoivent la chaleur du soleil, qui chauffe et sèche les matériaux. Des températures plus chaudes permettent au carburant de s'enflammer et de brûler plus rapidement, ce qui augmente le taux d'incendies de forêt. 

**Humidité**:

Alors que le vent aide à propager le feu, l'humidité agit contre le feu. L'humidité (sous forme d'humidité ou de précipitations) peut ralentir un incendie et réduire son intensité. Les matériaux peuvent être difficiles à enflammer s'ils contiennent des niveaux élevés d'humidité, car l'humidité absorbe la chaleur d'un incendie. Plus l'humidité est élevée, moins le matériau risque de se dessécher et de s'enflammer.
Étant donné que l'humidité peut réduire les risques d'incendie de forêt, les précipitations ont un impact direct sur la prévention des incendies.


### Bibliographie :
- https://www.agrimaroc.org/index.php/Actes_IAVH2/article/view/325/260
- https://www-sciencedirect-com.accesdistant.sorbonne-universite.fr/science/article/pii/S1470160X22001248?via%3Dihub

### Raisonnement et observation :
- Nous avons commencé par trouver un algorithme permettant tout d'abord de modéliser la propagation d'un feu de forêt sans nécessairement avoir de paramètre. Pour cela, il nous a fallu commencé par les bases : modéliser une forêt par une liste de liste sur Python, créer une fonction permettant de mettre le feu à un arbre de la forêt, programmer une fonction de propagation, etc...
- Pour propager un forêt, il nous a fallu programmer un "jeu de la vie" suivant un certain nombre de voisins. Pour déterminer le nombre de voisin, il existe deux types de voisinage : le voisinage de Von Neumann considère qu'un point possède 4 voisins (haut, bas, gauche, droite) tandis que le voisinage de Moore considère qu'un point en possède 8 (haut, bas, gauche, droite, ainsi que les diagonales). Dans notre cas, nous utilisons le voisinage de Von Neumann plutôt que le voisinage de Moore puisque cela illustre mieux la réalité.
- Pour rendre ce programme visible, nous avons utilisé les fonctions de Pygame pour modéliser cette propagation. Nous avons utilisé la bibliothèque Pygame plutôt que Tkinter ou Matplotlib pour des raisons d'efficacité et de simplicité.

Densité : 90% d'arbre
![Propagation d'un feu de forêt](https://s7.gifyu.com/images/enregistrement-de-lecran-2022-04-15-a-181849-v1u5zifc_iKGJvaBP.gif)

- A partir de ce modèle, nous avons essayé de créer des variantes dépendant de paramètre : densité, météo, ...

- La variante dépendant de l'humidité se base sur le même principe que la modélisation précédente, la seule différence est l'ajout de probabilité lors de la propagation du feu. Pour chaque voisin, nous générons une probabilité en fonction du taux d'humidité (compris entre 0 et 1). Ainsi, plus le taux d'humidité est élevé, plus les probabilités de propager le feu aux voisins est faible.

Humidité : 30% d'humidité
![Propagation d'un feu de forêt + Humidité](https://s7.gifyu.com/images/enregistrement-de-lecran-2022-04-15-a-184205-iqlvjjrh_8FlyrZkK.gif)

- La variante dépendant de l'humidité se base sur le même principe que la modélisation précédente, la seule différence est l'ajout de probabilité lors de la propagation du feu. Ici, on va définit un unique sens (droite), la probabilité de propager le feu aux voisin du haut et du bas et de 0.5 (1 chance sur 2) tandis que la propabilité de propager le feu au voisin de gauche est de 10% (contre 90% pour le voisin de droite).

Vent : vers la droite
![Propagation d'un feu de forêt + Vent](https://s7.gifyu.com/images/enregistrement-de-lecran-2022-04-15-a-185258-gmrxkyjx-rqgxjywc_hMuIZXZE.gif)

### Interprétation :


### Conclusion :



You can use the [editor on GitHub](https://github.com/ARE-dynamic-2022-G2-ScFo21-2B/Propagation_feu/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.Et plus précisément quels facteurs influent sur leur multiplication, leur intensité ou leur propagation. En effet, outre la prévention de ces feux, intervenir rapidement et efficacement est également synonyme de vies sauvées et de forêts préservées.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown
Et plus précisément quels facteurs influent sur leur multiplication, leur intensité ou leur propagation. En effet, outre la prévention de ces feux, intervenir rapidement et efficacement est également synonyme de vies sauvées et de forêts préservées.
Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

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

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes
PythonGame: https://youtu.be/LrcMOeUN1qI

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/ARE-dynamic-2022-G2-ScFo21-2B/Propagation_feu/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
