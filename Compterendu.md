Compte rendu
=

*Parti 1 : 

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

0- configuration : connection par pont

1- `aptitude install openssh-server`

2- ssh guillaume@ip
	-> connexion sur la vm reussui
   `ssh root@ip`
    -> connexion impossible

    ON ne peut pas se connecter en ssh avec l'utilisateur root

3- Pour modifier le port d'écoute ssh 
	modifier le ficher /etc/ssh/sshd_config
	Puis remplacer "port 22" par "port 26"
	Ensuite redémarrer le service : /etc/init.d/ssh restart

4- Pour se connecter en ssh sur notre vm gateway maintenant utiliser : ssh user@ip -p 26

	`ssh-keygen -t rsa`
	`ssh-copy-id -i .ssh/id_rsa.pub guillaume@192.168.99.217 -p 26`
	(pb rencontré "sign_and_send_pubkey: signing failed: agent refused operation" : solution ssh-add)
	`ssh guillaume@192.168.99.217 -p 26 `

5- Installation server dhcp 
	`sudo apt-get install isc-dhcp-server`