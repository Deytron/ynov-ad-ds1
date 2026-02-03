# Day 5

# Serveur de fichiers

Vous l'aurez sans doute deviné, le principe d'un serveur de fichiers est de pouvoir stocker et partager un grand nombre de fichiers, mais plus important, faire en sorte que ces fichiers puissent être accessibles dans le réseau, et cloisonnés pour ceux qui en ont besoin.
Vous n'avez pas envie que Martine de la compta puisse accéder à un dossier nommé `CONFIDENTIEL - Codes d'armement nucléaire`.

 Pour mettre en place le serveur de fichiers, assurez-vous que le rôle **Serveur de fichiers** soit bien installé sur votre DC. Vous l'avez normalement fait lors de la création de votre machine.

<img src="https://user.oc-static.com/upload/2022/12/21/16716375255617_unnamed%20%2855%29.png" title="" alt="Installez un serveur de fichiers - OpenClassrooms" width="562">

Mais il va aussi falloir un peu plus d'espace, sur un disque séparé. Même dans une VM, il est nécessaire d'allouer un disque dédié différent pour le stockage des fichiers.

🌞 Dans votre hyperviseur, attachez un nouveau disque à votre VM. Mettez-lui **15 Go**.

🌞 Une fois le disque placé et la machine rallumé, dans le Gestionnaire de partitions, attribuez-lui un nom et une lettre.

🌞 Dans le Gestionnaire de serveurs, catégorie Partages, créez un nouveau partage au format **SMB - Rapide**

🌞 N'autorisez que les utilisateurs d'une de vos OU à pouvoir effectuer des modifications. Donnez uniquement un accès en lecture aux autres groupes.

🌞 Testez l'accès au partage. Sur le PC Windows 11, connectez-vous avec un utilisateur ayant le droit de faire des modifications au partage `\\\NOMDUDC\nompartage`, et créez un fichier

🌞 Connectez-vous avec un autre utilisateur avec uniquement un droit de lecture, puis tentez sur ce partage de renommer le fichier. Que se passe-t-il ?




