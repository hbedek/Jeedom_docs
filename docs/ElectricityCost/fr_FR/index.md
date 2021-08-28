# Plugin Electricity Cost

Ce plugin permet de calculer la consommation de vos appareils électriques et des coûts associés en fonction de votre contrat fournisseur.

Le plugin peut:
- Calculer le coût d'un plugin suivant sa consommation kWh, sa puissance W ou kW, son état (Allumé-Eteint)
- Comparer les dépenses énergétiques de vos équipement par rapport au compteur
- Trouver les équipements les plus energivores

Pour pouvoir utiliser le plugin à son plein potentiel, vous devrez créer un équipement "Contrat" puis un équipement "Compteur".

Il est possible de se passer de ces deux équipements mais le plugin ne calculera alors que la consommation et non les coûts associés.

Pour créer un équipement, cliquez sur le bouton +

<img src="IMGS/eqs_plugin.PNG" alt="hi" class="inline"/>


## Equipement Contrat

L'équipement contrat est le premier équipement à créer. Il représente le contrat qui vous lie à votre fournisseur. Vous pourrez par la suite lié des équipements à ce contrat pour mesurer les coûts. 
L'équipement contrat ne possède pas de commandes mais doit tout de même être configuré.

1) Sélectionnez Contrat dans le champ ci dessous:
<img src="IMGS/dropdown_contrat.PNG" alt="hi" class="inline"/>

2) Choisissez votre type de contrat. Soit heures pleines / heures creuses, soit tout simplement heures pleines.

3) Suivant le contrat choisit, remplissez le début / fin des heures creuses ainsi que les prix au kWh de votre fournisseur d'électricité

Exemple:
<img src="IMGS/ex_config_contrat.PNG" alt="hi" class="inline"/>


## Equipement Compteur

L'équipement Compteur, représente votre compteur électrique et sa consommation.
Pour utiliser pleinement les fonctionnalité du plugin, il faut au préalable créer un équipement Contrat

### Configuration d'un compteur

Pour configurer un compteur:

1) Sélectionnez "Compteur" dans la champ de choix des équipements:
<img src="IMGS/dropdown_compteur.PNG" alt="hi" class="inline"/>

2) Choisissez une période de raffraîchissement pour cet équipement. Le plugin ne va pas récupérer les informations en temps réel et son raffraîchissement n'aura lieu que si vous remplissez cette commande.

3) Sélectionnez l'information que le plugin va utiliser pour calculer la consommationen kWh cumulée. Si votre compteur est un compteur ENEDIS, je vous conseille de prendre la puissance moyenne horaire de votre compteur (appelée consommation horaire sur le plugin ENEDIS):
<img src="IMGS/config_compteur.PNG" alt="hi" class="inline"/>

4) Sélectionnez la commande remontant la puissance horaire du compteur

5) Sélectionnez l'unité de la puissance (ENEDIS: kW)

L'équipement est configuré mais tel quel, il ne remontera pas les coûts associés. Pour cela vous devez lier cet équipement à un contrat:
<img src="IMGS/config_linked_contrat.PNG" alt="hi" class="inline"/>

Sélectionnez dans le champ qui apparaît en dessous le Contrat auquel le plugin doit lier cet équipement.

SAUVEGARDEZ l'équipement pour créer les commandes


### Informations remontées par l'équipement compteur

Cet équipement vous remontera les informations suivantes:
- Puissance
- Consommation
- Coût journalier (si vous avez lié un contrat)
- Coût mensuel (si vous avez lié un contrat)
- Coût toutes périodes confondues (si vous avez lié un contrat)
- Equipements liés (renvoie tous les équipements qui sont liés au compteurs, voir la catégorie autres équipements)
- Le pourcentage cumulé du coût mensuel de tous les équipements liés a compteur par rapport à ce dernier
- Le dépassement d'un budget pré-définit [BETA]
- Le pourcentage de consommation en heures creuses [BETA]
- L'économie réalisée si l'équipement fonctionnait uniquement en heures creuses [BETA]

La commande pourcentage cumulé vous permet de mieux comprendre la consommation de votre logement.


## Autres équipements

Cette catégorie regroupe tous les équipements en dehors du compteur pour lesquels vous souhaitez calculer la consommation.
Le plugin peut calculer le coût d'un équipement suivant :
- la consommation cumulée
- la puissance consommée
- l'état de l'équipement (Allumé / Eteint).

Bien sûr le plus précis reste la consommation cumulée en kWh.

Dans la configuration, choisissez "Equipement" et la période de raffraîchissement:
<img src="IMGS/config_eq_1.PNG" alt="hi" class="inline"/>

Les trois types d'équipements renvoient les mêmes commandes que le Compteur.

