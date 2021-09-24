# Plugin Laundry

Ce plugin permet de connecter une Machine à laver / Sèche linge, lave vaisselle via une mesure de puissance et un capteur d'ouverture de porte.

Pour que le plugin fonctionne, il faut impérativement:
- que la machine soit branchée sur une prise connectée remontant la puissance consommée.

Pour utiliser pleinement le plugin il faut que la machine puisse être monitorée via un capteur d'ouverture de porte.

Si vous n'avez pas de capteur d'ouverture de porte, le plugin passera en mode LITE [Beta]
Le mode LITE avertit uniquement lorsque la machine se lance et se termine.

## Configuration de l'équipement

Avant de configurer l'équipement, vous devez au préalable mettre un capteur d'ouverture de porte sur la porte de votre machine et brancher cette dernière sur une prise connectée.
Pour référence, de mon côté j'utilise un capteur d'ouverture de porte xiaomi, et une prise connectée Fibaro Walli Outlet qui fourni une mesure de puissance.

Concernant la configuration:
<img src="IMGS/configuration.PNG" alt="hi" class="inline"/>

- La puissance de déclenchement est la puissance a partir de laquelle la machine est considérée en fonctionnement. Généralement la puissance de veille de la machine est aux alentours des 1.7 W. De mon côté 5W fonctionne très bien.
- La puissance d'arrêt de la machine. Lorsque la machine atteint la fin de son cycle, la puissance de cette dernière va chuter. Il faut donc ici mettre la puissance a partir de laquelle le cycle est considéré comme terminé.
- Le temps tampon. Certaines machines (dont la mienne), peuvent faire une pause entre par exemple la partie nettoyage et la partie séchage. Il faut donc ici mettre un temps tampon après lequel le plugin ira de nouveau vérifier la mesure de puissance. (entre 2 et 5 minutes).

## Description de l'équipement
Le plugin peut remonter 4 états:
- opened (la porte de la machine est ouverte)
- notRunning (la machine est vide)
- running (la machine est en fonctionnement)
- finished (la machine est terminée mais non vidée)

<img src="IMGS/cmds.PNG" alt="hi" class="inline"/>

Le widget de l'équipement remonte ces 4 états sous la forme d'icônes:
<img src="IMGS/laundry_opened.png" alt="hi" class="inline" height="100px" width="auto"/>
<img src="IMGS/laundry_closed.png" alt="hi" class="inline" height="100px" width="auto"/>
<img src="IMGS/laundry_running.png" alt="hi" class="inline" height="100px" width="auto"/>
<img src="IMGS/laundry_finished.png" alt="hi" class="inline" height="100px" width="auto"/>

## Mode ECO (Non compatible avec le mode LITE)

Le plugin est en capacité d'éteindre votre machine lorsque celle ci ne tourne pas.
Ce mode eco vous permet d'économiser la consommation du mode veille de votre machine.

### Configuration du mode ECO

Pour que le mode ECO puisse s'enclencher, il faut d'abord configurer l'équipement
<img src="IMGS/eco_config.png" alt="hi" class="inline"/>

### Apprentissage du mode ECO

Le mode ECO nécessite un apprentissage avant de pouvoir s'activer. Cet apprentissage permet au plugin d'estimer la puissance que consomme votre machine en veille et donc ce que fait économiser le mode ECO à votre machine.

Une fois cette puissance acquise, le mode ECO peut s'activer tout seul.
L'activation du mode ECO est symbolisé par:
<img src="IMGS/laundry_eco.png" alt="hi" class="inline" height="100px" width="auto"/>


### Les règles du mode ECO

Le mode ECO ne s'active que si:
- la machine ne tourne pas.
- la porte de la machine est fermée.
- le mode ECO n'a pas déjà été activé depuis la fin du dernier cycle.
- les 3 conditions ci-dessus sont restées inchangées depuis 10 minutes.

Le mode ECO se désactive si:
- la porte de la machine s'ouvre

Le mode ECO ne peux ainsi s'activer qu'une fois entre deux cycle.

### Mode ECO et lancement des machines en décalé.

Attention, si vous avez pour habitude de lancer vos machines avec retardateur, le mode ECO n'est peut être pas fait pour vous.
Si vous souhaitez utiliser les deux fonctionnalités en parallèle, le mode ECO ne peut se lancer qu'une seule fois entre deux cycle

## Compatibilité Electricity Cost

Ce plugin est compatible avec Electricity Cost.
Vous pourrez ainsi profiter de toutes les fonctionalités d'Electricity Cost sans avoir à créer de nouvel équipement.
Voici la documentation du plugin: 
<a href="https://hbedek.github.io/Jeedom_docs/docs/ElectricityCost/fr_FR/">ICI</a>
