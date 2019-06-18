---
id: Générateur de PLD
title: Générateur de PLD
---
# Générateur de PLD

Le générateur de PLD (Project Log Document) permet de générer l'organigramme des livrables ainsi que les cartes des livrables.

Les information permettant de générer ces diagramme sont récupéré grace a l'api d'asana. Les taches sont arrangé dans un format spécifique sur asana afin des pouvoir les reccupérer dans un ordre précis qui est le suivant:
````
Nom du sprint
├── Livrable 1
|   ├── Carte 1
|       ├── Storie 1
|       └── Storie 2
|   └── Carte 2
|       └── Storie 1
├── Livrable 2
|   ├── Carte 1
|       ├── Storie 1
|       └── Storie 2
|   └── Carte 2
|       ├── Storie 1
|       └── Storie 2
└── Livrable 3
	└── Carte 1
````

# La génération

Les diagramme sont généré grace aux informations récupéré par l'api. Chaque élément récupéré vas générer un fichier xml utilisant des balise spécifique de la librairie [JGraphX](https://www.jgraph.com/) comme la balise \<mxCell> qui sont ensuite exporter en un diagramme en format svg a l'aide d'un package nodejs qui s'appelle **[drawio-batch](https://github.com/languitar/drawio-batch)** qui est un module permettant de simuler le comportement de l'application drawio. Dans le cas du générateur de PLD on utilise que la partie import d'un fichier xml pour l'exporter en un diagramme au format svg.
Ce code xml:

    <mxCell id="68060688" parent="2" style="rounded=1;fillColor=#23445D;gradientColor=none;strokeColor=none;fontColor=#FFFFFF;fontStyle=1;fontFamily=Montserrat;whiteSpace=wrap;fontSize=15" value="Générateur de PLD" vertex="1">  
		<mxGeometry as="geometry" height="80" width="200" x="880.0" y="250.0"/> 
	</mxCell>
Génère une cellule comme celle-ci

![enter image description here](https://lh3.googleusercontent.com/WjFq-Yf6hPcwJ70jk632rnmw_i3JhO7ETAHP0wfg4GowEiq5ibDQgqtioMpxTpUQqw70oz62ru9y)

# L'organigramme des livrables

L'organigramme des livrable après génération est représenter sous cette forme là, avec, a la racine le nom du projet, en dessous a l'horizontale ce trouvent les livrable, puis en dessous des livrables a la verticale ce trouvent les cartes associé a leurs livrables. 
![enter image description here](https://lh3.googleusercontent.com/ad9XQLEZ8xdxyp41MUh1nD__DT55yYegbDqF_rcZShahOCzcfc-wc9VOkH886ekH3czcFB7QuSkR)

# Les cartes des livrables

Chaque carte sera généré de cette manière avec, a la racine le nom du livrable généré, en dessous a l'horizontal les cartes associées a ce livrable, et en dessous de celles-ci, a la verticale se trouvent les stories associées a ces cartes

![enter image description here](https://lh3.googleusercontent.com/dZciWd66c4ehIlAYBbfCaawfOuDpccupQoZuT0f0kIwIBoeDi1QhQL1N6UU2OV9xmgC6z1f_-KAv)

