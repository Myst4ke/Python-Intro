# Intro au Python 
Ce README a pour but de permettre aux personnes ayant du mal avec l'apprentissage de Python de mieux appréhender le langage grâce à des exemples détaillés.


## Table des Matières
- [Les variables](#les-variables)
- [Les types de base en Python](#les-types-de-base)
- [Les opérateurs](#les-opérateurs)
  - [Les opérateurs de calcul](#les-opérateurs-de-calcul)
  - [Les opérateurs logiques & de comparaison](#les-opérateurs-logiques--de-comparaison)
- [Listes et Strings](#listes-et-strings)
  - [Accès aux Éléments de la Liste](#accès-aux-éléments-de-la-liste)
  - [Opérations sur les Listes](#opérations-sur-les-listes)
    - [Concaténation de Listes](#concaténation-de-listes-)
    - [Répétition de Listes](#répétition-de-listes-)
  - [Slicing](#slicing)
  - [Strings](#strings)

- [Boucles](#boucles)

- [Fonctions](#fonctions)
  - [Type annotation](#type-annotation)

- [Classes](#classes)




## Les variables 
Pour définir des varaibles en python aucun type n'est nécessaire. Une variable peut prendre n'importe quel type.
```python
a = "Hello"
a = 32
```
Les types sont implicites, il sont utilisés dans des test ou pour donner des indications sur les arguments des fonctions.
Pour connaitre le type d'une variable on peut utiliser la fonction native de **Python** `type()`
```python
a = 32.3
print(type(a))
```
> <class 'float'>

*Vous noterez qu'à la place de simplement renvoyer le type python précise que la variable appartient à la class `float`.*

Python est entièrment basé sur des classes, presque tout est objet en Python.
Ainsi, lorsque vous créez une variable en lui attribuant une valeur de type : `int`, `float`, ou `str` vous créez une instance de cette classe.
Cela vous permet donc d'utiliser des méthodes présentes dans la classe, exemple avec la classe `str`:
```python
test = "Hello World!"
print(test.lower())

print(test.upper())
```
>hello world!
>
>HELLO WOLRD!
<br>

Ici on utilise respectivement les méthodes `lower()` et `upper()` de la classe `str` qui permettent comme vous l'aurez remarqué de modifier le texte en minuscule ou majuscule.
Il existe une multitude de méthode disponible, vous aurez donc le loisir de les découvrir par vous même.
<br>

#### Les types de base
Voici la liste des différents types de bases en python :
| Type de base       | Description                                      | Exemple                    |
|--------------------|--------------------------------------------------|----------------------------|
| int                | Entier signé                                     | `42`                       |
| float              | Nombre à virgule flottante                       | `3.14`                     |
| str                | Chaîne de caractères                             | `"Hello, World!"`          |
| bool               | Valeur booléenne (True ou False)                 | `True` ou `False`          |
| list               | Liste mutable d'éléments                         | `[1, 2, 3]`                |
| tuple              | Tuple immuable d'éléments                        | `(1, 2, 3)`                |
| dict               | Dictionnaire (tableau associatif)                | `{"clé": "valeur"}`        |
| set                | Ensemble non ordonné d'éléments uniques          | `{1, 2, 3}`                |
| frozenset          | Ensemble immuable d'éléments uniques             | `frozenset([1, 2, 3])`     |
| NoneType           | Type de None (valeur nulle)                      | `None`                     |

Certains peuvent faire peur mais pas de problème il ne sont pas tous autant utiles les uns que les autres.
<br>
<br>

## Les opérateurs

#### Les opérateurs de calcul

| Opérateur    | Description                                 | Exemple                    | Types de données                       |
|--------------|---------------------------------------------|----------------------------|----------------------------------------|
| `=`          | Affectation (assignation de valeur)         | `x = 5`                    | Tous les types                         |
| `+`          | Addition                                    | `5 + 3`                    | `int`, `float`, `str`, `list`, `tuple` |
| `-`          | Soustraction                                | `7 - 2`                    | `int`, `float`                         |
| `*`          | Multiplication                              | `4 * 6`                    | `int`, `float`                         |
| `/`          | Division                                    | `8 / 2`                    | `int`, `float`                         |
| `//`         | Division entière                            | `9 // 2`                   | `int`                                  |
| `%`          | Modulo (reste de la division)               | `10 % 3`                   | `int`                                  |
| `**`         | Exponentiation                              | `2 ** 3`                   | `int`, `float`                         |

<br>

#### Les opérateurs logiques & de comparaison


| Opérateur    | Description                                                          | Exemple                    | Types de données   |
|--------------|----------------------------------------------------------------------|----------------------------|--------------------|
| `==`         | Égalité (comparaison de valeurs)                                     | `a == b`                   | Tous les types     |
| `!=`         | Inégalité (différence de valeurs)                                    | `x != y`                   | Tous les types     |
| `<`          | Inférieur à                                                          | `3 < 5`                    | `int`, `float`     |
| `>`          | Supérieur à                                                          | `7 > 4`                    | `int`, `float`     |
| `<=`         | Inférieur ou égal à                                                  | `2 <= 2`                   | `int`, `float`     |
| `>=`         | Supérieur ou égal à                                                  | `9 >= 8`                   | `int`, `float`     |
| `and`        | Opérateur logique ET                                                 | `True and True`            | `bool`             |
| `or`         | Opérateur logique OU                                                 | `True or False`            | `bool`             |
| `not`        | Opérateur logique NON                                                | `not False`                | `bool`             |
| `is`         | Identité (vérifie si deux objets sont identiques)                    | `x is y`                   | Tous les types     |
| `is not`     | Non-identité (vérifie si deux objets ne sont pas identiques)         | `a is not b`               | Tous les types     |
| `in`         | Appartenance (vérifie si un élément est dans une séquence)           | `3 in [1, 2, 3]`           | Tous les types     |
| `not in`     | Non-appartenance (vérifie si un élément n'est pas dans une séquence) | `4 not in [1, 2, 3]`       | Tous les types     |


**N-B** : l'opérateur `in` peut être utilisé sur des chaines de caractères, `"Hello" in "Hello Wolrd!"` renvoie `True`
<br>
<br>


## Listes et Strings

Une liste est l'une des **structures de données** les plus couramment utilisées en Python. Elle permet de stocker **une collection ordonnée d'éléments**. Les listes sont très flexibles, car elles peuvent contenir des éléments de **différents types**, y compris des nombres, des chaînes de caractères, d'autres listes, et bien plus encore.

La défintion d'un liste en python est assez simple, vous pouvez utiliser des crochets `[]` et séparer les éléments par des virgules.

```python
ma_liste = [1, 2, 3, 4, 5]
```
Comme dit plus tôt une liste peut contenir plusieurs type de donées exemple :

```python
ma_liste = ["Hello", 2, 3.96, True, [1,2]]
```
Ici on peut voir que la liste contient respectivement, une chaine de caractère (`str`), un `int`, un `float`, un booléen (`bool`) et une autre liste (`list`).
<br>

### Accès aux Éléments de la Liste
Les éléments d'une liste sont **indexés**, ce qui signifie que chaque élément a un numéro d'index. L'index du premier élément est 0, le deuxième est 1, et ainsi de suite. Vous pouvez accéder à un élément de la liste en utilisant son index entre crochets. Par exemple :

```python
ma_liste = [1, 2, 3, 4, 5]
premier_element = ma_liste[0]  # Accède au premier élément (1)
deuxieme_element = ma_liste[1]  # Accède au deuxième élément (2)
```
Les indexes peuvent être négatifs ce qui signifie qu'on part de la fin de la liste, exemple :

```python
ma_liste = [1, 2, 3, 4, 5]
premier_element = ma_liste[-1]  # Accède au dernier élément 
deuxieme_element = ma_liste[-2]  # Accède au avant-dernier élément
```
<br>

Les listes sont mutables, ce qui signifie que vous pouvez modifier leurs éléments après leur création. Pour modifier un élément, il suffit d'accéder à son index et de lui affecter une nouvelle valeur.
```python
ma_liste = [1, 2, 3, 4, 5]
ma_liste[2] = 10  # Modifie le troisième élément pour qu'il soit égal à 10
```
Plusieures méthodes de la classe `list` peuvent être très utiles dans la gestion des liste telle que : `remove()`, `append()`, `pop()`, `len()`, `insert()`, etc ... 
`len()` par exemple permet de récupérer la taille d'un objet en l'occurence ici on l'utilise pour des listes.
<br>

### Opérations sur les Listes
Les listes en Python prennent en charge plusieurs opérations qui permettent de les combiner, de les répéter ou de les modifier en utilisant des opérateurs.

#### Concaténation de Listes (+)
L'opérateur `+` permet de concaténer (fusionner) deux listes en une seule. Cela signifie que vous pouvez ajouter les éléments d'une liste à la fin d'une autre liste. Voici un exemple :
```python
liste1 = [1, 2, 3]
liste2 = [4, 5, 6]
resultat = liste1 + liste2  # Concaténation des deux listes
print(resultat)
```
>[1, 2, 3, 4, 5, 6]



#### Répétition de Listes (*)
L'opérateur `*` permet de répéter une liste en créant une nouvelle liste qui contient plusieurs copies de la liste d'origine. Voici un exemple :
```python
liste = [1, 2, 3]
repetition = liste * 2  # Répétition de la liste deux fois
print(repetition)
```
>[1, 2, 3, 1, 2, 3]

<br>

### Slicing
Le slicing est une opération courante lors de la manipulation de listes et de chaînes de caractères en Python. Il permet d'extraire des sous-ensembles de données à partir d'une séquence.

Pour effectuer le slicing, vous pouvez utiliser la notation `[start:stop:step]`, où `start` est l'indice du premier élément inclus dans la tranche, `stop` est l'indice du premier élément exclu de la tranche, et `step` est le pas (l'intervalle entre les éléments).
Voici quelques exemples : 

```python
liste = [1, 2, 3, 4, 5]
sous_liste = liste[1:4:1]  # Extrait les éléments de l'indice 1 à 3 (4 exclu)
print(sous_liste)
```
> [2, 3, 4]

<br>

```python
chaine = "Hello, World!"
sous_chaine = chaine[0:5]  # Extrait les caractères de l'indice 0 à 4 (5 exclu)
print(sous_chaine)
```
>Hello

Vous noterez qu'ici le paramètre `step` n'est pas précisé. En effet chaque paramètre peut être délibérement omis. Par défaut si on omet `step` il est défini à `1` il n'est donc pas nécessaire de le préciser. Les deux autres paramètres en revanche eux, sont définis à 0 par défaut.<br>
Voici des exemples de **slicing** valides :

```python
liste = [1, 2, 3, 4, 5]
sous_liste = liste[::2]  # Extrait les éléments avec un pas de 2 (tous les indices pairs)
```
>[1, 3, 5]

<br>

``` python
liste = [1, 2, 3, 4, 5]
sous_liste = liste[:-2] # Extrait les caractères de l'indice 0 à -2
```
>[1, 2, 3]

<br>

``` python
liste = [1, 2, 3, 4, 5]
sous_liste = liste[-2:] # Extrait les caractères de l'indice -2 jusqu'à la fin de la liste
```
>[4, 5]

### Strings
Les strings (`str`) ou chaîne de caractères, fonctionnent comme des listes. En effet les caractères dans une chaîne de caractères sont **indexés**, tout comme les éléments dans une liste. On peut donc accéder à un caractère particulier en utilisant son indice entre crochets comme pour les listes et utiliser les opérations vu plus tôt.
``` python
texte = "Python"
premier_caractere = texte[0]  # Accès au premier caractère "P"
dernier_caractere = texte[-1]  # Accès au dernier caractère "n"
```
``` python
texte1 = "Hello"
texte2 = "World!"
resultat = texte1 + " " + texte2  # Concaténation des deux chaînes avec un espace entre elles
print(resultat)
```
>Hello World!

<br>

``` python
mot = "Python "
repetition = mot * 3  # Répétition du mot trois fois
print(repetition)
```
>Python Python Python 

<br>


## Boucles


## Fonctions
### Type annotation


## Classes
