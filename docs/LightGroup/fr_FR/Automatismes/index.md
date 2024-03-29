# Plugin Light Group - Automatismes

Cette sous section regroupe les informations concernant les automatismes du plugin de Light Group.
Les automatismes sont de petits algorithmes pour vos lumières que vous pouvez créer comme des équipements puis les affecter à vos lumières ou vos groupes de lumières.

Lorsqu'une lumière est actuellement conditionée par un automatisme, elle prend le symbole suivant:
<img src="IMGS/automatisme_icon.png" alt="hi" class="inline"/>

Voici la liste des automatismes disponibles:

- Lumière de pièce: La lumière est conditionnée par autant de capteurs de présence que vous le souhaitez. La lumière est également conditionnée par une luminosité. Il suffit que l'un des capteurs détecte une présence ou une luminosité suffisante pour que l'automatisme se déclenche.
Tutoriel expliquant pour cet automatisme: <a href="https://community.jeedom.com/t/tutoriel-comment-automatiser-les-lumieres-dune-piece-avec-de-multiples-conditions-presence-luminosite-volets-soleil/69768">ICI</a>

- Gestion de la luminosité / couleur / température: les paramètres de la lumière sont conditionnés par différents capteurs. Dès que l'un des capteurs s'enclenche, la luminosité est demandée à la lumière. Si la lumière est allumée, la luminosité s'applique immédiatement, sinon la luminosité s'appliquera dès que la lumière s'allumera.Tutoriel expliquant pour cet automatisme: <a href="https://community.jeedom.com/t/tutoriel-comment-automatiser-la-luminosite-couleur-et-temperature-de-vos-lumieres/70024?u=hbe">ICI</a>



- Restriction des automatismes en fonction du budget. Cet automatisme nécessite que le plugin Electricity Cost soit installé et que les lumières dont vous voulez restreindre les automatismes soient paramétrées sur Electricity Cost. Lorsque le budget mensuel alloué à une lumière est dépassé, le plugin restreindra l'ensemble des automatismes affectés à cette lumière. Les automatismes ne pourront plus allumer la lumière, modifier la luminosité et modifier la couleur.
Tutoriel expliquant pour cet automatisme: <a href="https://community.jeedom.com/t/tutoriel-comment-reduire-controler-le-cout-de-ses-automatismes-de-lumiere/70105?u=hbe">ICI</a>

Les automatismes s'éxecutent comme des tâches. Prenons un petit exemple:
J'utilise l'automatisme de placard et ma lumière s'allume lorsque j'ouvre la porte. Si la porte reste ouverte trop longtemps, la lumière s'éteint.
Lorsque j'ouvre la porte, le plugin crée une première instance de l'automatisme. Je ferme puis j'ouvre de nouveau la porte, le plugin crée une nouvelle instance qui vient remplacer l'ancienne. Ma lumière n'est ainsi conditionée que par la nouvelle instance.

Cette documentation explique:
- Comment créer un automatisme
- Comment affecter un automatisme à une lumière
- Comment activer et désactiver un automatisme
- Comment combiner les automatismes entre eux

L'activation d'un automatisme est représentée de la manière suivante:
- un badge est ajouté sur la lumière lorsqu'un automatisme est en cours d'execution.
- une icône mouvement est ajoutée lorsque l'automatisme détecte un mouvement
- un chronomètre se lance lorsque la lumière prévoit une extinction
<img src="IMGS/light_mov.PNG" alt="hi" class="inline"/>
<img src="IMGS/light_extinc.PNG" alt="hi" class="inline"/>



# 1) Consulter les automatismes

Les automatismes créés sont regroupés dans la page de configuration du plugin dans la sous-section automatismes:

<img src="IMGS/list_automatismes_config.PNG" alt="hi" class="inline"/>


# 2) Créer un automatisme

Pour créer un automatisme, cliquez sur le bouton + dans la page de configuration:

<img src="IMGS/button_create_autom.PNG" alt="hi" class="inline"/>

Depuis la page de configuration de l'équipement, choisissez:

<img src="IMGS/automatisme_type.PNG" alt="hi" class="inline"/>

Une nouvelle liste apparaît. Vous pouvez choisir dans cette liste les automatismes que vous souhaitez configurer.

L'automatisme le plus complet est l'automatisme "Pièce". Vous pouvez depuis cet automatisme définir de multiples capteurs de présence ou de luminosité.


## 2.1) Affecter des capteurs à un automatisme

Pour affecter des capteurs à un automatisme, sélectionnez l'onglet "Capteurs":
<img src="IMGS/sensorTab.png" alt="hi" class="inline"/>

Dans cet onglet vous pouvez ajouter autant de conditions, capteurs de présence et de capteurs de luminosité que vous le souhaitez:
<img src="IMGS/sensorTables.png" alt="hi" class="inline"/>

