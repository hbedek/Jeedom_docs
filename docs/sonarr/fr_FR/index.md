# Plugin Sonarr

Ce plugin permet à Jeedom de récupérer des informations de Sonarr:
- une liste des épisodes à venir
- une liste des épisodes téléchargés
- une liste des épisodes manquant
- le dernier épisode téléchargé

Un épisode est considéré "téléchargé" lorsqu'il est importé par Sonarr

Un serveur Sonarr est représenté par un équipement et il est donc possible de récupérer des informations de plusieurs serveurs Sonarr

Le nom des épisode est au format suivant: (NOM DE LA SERIE) S(NUMEROS DE LA SAISON)E(NUMEROS DE L'EPISODE).
Ainsi pour le 3e épisode de la saison 2 de la série GOT, le format est le suivant: GOT S2E3

# Configuration du plugin

Le plugin en lui même ne nécessite pas de configuration spécique. Vous pouvez directement ajouter un équipement pour ajouter un nouveau serveur Sonarr

# Configuration d'un équipement

Lorsque vous ajoutez un équipement (Un serveur Sonarr donc), vous devez au minimum fournir deux informations:
- l'url de votre Sonarr
- la clef API

Vous pourrez trouver la clef API dans la page /settings/general de votre Sonarr
Par défaut l'équipement se ré-actualise toutes les 5 minutes. Vous pouvez modifier cela via l'outil cron actualisation dans la configuration de l'équipement

# Notification à la réception d'un nouvel épisode

Le plugin Sonarr est notifié lorsqu'un nouvel épisode est importé dans Sonarr.
La commande Info "Dernier épisode" est alors appelée avec le dernier épisode téléchargé.
Si il y a plusieurs épisodes qui arrivent d'un coup (dépend du raffraîchissement choisit), alors la commande Info sera  appelée plusieurs fois.
Vous pouvez donc vous servir de cette commande pour créer un scénario de notification.

