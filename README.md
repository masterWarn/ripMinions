# ripMinions
Procédure de root de Blinux 3.0

## Avertissement
> "Un grand pouvoir implique une grande responsabilité."

Attention, une fois root, vous pouvez tout faire sur vos dump. Si vous faites une connerie vous êtes le seul responsable, surtout si vous devez redump.

## Procédure

Modification du sudoers:

-Booter sur Windows et installer ext2fsd (permet l'accès à votre partition linux depuis windows):
http://www.ext2fsd.com/
-Modifier le fichier /etc/sudoers de votre partition blinux 3.0. (Par défaut la lettre attribué sous windows est D).
Vous devez changer la ligne:

> ALL =(ALL) ALL

en:

> ALL =(ALL) NOPASSWD:ALL

Sauvegardez puis booter sous Blinux

Root de blinux et désactivation des salt minions et du salt master (script anti root):

Puis dans un terminal taper ces 5 commandes:

sudo su (pour passer root)
passwd root (pour changer le mot de passe du compte root)
pkcon remove salt-minion
systemctl disable salt-master
systemctl disable salt-minion

Rebootez la machine.
Félicitation, vous êtes root.
Si après reboot sudo vous demande un mot de passe root, appliquez la procedure de modification du sudoers ci dessus.
