# Day 1

## Y avait quoi avant ?

À l'époque, à l'arrivée de l'informatique dans les entreprises dans les années 70 80, y a avait pas Linux ou Windows. À l'arrivée des vrais systèmes d'exploitation UNIX ou DOS, c'était le far west et chaque boîte faisait son OS à vendre aux entreprises pour pouvoir utiliser leur informatique. Et l'OS était bien sûr payant et coûtait une méga couille, genre les licences System 3 et 32V pour un seul CPU venant d'AT&T (l'opérateur américain), c'était 10k$. Sun (Solaris), c'était 25k.

En 1988 est arrivé Richard Stallman, un gros gourou extrêmiste au point de désactiver Javascript sur toutes les pages et de faire ses toilettes open-source s'il le pouvait, qui a amené la norme **POSIX** qui est une famille de normes techniques pour les systèmes Unix.

> Par exemple, dans Linux, le fait de dire que le dossier actuel c'est ., deux dossiers en arrière c'est .., et trois dossiers en arrière c'est ... et ainsi de suite, c'est les conventions POSIX.

En soi POSIX n'est pas le sujet principal, mais c'est assez intéressant de le mentionner pour montrer la philosophie de Microsoft, qui n'a jamais pensé un seul instant à utiliser l'existant et a toujours fait avec son propre MS-DOS.

## L'arrivée de Windows NT et Server

En 1993 arrive Windows NT 3.1 Advanced Server, une édition spéciale de Windows NT 3.1 orientée gestion et management d'ordinateur comme serveur et non poste personnel.

<img title="" src="https://socket3.wordpress.com/wp-content/uploads/2016/10/nt31as-1.jpg" alt="eBay Purchase #1 – Windows NT Advanced Server 3.1 – Socket 3" width="288" data-align="inline">

Personne dans cette classe n'était né. Voilà.

L'intérêt de cette version de Windows est que par rapport à l'époque, c'est un Windows entier qui n'avait pas besoin d'être lancé depuis DOS, en plus d'ajouter tous les trucs de base dans un OS genre le TCP/IP, le FTP et tout ce qui vient avec. Mais surtout, pourquoi par rapport à aujourd'hui avec une omniprésence de Linux dans les plus grosses boîtes et une gratuité de l'OS, est-ce que Windows Server est-il aussi utilisé dans le monde avec son prix et ses inconvénients ?

## Pourquoi Windows Server ?

De la même manière que tout le monde parle anglais parce que... bah tout le monde parle anglais, tout le monde utilise Windows Server parce que c'est le truc que tout le monde a. Il faut bien se dire qu'à l'époque, l'informatique c'est très nouveau et à moins d'avoir un papy barbu, personne ne savait trop comment ça fonctionnait dans le monde hors entreprise.

Le corps de métier en lui-même ne peut devenir accessible que s'il l'est au grand public, et à l'époque dans les années 90, les gens avaient MS-DOS à la maison avec son interface utilisateur parue en 85. Donc les gens ont appris depuis le temps à se familiariser avec cet OS, et l'arrivée de Windows 95 et 98 va conforter la place de Microsoft et donc l'utilisation de l'OS par les gens. Si ça fait des années que les gens utilisent un truc qui ressemble à ce qu'ils pourraient utiliser au taf, c'est bien plus pratique de bâtir des infrastructures avec des cerveaux déjà habitués et doués sur l'outil.

Linux n'est arrivé qu'en 1995, et juste après ça Windows Server 2000 est arrivé. Depuis le temps, tout le monde a déjà fait joujou avec DOS ou Windows et a des connaissances dessus. De ce fait, les entreprises voulant un système d'information n'avaient pas forcément besoin de tout réapprendre aux administrateurs systèmes qui arrivaient car ils avaient déjà des connaissances, et de ce fait, les prestataires faisant des logiciels pouvaient cibler Windows si cet OS était le plus utilisé, faisant un cercle vertueux.

**Les gens connaissent Windows > L'entreprise recrute des gens déjà formés > Windows est de plus en plus utilisé > Les gens connaissent Windows**

Ça c'est sur le plan social et pratique. D'un point de vue technique, l'**Active Directory** et tout le management des systèmes d'un serveur avec une interface graphique est un cadeau de dieu. Bien plus accessible, l'annuaire permet à même des gens qui ne sont pas 100% qualifiés pour le faire de créer des utilisateurs dans une entreprise, avec tout qui est déjà codifié : les groupes, les permissions etc... Et à une époque où on passait du papier aux PC, il fallait absolument réduire les temps d'adaptation des employés, et c'était parfait.

![Vue d'ensemble du tutoriel ADSI avec Visual Basic - Win32 apps | Microsoft  Learn](https://learn.microsoft.com/fr-fr/windows/win32/adsi/images/adadsi1.png)

Genre ça là, c'est de la folie. C'est trop bien. Du moins d'un point de vue gestion.

## Et de nos jours ?

De nos jours, il est assez simple de dresser un constat sur l'utilisation des OS côtés serveurs.

- Si vous êtes une grosse boîte blindée de thunes : tout tourne sous des couches de virtualisation supérieures (type Kubernetes), souvent cloud. Donc au final, basé sur du Linux.

- Si vous êtes une entreprise française moyenne : un très grand nombre d'entreprises dispose de centaines de VM sous Windows Server. De nos jours, ça va généralement du 2012 R2 avec support étendu jusqu'au 2022.

Évidemment, c'est vu ici sous le prisme de l'argent, mais ça dépend toujours d'un gros nombre de facteurs : corps de métier, nombre d'employés, âge de l'entreprise, habitudes des anciens sysadmins...
Mais généralement, l'aspect historique gagne toujours. En prenant l'exemple d'une manufacture de portes (oui sacré exemple), leur système d'informations est généralement renouvelé à rythme fixe avec des contrats des prestataires. Si par exemple, ils doivent changer leur logiciel ou leur machine tous les 10 ans, ça fait un coût à peu près fixe tous les 10 ans. En imaginant qu'il faille changer l'OS, si les admins sur place ne connaissent que Windows, il faudra dépenser plus d'argent pour soit les remplacer, soit les former à un autre OS. On peut donc voir pourquoi les choses changent assez lentement.

C'est pour ça que de nos jours, si vous restez en France et surtout pour vos débuts, **les connaissances de base du fonctionnement d'une entreprise sous Windows Server sont primordiales.** D'ailleurs, vous aurez mille fois plus de chances d'être recruté en junior dans une boîte en affichant vos compétences avec et Windows et Linux.

Par contre, comme Linux est enseigné dans toutes les écoles comme OS primaire avant même Windows, du fait de sa simplicité d'utilisation plus relative, son efficacité et et gratuité (surtout), en plus d'amener toutes les notions d'open-source, il n'est pas rare de voir des entreprises prendre le train en marche et changer radicalement de systèmes dans leur SI. Effectivement, si vos ingénieurs partent à la retraite, et que vos futurs employés s'adaptent au marché, aka Linux, vous n'aurez pas d'autres choix que de faire un peu de changement dans votre SI. Même débat avec les langages de programmation : Plus personne ne fait de Pascal ou de Fortran. Tout le monde fait du C++, du Python ou du Javascript (par exemple).

# Comment ça marche ?

> Nous n'allons ici pas rentrer dans les détails type ressources serveur, redondance, réseau etc... On va en parler en cours, ce sera plus visuel et plus parlant

Tout SI basé sur Windows Server est basé sur un **Active Directory**. Un AD, c'est comme une grosse base de données qui contient des objets. Ça peut être des utilisateurs, des ordinateurs, des groupes, des comptes de service, des imprimantes etc...

Généralement, l'AD est hébergé sur le même serveur que le Contrôleur de domaine (DC), et il y en a toujours **au moins 2** d'un point de vue logiciel. Si y en a un qui meurt, l'autre prend le relais.

Chaque AD tient un domaine, qui est généralement au format **nomentreprise.zone**. C'est pas très parlant comme ça, mais on peut s'imaginer que pour les employés d'Ynov Bordeaux, le domaine pourrait être `ynov.bordeaux`, ou `bordeaux.ynov.campus`, ou tout autre nom qui fait sens et qui rentrerait. Tous les objets d’un domaine partagent les mêmes règles de base et font confiance au même AD.

Sur des très grosses entreprises, il est possible d'avoir des **forêt**, et là le nom parle littéralement de lui-même. Vous pouvez disposer de plusieurs domaines dans une forêt. Exemple toujours avec Ynov : 

- `bordeaux.ynov.local`

- `paris.ynov.local`

- `roubaix.ynov.local`

La forêt définit :

- Le schéma AD (structure des objets)

- Les règles globales

- Les limites de sécurité majeures

**Une forêt = une entreprise (dans 95 % des cas)**

<img src="https://www.varonis.com/hs-fs/hubfs/Imported_Blog_Media/domain-forest@2x.png?width=3000&height=2664&name=domain-forest@2x.png" title="" alt="What is an Active Directory Forest?" width="715">

# Le plan

Comme prévu dans le README, on va prévoir les choses comme ceci : 

- On va créer un domaine, avec les composants de base, à savoir :
  - Un Windows Server 2022 contrôleur de domaine
  - Une machine Windows 11 qui servira de client test pour se connecter au domaine
- Ce domaine portera le nom que vous souhaitez, en gardant la nomenclature type `aaa.bbb` ou `aaa.bbb.ccc`.
- On intégrera le PC Windows 11 dans le domaine et on créera des utilisateurs tests pour voir s'ils peuvent se connecter

---

# Étapes

- [ ] Télécharger les ISO de Windows Server 2022 et Windows 1
  Vous pouvez les trouver à ces adresses : [Télécharger Windows Server 2022 (64 bits) (gratuit) – Systèmes d’exploitation – Le Crabe Info](https://lecrabeinfo.net/telecharger/windows-server-2022-x64/) et [Télécharger les ISO de Windows 11 (64 bits) (français) – Le Crabe Info](https://lecrabeinfo.net/tutoriels/telecharger-iso-windows-11/)

- [ ] Téléchargez et installez l'hyperviseur selon votre OS
  Si vous êtes sur Windows : Faites simple et téléchargez [Vmware Workstation]([VMWare Workstation Pro 25H2 Download | TechPowerUp](https://www.techpowerup.com/download/vmware-workstation-pro/)) qui a été rendu complètement gratuit
  Si vous êtes sur Mac : ...J'en ai aucune foutre idée, on verra sur place
  Si vous êtes sur Linux : Vous avez le choix. Ça change selon votre distrib. Je vous conseille d'utiliser Libvirt, autrement vous pouvez installer VirtualBox ou Vmware Workstation

- [ ] Procédez à l'installation de la VM Windows Server 2022. Mettez-y 2 vCPU et minimum 4Go de RAM, et 50Go d'espace disque

- [ ] Procédez à l'installation de la VM Windows 11. Mettez-y 2 vCPU, 4Go de RAM et 30Go d'espace disque.

- [ ] Sur les deux VM, le paramétrage initial est identique. Partitionnez les disques, entrez un mot de passe pour le compte administrateur local et **notez-le quelque part**

- [ ] Une fois les VM sur le bureau, paramétrez le réseau de vos VM en IP fixe selon le réseau virtuel donné par votre hyperviseur

- [ ] Assurez-vous que les deux VM puissent communiquer entre elles, normalement sans configuration de base, elles sont dans le même réseau

# Créer un domaine

Il va être temps de créer un domaine. Comme expliqué avant, ce domaine va servir à lier tous vos PC pour y appliquer des règles entre autre, histoire qu'ils soient tous quasi identiques.
Pour créer un domaine, rendez-vous sur votre machine Windows Server (n'hésitez pas à activer le RDP si ce n'est pas fait).

Ensuite, pas besoin de réinviter la roue. [Ce tutoriel explique très bien de manière textuelle ce qu'il faut faire]([Créer un domaine Active Directory avec Windows Server](https://www.it-connect.fr/creer-un-domaine-ad-avec-windows-server-2016/)).

# Rejoindre le domaine

Une fois le domaine créé et les étapes de redémarrage insupportables de la machine faites, [faites rejoindre le domaine avec votre PC Windows 11]([Joindre un PC Windows 10 au domaine, peu importe la version | IT-Connect](https://www.it-connect.fr/joindre-un-pc-windows-10-au-domaine-peu-importe-la-version/)).
