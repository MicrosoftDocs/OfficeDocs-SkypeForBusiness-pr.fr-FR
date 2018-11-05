---
title: "Lync Server 2013 : Prise en ch. de la haute dispo. et de la récup. d’urgence"
TOCTitle: Prise en charge de la haute disponibilité et de la récupération d’urgence
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204866(v=OCS.15)
ms:contentKeyID: 49297091
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prise en charge de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-25_

Lync Server 2013 fournit une haute disponibilité par redondance des serveurs via la création de pools. Si un serveur exécutant un rôle serveur particulier rencontre une défaillance, les autres serveurs du pool qui exécutent le même rôle assument la charge de ce serveur. Cela s’applique aux serveurs frontaux, aux serveurs Edge, aux serveurs de médiation et aux directeurs. Pour plus d’informations sur les rôles serveur, reportez-vous à [Rôles serveur dans Lync Server 2013](lync-server-2013-server-roles.md).

Lync Server 2013 fournit également des mesures de récupération d’urgence par appariement des pools. Si vous déployez cette topologie, vous désignez des paires de pools frontaux, chaque pool d’une paire étant situé dans un centre de données distinct et dans une zone géographique distincte. Si un pool ou un site n’est plus opérationnel, vous pouvez rediriger les utilisateurs de ce pool afin qu’ils se servent de l’autre pool de la paire, avec une interruption minimale du service.

Lync Server 2013 prend également en charge la haute disponibilité des serveurs principaux. Il s’agit d’une topologie facultative dans laquelle vous déployez deux serveurs principaux pour un pool frontal et où vous configurez une mise en miroir SQL Server synchrone pour toutes les bases de données Lync qui s’exécutent sur les serveurs principaux.

Pour plus d’informations sur l’appariement des pools et la mise en miroir des serveurs principaux, reportez-vous à [Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

## Voir aussi

#### Concepts

[Rôles serveur dans Lync Server 2013](lync-server-2013-server-roles.md)  
[Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)

