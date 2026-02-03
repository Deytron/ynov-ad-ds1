# Day 5

# Serveur de fichiers

Vous l'aurez sans doute deviné, le principe d'un serveur de fichiers est de pouvoir stocker et partager un grand nombre de fichiers, mais plus important, faire en sorte que ces fichiers puissent être accessibles dans le réseau, et cloisonnés pour ceux qui en ont besoin.
Vous n'avez pas envie que Martine de la compta puisse accéder à un dossier nommé `CONFIDENTIEL - Codes d'armement nucléaire`.

 Pour mettre en place le serveur de fichiers, assurez-vous que le rôle **Serveur de fichiers** soit bien installé sur votre DC. Vous l'avez normalement fait lors de la création de votre machine.

<img src="https://user.oc-static.com/upload/2022/12/21/16716375255617_unnamed%20%2855%29.png" title="" alt="Installez un serveur de fichiers - OpenClassrooms" width="562">

Mais il va aussi falloir un peu plus d'espace, sur un disque séparé. Même dans une VM, il est nécessaire d'allouer un disque dédié différent pour le stockage des fichiers.

🌞 Dans votre hyperviseur, attachez un nouveau disque à votre VM. Mettez-lui **15 Go**.

🌞 Une fois le disque placé et la machine rallumé, dans le Gestionnaire de serveurs, rendez-vous dans la partie **Services de fichiers et de stockage**, puis dans **Volumes > Pools de stockage**. Ajoutez votre nouveau disque dans le pool de stockage pour le rendre utilisable. Si besoin, relancez l'analyse du stockage.




