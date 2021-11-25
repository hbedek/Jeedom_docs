# Changelog plugin Light Group

# 25/11/2021 [Beta]
Ajout des actions manuelles sur les lumières / prises / groupes de lumières.
Vous pouvez maintenant ajouter des conditions qui une fois réalisées créeront une action manuelle. Par défaut une action manuelle a une priorité de 800 et annule les automatismes dont leur priorité est inférieure.
Une action manuelle est symbolisée par un engrenage barrée sur le widget.
Voir la documentation pour plus d'informations.

INFORMATION 1: comme annoncée le 07/11/2021, les commandes d'autorisation / interdiction des automatismes au niveau des lumières ne sont plus utilisés. Je vous conseille de nettoyer les commandes. Dans un deuxième temps un script de nettoyage automatisera ce processus.

INFORMATION 2: Le plugin venant de passer en Beta, l'objectif des 2 prochaines semaines et d'arrêter l'ajout de nouvelles fonctionnalités, stabiliser le plugin et proposer les automatismes en Stable.

# 09/11/2021 [Beta]
Ajout possibilité de tester les conditions dans les automatismes

# 07/11/2021 [Beta]
- Ajout priorisation des automatismes. Il vous est possible de prioriser les automatismes entre eux. Si un automatisme est déjà en cours sur une lumière, le plugin ira vérifier la priorité du nouvel automatisme avatn de l'appliquer. Un tutoriel suivra pour expliquer ce concept.
- Ajout de 2 nouvelles commandes: "Heure extinction" qui renvoie l'heure d'extinction prévue pour une lumière, "Extinction automatisme" qui renvoie MOV si la lumière vient de percevoir et un mouvement et renvoie un timestamp si la lumière a prévue une extinction.
- Ajout du widget statut_autom. Ce widget renvoie les informations de la commande "Extinction automatisme" mais formattées.
- Ajout d'un widget statut_light qui renvoie uniquement l'état de la lumière.

Il s'agit d'une grosse mise jour sur laquelle je travaille depuis de nombreuses heures. J'espère que le nouveau widget statut_autom vous conviendra.

INFORMATION: Avec l'arrivée des priorisations et la possibilité d'autoriser / interdire un automatisme au niveau de l'automatisme en lui même, je trouve que les commandes d'autorisation / interdiction des automatismes au niveau des lumières perdent leur intêret et pollue l'affichage des commandes. Je pense donc les supprimer dans la prochaine mise à jour.

# 02/11/2021 [Beta]
- Les automatismes ne peuvent allumer que les lumières allumées et ne peuvent éteindre que les lumières allumées (optimisation)
- Il est dorénavant possible de rajouter les prises aux groupes
- Vous pouvez maintenant définir des expressions pour le lever et le coucher du soleil

# 01/11/2021 [Beta]
Ajout d'ids uniques dans les logs d'automatismes pour isoler les tâches

