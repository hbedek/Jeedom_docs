# Plugin Light Group - Automatismes

Cette sous section regroupe les informations concernant les automatismes du plugin de Light Group.
Les automatismes sont de petits algorithmes pour vos lumières que vous pouvez créer comme des équipements puis les affecter à vos lumières ou vos groupes de lumières.

## Consulter les automatismes

Les automatismes créés sont regroupés dans la page de configuration du plugin dans la sous-section automatismes:

<img src="IMGS/list_automatismes_config.PNG" alt="hi" class="inline"/>


## Créer un automatisme

Pour créer un automatisme, cliquez sur le bouton + dans la page de configuration:

<img src="IMGS/button_create_autom.PNG" alt="hi" class="inline"/>

Depuis la page de configuration de l'équipement, choisissez:

<img src="IMGS/automatisme_type.PNG" alt="hi" class="inline"/>

Une nouvelle liste apparaît. Vous pouvez choisir dans cette liste les automatismes que vous souhaitez configurer.

La liste contient actuellement:
- Lumière de placard: La lumière est conditionnée par un capteur binaire (ouverture de porte) et s'allume puis s'éteint suivant la valeur du capteur. Si la porte reste ouverte plus de X minutes, la lumière s'éteint.

- Lumière de veille: La lumière est conditionnée par un capteur binaire (présence) et s'allume suivant la valeur du capteur. Une fois allumée, la lumière reste allumée X minutes, passé ce temps, la lumière s'éteint.

- Modification de la luminosité / couleur suivant une heure. Le plugin ira demander une couleur et / ou une luminosité à une heure précise. Si la lumière est éteinte, elle ne s'allumera pas mais prendra en compte la nouvelle luminosité / couleur la prochaine fois qu'elle sera allumée

Une fois votre automatisme choisit, configurez le et sauvegardez l'équipement.


## Affecter un automatisme

Choisissez une lumière ou un groupe de lumière et allez dans la page de configuration de l'équipement.
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

## Combiner les automatismes

Il vous est possible depuis le plugin de combiner des automatismes pour obtenir le comportement que vous souhaitez.
Exemple: je souhaite que la lumière de mon placard s'allume lorsque j'ouvre la porte. Je souhaite également que la luminosité de la lumière soit plus faible durant la nuit.

Pour cela je vais créer 3 automatismes:
- mon automatisme lumière de placard qui ne gérera pas la luminositée
- un automatisme pour demander une modification de la luminositée à 20% à 21h
- un automatisme pour demander une modification de la luminosité à 100% à 8h

J'affecte ces trois automatismes à ma lumière de placard.

Ainsi lorsque j'ouvrirais la porte à 15h la lumière s'allumera avec une luminosité de 100 %, lorsque j'ouvrirais la porte à 22h, la lumière s'allumera avec une luminosité de 20%.

## A venir

Plusieurs automatismes vont être rajoutés graduellement sur le plugin.
La possibilité d'ajouter plusieurs capteurs sera également proposée.
Enfin il sera possible de prioriser les automatismes entre eux pour une lumière / groupe de lumière
Vous pouvez suivre les avancées depuis le board: <a href="https://github.com/users/hbedek/projects/5">ICI</a>