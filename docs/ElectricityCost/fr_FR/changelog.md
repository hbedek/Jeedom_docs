# Changelog plugin Electricity Cost

# 23/09/2021 [Beta]
- Ajout commande coûts hebdomadaire
- Ajout pourcetage journalier
- Ajout pourcetage hebdomadaire
- Ajout pourcetage annuel

# 22/09/2021 [Beta]
- Ajout commande coûts annuels
- Mise à jour des commandes de Laundry et Light Group lors d'un update de Electricity Cost

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