# 31/10/2021 [Beta]
Ajout des prises. Les prises possèdent leur propre icône et il vous est possible de choisir entre 3 icônes dans la configuration.
Le widget des prises possède les mêmes badges que les autres widget du plugin (badge budget dépassé et badge en cours d'automatisme).
Il est possible d'affecter des automatismes à une prise comme pour une lumière. Attention il n'est pas possible pour l'instant de grouper les prises ni de les ajouter au groupe de lumières. Je cherche un moyen d'intégrer cela proprement au plugin afin de ne pas créer la confusion. Si jamais vous avez des idées n'hésitez pas à m'en faire part sur Community.


# 29/10/2021 [Beta]
- Amélioration du niveau de log INFO, moins d'informations, plus à l'essentiel
- Correction BUG ajout des créneaux d'interactions horaires

# 27/10/2021 [Beta]
- Ajout de l'automatisme de gestion de luminosité
- Ajout de l'interaction horaire pour l'automatisme de pièce 
- Amélioration du système de demande de luminosité afin que la lumière se mette directement à la bonne luminosité lors de l'allumage
- Ajout d'un badge sur le widget lorsque le budget est dépassé
- Correction du BUG sur le temps maximum pour l'automatisme pièce
- Correction du BUG de suppression des commandes lors d'une désaffectation d'un automatisme à une lumière
- Ajout de widget par défaut pour les automatismes
- Correction BUG affichage des jours enregistrés

# 22/10/2021 [Beta]
- Ajout de plage de luminosité pour les capteurs de luminosité
- Ajout d'une marge de luminosité. Si la lumière est allumée, elle ne s'éteindra que si la luminosité repaasse au dessus de la luminosité MAX + marge. Mettre une marge permet d'éviter que la lumière "clignote" lorsque la luminosité passe constamment au dessus / en dessous de la luminosité de seuil.
- Ajout d'une plage d'ouverture pour les volets roulant
- Ajout d'indicateurs de présence (porte / prise ... etc). Il est possible de conditionner cette présence avec un temps -> ma porte ouverte ne remonte une présence que les 3 premières minutes d'ouverture
- Ajout des liens vers le tutoriel / documentation

Amusez-vous bien avec ces nouvelles fonctionnalités. 
Si vous souhaitez que je rajoute des conditions supplémentaires aux automatismes, n'hésitez pas à me le faire savoir.
La prochaine étape est de mettre en place dans le plugin un automatisme de gestion de luminosité que vous pourrez combiner avec l'automatisme pièce afin que le plugin gère l'allumage de vos lumières et leur luminosité.

# 21/10/2021 [Beta]
- Correction bug affectation d'un automatisme depuis une lumière

# 19/10/2021 [Beta]
- Ajout de la position du soleil en tant qu'indicateur de luminosité
- Ajout de la posibilité d'affecter un automatisme directement depuis la configuration d'un automatisme
- Un automatisme ne peut maintenant éteindre une lumière que si il l'avait lui même allumé
- REFONTE totale du système d'affectation d'un automatisme

ATTENTION: Cette nouvelle version contient une migration de configuration.
Pour plus de stabilité et faire un premier pas vers la priorisation des automatismes, l'ensemble du système d'affectation a été remodelé.
Cette version contient donc un code s'éxecutant à l'installation du plugin qui migrera votre ancienne configuration des automatismes affectés vers la nouvelle.
Vérifiez après installation du plugin que vos lumières soient toujours affectées à vos automatismes.
Si jamais vous avez un problème:
- Remapper vos automatismes vers vos lumières
- Contactez moi

Enfin les commandes pour activer et désactiver les automatismes au niveau des LUMIERES (et non des automatismes), ont été modifiées. Si vous les utilisiez pour des scénarios, vous allez devoir utiliser les nouvelle.

Cette migration est normalement la dernière.

# 17/10/2021 [Beta]
- Correction bug déclenchement de la lumière si absence de volets roulants
- Correction bug restrictivité non prise en compte
- Correction bug suppression volets roulants

# 16/10/2021 [Beta]
- Ajout possibilité de compléter les indicateurs de luminosité de l'automatisme pièce avec la position des volets roulants.

# 15/10/2021 [Beta]
- Ajout possibilité de rajouter des conditions dans l'automatisme "pièce". L'automatisme ne se déclenche pas tant que les conditions ne sont pas résolus. A terme les conditions pourrait être appliquées sur l'ensemble des automatismes
- Ajout possibilité de rendre certains capteurs restrictifs. Lorsqu'un capteur est restrictif, l'automatisme ne se déclenchera pas tant que ce dernier ne passera pas à 1.

# 14/10/2021 [Beta]
- Correction du bug de programmation pour date de début supérieure à une date de fin
- Correction du bug de calcul de luminosité d'un groupe
- Correction automatisme modification horaire

ATTENTION: La mise à jour de cette version intègre une migration de la configuration de vos automatismes ainf que la gestion de la luminosité / couleur et température soit géré via un onglet dédié. Vérifiez bien que ces données soient bien à jour pour ces automatismes.

# 13/10/2021 [Beta]
- Correction du bug d'affichage de la sélection des éléments d'un groupe de lumière
- Correction du bug de programmation pour date de début supérieure à une date de fin
- Ajout d'un onglet de gestion de la luminosité / couleur / température pour les automatismes

ATTENTION: La mise à jour de cette version intègre une migration de la configuration de vos automatismes ainf que la gestion de la luminosité / couleur et température soit géré via un onglet dédié. Vérifiez bien que ces données soient bien à jour pour ces automatismes.

# 12/10/2021 [Beta]
- Ajout d'un onglet programmation horaire pour l'ensemble des automatismes
- Il est maintenant possible définir la luminosité / couleur / température d'un automatisme depuis une commande info
- Ajout de la température dans les automatismes
- Ajout d'une condition binaire permettant d'activer et de désactiver un automatisme -> MODE
- Correction du bug d'affichage de la sélection des éléments d'un groupe de lumière

ATTENTION: Pour cette nouvelle version l'ensemble des automatismes est programmable. L'automatisme de veille qui auparavant était le seul à être programmable doit être reconfigurer depuis l'onglet de programmation. 

# 06/10/2021 [Beta]

- Ajout de l'automatisme pièce de vie pouvant prendre de multiples capteurs de présence et de luminosité
- Modification configuration automatisme de veille


# 03/10/2021 [Beta]

- Ajout de la gestion des automatismes en tâches. Lors du lancement d'un automatisme pour une lumière, si le même automatisme est en cours d'éxecution, la nouvelle instance vient remplacer l'ancienne
- Ajout d'un marqueur sur le widget lorsque qu'une lumière ou groupe de lumière est en cours d'automatisme
- Il est désormais possible de définir un temps tampon pour l'automatisme placard pour lequel la lumière restera allumée même si le capteur passe à 0. Au dela de ce temps la lumière s'éteint (si l'instance de l'automatisme est toujours en cours).

# 03/10/2021 [Beta]

- Correction bug sur le temps d'allumage de l'automatisme veilleuse
- Ajout lien vers community


# 01/10/2021 [Beta]

- Ajout des commandes info et action pour gérer la température du lumière en °K

# 29/09/2021 [Beta]

- Multiples bug fixes
- Ajout limitation des automatismes suivant le budget (Nécessite Electricity Cost). Si vous rajoutez cet automatisme à une lumière, le plugin ira vérifier si le budget de l'ampoule est dépassé avant d'allumer une lumière, changer la luminosité ou changer la couleur avec un automatisme. La limitation de budget n'impacte que les automatismes. SI le budget est dépassez et que vous souhaitez allumer la lumière, le plugin ne vous bloquera pas

# 28/09/2021 [Beta]

- Ajout commandes demande de luminosité. On demande une luminosité spécifique. Si la lumière est allumée, la luminosité est appliquée, si la lumière est éteinte, la luminosité sera appliquée dès que la lumière s'allumera
- Ajout commandes demande de couleur. On demande une couleur spécifique. Si la lumière est allumée, la couleur est appliquée, si la lumière est éteinte, la couleur sera appliquée dès que la lumière s'allumera
- Ajout automatisme demande de couleur / luminosité à une heure précise

# 27/09/2021 [Beta]

- Ajout des automatismes

# 25/09/2021 [Beta]

- Interface 3.0
- Correction bug sur la modification de l'état d'un groupe depuis une lampe avec un état numérique

# 13/09/2021 [Beta]

- Nouvelle interface de commandes
- Ajout du filtre info / action lors de la selection d'une commandes
- Ajout du type générique pour la luminosité INFO
- Suppression des commandes inutiles lors de la désactivation de la luminosité ou de la couleur
- Liaison des commandes actions aux commandes infos

# 10/09/2021 [Beta]

Fix configuration d'une lumière dans Electricity Cost

# 06/09/2021

Fix problème affichage des équipements aggrégées pour les groupes

# 05/09/2021

Ajout compatibilité avec Electricity Cost

# 05/09/2021

Catégorisation du plugin en Automatisation
Affichage du nom complet de l'équipement pour l'aggrégation des groupes
Décomposition de l'interface de configuration entre lumière et groupe de lumière

# 04/09/2021

Première version du plugin en beta

