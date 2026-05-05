# Hugo Mériaux

# 2526_Maker_Oreiller_Reveil

## Vidéo

lien : https://drive.google.com/file/d/12lueG6ONoEjNcp9p2Bfdsy5rfTH5zyUq/view?usp=sharing

## Objectif du projet

Le but de ce petit projet est de créer un réveil intégré dans un oreiller qui puisse nous réveiller à coup sur afin de nous faire éviter d'être en retard au CM de 8h. J'aimerai pouvoir ajouter de la couture et faire moi même l'oreiller pour réutiliser les compétences apprises lors de l'atelier couture.
De plus, ce projet contiendra de la CAO et de l'impression 3D pour le boitier ainsi qu'un PCB et un pack de LIPO.


## Retro-Planning

Lundi 13 avril 2026 - Projet terminé

Jeudi 9 avril 2026 - Conception oreiller

Jeudi 2 avril 2026 - Conception oreiller

Lundi 30 mars 2026 - Programmation

Jeudi 26 mars 2026 - Programmation

Lundi 23 mars 2026 - Soudure PCB

Jeudi 19 mars 2026 - Soudure PCB

Lundi 16 mars 2026 - Soudure PCB

Jeudi 12 mars 2026 - Modélisation 3D et impression 3D

Lundi 9 mars 2026 - Modélisation 3D et impression 3D

Jeudi 19 février 2026 - PCB

Lundi 16 février 2026 - PCB


## Réflexion autour des composants à utiliser

Pour être sur d'être réveillé je vais miser sur 2 actionneurs différents : 
- un petit vibreur (le VPM1)
- un haut parleur (le ASX03608-R, petite particularité pour ce dernier je vais esssayer d'utiliser un exciter qui est un HP qui ne fait pas vibrer l'air mais la surface sur laquelle il est fixé ca va permetter théoriquement de faire une caisse de résonnance avec le boitier)

Au niveau des capteurs je vais utiliser un capteur de force, le FSR03 qui va me permettre de savoir si la tête de la personne est toujours sur l'oreiller pour pouvoir désactiver l'alarme quand il se leve.

Enfin je vais utiliser un module Bluethooth, le HC-05 qui va me permetttre une connexion sans fil au réveil pour le configurer et éventuellement l'arreter sans le capteur de force.

Pour pouvoir utiliser le Haut-Parleur et choisir des musiques en fonction de l'intensité de réveil je vais me baser sur le DFPlayer.

Le tout piloté par un NUCLEO G431KB.

Liste des composants : 
- https://www.gotronic.fr/art-vibreur-miniature-vpm1-32423.htm
- https://www.gotronic.fr/art-capteur-de-force-fsr03-17595.htm
- https://www.gotronic.fr/art-module-mp3-dfplayer-22404.htm
- https://www.mouser.fr/ProductDetail/PUI-Audio/ASX03608-R?qs=RXK%252BYb%252BisXRSfadtXjQpoA%3D%3D
- https://www.gotronic.fr/art-vibreur-miniature-vpm1-32423.htm
- https://www.st.com/en/evaluation-tools/nucleo-g431kb.html

## PCB

On commence par ce qui va mettre le plus de temps à arriver à savoir le PCB.

<img width="1091" height="755" alt="image" src="https://github.com/user-attachments/assets/d7c47ec2-fe15-423e-997c-94ffdfc06a48" />

 <img width="673" height="587" alt="image" src="https://github.com/user-attachments/assets/919122b6-a07b-4a5a-9f40-a83959bd2229" />

 <img width="932" height="791" alt="image" src="https://github.com/user-attachments/assets/80ddd4d1-ada7-45f6-add9-b252e8c72312" />

 <img width="918" height="776" alt="image" src="https://github.com/user-attachments/assets/6d7b96f2-e859-4697-9779-c412285f0465" />

 On soude nos différents composants dessus.

## Modélisation et Impression 3D

Puis on vient modéliser et imprimer un boitier qui contiendra toute notre électronique.

<img width="1167" height="745" alt="image" src="https://github.com/user-attachments/assets/9fd57685-7a48-41cf-9045-298872422ef7" />

## Plusieurs revers et changements de direction du projet

Après avoir tout soudé premier problème qui advient c'est que le DFPlayer qui commande le HP ne veut pas s'alimenter je n'ai aucune LED témoin, rien.
Pas le temps d'en commander un autre donc on laisse tomber la partie HP et on se concentre sur le vibreur.

Je me rends compte égalemennt de l'inutilité du capteur de force qui fait que si la personne ne mets plus sa tête sur l'oreiller l'alarme s'arrete et on peut continuer de dormir donc je décide de l'enlever du projet.

De même, j'avais initiallement prévu le projet pour être alimenté via une batterie 1S mais je me rends compte qu'il va fallori utiliser une batterie 2S et que je n'ai pas de BMS USB 2S donc on ne pourra recharger l'oreiller que en le dévissant et en rechargant manuellement la batterie. En réalité la consommation est tellement ridicule et la batterie tellement surdimensionnée que ca ne devrait pas être véritablement une contrainte.

Enfin je me rends compte que je commence à être vraiment juste au niveau du temps et je préfère me concentrer sur avoir un produit fini et fonctionnel plutôt qu'avec des fonctionnalités plus intéressantes mais non fonctionnel donc je décide aussi de supprimer l'étape de couture de l'oreiller qui va me prendre trop de temps. On viendra glisser le boitier sous ou dans un oreiller classique.
