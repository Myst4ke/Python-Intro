# Intro au Python 
Ce README a pour but de permettre aux personnes ayant du mal avec l'apprentissage de Python de mieux appréhender le langage grâce à des exemples détaillés.
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
<br>

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
### Slicing


## Boucles


## Fonctions
### Type annotation


## Classes
