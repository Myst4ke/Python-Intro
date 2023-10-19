# Intro au Python 
Ce README a pour but de permettre aux personnes ayant du mal avec l'apprentissage de Python de mieux appréhender le langage grâce à des exemples détaillés.


## Table des Matières
- [**Les variables**](#les-variables)
- [**Les types de base en Python**](#les-types-de-base)
- [**Les opérateurs**](#les-opérateurs)
  - [Les opérateurs de calcul](#les-opérateurs-de-calcul)
  - [Les opérateurs logiques & de comparaison](#les-opérateurs-logiques--de-comparaison)
<br>

- [**Listes et Strings**](#listes-et-strings)
  - [Accès aux Éléments de la Liste](#accès-aux-éléments-de-la-liste)
  - [Opérations sur les Listes](#opérations-sur-les-listes)
    - [*Concaténation de Listes*](#concaténation-de-listes-)
    - [*Répétition de Listes*](#répétition-de-listes-)
  - [Slicing](#slicing)
  - [Strings](#strings)
    - [*Méthodes*](#méthodes)
    - [*Formatted Strings*](#les-formatted-strings) 
<br>

- [**Boucles & Conditions**](#boucles--conditions)
  - [Conditions](#conditions)
  - [Boucles](#les-boucles)
    - [*La boucle for*](#la-boucle-for)
    - [*La boucle while*](#la-boucle-while)
<br>

- [**Fonctions**](#fonctions)
  - [Portée des Variables](#portée-des-variables)
  - [Fonction Main](#fonction-main)
  - [Arguments](#arguments)
    - [*args et kwargs*](#args-et-kwargs)
  - [Type annotation](#type-annotation)
<br>

- [**Gestions des fichiers**](#gestions-des-fichiers)
- [**Classes**](#classes)




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
Il est possible en python, malgré le fait que les types soient implicites, de convertir une variable dans un autre type, exemple :
```python
a = 34
a_string = str(a)
print(a_string)
print(type(a_string))
```
> "34"
>
> <class 'str'>

**Attention** : certains type ne sont pas convertissable en n'importe quoi, par exemple il est impossible de convertir une `list` en `int`

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

Vous noterez qu'ici le paramètre `step` n'est pas précisé. En effet chaque paramètre peut être délibérement omis. Par défaut si on omet `step` il est défini à `1` il n'est donc pas nécessaire de le préciser. Les deux autres paramètres en revanche eux, sont définis à `0` pour `start` et **la taille de la liste** pour `stop` par défaut.<br>
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

Le pas (`step`) peut être négatif afin d'obtenir une slice inversée, voici un exemple :
```python
liste = [1, 2, 3, 4, 5]
print(liste[::-1])
```
>[5, 4, 3, 2, 1]

<br>

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

``` python
mot = "Python "
repetition = mot * 3  # Répétition du mot trois fois
print(repetition)
```
>Python Python Python 


#### Méthodes
Python propose de nombreuses méthodes pour manipuler les chaînes de caractères. En voici quelques-unes des plus couramment utilisées :

``` python
texte = "Bonjour, Python !"
minuscules = texte.lower()  # "bonjour, python !"
majuscules = texte.upper()  # "BONJOUR, PYTHON !"
remplace = texte.replace("Python", "mon ami Python")  # "Bonjour, mon ami Python !"
indice = texte.find("Python")  # 9 (indice de la première lettre du mot)
occurrences = texte.count("o")  # 3
```
Une autre combinaison de méthodes très utile en python, sont les méthodes `split()` et `join()` elle permettent respectivement, de séparer une chaine de caractères à partir d'un patern (ou un caractère) passé en argument et de fusionner une liste grâce à un autre patern. Voici un exemple :

``` python
texte = "Ceci-est-un-test "
mots = texte.split("-")  # ["Ceci", "est", "un", "test"]
" ".join(mots) # "Ceci est un test"
```
Ici on a séparé la chaine de caractères grâce au patern (`-`) pour ensuite fusionner la liste qui résultait de cette opération grâce au patern (` `). 

#### Les Formatted Strings
En Python, les f-strings, ou formatted strings, sont une manière pratique d'insérer des valeurs de variables dans une chaîne de caractères. Les f-strings sont délimitées par des guillemets ou des apostrophes précédés de la lettre `f` (par exemple, `f"..."` ou `f'...'`).

L'utilisation des f-strings simplifie l'incorporation de variables dans une chaîne en les plaçant entre des accolades `{}` à l'intérieur de la chaîne. Les variables ou expressions placées à l'intérieur de ces accolades sont évaluées et leur valeur est insérée dans la chaîne.

Voici un exemple d'utilisation d'une f-string :
``` python
nom = "Alice"
age = 30
message = f"Bonjour, je m'appelle {nom} et j'ai {age} ans."
print(message)
``` 
>Bonjour, je m'appelle Alice et j'ai 30 ans.

Les f-strings offrent également un formatage avancé en permettant de spécifier comment les valeurs doivent être affichées. Cela peut être utile pour contrôler le nombre de décimales d'un nombre ou pour définir la largeur d'un champ de texte.


``` python
prix = 24.95534
message = f"Le prix est de ${prix:.2f}"
print(message)
``` 
>Le prix est de $24.95

<br>

```python
produit = "Livre"
prix = 19.99
message = f"{produit:10} : ${prix:.2f}"
print(message)
```
<!-- C'est super moche mais jsuis obligé, markdown de golmon -->
>Livre &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: $19.99

<br>
<br>

## Boucles & Conditions
### Conditions
Les **conditions** ou **instructions de contrôle de flux** en Python permettent de prendre des décisions en fonction de conditions spécifiques. Voici quelques-unes des instructions de contrôle de flux les plus couramment utilisées.
L'instruction if est utilisée pour exécuter un bloc de code si une condition est vraie (**cf**: [Les opérateurs logiques](#les-opérateurs-logiques--de-comparaison)). Voici un exemple :
```python
age = 18
if age >= 18:
    print("Vous êtes majeur.")
```
Pour pouvoir tester plusieures condition, le `if` peut être combiné avec la condition `else` qui permet de gérer les cas ou la condition du `if` n'est pas remplie.
```python
age = 13
if age >= 18:
    print("Vous êtes majeur.")
else:
    print("Vous êtes mineur.")
```
Pour pouvoir ajouter une condition suivant le `if` il est possible d'utiliser le `elif`. Cela permet de rajouter une condition au cas où la première ne serait pas remplie.
```python
note = 13
if note >= 15:
    print("Très bien")
elif note >= 10:
    print("Bien")
else:
    print("Mauvais")
```
Il existe une structure permettant un **enchainement de condition**, l'instruction `match`. L'instruction `match` est utilisée pour effectuer des comparaisons plus complexes et est apparue dans **Python 3.10** (*Attention à votre version de python*). Elle permet de faire correspondre une valeur à des modèles et d'exécuter le code associé à un modèle correspondant.
```python
fruit = "pomme"
match fruit:
    case "pomme":
        print("C'est une pomme.")
    case "banane":
        print("C'est une banane.")
    case _:
        print("Je ne sais pas quel fruit c'est.")
```
Il faut aussi savoir qu'il est possible de **combiner des condition** grâce aux opérateurs logiques `and` et `or` de la manière suivante.
```python
note = 19
if note >= 18 and note <= 20:
    print("Excellent !")
```
<br>

### Les Boucles
Les boucles en Python sont utilisées pour répéter des actions un certain nombre de fois ou jusqu'à ce qu'une **condition spécifique soit satisfaite**. Il existe deux types principaux de boucles en Python : la boucle `for` et la boucle `while`. On utilise plus souvent la boucle `for` de part sa facilité d'écriture mais aussi pour se prévenir des boucles infinies.

#### La Boucle for
En Python, une boucle `for` prend généralement **une séquence** comme paramètre d'itération. Cette séquence peut être une *liste*, un *tuple*, une **chaîne de caractères**, un **dictionnaire**, un **ensemble** ou **tout autre objet itérable**. La boucle `for` parcourt ensuite les éléments de cette séquence, un par un. Pour parcourir une liste deux méthodes sont disponibles :

**La méthode plus "Python" :**
```python
liste = [1, 2, 3, 4, 5]
for chiffre in liste:
    print(chiffre)
```
Dans ce cas on défini `chiffre` comme élément de la liste qui va prendre tour à tour toutes les valeures de la liste.

<br>

**La méthode classique des autres langages :**

```python
liste = [1, 2, 3, 4, 5]
for i in range(len(liste)):
    print(liste[i], end=' ')
```
>1 2 3 4 5

Dans cet exemple on accède à chaque élément de la liste grâce à son indexe. Pour cela on utilise `range()` qui permet de créer un **itérateur** (une séquence de valeures) allant jusqu'à la taille renseigné en paramètre, ici la longueur de la liste (`len(liste)`).

*Vous noterez qu'ici on utilise le paramètre `end` de la fonction print afin de ne pas revenir à la ligne, il est par défaut défini à "\n" (retour à la ligne).*


**N-B** : Le nom de l'élément de la liste n'a pas d'importance (ici `chiffre`), par convention si il n'est pas utilisé dans la boucle on le définit à `_`
<br>

Vous pouvez également utiliser des conditions pour contrôler l'exécution d'une boucle for. Par exemple, vous pouvez utiliser l'instruction break pour sortir prématurément de la boucle lorsque certaines conditions sont remplies.
```python
nombres = [1, 2, 3, 4, 5]
for nombre in nombres:
    if nombre == 3:
        break
    print(nombre)
```
Dans cet exemple, la boucle `for` parcourt la liste `nombres`, mais elle s'arrête prématurément lorsque le nombre 3 est atteint en utilisant l'instruction `break`. À l'inverse l'instruction `continue` permet de passer de passer à l'itération suivante si certaines conditions sont satisfaites.

#### La Boucle while
La boucle `while` est utilisée pour répéter un ensemble d'instructions tant qu'une condition spécifique est vraie. À la différence le la boucle for, il est nécessaire de définir explicitement une **condition d'arrêt**. Ce qui fait qu'une boucle while peut être infinie si elle est mal définie. En voici un exemple :

```python
compteur = 0
while compteur < 5:
    print(compteur)
    compteur += 1
```

<br>
<br>

## Fonctions

En Python, vous pouvez définir des fonctions à l'aide du mot-clé `def` suivi du nom de votre fonction, puis des paramètres (si il y en a) entre parenthèses. À la suite de la déclaration de la fonction on trouve le corps de la fonction contenant les différent calculs ou opérations à effectuer lors de l'appel. Une fonction peut tout à fait ne rien faire et avoir un corps vide, pour cela on utlise l'instruction `pass`. 
Voici un apperçu d'a quoi peut ressembler une fonction Python :
```python
def ma_fonction(parametre1, parametre2):
    # Corps de la fonction
    resultat = parametre1 + parametre2
    return resultat
```
Comme dit plus tôt voici une fonction vide, sans arguments ni corps.
```python
def rien():
    pass
```
Dans l'exemple précédent on peut noter l'utilisation de l'intruction `return` qui permet de retourner le "résultat" d'une fonction. En effet cette instruction permet de sortir de la fonction et de renvoyer la valeur mise en paramètre. Il est possible par exemple, de faire un retrun pour chaque option possible d'une condition.
```python
def test_age(age):
    if age >= 18:
        return "Vous êtes majeur."
    else:
        return "Vous êtes mineur."
```
À défaut d'afficher la valeur comme dans les exemples précédents, ici on retourne la valeur pour l'utiliser ou non lors de l'appel de la fonction. Pour appeller une fonction il suffit d'utiliser le nom de la fonction suivi de/des paramètre(s) entre parenthèses (s'il y en a).
```python
réponse = test_age(13)
print(réponse)
```
>"Vous êtes mineur."

Ici on récupère le résultat de la fonction lors de l'appel puis on l'affiche. Notez qu'il est possible d'appeller une fonction qui retourne normalement un résultat sans l'utiliser.
```python
test_age(13)
```
Dans cet exemple on appelle la fonction `test_age` sauf puisque l'on ne récupère pas le résultat, ce code ne fait rien.
<br>

### Portée des Variables
Les variables définies à l'intérieur d'une fonction sont dites locales à la fonction. Cela signifie qu'elles ne sont accessibles qu'à l'intérieur de la fonction. Les variables définies en dehors des fonctions ont une portée globale et peuvent être utilisées dans tout le programme.
```python
total = 0
def ajoute_a_total(nombre):
    total = total + nombre  # Cela provoquera une erreur
ajoute_a_total(5)
```
Dans cet exemple la variable `total` est définie **globalement**, sauf que dans le corps de la fonction on définit de nouveau `total` cette foi **localement** ce qui écrase momentanement la variable `total` globale dans le corps de la fonction. 

L'erreur produite par ce code vient du fait que lors de l'intitalisation de la variable on utilise la valeur de cette même variable ce qui est impossible. Il faut bien comprendre que dès l'instant où l'on écrit `total =`, la variable `total` globale **n'existe plus** dans le corps de la fonction ce qui provoque cette erreur.

Pour palier à cette erreur on peut utiliser l'instruction `global total` avant de re-définir `total`, qui permet de signaler à Python qu'on souhaite utiliser la variable globale.
```python
total = 0
def ajoute_a_total(nombre):
    global total
    total = total + nombre  # Cela ne provoquera plus d'erreur
ajoute_a_total(5)
```
**Attention** : il n'est pas recommandé d'utiliser `global`, il faut en priorité trouver un moyen de ne pas se retrouver dans cette situation.
<br>

### Fonction Main
En Python, il n'est pas obligatoire d'avoir une fonction `main()`. Il est néanmoins courant d'utiliser une fonction `main()` comme point d'entrée principal de votre programme. Cela permet d'organiser et de structurer votre code de manière plus lisible. 

Pour cela on affectue un test `if __name__ == "__main__":` qui garantit que le code dans la fonction main() est exécuté uniquement si le script est exécuté en tant que programme principal et non s'il est importé en tant que module dans un autre script.

```python
def main():
    # Code principal de votre programme
    print("Hello, world!")

if __name__ == "__main__":
    main()
```
<br>

### Arguments 
Vous pouvez attribuer des valeurs par défaut aux paramètres d'une fonction. Cela signifie que si vous appelez la fonction sans spécifier une valeur pour un paramètre, la valeur par défaut sera utilisée.
```python
def saluer(nom, message="Bonjour"):
    print(f"{message}, {nom}!")

saluer("Alice")
saluer("Bob", "Salut")
```
>"Bonjour, Alice!"
>"Salut, Bob!"

#### args et kwargs
En Python, `*args` et `**kwargs` sont des mécanismes puissants qui vous permettent de travailler avec un nombre variable d'arguments dans vos fonctions. Ces notations vous offrent une grande flexibilité lors de la conception de fonctions pour traiter des cas où le nombre d'arguments n'est pas connu à l'avance.

<br>

- `*args` : Arguments Non Nommés

Le terme `*args` signifie "arguments non nommés" (ou "arguments positionnels"). Il vous permet de traiter un nombre variable d'arguments sans nom dans une fonction. Les arguments passés à `*args` sont rassemblés dans un tuple, que vous pouvez ensuite parcourir et traiter dans votre fonction.
```python
def ma_fonction(*args):
    for argument in args:
        print(argument)

ma_fonction(1, 2, 3, "Python")
```
Dans cet exemple, la fonction ma_fonction peut accepter un nombre variable d'arguments non nommés. Les valeurs passées (1, 2, 3, "Python") sont collectées dans le tuple args, puis parcourues et affichées.

<br>

- `**kwargs` : Arguments Nom de Clé - Valeur

Le terme `**kwargs` signifie "arguments nom de clé - valeur" (ou "arguments par mot-clé"). Il vous permet de traiter un nombre variable d'arguments nommés (ou arguments clé-valeur) dans une fonction. Les arguments passés à `**kwargs` sont rassemblés dans un dictionnaire, ce qui vous permet d'accéder aux valeurs associées à des noms de clé spécifiques.

```python
def ma_fonction(**kwargs):
    for cle, valeur in kwargs.items():
        print(f"{cle} : {valeur}")

ma_fonction(nom="Alice", age=30, langage="Python")
```

Dans cet exemple, la fonction ma_fonction peut accepter un nombre variable d'arguments nommés. Les valeurs passées `("Alice", 30, "Python")` sont collectées dans le dictionnaire kwargs, puis parcourues pour afficher les paires clé-valeur. Notez que `items()` est une méthode des dictionnaires pour lister les clés et les valeurs du dictionnaire.
Le dictionnaire `**kwargs` aurait donc la forme :
```python
kwargs = {
    nom = "Alice", 
    age = 30, 
    langage = "Python"
}
```

<br>

### Type annotation
Comme vous l'aurez remmarqué, en Python **il n'est pas nécessaire de préciser le type des variables ainsi que le type de retour des fonctions**. Pour palier à ce potentiel manque d'information, **les annotations de types** permettent aux développeurs de spécifier le type attendu d'une variable ou d'un argument de fonction. Les annotations de types n'affectent pas le comportement du code en temps d'exécution, mais elles sont utilisées pour améliorer la lisibilité de celui-ci. 
Une annotaion de type sur une variable s'effectue en précisant après `:`, le type la dite variable.
```python
test : int = 3
```
<br>

Dans cet exemple l'annotation de type n'est pas vraiment utile car le type est évident. En revanche quand il s'agit de **paramètres de fonction**, les annotations de type sont beaucoup plus utiles pour pouvoir préciser le type d'arguments attendus.
```python
def addition(a: float, b: float) -> float:
    return a + b
```
Ici notre fonction addition précise qu'elle attend des arguments de type `float`. Notez que le type présent après la `->` désigne le type de retour de la fonction. 
Il est possible de spécifier plusieurs type de la manière suivante :
```python
# Utilisation de l'opérateur | pour des annotations de types multiples
def fonction_multitype(valeur: int | float | str) -> None:
    print(valeur)
```



Malgré le fait que les annotations de type précisent le type attendu il est tout à fait possible d'utiliser la fonction `addition()` avec des arguments de type `int`, ou la fonction `fonction_multitype()` avec un argument de type `list`. **Les annotations de type ne sont qu'à but purement informatif.**

Il est néanmoins recommandé d'ajouter des annotations de type à son programme, pour une meilleure compréhension.
## Gestions des fichiers

## Modules 
## Classes

