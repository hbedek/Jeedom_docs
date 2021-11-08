# Changelog plugin Laundry

# 08/11/2021

- Correction BUG erreur commandes manquante pour le mode ECO si ECO non configuré.

# 07/11/2021

- Ajout des icônes en SVG
- Ajout: rallume la prise suite à une programmation
- Ajout d'un badget de dépassement de budget sur le widget (uniquement si Electricity Cost est installé / configuré).
- Ajout du mode PROGRAMMATION. Ce mode nécessite le plugin Electricity Cost. Lorsque vous lancez une machine, le plugin ira vérifier quel est le créneau d'heures creuses le plus proche. Si le créneau est à une distance temporelle inférieure à X minutes (A définir en configuration), la machine ne se lancera qu'une fois le créneau atteint. Laundry utilise les créneaux creuses du contrat ELectriciy Cost lié à votre machine (ou du contrat du compteur lié à votre machine).

# 03/10/2021

Ajout possibilité de réparer un équipement depuis Electricity Cost
Amélioration modales INFO et ACTION
Ajout du mode LITE sans capteur d'ouverture de porte
Modification interface visualisation des commandes
Ajout notifications HTML fin de cycle
Retirer information présence mode ECO sur interface du plugin
Fix modification interface Electricity Cost

# 30/08/2021

Fix activation ECO
Modification interface Electricity Cost

# 23/08/2021

Ajout du mode ECO

# 16/08/2021

Fix erreur refresh widget si aucune cmd
Nouvelle version du widget

# 15/08/2021

Amélioration de la compatibilité à Electricity Cost
Ajout des fonctionalités d'Electricity Cost dans le widget de Laundry

# 13/08/2021

Ajout de la compatibilité au plugin Electricity Cost qui devrait arriver prochainement

# 10/08/2021

Première version du plugin avec ses 4 états

