# LVM sur Linux

Installation d'un système debian avec LVM   

L'ensemble des commandes et leurs affichages sont à recopier dans la solution de cette quête   

Ajoute un nouveau disque à la machine et ajoute le au groupe de volume debian-vg pour au moins doubler l'espace du groupe de volume
Créer un snapshot de LV home   
Monte le snapshot créé sur /home-snap   
Constate que /home-snap est bien une copie de /home   
On peut alors travailler sur /home-snap et y faire des modifications. En supposant qu'on a maintenant plus besoin de la copie, démonte /home-snap   
Détruit le snapshot  

_____

