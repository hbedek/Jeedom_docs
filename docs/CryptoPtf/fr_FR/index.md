# Plugin Crypto Portfolio

Ce plugin permets de récupérer les informations de vos portefeuilles de Cryptomonnaie.
Actuellement disponible sur le plugin:
- JustMining
- Binance

## JustMining

Un équipement JustMining vous permet de récupérer les informations:
- d'un stacking
- d'un masternode
- d'un wallet

### Description de l'équipement
Le plugin retourne le nombre de tokens de votre contrat ainsi que le nombre de récompenses de votre contrat de Stacking / Masternode.
Si vous cochez l'option "remonter les informations de Binance", le plugin remontera l'équivalent EUR de votre portefeuille / récompenses et calculera les performances de votre contrat pour différentes durées.
Si jamais vous renseignez en plus le coût d'achat de vos tokens, le plugin calculera les plus value. 


### configuration de l'équipement
Pour configurer un équipement Just Mining, il faut au préalable fournir la clef API.
Il faut choisir un contrat:
- Stacking
- Masternode
- Wallet

Si la clef API est correcte, le plugin vous demandera alors de choisir un des contrats de votre compte. Choisissez le contrat et sauvegarder pour créer les commandes.

Paramètre optionnels:
Vous pouvez indiquer le prix d'achat de vos tokens et le plugin calculera votre plus value.

## Binance
Un équipement Binance permet de récupérer les informations d'un portefeuille Spot.

### Description de l'équipement
Le plugin retourne le nombre de tokens disponibles et bloqués pour une cryptomonnaie de votre portefeuille Spot.
Le plugin crée une commande portefeuille correspondant au nombre de tokens disponible + nombre de tokens bloqués.
Pour disponible / bloqués / portefeuille le plugin retourne la conversion en EUR.
Le plugin calcule les performances de votre cryptomonnaies pour plusieurs périodes de temps:
- 24h
- 1 semaine
- 1 mois
- 1 an
Si jamais vous renseignez en plus le coût d'achat de vos tokens, le plugin calculera les plus value. 

### configuration de l'équipement
Pour configurer un équipement Binance, il faut au préalable fournir la clef API et l'API secret.
ATTENTION: par mesure de sécurité, veillez bien à créer une clef API distincte pour votre Jeedom avec des droits en LECTURE SEUL (le plugin ne fait aucun transactionnel) et idéalement n'autorisez que l'IP de votre JEEDOM.

Une fois la clef API et l'API secret saisis, vous pouvez choisir un type de portefeuille:
- Spot

Si la clef API et l'API Secret sont correctee, le plugin vous demandera alors de choisir une des cryptomonnaies de votre portefeuille SPOT. Choisissez la cryptomonnaie et sauvegarder pour créer les commandes.

Paramètre optionnels:
Vous pouvez indiquer le prix d'achat de vos tokens et le plugin calculera votre plus value.


## Configuration de la devise
Il est possible pour tous les équipements de configurer la devise dans laquelle le plugin doit convertir la valeur des tokens.
Pour cela il faut d'abord cocher l'option "Récupérer le cours sur Binance".
De la vous avez le choix entre EUR et USDT.
Le plugin tente de remonter la conversion pour les tokens en Stacking sur binance (préfixé par LD) ainsi que certains tokens propre à binance (BETH).
Dans le cas ou le plugin ne remonte pas, ou la mauvaise conversion, vous pouvez sélectionner un autre token de référence.
Pour cela cochez la case "Saisir à la main le symbole", et saisissez le bon symbole dans le champ qui s'affiche.
EX: Pour la monnaie LDXRP, le plugin va bien aller récupérer la device de XRP. Dans le cas ou cela ne fonctionnerait pas, il faudrait alors cocher la case "Saisir à la main le symbole" et saisir "XRP" dans le champ qui s'affiche.

## A venir

Attention, je ne m'engage sur aucune date / implémentation mais voici les projets en cours:
- Intégration de Binance Saving
- Intégration des portefeuille ERC20
- Ajout d'un équipement génériques regroupant les informations de tous les porteuilles
- Ajout de widgets