L'automatisme sera activé si: une présence est détectée ET la luminosité est insuffisante.
Il est possible de ne saisir aucun capteur de présence ou aucun capteur  de luminosité. Dans ce cas une présence détectée ou une luminosité suffisante suffit pour déclencher l'automatisme.

### 2.1.1) Les conditions

Il est possible d'affecter des conditions à la réalisation de l'automatisme. Tant que toutes ces conditions ne seront pas réalisées, l'automatisme ne pourra pas se déclencher.
<img src="IMGS/conditionTable.png" alt="hi" class="inline"/>

Les conditions doivent être déclarées sous forme de "code".
Vous devez déclarez les équipements sous la forme #[Pièce][Equipement][Commande Info]#
Vous pouvez utilisez les conditions ET -> &&, OU -> ||, EGALE -> ==, ainsi que toutes les autres.

<img src="IMGS/cuisineExCondition.png" alt="hi" class="inline"/>

### 2.1.2) Les indicateurs de présence

Si vous ne renseignez aucun indicateur de présence, la présence est validée par défaut.
Si vous renseignez plusieurs indicateurs de présence, la présence sera validée dès qu'un des indicateurs détecte une présence.

Il existe plusieurs types d'indicateurs de présence. Plus vous en mettrez plus votre automatisme sera précis.

#### 2.1.2.1) Capteurs de présence

Ici vous pouvez ajouter des capteurs de présence. La commande information renseignée doit être binaire et renvoyer 1 si il y a de la présence et 0 si il n'y a pas de présence
<img src="IMGS/cuisineExPresence.png" alt="hi" class="inline"/>

#### 2.1.2.2) Les interactions

Vous pouvez lister des interactions que vous pouvez faire avec vos objets du quotidien. Le plugin comptera chaque interaction comme une présence. 
Vous pouvez définir un temps maximum pour l'interaction. Passé ce temps, l'interaction ne sera plus prise en compte dans la recherche de présence.
L'interaction doit être une commande information binaire avec 1 une interaction et 0 aucune interaction. Une interaction peut être une prise, une porte, un interrupteur etc ...

<img src="IMGS/cuisineExInter.png" alt="hi" class="inline"/>

#### 2.1.2.3) Les interactions horaires

Vous pouvez donner des créneaux horaires pour lesquels l'automatisme doit comptabiliser une présence. 
Si vous ne renseignez qu'une heure de début, l'automatisme ne prendra alors pas en compte un "créneau" de présence mais uniquement une "minute" de présence.
<img src="IMGS/cuisineExTimeCron.png" alt="hi" class="inline"/>

### 2.1.3) Les indicateurs de luminosité

Si vous ne renseignez aucun indicateur de luminosité, la luminosité est faible par défaut.

Il existe plusieurs types d'indicateur de luminosités. Plus vous en mettrez plus votre automatisme sera précis.

#### 2.1.3.1) L'intensité lumineuse

Vous pouvez définir des capteurs de luminosité. Pour chaque capteur, vous devez définir une luminosité minimale.
Il vous est possible de rendre un ou plusieurs capteurs restrictifs. Dans ce cas là, tant que la luminosité n'est pas faible pour ce capteur, l'automatisme ne se déclenche pas.

Une luminosité est considérée comme faible lorsqu'elle est comprise entre les bornes MIN et MAX.

Pour éviter un clignotement de vos lumières lorsque la luminosité passe en dessous du seuil, vous pouvez définir une marge.

La marge n'est prise en compte que lorsque l'automatisme cherche à éteindre la lumière, il ira alors vérifier si la luminosité est comprise entre luminosité MIN - marge et luminosité MAX + Marge. Si c'est le cas il n'éteindra pas la lumière.

<img src="IMGS/cuisineExLumen.png" alt="hi" class="inline"/>

#### 2.1.3.2) La position des volets roulants

Vous pouvez ici déclarer la position de vos volets roulants. Vous pouvez pour chaque volet définir une position minimale en dessous de laquelle vous considérez que la luminosité est faible dans votre pièce. L'automatisme considère que la luminosité est faible dans votre pièce que si l'ensemble des volets roulants déclarés possèdent une ouverture faible.
Il vous est possible de rendre un ou plusieurs de vos volets roulants restrictifs. Dans ce cas la, tant que le volet ne sera pas en dessous de son ouverture minimale, l'automatisme ne se déclenchera pas.
<img src="IMGS/cuisineExVolet.png" alt="hi" class="inline"/>


#### 2.1.3.3) La position du soleil

Vous pouvez ici déclarer l'heure de lever et de coucher du soleil. Si jamais l'heure actuelle est après le coucher du soleil ou avant le lever du soleil, l'automatisme considérera que la luminosité est faible.
Il vous est possible de rendre le coucher / lever du soleil restrictif. Dans ce cas la, tant que le soleil n'est pas couché, l'automatisme ne se déclenchera pas.

