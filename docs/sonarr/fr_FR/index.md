# Plugin Sonarr & Radarr

Ce plugin permet à Jeedom de récupérer des informations de Sonarr et de Radarr

## Sonarr

### Description de l'équipement
Voici la liste des informations que Jeedom va pouvoir récupérer sur votre Sonarr:
- La liste des épisodes qui sortiront dans les prochains jours (paramétrable)
- La liste des derniers épisodes téléchargés (nombre paramétrable)
- La liste des derniers épisodes manquants (nombre paramétrable)
- La liste des séries monitorées sur Sonarr
- Le dernier épisode venant d'être téléchargé (Information pouvant servir à recevoir des notifications)
- Le dernier épisode venant d'être téléchargé ainsi que le poster associé à la série (Information pouvant servir à recevoir des notifications)

Un épisode est considéré "téléchargé" lorsqu'il est importé par Sonarr

Un serveur Sonarr est représenté par un équipement et il est donc possible de récupérer des informations de plusieurs serveurs Sonarr

Le nom des épisode est au format suivant: (NOM DE LA SERIE) S(NUMEROS DE LA SAISON)E(NUMEROS DE L'EPISODE).
Ainsi pour le 3e épisode de la saison 2 de la série GOT, le format est le suivant: GOT S2E3

Le plugin est évolutif, suivant la demande il m'est possible de rajouter plus d'informations remontées par Sonarr, tout comme envoyer des commandes à Sonarr

### configuration de l'équipement
Lorsque vous ajoutez un équipement (Un serveur Sonarr donc), vous devez au minimum fournir deux informations:
- l'url de votre Sonarr
- la clef API

D'autres paramètres, optionnels, peuvent être ajoutés :
- le nombre de jours pour lesquels vous souhaitez récupérer les épisodes à venir
- le nombre d'épisode à récupérer pour les épisodes déjà téléchargés et les épisodes manquants
- le séparateur que le plugin utilisera pour générer la liste des épisodes manquant / téléchargé

Vous pourrez trouver la clef API dans la page /settings/general de votre Sonarr
Par défaut l'équipement se ré-actualise toutes les 5 minutes. Vous pouvez modifier cela via l'outil cron actualisation dans la configuration de l'équipement

### Notification à la réception d'un nouvel épisode

Le plugin Sonarr est notifié lorsqu'un nouvel épisode est importé dans Sonarr.
La commande Info "Dernier épisode" est alors appelée avec le dernier épisode téléchargé.
Si il y a plusieurs épisodes qui arrivent d'un coup (dépend du raffraîchissement choisit), alors la commande Info sera appelée plusieurs fois.
Vous pouvez donc vous servir de cette commande pour créer un scénario de notification.

La commande Notification fonctionne de la même manière mais fournit en plus l'artwork de la série

## Radarr

### Description de l'équipement
Voici la liste des informations que Jeedom va pouvoir récupérer sur votre Radarr:
- La liste des films qui sortiront dans les prochains jours (paramétrable)
- La liste des derniers films téléchargés (nombre paramétrable)
- La liste des films manquants
- Le dernier film venant d'être téléchargé (Information pouvant servir à recevoir des notifications)
- Le dernier film venant d'être téléchargé ainsi que le poster associé au film (Information pouvant servir à recevoir des notifications)

Un film est considéré "téléchargé" lorsqu'il est importé par Radarr

Un serveur Radarr est représenté par un équipement et il est donc possible de récupérer des informations de plusieurs serveurs Radarr

Le plugin est évolutif, suivant la demande il m'est possible de rajouter plus d'informations remontées par Radarr, tout comme envoyer des commandes à Radarr

### configuration de l'équipement
Lorsque vous ajoutez un équipement (Un serveur Radarr donc), vous devez au minimum fournir deux informations:
- l'url de votre Radarr
- la clef API

D'autres paramètres, optionnels, peuvent être ajoutés :
- le nombre de jours pour lesquels vous souhaitez récupérer les films à venir
- le nombre d'épisode à récupérer pour les films déjà téléchargés
- le séparateur que le plugin utilisera pour générer la liste des films manquant / téléchargé

Vous pourrez trouver la clef API dans la page /settings/general de votre Radarr
Par défaut l'équipement se ré-actualise toutes les 5 minutes. Vous pouvez modifier cela via l'outil cron actualisation dans la configuration de l'équipement

### Notification à la réception d'un nouvel épisode

L'équipement est notifié lorsqu'un nouveeau film est importé dans Radarr.
La commande Info "Dernier film" est alors appelée avec le dernier film téléchargé.
Si il y a plusieurs films qui arrivent d'un coup (dépend du raffraîchissement choisit), alors la commande Info sera appelée plusieurs fois.
Vous pouvez donc vous servir de cette commande pour créer un scénario de notification.

La commande Notification fonctionne de la même manière mais fournit en plus l'artwork du film

# Configuration du plugin

Le plugin en lui même ne nécessite pas de configuration spécique. Vous pouvez directement ajouter un équipement pour ajouter un nouveau serveur Sonarr


