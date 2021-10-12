# Changelog plugin Light Group

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

