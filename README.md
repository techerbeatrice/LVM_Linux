# LVM sur Linux
_____

**Installation d'un système debian avec LVM** 

**Passer en root pour afficher les informations sur le stockage**  

lsblk affiche la liste des périphériques bloc et leur type donc aussi la liste des LV   
pvs, vgs et lvs affichent la liste courte des PV, VG et LV  
pvdisplay, vgdisplay et lvdisplay affichent le détail des PV, VG et LV  

___

![image](https://github.com/techerbeatrice/LVM_Linux/assets/138071140/2237df91-14eb-460c-9d97-ddde36f23c64)

![image](https://github.com/techerbeatrice/LVM_Linux/assets/138071140/dcc9c421-e9db-4f37-a24d-cd9eaafa3432)

![image](https://github.com/techerbeatrice/LVM_Linux/assets/138071140/1a4e86a7-84e9-4614-9115-22f6619e3370)

____

Affichage des 3 partitions du système

![image](https://github.com/techerbeatrice/LVM_Linux/assets/138071140/4bf23b3a-611d-4fb6-ab94-cffa05ceee08)

![image](https://github.com/techerbeatrice/LVM_Linux/assets/138071140/d4c2d5a2-de2a-4f4c-beb7-6b72a393d21d)

____

Ajoute un nouveau disque à la machine et ajoute le au groupe de volume debian-vg pour au moins doubler l'espace du groupe de volume   

![image](https://github.com/techerbeatrice/LVM_Linux/assets/138071140/7b96b2a2-3eb9-4a2b-890d-d10dc53cb07b)

____

Affichage du nouveau disque (sdb)   

![image](https://github.com/techerbeatrice/LVM_Linux/assets/138071140/5298d332-c7da-4cd1-8ab5-d9075c933a38)

___

Ajoute le au groupe de volume debian-vg pour au moins doubler l'espace du groupe de volume   

