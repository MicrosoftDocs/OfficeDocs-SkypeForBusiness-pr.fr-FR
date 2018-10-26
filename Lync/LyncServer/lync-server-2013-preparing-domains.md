---
title: 'Lync Server 2013 : Préparation des domaines'
TOCTitle: Préparation des domaines
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398721(v=OCS.15)
ms:contentKeyID: 49298042
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Préparation des domaines pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-29_

La préparation du domaine est l’étape finale dans la préparation des services de domaine Active Directory pour Lync Server 2013. L’étape de préparation du domaine ajoute les entrées de contrôle d’accès nécessaires aux groupes universels qui accordent les autorisations d’hébergement et de gestion des utilisateurs dans le domaine. La préparation du domaine créé des entrées de contrôle d’accès sur la racine du domaine et dans trois conteneurs intégrés : Utilisateurs, Ordinateurs et Contrôleurs de domaine.

Vous pouvez exécuter la préparation du domaine sur n’importe quel ordinateur du domaine sur lequel vous déployez Lync Server. Vous devez préparer chaque domaine destiné à héberger un serveur ou des utilisateurs Lync Server.

Si l’héritage des autorisations ou les autorisations des utilisateurs authentifiés sont désactivés dans votre organisation, la procédure de préparation du domaine comporte des étapes supplémentaires. Pour plus d’informations, reportez-vous à [Préparation des services de domaine Active Directory verrouillés dans Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

Si votre organisation utilise des unités d’organisation à la place des trois conteneurs intégrés (Utilisateurs, Ordinateurs et Contrôleurs de domaine), le groupe Utilisateurs authentifiés doit disposer d’un accès en lecture aux unités d’organisation. L’accès en lecture aux conteneurs est obligatoire pour la préparation du domaine. Si tel n’est pas le cas, exécutez l’applet de commande **Grant-CsOuPermission** comme illustré dans les exemples de code suivants afin d’accorder des autorisations de lecture pour chaque unité d’organisation.

```
Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
```
```
Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
```

Pour plus d’informations sur l’applet de commande **Grant-CsOuPermission**, reportez-vous à la documentation Lync Server Management Shell.

> [!TIP]  
> Pour plus d’informations sur les entrées de contrôle d’accès créées sur le domaine racine et dans les conteneurs Utilisateurs, Ordinateurs et Contrôleurs de domaine, reportez-vous à <a href="lync-server-2013-changes-made-by-domain-preparation.md">Modifications effectuées par la préparation de domaine dans Lync Server 2013</a>.

## Dans cette section

  - [Exécution de la préparation du domaine pour Lync Server 2013](lync-server-2013-running-domain-preparation.md)

  - [Utilisation d’applets de commande pour inverser la préparation d’un domaine pour Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

