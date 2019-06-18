---
id: Doc Python
title: Doc Python
---
# Python

Python est un language interprété simple de prise en main. De par sa syntaxe simple il apporte une clareté dans la lécture du code du moment que la personne qui écrit ce code suis les **"best practice"** dictés par [PEP 8 (Python Enhancement Proposals)](https://www.python.org/dev/peps/pep-0008/) créé par la Python Software Foundation

# Syntaxe

Du fait que Python est un language interprété et que sa syntaxe obéit à moins de règles par rapport à d'autres langages, il est très facile d'écrire de petit programme. Prenons par exemple le simple fait d'affichier **"Hello World"** sur la console en Java ce la s'écrit de la manière suivante:
	

    class HelloWorld {
	    public static void main(String[] args)
	    {
		    System.out.println("Hello World");
		}
	}
Alors que en Python ce code s'écrit simplement comme ceci:

    print("Hello World")

De même du fait que la syntaxe python est indentée et non par bloc comme le java ou le C cela permet de produire un code plus rapidement

    def main():
	    print("Hello World")
Attention toutefois à ne pas produire des fonctions trop volumineuse afin de ne pas perdre la simplicité de lecture, mieux vaut faire de petite fonction et de nommer ses variables et fonctions avec des nom explicite, car on se retrouve très vite avec des gros pavés où l'on se pert très facilement.

    def queens(n): 
	    a = list(range(n)) 
	    up = [True] * (2 * n - 1) 
	    down = [True] * (2 * n - 1) 
	    def sub(i): 
	        for k in range(i, n): 
	            j = a[k] 
	            p = i + j 
	            q = i - j + n - 1 
	            if up[p] and down[q]: 
	                if i == n - 1: 
	                    yield tuple(a) 
	                else: 
	                    up[p] = down[q] = False 
	                    a[i], a[k] = a[k], a[i] 
	                    yield from sub(i + 1) 
	                    up[p] = down[q] = True 
	                    a[i], a[k] = a[k], a[i] 
	    yield from sub(0) 
  
	sum(1 for a in queens(8))
Dans ce cas là une seul erreur d'indentation et le scripte peut fonctionner mais ne pas faire ce que l'ont voulais

# Gestionnaire de Paquet

Le gestionnaire de paquet python **[PyPI](https://pypi.org/)** pour **Python Package Index** est le dépôt officiel de python, contenant près de 180000 modules apportant des scripts près a l'emploie afin de simplifier l'écriture de code. Dans le cas du projet de générateur de PLD l'utilisation des module [python-asana](https://pypi.org/project/asana/#description) et [Flask](https://pypi.org/project/Flask/) simplifie grandement la communication entre le script et l'API d'asana.

	import asana
	
	class AsanaSprint:  
	    def __init__(self, token):  
	        self.access_token = token  
	        self.client = asana.Client.access_token(self.access_token)

