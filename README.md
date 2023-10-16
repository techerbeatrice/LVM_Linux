# LVM sur Linux
_____

**Installation d'un système debian avec LVM** 

**Passer en root pour afficher les informations sur le stockage**  

- Volume physique (physical volume = PV) : **1 PV = 1 disque dur**, par exemple /dev/sda
- Groupe de volumes (volume group = VG) : **1 VG =  1 groupe de disques durs**          
- Volumes logiques (logical volume = LV) : **1 LV = 1 groupe partionné de disques durs**      
  
lsblk affiche la liste des périphériques bloc et leur type donc aussi la liste des LV         
pvs, vgs et lvs affichent la liste courte des PV, VG et LV    
pvdisplay, vgdisplay et lvdisplay affichent le détail des PV (disques durs), VG (groupe de disques durs) et LV (groupe partionné de disques durs)       

___

![image](https://github.com/techerbeatrice/LVM_Linux/assets/138071140/2237df91-14eb-460c-9d97-ddde36f23c64)

![image](https://github.com/techerbeatrice/LVM_Linux/assets/138071140/dcc9c421-e9db-4f37-a24d-cd9eaafa3432)

![image](https://github.com/techerbeatrice/LVM_Linux/assets/138071140/1a4e86a7-84e9-4614-9115-22f6619e3370)

____

Affichage des **3 partitions du système**  

![image](https://github.com/techerbeatrice/LVM_Linux/assets/138071140/4bf23b3a-611d-4fb6-ab94-cffa05ceee08)

![image](https://github.com/techerbeatrice/LVM_Linux/assets/138071140/d4c2d5a2-de2a-4f4c-beb7-6b72a393d21d)

____

Ajoute un nouveau disque à la machine et ajoute le au groupe de volume _debian-vg_ pour au moins doubler l'espace du groupe de volume   

![image](https://github.com/techerbeatrice/LVM_Linux/assets/138071140/7b96b2a2-3eb9-4a2b-890d-d10dc53cb07b)

____

Affichage **du nouveau disque (sdb)**     

![image](https://github.com/techerbeatrice/LVM_Linux/assets/138071140/5298d332-c7da-4cd1-8ab5-d9075c933a38)

___

Ajouter le nouveau disque au groupe de volume _debian-vg_ pour au moins doubler l'espace du groupe de volume avec la commande **_vgextend_**     
Vérifier l'ajout du nouveau disque au volume _debian-vg_ avec la commande **_vgdisplay_**      

![image](https://github.com/techerbeatrice/LVM_Linux/assets/138071140/eeec3a3b-1a2f-4a36-82ac-15eea38fa2a0)

___

Créer un snapshot (une sauvegarde) de LV home avec la commande **_lvcreate_** 
Dans un premier temps, vérifier qu'il y a de la place sur le VG : ici il y a 10 go de free  
On crée le snapshot en lui donnant un nom explicite (par exemple le nom du lv avec snap en suffixe) et on lui définit une taille, par exemple ici 4Go :   

![image](https://github.com/techerbeatrice/LVM_Linux/assets/138071140/fb6fed03-480e-4821-997b-11f52e6d5114)

![image](https://github.com/techerbeatrice/LVM_Linux/assets/138071140/ef0faadc-2792-4b6b-90a6-0a5208b5146b)

___

créer le dossier home-snap et monter le snapshot créé sur /home-snap avec la commande **_mount_**   

![image](https://github.com/techerbeatrice/LVM_Linux/assets/138071140/3b2bcd77-bb19-486c-8a97-cc319330b362)

___

On peut alors travailler sur /home-snap et y faire des modifications. En supposant qu'on a maintenant plus besoin de la copie, démonte /home-snap avec la commande **_umount_**  
Détruit le snapshot avec la commande **_lvremove_**  

![image](https://github.com/techerbeatrice/LVM_Linux/assets/138071140/52fcb654-faca-49c6-a588-9ef562ac0cbc)

![image](https://github.com/techerbeatrice/LVM_Linux/assets/138071140/481c4eef-1ccd-459e-b6c5-8ab1cf660641)


