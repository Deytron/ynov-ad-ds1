# Day 6 à peu près

# Stratégie de mot de passe affinée (PSO)

Il existe deux manières d'appliquer des stratégies de mots de passe et de forcer vos utilisateurs à éviter de mettre "Azerty123" partout : 

- En GPO **Default Domain Policy**

- En utilisant une **PSO**

La deuxième option est la meilleure, car plus granulaire et plus précise en terme de ciblage. Par exemple, vous pouvez facilement faire en sorte que vos utilisateurs soient forcés à avoir un mot de passe d'au moins 8 caractères, et vos comptes admin le double.

Tout le concept de mise en place d'une PSO et les explications sont présentes comme d'hab [ici](https://www.it-connect.fr/strategie-de-mot-de-passe-affinee-sous-windows-server-2012-r2/) (oui je vais pas réinventer la roue)

---

🌞 Pour vos OU admins dans chaque tier, appliquez une politique stricte : 16 caractères, majuscule, minuscule, chiffre, caractère spécial, pas de ressemblance aux anciens mots de passe

🌞 Pour vos autres OU, appliquez la même chose avec 12 caractères seulement

🌞 Vérifiez les politiques appliquées pour un utilisateur admin et un utilisateur d'une autre OU

🐸 Remettez tout le paramétrage précédent en Powershell pour pouvoir refaire les actions plus vites si besoin




