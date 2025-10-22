# Exercice
## Les conditions
### Système de recommandation

Créer un système de recommandation qui conseille le bon film en fonction de l'âge de l'utilisateur

> Si l'utilisateur a moins de 13 ans (13 ans inclu) on lui affichera "Lilo & Stitch"
> 
> Si l'utilisateur a plus de 13 ans et moins de 18 ans (strictement) on lui affichera "Matrix" (je sais c'est un peu jeune)
> 
> Si l'utilisateur a plus de 18 ans on lui affichera "Evil Dead"

On commencera avec le code suivant

```js
const currentYear = 2025
const birthyear = prompt('Quel est votre année de naissance ?')
// Ecrire votre code ici, afficher le film à l'aide de console.log('votre réponse")
```

### Multiplication

On souhaite créer une calculatrice simplifiée qui est capable de multiplier 2 nombres et de nous donner le signe du résultat. L'objectif est d'afficher nombre1 x nombre2 = resultat est positif

On commencera avec la base suivante

```js 
const a = prompt('Entrez un premier nombre')
const b = prompt('Entrez un second nombre')
```
## Les boucles
### Décompte

Pour cet exercice on demandera à l'utilisateur (à l'aide de prompt) un nombre entre 0 et 10, on affichera ensuite tous les chiffres sous le nombre indiqué par l'utilisateur (s'il rentre 4, on affichera 4, 3, 2, 1, 0). Si l'utilisateur rentre un chiffre erroné on affichera un message d'erreur.

### Deviner le chiffre

On créera une variable guess qui contiendra un nombre entre 0 et 10, l'objectif sera ensuite de faire deviner ce chiffre à l'utilisateur. Si l'utilisateur se trompe on lui donnera une indication "plus" ou "moins" pour l'orienter vers la bonne réponse.

## Les fonctions personnalisé
### Deviner le nombre

 On crée un nombre aléatoire entre 0 et 10, ensuite on demandera à l'utilisateur de deviner ce nombre avec 3 essais. Pour créer la logique on utilisera des fonctions spécifiques

- Une fonction isRight(n) qui renverra un booléen si l'utilisateur à la bonne réponse ou non
- Une fonction guess() qui permet de faire un essai, cette fonction renverra true ou false en fonction de la réponse donnée

### Les nombres premiers

Créer une fonction isPremier() qui permet d'indiquer si un nombre est premier

```js 
console.log('0', isPremier(0))      // false
console.log('1', isPremier(1))      // false
console.log('2', isPremier(2))      // true
console.log('3', isPremier(3))      // true
console.log('11', isPremier(11))    // true
console.log('12', isPremier(12))    // false

```

## Les fonctions
### Le palindrome 

L'objectif de cet exercice est de créer une fonction isPalindrome() qui renverra vrai si un mot est un palindrome et false sinon. La fonction ne sera pas sensible à la casse.

```js
console.log(isPalindrome('kayak')) // true
console.log(isPalindrome('SOS')) // true
console.log(isPalindrome('Kayak')) // true
console.log(isPalindrome('Bonjour')) // false
```
Pour cet exercice vous aurez besoin d'utiliser des fonctions que l'on n'a pas encore vues mais c'est l'occasion d'essayer de voir comment lire la documentation :

- [split](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/String/split)
- [reverse](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse)
- [join](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Array/join)
- [toUpperCase](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/String/toUpperCase)


## Moyenne
Dans cet exercice on souhaite modifier l'objet suivant pour ajouter une propriété moyenne qui contiendra la moyenne de chaque élève.

```js
const students = [
    {
        name: 'John',
        notes: [1, 20, 18, 19, 12]
    },
    {
        name: 'Jane',
        notes: [17, 18, 20, 13, 15]
    },
    {
        name: 'Sophie',
        notes: [17, 12, 14, 15, 13]
    },
    {
        name: 'Marc',
        notes: [2, 3, 5, 8, 9]
    },
    {
        name: 'Manon',
        notes: [18, 17, 18, 19, 12]
    }
]
```

Une fois cet objet modifié on créera un top 3 des élèves.

Pour cet exercice vous aurez besoin de la fonction [sort](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Array/sort).

### Calculateur de fréquence
#### partie 1
Nous allons créer un système capable de calculer la fréquence des mots dans une chaine de caractère. L'objectif sera dans un premier temps d'obtenir un objet qui contiendra en propriété le mot, et en valeur le nombre d'occurence ({bonjour: 3, maison: 2})

```js
const phrase = `Vous savez, moi je ne crois pas qu’il y ait de bonne ou de mauvaise situation. Moi, si je devais résumer ma vie aujourd’hui avec vous, je dirais que c’est d’abord des rencontres.`
```

Pour cet exercice on nettoiera la chaine en retirant les caractères qui ne sont pas des mots (, ? : ...). Pour cela vous aurez besoin de la fonction [replaceAll](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/String/replaceAll). Vous aurez aussi besoin de mettre la phrase en minuscule à l'aide de [toLowerCase](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/String/toLowerCase)

#### partie 2

Maintenant vous devez ajouter de la logique pour extraire le top 3 des mots les plus utilisé dans la phrase.