Les commandes de lever et de coucher du soleil se basent sur celle du plugin Héliotrope.

<img src="IMGS/cuisineExSun.png" alt="hi" class="inline"/>

Les commandes doivent retourner une valeur au format Hi. Par exemple 730 pour 7h30 et 1415 pour 14h15.
Il vous est possible au début du créneau et la fin du créneau de mettre en place des conditions si vous souhaitez temporiser le lever du soleil ou le coucher du soleil.

Ex: #[CMD LEVER DU SOLEIL]# + 30
Si le lever du soleil est à 6h30, la condition ci dessus donne 700 (630 + 30).


## 2.2) Définir les temps tampons

Revenons sur l'onglet principal de configuration de l'automatisme. Vous avez la possibilité ici de définir plusieurs temps tampon:
<img src="IMGS/timeTampon.png" alt="hi" class="inline"/>

### 2.2.1) Temps maximum d'automatisation

Le premier temps que vous pouvez définir est le temps maximum pour lequel l'automatisme sera enclenché. Passé ce temps, l'automatisme sera arrêté et les lumières s'éteindront. Si vous ne définissez aucun temps alors les lumières ne seront conditionnées que par les capteurs de présence et de luminosité

### 2.2.2) Temps tampon

Lorsque les capteurs de présences ne détectent plus de mouvement ou bien que la luminosité est suffisante, l'automatisme va s'arrêter et les lumières vont s'éteindre. Il est possible de définir un temps tampon avant que les lumières ne s'éteignent. Si, pendant ce temps tampon, un mouvement est détecté et que la luminosité redevient insuffisante, les lumière ne s'éteindront pas et un nouveau cycle est lancé.

<img src="IMGS/cuisineExTpsTampon.png" alt="hi" class="inline"/>


## 2.3) Paramétrer les lumières

L'automatisme lorsqu'il sera déclenché allumera les lumières. Il est possible en plus de cela de faire modifier la luminosité, la couleur ou la température des lumières compatibles. Pour ces 3 paramètres, il est possible de définir une valeur:
<img src="IMGS/lumen.png" alt="hi" class="inline"/>

Il vous est également possible de récupérer la valeur d'une commande à appliquer sur les lumières de l'automatisme. Il vous faut pour cela cocher la bonne case:
<img src="IMGS/lumenCmd.png" alt="hi" class="inline"/>

## 2.4) Programmer les automatismes

Vous pouvez définir des plages temporelles pour lesquelles l'automatisme peut ou non se déclencher.
Par défaut aucune plage n'est définie et l'automatisme peut s'activer n'importe quand.

Si vous souhaitez définir des plages horaires spécifiques, cochez:
<img src="IMGS/tickProgrammation.png" alt="hi" class="inline"/>

Un nouvel onglet "Programmation" apparaît alors. Cliquez dessus pour la suite de la configuration.
<img src="IMGS/programmationTable.png" alt="hi" class="inline"/>

Cliquez sur le bouton pour ajouter une plage de programmation.
- Vous pouvez sélectionner les jours pour lequels l'automatisme peut s'activer. Ce champ est multi sélectionnable.
- Vous pouvez définir l'heure de début et l'heure de fin de la programmation. Si l'heure de début est plus tard que l'heure de fin, le plugin considéra que vous avez sélectionné le créneau heure de début -> minuit minuit -> heure de fin.
- Vous pouvez cocher "Jour entier" qui annule la plage définie et rend l'automatisme activable pour le jour entier.

<img src="IMGS/cuisineExProgrammation.png" alt="hi" class="inline"/>



SAUVEGARDER pour créer les différentes commandes.

# 3) Affecter un automatisme

Pour qu'un automatisme puisse agir sur une lumière, nous devons affecter l'automatisme sur cette dernière.
Vous pouvez affecter un automatisme à une lumière depuis deux endroits:
- depuis la page de configuration d'un automatisme.
- depuis la page de configuration d'une lumière.

## 3.1) Affectation depuis un automatisme

Vous pouvez accéder à cette page dans la configuration d'un automatisme en cliquant sur l'onglet:
<img src="IMGS/tabAffectation.png" alt="hi" class="inline"/>

Depuis cet onglet vous pouvez affecter votre automatisme aux lumières / groupes de lumières que vous souhaitez.
Il n'est pas possible depuis cet onglet d'influer sur la priorisation des automatismes les uns par rapport aux autres.
<img src="IMGS/affectationTable.png" alt="hi" class="inline"/>

Pour valider les affectations, cliquez sur:
<img src="IMGS/saveAffectButton.png" alt="hi" class="inline"/>

ATTENTION: Cliquer sur le bouton sauvegarder de l'équipement ne validera pas vos affectations.

