---
title: "Lync Server 2013 : Aj. de domaines d’ut. et de gr. d’ut. à la cat. de salles"
TOCTitle: Ajout de domaines d’utilisateurs et de groupes d’utilisateurs à la catégorie de salles
ms:assetid: ee03f2cf-1c84-41c4-b524-d0729be33b8c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ215884(v=OCS.15)
ms:contentKeyID: 49299243
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ajout de domaines d’utilisateurs et de groupes d’utilisateurs à la catégorie de salles dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-02-07_

Pour ajouter de plus grands groupes d’utilisateurs à une salle de conversation, reportez-vous à [Configuration des catégories dans Lync Server 2013](lync-server-2013-configure-categories.md) et [Gestion des catégories](manage-categories.md) dans la documentation de déploiement. Par exemple, la commande suivante ajoute tous les utilisateurs de l’unité d’organisation NorthAmericaUsers dans Active Directory à la salle de conversation NorthAmerica :

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=litwareinc,DC=com"}

Cette commande ajoute tous les membres du groupe de distribution Finance à la même salle de conversation :

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=litwareinc,DC=com"}

