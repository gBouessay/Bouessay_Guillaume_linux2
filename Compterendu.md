**Compte rendu**

*Parti 1 :* 

créer une vm debian

Je n'ai pas accès a visudo avec mon utilisateur car je ne suis pas en root. 
Les groupes de mon utilisateur courant sont : guillaume, cdrom, floppy, audio, dip, video, plugdev, netdev, bluetooth
Il n'appartient pas au groupe root

ensuite cloner la en 3 exemplaires : Gateway, Serveur Web, Client

La vm ne démarre pas car on a supprimer la racine 

configurer la connexion réseau de votre vm en mode "par pont" sur la vm debian_base

ensuite lancé votre vm, lancer la commande lynx

puis saisir les identifiants pour vous connecter au réseau afin de pouvoir avoir accès aux sites via lynx
Ensuite en utilisant la commande lynx suivi d'une url valide on a accès à la page web en ligne de commande.

*Parti 2 :*

1- configuration : connection par pont

2- aptitude install openssh-server

3- ssh guillaume@ip
	-> connexion sur la vm reussui
   ssh root@ip
    -> connexion impossible

    ON ne peut pas se connecter en ssh avec l'utilisateur root

4-