## 3.1) Affectation depuis une lumière

Choisissez une lumière ou un groupe de lumières et allez dans la page de configuration de l'équipement.
Cliquez sur la section automatisme:

<img src="IMGS/automatisme_section.PNG" alt="hi" class="inline"/>

Une table apparaît. Vous pouvez depuis cette table, affecter et retirer un automatisme.

<img src="IMGS/empty_automatisme_table.PNG" alt="hi" class="inline"/>

Cliquez sur le bouton ajouter un automatisme et choisissez votre automatisme dans la vue qui apparaît.
Enfin validez la vue.

Vous devriez voir apparaître votre automatisme dans la table comme cela:

<img src="IMGS/new_automatisme_table.PNG" alt="hi" class="inline"/>

Si cet automatisme vous convient, sauvegardez la lumière.
Une fois sauvegardée, vous devriez voir apparaître 3 commandes dans la liste des commandes pour votre lumière:
<img src="IMGS/command_list_automatisme.PNG" alt="hi" class="inline"/>

Vous pouvez depuis ces 3 commandes autoriser ou interdire un automatisme. Si l'automatisme est interdit, il ne s'activera plus pour cette lumière.

# 4) Activer et Désactiver un automatisme

Il possible d'activer et de désactiver un automatisme. Lorsque qu'un automatisme est désactivé, il ne pourra plus se déclencher et n'aura donc plus d'impact sur les lumières concernées que ce soit pour allumer ou éteindre une lumière.

Il existe 2 possibilités pour activer et désactiver un automatisme:
- Désactiver l'automtatisme
- Désactiver l'instance d'un automatisme

## 4.1) Agir au niveau de l'automatisme

L'automatisme possède 3 commandes:
<img src="IMGS/cmds_autom.png" alt="hi" class="inline"/>

Lorsque vous activez et désactivez l'automatisme depuis ces commandes, l'automatisme est désactivé pour l'ensemble des lumières qui le possèdent. Si vous souhaitez agir lumière par lumière alors consultez le point ci dessous.

## 4.2) Agir au niveau d'une lumière

Il est possible d'activer et de désactiver un automatisme pour uniquement une lumière. 
Chacune des lumières possédant l'automatisme possède 3 commandes permettant cela

# 5) Combiner les automatismes

Il vous est possible depuis le plugin de combiner des automatismes pour obtenir le comportement souhaité.
Exemple: je souhaite que la lumière de mon placard s'allume lorsque j'ouvre la porte. Je souhaite également que la luminosité de la lumière soit plus faible durant la nuit.

Pour cela je vais créer 3 automatismes:
- mon automatisme lumière de placard qui ne gérera pas la luminositée
- un automatisme pour demander une modification de la luminositée à 20% à 21h
- un automatisme pour demander une modification de la luminosité à 100% à 8h

J'affecte ces trois automatismes à ma lumière de placard.

Ainsi lorsque j'ouvrirai la porte à 15h la lumière s'allumera avec une luminosité de 100 %, lorsque j'ouvrirai la porte à 22h, la lumière s'allumera avec une luminosité de 20%.


# 6) Définir des actions manuelles

Il est possible de définir des actions manuelles pour les lumières / prises / groupes de lumières.
Une action manuelle annule les automatismes dont la priorité est inférieure.
Par défaut un automatisme à une priorité de 500.
Par défaut une action manuelle à une priorité de 800.

## 6.1) Créer une action manuelle

La création des actions manuelles se fait au niveau des lumières / prises / groupes d'automatismes.
Il faut aller dans l'onglet automatisme.

Dans cette onglet, vous pouvez accéder à la section:
<img src="IMGS/action_manuelle_section.png" alt="hi" class="inline"/>

Pour ajouter une action manuelle, cliquez sur le bouton correspondant.
Une ligne apparaît alors.
<img src="IMGS/actionligne.png" alt="hi" class="inline"/>

Sur cette ligne, vous devez définir:
- La condition de déclenchement (quand la condition est VRAI, le plugin considère qu'il y a action manuelle)
- Le temps de désactivation des automatismes. Passé ce temps, l'action manuelle disparaît et les automatismes reprennent le dessus.
- La pondération / Priorité. Par défaut elle est de 800.

## 6.2) Représentation d'une action manuelle

Lorsque qu'une lumière / prise / automatisme est sous le joug d'une action manuelle (peut importe sa priorité), le widget change.
<img src="IMGS/manualActionEx.png" alt="hi" class="inline"/>



## A venir

Plusieurs automatismes vont être rajoutés graduellement sur le plugin.
Il sera possible de prioriser les automatismes entre eux pour une lumière / groupe de lumières
Vous pouvez suivre les avancées depuis le board: <a href="https://github.com/users/hbedek/projects/5">ICI</a>