### Configuration d'un équipement suivant sa consommation cumulée kWh

Cette configuration est la plus précise.
Choisissez la commande qui va renvoyer la consommation cumulée pour cet équipement.
ATTENTION: cette commande doit être historisée, suivant la période de rafraîchissement sélectionnée, le plugin peut être amené à récupérer des informations historisées.

### Configuration d'un équipement suivant sa puissance instantanée

Choisissez la commande qui va renvoyer la puissance  instantanée pour cet équipement.
ATTENTION: cette commande doit être historisée, suivant la période de rafraîchissement sélectionnée, le plugin peut être amené à récupérer des informations historisées.

Choisissez ensuite l'unité de la puissance renvoyée par la commande que vous avez saisit.

### Configuration d'un équipement suivant sa puissance moyenne [BETA]

Cette configuration diffère de la puissance instanée, ici la commande que vous allez saisir renvoie une moyenne de puissance sur une plage de temps. Le compteur électrique du plugin ENEDIS par exemple renvoie la puissance moyenne par demi heure.
ATTENTION: cette commande doit être historisée, suivant la période de rafraîchissement sélectionnée, le plugin peut être amené à récupérer des informations historisées.


### Configuration d'un équipement suivant son état

Cette configuration est la moins précise mais permet cependant d'avoir une estimation du coût des équipements ne remontant qu'un état comme une lampe, une télévision, un amplificateur etc
<img src="IMGS/config_eq_2.PNG" alt="hi" class="inline"/>

Renseignez la commande remontant l'état de l'équipement.
ATTENTION: cette commande doit être historisée, suivant la période de rafraîchissement sélectionnée, le plugin peut être amené à récupérer des informations historisées.

Renseignez la puissance que consomme cet équipement allumé et la puissance que consomme cet équipement éteint.

Renseignez l'unité des puissances que vous avez renseigné.


## Lier un équipement à un compteur

Vous pouvez lier tous les équipements que vous avez créé sur ce plugin ou les plugins compatibles à Electricity Cost à un compteur.

En liant un équipement à un compteur, l'équipement récupère le contrat lié au compteur mais permet également d'obtenir plus d'informations:
- Chaque équipement lié vous renverra alors le pourcentage que représente le coût mensuel de l'équipement par rapport au coût mensuel du compteur.
- Le compteur vous renverra les équipements qui lui sont associés.
- Le compteur vous renverra le cumul du pourcentage de tous les équipements liés (Permet d'investiguer des éventuels problèmes de consommation électrique dans votre foyer).

ATTENTION: Le pourcentage se basant sur le coût mensuel, les pourcentages ne sont vraiment exploitable que passé un mois.

## Calcul du coût pour les équipements Etat / Puissance instantanée

Prenons un exemple pour expliquer le fonctionnement:
Je possède un téléviseur qui est soit allumé (état 1), soit éteint (état 0).
Lorsque que mon téléviseur est allumé, sa puissance est de 100 W, lorsqu'il est éteint sa puissance est de 0,3W.
Je possède un contrat Heures creuses / Heures pleines avec le début des heures creuses à 22h04.

Afin de calculer les coûts, le plugin se base sur l'historique de l'état de l'équipement.
Si j'allume ma télévision à 21h, et que je l'éteint à 23h, le plugin devrait calculer que j'ai consommé 100W pendant 2h. Cette consommation chevauche une période heures creuses / heures pleines. Le plugin décomposera alors la consommation pour établir la consommation avant le début des heures creuses et après le début des heures creuses.

En image:
<img src="IMGS/etat_elec.PNG" alt="hi" class="inline"/>
Ici l'état de ma télévision

<img src="IMGS/puissance_elec.png" alt="hi" class="inline"/>
Ici la puissance de ma télévision en ayant décomposé début heures creuses / fin heures creuses

<img src="IMGS/consommation_elec.png" alt="hi" class="inline"/>
Ici la consommation de ma télévision qui prends bien en compte le début de l'heure creuse


## Compatibilité des plugins

Ce plugin est compatible avec le plugin Laundry.
Si vous créé un équipement sur le plugin Laundry et qu'Electricity Cost est installé sur votre Jeedom, Laundry vous proposera de configurer votre équipement avec les mêmes paramètres que les équipements d'Electricit Cost.

Voici la documentation du plugin:
<a href="https://hbedek.github.io/Jeedom_docs/docs/Laundry/fr_FR/">ICI</a>

## Que faire si le plugin ne renvoie pas les informations:
1) Vérifier que la configuration de l'équipement est bien complète
2) Vérifier que les commandes que l'on a saisit dans la configuration de l'équipement soient bien historisés
3) Vérifier que les commandes Etat / Puissance / Consommation / Coût total soient bien historisées pour cet équipement
