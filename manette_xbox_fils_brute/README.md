# Manette Xbox à Fils au format Brute

Cette manette à pour bute majoritaire de servir dans des projets de robotique amateur. Son format de sorti n'est donc pas traité et c'est à vous de le faire.

# Etapes de conceptions

## Réalisation du modèle 3D

Pour la réalisation du modèle 3D j'ai décidé d'utiliser freecad 0.20.

### Apprendre FreeCad

Quand j'ai commencé ce projet je n'avais pas une trés grande connaissance de freecad, mais je savais que c'est sur ce logiciel que je voulais faire la partie mécanique de ce controller.

J'ai donc commencé par suivre quelques tutos de bases :
* https://www.youtube.com/watch?v=sVT9Cnz83Q4&t=862s
* https://www.youtube.com/watch?v=twRgek552j0
* https://www.youtube.com/watch?v=sXPapS0WLgk&t=11s
* https://www.youtube.com/watch?v=eWzT33H6jEg&t=9s
* https://www.youtube.com/watch?v=waAOwu4RwCM

Puis des tutos sur des parties plus précises :
* https://www.youtube.com/watch?v=yZQV8tlyq-M
* https://www.youtube.com/watch?v=rBlmyoqXRJw
* https://www.youtube.com/watch?v=MYjEPXKqwfo&t=627s
* https://www.youtube.com/watch?v=BfqCsTaO42U&t=136s
* https://www.youtube.com/watch?v=sn2aU4oMDQA
* https://www.youtube.com/watch?v=p68TArJWZ0k&t=1112s

### Réalisation d'une première version

Après ces tutos j'ai décidé de mettre en application mes connaissances pour voir ce que j'étais déjà capable de faire, et mon premier essaie est encouragant.

![image](https://github.com/ThibaultTostain/controllers/blob/77ab172a65dd84ddcd63c146bc4a7accdef095a2/manette_xbox_fils_brute/imgs/fc_01_multiple_02.webp)

[Plus d'image ici](https://github.com/ThibaultTostain/controllers/tree/main/manette_xbox_fils_brute/imgs)

## Faire le schéma KiCad

### Le souhait de traiter le signal au départ et tout faire soi-même

Au départ je souhaitais faire une vraie manette xbox pour mon ordinateur. Finalement, j'ai voulu y aller étape par étape car le projet semblait trop compliqué pour l'instant. Voici quelques images de ce j'avais avant de changer d'idée

![image](https://github.com/ThibaultTostain/controllers/blob/afe7c352c5dbc51156bcda18fa8cb560bcfa6329/manette_xbox_fils_brute/imgs/ancienne_version_img_03.PNG)

[Plus d'image ici](https://github.com/ThibaultTostain/controllers/tree/main/manette_xbox_fils_brute/imgs)

### Changement de direction : pas de traitement et on ne fait pas tout

#### Fabrication de l'empreinte du Joystick

J'ai d'abord voulu récupérer l'empreinte et le modèle 3D sur un site, mais les fichiers ne fonctionnait pas bien sur KiCad 6.0.7. Du coup j'ai décidé de refaire moi-même l'empreinte. J'ai alors suivi 2 tutos, l'un pour le schéma, l'autre pour le pcb, mais je n'ai pas encore fait la version 3D :
* https://www.youtube.com/watch?v=jlKqVysg-ts
* https://www.youtube.com/watch?v=LMgBfsWX_z0

### Réalisation d'une première version

J'ai donc décidé de réaliser à nouveau un pcb mais cette fois avec un joystick déjà fabriqué et un signal de sorti "brut".

![image](https://github.com/ThibaultTostain/controllers/blob/77ab172a65dd84ddcd63c146bc4a7accdef095a2/manette_xbox_fils_brute/imgs/V2_RT_dessus.png)

[Plus d'image ici](https://github.com/ThibaultTostain/controllers/tree/main/manette_xbox_fils_brute/imgs)

Et même si j'avais déjà posé les contraintes de dimensions sur l'écart entre les élements, le pas entre les boutons, je n'avais pas prété attention dans cette version aux dimensions externes. Ce qui ma fait réaliser une carte bien trop grande pour rentrer dans une manette.

### Optimisation des placements pour tout faire rentrer dans un format conventionnel

J'ai donc décidé de réarenger les composants pour avoir des dimensions plus petite. Et avec succés, j'ai réalisé une carte qui rentre dans un boitier de manete sans problème, et cela en gardant la contrainte de pouvoir fabriquer cette pièce facilement chez soi, et donc sans composants CMS.
On est passé de 106x74mm à 100x53mm, soit une réduction de 32% de la surface.

![image](https://github.com/ThibaultTostain/controllers/blob/77ab172a65dd84ddcd63c146bc4a7accdef095a2/manette_xbox_fils_brute/imgs/V2.1_RT_dessus_cote.png)

[Plus d'image ici](https://github.com/ThibaultTostain/controllers/tree/main/manette_xbox_fils_brute/imgs)

### Prochaine étape : mettre une extension de ports Arduino intégré tout en restant dans les tailles limites

Pour réduire le nombre de pins utilisés par la manette, j'aimerai ajouté une extension de ports arduino directement dans la manette pour n'utiliser que 2 pins Arduino mais tout de même garder les pins lisibles séparement par l'Arduino.

Voici mes premières ressources :
- https://esphome.io/cookbook/arduino_port_extender.html
- https://thecustomizewindows.com/2017/10/increase-number-digital-pins-arduino/
