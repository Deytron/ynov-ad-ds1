# Day 2

# Hiérarchie d'un AD

Un Active Directory dispose d'une hiérarchie. C'est-à-dire que des objets vont contenir d'autres objets, qui vont eux-même en contenir d'autres etc...

Le tout premier objet, et en soi le plus important dans un domaine, est **l'Organizational Unit**, ou OU pour faire court. C'est littéralement une sorte de gros dossier, qui peut lui-même contenir d'autres OU, ou tout élément comme un ordinateur, ou un utilisateur, un groupe etc...
L'intérêt d'une OU est d'une part de créer une sorte de spécialisation, un peu comme dans la vraie. On peut prendre l'exemple d'Ynov, où on pourrait avoir une **OU Informatique**, et une **OU Marketing**. Chacune se verra contenir des éléments différents, comme dans la vraie vie, où il n'y a pas les même cours ou les mêmes étudiants dans ces filières. Pourtant, elles sont dans le même domaine.

![21 Effective Active Directory Management Tips - Active Directory Pro](https://activedirectorypro.com/wp-content/uploads/2022/12/ou-best-practice-2.webp)

Gardez en tête que chaque OU peut contenir tout type d'objet. D'ailleurs, voici la liste des principaux objets d'un Active Directory : 

## Objets conteneurs

Ces objets **peuvent** contenir d'autres objets à l'intérieur. Outre les OU, on compte :

### Les groupes

Un groupe Active Directory est un object pouvant contenir d'autres objets, aussi bien des ordinateurs que des utilisateurs. Ça ressemble vachement aux OU, à quelques différences près : 

- On se sert de groupe de manière plus rapide et facile pour rassembler des éléments par rapport aux OU

- Il n'est pas possible de faire de délégation de contrôle sur un groupe, ou du moins c'est pas fait pour

- Les GPO s'appliquent à des OU, et pas à des groupes.  Si vous souhaitez appliquer une GPO uniquement sur un groupe, vous allez passer par un filtre, et ça peut vite devenir le bordel

Un point intéressant des groupes est que pour une utilisation avec une appli et un lien LDAP, les groupes ont un attribut `members` qui listent directement tout ce qu'il y a dedans.

## Objets leaf

Les objets leaf représentent des points finaux, des objets qui **ne peuvent pas** contenir d'autre objet.

### Les utilisateurs

Le truc que vous allez utiliser le plus. Le coeur de l'Active Directory. Un utilisateur dispose de beaucoup de propriétés qui n'ont pas changées depuis les débuts de l'Active Directory : nom, prénom, SID, fonction, téléphone..
Vous pouvez attribuer des groupes aux utilisateurs, qui auront le droit de faire telles actions ou être bloqués pour telles actions.

> Il est déconseillé d'appliquer des droits uniquement sur un utilisateur. Selon le principe **d'ADGLP** (qu'on verra plus tard), associez toujours un utilisateur à un groupe, puis attribuez des permissions à ce groupe.

### Les contacts

Comme des utilisateurs, mais vous ne pouvez pas vous en servir pour vous connecter à une session.
C'est vraiment juste pour noter que quelqu'un existe. Complètement désuet depuis l'arrivée de l'Internet moderne et de l'interconnexion de la planète, genre depuis 30 ans.

### Les imprimantes

<img src="assets/2026-01-26-21-05-44-image.png" title="" alt="" width="317">

Le putain d'enfer sur Terre. Sauf dans un AD.
Dans le même principe que les utilisateurs, les objets imprimantes disposent de propriétés différentes comme un port et une adresse, contrairement aux utilisateurs.

### Les ordinateurs

Pour le coup bien différent des utilisateurs, un ordinateur peut logiquement appartenir à un utilisateur (mais personne ne fait ça). Les objets ordinateurs disposent de GPO Ordinateur, différentes des GPO utilisateur et qu'on verra plus tard. En terme de propriétés, ils disposent d'un nom NETBIOS, d'un nom DNS, d'un rôle, d'une version d'OS etc...

### Les autres

Sans rentrer dans les détails, voici les autres objets qui existent mais que vous verrez moins souvent : 

- **Les dossiers partagés** : Gérés différemment depuis longtemps, ils servaient à rendre disponibles des ressources dans un domaine.

- **Les contrôleurs de domaine** : C'est un vrai objet que vous pouvez gérer dans votre DC, comme un PC

- **Les sites** : Disposant d'une console pour eux-mêmes, les sites permettent d'autres paramétrages granulaires de certains services dans votre domaine

# Attributs

Les attributs sont présents sur TOUS les objets AD, sauf les OU. Ces attributs peuvent être lus et manipulés si l'on en a les droits.

[Vous pouvez retrouver la plupart des attributs les plus importants ici.]([Les principaux attributs d’objets dans l&#39;Active Directory](https://www.it-connect.fr/chapitres/les-principaux-attributs-dobjets-dans-lactive-directory/)), très bien expliqué.

> En gros, retenez surtout l'importance des `cn`, `distinguishedName` et `samAccountName`

## Lire un attribut

Pour lire un attribut, pas le choix, vous allez devoir passer par du **Powershell**. C'est le langage de prédilection de scripting pour les systèmes Microsoft, apparu avec Windows Server 2003 R2.

Contrairement aux autres langages de scripting comme Bash, le Powershell se permet le luxe de réinventer la roue en utilisant des mots clés avec casse et anglais pour exécuter ses actions. Exemple : 

- Pour tester si un port d'une machine est acessible avec Linux (Bash) : `telnet MACHINE PORT`

- En Powershell : `Test-NetConnection -ComputerName MACHINE -Port PORT`

C'est bien plus verbeux, mais ça a le mérite d'être clair. Très clairement, on aime ou on aime pas.

Pour chercher un utilisateur, vous allez devoir utiliser le module `Get-ADUser` Exemple : 

- Trouver un mec avec comme nom **jmorana** : `Get-ADUser -Identity jmorana -Properties *` 
  
  ```
  Surname           : Morana
  Name              : Julien Morana
  UserPrincipalName :
  GivenName         : Julien
  Enabled           : True
  SamAccountName    : jmorana
  ObjectClass       : user
  SID               : S-1-5-21-2889043008-4136710316-2444824263-3544
  ObjectGUID        : e1418d64-096c-4cb0-b903-ebb66562d99d
  DistinguishedName : CN=Julien Morana,OU=NorthAmerica,OU=Sales,OU=UserAccounts,DC=FABRIKAM,DC=COM
  ```

- Afficher certaines propriétés de manière un peu stylisée : `Get-ADUser -Filter 'Name -like "*Julien Morana"' | Format-Table Name,SamAccountName -A`

```
Name             SamAccountName
----             --------------
Julien Morana     jmorana    
```

# Un peu de sécurité : le principe du Tiering

Récemment (genre depuis une dizaine d'années hein), Microsoft, l'ANSSI et tous les pros dans le domaine, se sont penchés sur la problématique de **l'admin du domaine**. Avec un compte pété, un attaquant a accès à littéralement toute votre infrastructure en tant qu'admin, ce qui est une catastrophe. L'approche du Tiering **permet** de réduire le risque encouru d'un compte admin compromis en cloisonnant proprement les ressources dans un AD.

[Vous pouvez retrouver toutes les infos textuelles sur le tiering ici.]([Sécuriser Active Directory : comprendre le Tiering Model](https://www.it-connect.fr/active-directory-tiering-model-les-fondamentaux/))

# On va manipuler un peu

> Imaginez-vous une entreprise au choix histoire de vous amuser un peu, de manière à ce que différents départements puissent exister à l'intérieur. Ça peut tout simplement être Ynov, ou alors une grosse entreprise d'import export de saumon, ou un Active Directory pour les employés d'un site de fiak. Le choix est libre.

🌞 Dans votre AD, créez au moins **4 OU au premier niveau, dont 2 de ces OU contiennent au moins une sous OU**. En gros, ça ressemblerait à ça :

```
.
├── Admins
├── Compta
│   ├── Departement Nord
│   └── Departement Sud
├── Finances
└── Market
    └── France
```

🌞 Peuplez ces OU avec des utilisateurs. Faites-en une dizaine bien répartis

🌞 Créez une **OU Computers ou Ordinateurs**. Celle de base est un conteneur, pas vraiment utilisable.

🌞 Créez une **OU Admins**, ou vous y créerez des comptes admins.

🌞 Rendez vos comptes "admins" en les ajoutant à un groupe

🌞 Vous voyez le PC que vous avez joint au domaine ? Trouvez-le, mettez-le dans votre AD ordi créée précédemment

🌞 Sur le PC Windows 11, avec le RDP activé, créez un groupe qui permet d'autoriser un utilisateur à se connecter à distance à ce PC

## Plus de manips

🐸 Allez plus loin : sur le modèle du tiering, faites les trois tiers dans votre AD

🐸 Créez des comptes admins avec chacun un tier d'accès assigné
