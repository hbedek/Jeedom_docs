# Changelog plugin Electricity Cost


# 03/06/2023
- Fix création groupe lorsque le plugin LightGroup n'est pas installé
- Fix du calcul du pourcentage d'heures dans le cas des contrats multi heures creuses
- Passage des logs en français
- Optimisation de la réparation de l'historique
- Fix bug calcul coûts sur les groupes
- Ajout possibilité de lier un groupe à un contrat

# 20/02/2022
- Configuration notifications cachées et plus prise en compte pour un contrat
- Fix bug, retour de la commande etat heure creuse du contrat HCHP incorrecte
- Fix bug, retour de la commande heure creuse du contrat multi HC incorrecte

# 08/01/2022

-  Si le budget n'est pas renseigné, l'équipement considère que le budget n'est pas dépassé par défaut

# 14/12/2021

- Ajout du pourcentage en HC pour les contrats multi HC
- Ajout des économies potentielles en HC pour les contrats multi HC


# 19/11/2021 

- Ajout possibilité de grouper des équipements. Il est possible d'affecter un groupe à un compteur. Le gorupe renverra le pourcentage de consommation par rapport à celui du compteur mais ne participera pas au pourcentage d'investigation du compteur.
- Amélioration: possibilité de lier plusieurs jours pour les contrats à multiples créneaux HC
- Amélioration: possibilité de choisir entre Wh et kWh lorsque l'on lie une commande de consommation cumulée
- Correction BUG: Problème génération des commandes isHC pour le contrat
- Correction BUG: Les commandes isHC et nextHC ne doivent se créer que si le contrat contient des heures creuses
- Correction BUG: Les commandes de notifications ne doivent pas se créer si aucun contrat / compteur n'est lié

ATTENTION: pour les utilisateurs de contrat à multiples créneaux HC, le calcul des heures creuses a été modifié. Cette fonctionnalité est en beta depuis le 29/10 et aucun problème ne m'est remonté. Cependant je vous conseille également de vérifier de votre côté. Pour cela vous pouvez utilisez la commande "Etat heures creuses" de l'équipement contrat qui vous remonte si l'on est actuellement en heures creuses et la commande "Prochain créneau heures creuses (minutes)" qui vous remonte le nombre de minutes avant le prochain créneau d'heures creuses.


# 26/10/2021

- Ajout de la commande état de l'heure creuse pour le contrat / compteur / équipement. Renvoie 1 si actuellement en heures creuses
- Ajout de la commande temps restant avant heures creuses en minutes pour le contrat / compteur / équipement. Renvoie le nombre de minutes restant avant le prochain créneau d'heures creuses
- Ajout du type de contrat multiples heures creuses. Vous pouvez définir un tarifs au kWh par défaut et autant de créneaux d'heures creuses que vous oushaitez. Un créneau d'heure creuse est définit par un jour de la semaine, une heure de début, une heure de fin et un prix du kWh

# 03/10/2021
- Ajout possibilité de ne récupérer aucun historique ou l'historique du dernier mois lors de la configuration d'un équipement
- Lorsque le plugin n'aura aucune information pour une date antérieure, il considérera que le coût est égal à 0
- Ajout des commandes remontant les montants des dates antérieurs (semaine précédente, mois précédent, année précédente)
- Ajout du bouton de réparation des données de l'historique dans la configuration de l'équipement (voir documentation)
- Ajout de la commande coût aujourd'hui. ATTENTION, si vous utilisiez la commande coût de la veille en historique, vous devez dorénavant utiliser la commande coût d'aujourd'hui
- Ajout des notifications journalière, hebdomadaire, mensuelle, annuelle. Les notifications sont de type HTML et doivent être utilisé avec Telegram ou un équivalent
- Récupération et calcul des coûts pour les jours / semaines / mois / années précédentes (ne dépend plus de la date du refresh)
- Ajout de la possibilité de ne récupérer que l'historique du mois en cours lors de l'initialisation
- Ajout de l'unité de la puissance lors de la création des commandes
- Ajout du nombre de décimales pour les coûts et les pourcentages (au niveau du contrat et se répercute sur l'ensemble des équipements liés)
- Correction Bug création de commande puissance lorsque sélection puissance moyenne
- Ajout commande coûts hebdomadaire
- Ajout pourcentage journalier
- Ajout pourcentage hebdomadaire
- Ajout pourcentage annuel
- Ajout commande coûts annuels
- Mise à jour des commandes de Laundry et Light Group lors d'un update de Electricity Cost

ATTENTION avec l'ajout des nouvelles commandes dont la commande coût d'aujourd'hui, le premier raffraîchissement de l'équipement peut prendre du temps


# 22/09/2021

- Revisite de l'interface
- Fix création commandes pour un contrat
- Ajout d'un lien vers le market si aucune équipement de Laundry ou Light Group n'est configuré
- Ajout des équipements compatibles avec Electricity Cost dans l'interface du plugin
- La création des commandes ne s'effectue que si le type est sélectionné

# 23/08/2021

- Ajout du calcul du pourcentge de heures creuses
- Ajout calcul économies si heures creuses
- Refonte de l'interface
- Ajout de la budgétisation

# 20/08/2021

- Ajout d'une information sur la nécessité d'historisation des cmds dans la configuration d'un équipement.
- Ajout de la catégorie puissance moyenne à différencier de puissance instantanée.
- Par défaut le plugin prendra comme date le début du mois plutôt qu'un mois entier pour l'initialisation des valeurs.
- Amélioration du calcul du coût pour les équipements de puissance instantanée et état. Le plugin créera des valeurs pour le début des heures creuses et la fin des heures creuses si nécessaire afin d'avoir un calcul de coût plus précit entre deux valeurs trop distantes.
- Modification de l'interface pour la compatibilité entre plugins

# 19/08/2021

Fix problème du calcul du pourcentage si l'équipement est lié à un contrat

# 16/08/2021

Fix refresh des équipements puissance
Init des équipements récupère l'historique d'un mois entier

# 15/08/2021

Première version du plugin


