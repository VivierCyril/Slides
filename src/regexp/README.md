# À propos de ce tutoriel

Je vous propose de découvrir ensemble le principe des expressions régulières. Les expressions régulières sont un moyen d'identifier certains motifs dans une chaîne de caractères et vont avoir plusieurs utilités.

- Détecter des motifs dans une chaîne de caractères
- Valider le format d'une chaîne de caractère
- Remplacer du texte de manière intelligente en conservant certains éléments.

## Format général

Une expression régulière sera délimitée par des slashs à l'intérieur desquels on va pouvoir mettre une expression pour décrire le motif que l'on souhaite reconnaître. Ce motif va être composé de plusieurs éléments :

### Les symboles

En premier lieu on aura les symboles qui vont permettre de détecter un ou plusieurs caractères. Pour vous donner les plus importants :

- a, b, é..., permet de chercher un symbole particulier.
- [a-z], [0-9], [A-Z0-9], fera correspondre une plage de caractère.
- [^0-9], est la négation, fera correspondre n'importe quel caractère qui n'est pas un nombre (ou autre en fonction de ce que l'on met dans les croches).
- . correspondra à n'importe quel caractère.
- \d pour un nombre.
- \s pour un espace.
- ^ pour identifier le début d'une chaîne
- $ pour identifier la fin d'une chaîne

Vous pouvez retrouver tous les symboles communs dans la partie "Quick Reference" de Regex101. Avec ces symboles il est possible par exemple de trouver le mot "tonte", "tante" et "tente" dans une chaîne.
```
/t[aeo]nte/
```
### Les quantificateurs

On a ensuite la possibilité de définir la quantité de symboles que l'on veut en utilisant les quantificateurs.

- {2}, {10}, permet de chercher X fois le motif précédent.
- {1,10}, permet de chercher le motif répété 1 à 10 fois.
- {2,}, permet de chercher le motif répété 2 fois ou plus.
- *, permet de chercher le motif répété 0 ou plusieurs fois.
- +, permet de chercher le motif répété 1 fois ou plus.
- ?, permet de chercher le motif répété 0 ou une fois.

Vous pouvez retrouver tous les quantificateurs dans la partie "Quick Reference" de Regex101.

Par exemple si je souhaite trouver le mot "helllllo" :
```
/hel{5}o/
```
### Les groupes

Enfin, on a aussi la possibilité de créer des groupes afin de pouvoir répéter certains motifs mais aussi pour les extraire dans le résultat final. Pour cela on utilisera des parenthèses. Par exemple si je souhaite trouver le mot "papapa" je pourrais utiliser un groupe pour éviter la répétition.
```
/(pa){3}/
```
Les groupes seront aussi renvoyé lorsque l'on utilisera l'expression régulière, par exemple si on a une heure avec ce format XXhXXminXXs on peut récupérer l'heure, les minutes et les secondes.
```
/^(\d{2})h(\d{2})min(\d{2})s$/
```
On peut aussi faire référence à ces groupes lors des remplacements à l'aide de $ suivi du numéro de groupe. Par exemple $1 fera référence à l'heure dans notre exemple précédent.

### Les drapeaux

Les drapeaux permettent de modifier le comportement général d'une expression régulière et s'applique en utilisant un caractère après le slash final.

- g, permet de faire une recherche global (on ne s'arrète pas à la première correspondance)
- m, permet de faire une recherche multiligne ou ^ correspondrant au début d'une ligne et $ à la fin d'une ligne
- i, permet de faire une recherche non sensible à la casse [a-z] capturera un A par exemple.

Il en existe d'autres mais ce sont les 3 principaux que l'on va retrouver très souvent sur une expression régulière (ils peuvent d'ailleurs être combinés en les mettant les uns à la suite des autres).
```
/bonjour/gi
```

### Tester et déboguer via Regex101

Une expression régulière s'écrit rarement du premier coup il est donc important d'avoir un outil pour pouvoir l'écrire et la tester plus facilement. Il existe plusieurs sites qui vont vous permettre d'écrire des expressions régulières mais mon préféré à l'heure actuelle est Regex101. Il intègre plusieurs outils intéréssant :

- Support de plusieurs version de moteur d'expression régulière (pour assurer la compatibilité de ce que l'on tape)
- Mise en surbrillance des groupes de captures
- Quick Reference qui sert de pense-bête pour les différents motifs identifiables
- Un mode debugger qui permet d'éxécuter une expression pas à pas pour comprendre son fonctionnement

Pour utiliser le site il vous suffit de taper dans le grand champs votre texte, puis d'écrire votre expression pour avoir un retour visuel sur son effet.