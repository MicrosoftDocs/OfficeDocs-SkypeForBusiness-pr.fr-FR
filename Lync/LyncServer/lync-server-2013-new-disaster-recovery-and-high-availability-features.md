---
title: "Lync Server 2013 : Nlles fonct. de haute dispo. et de récupération d’urgence"
TOCTitle: Nouvelles fonctionnalités de haute disponibilité et de récupération d’urgence
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204892(v=OCS.15)
ms:contentKeyID: 49297183
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Nouvelles fonctionnalités de haute disponibilité et de récupération d’urgence dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-20_

Comme dans Lync Server 2010, le principal modèle de haute disponibilité de Lync Server 2013 est basé sur une redondance des serveurs via la création de pools. Si un serveur exécutant un rôle serveur particulier rencontre une défaillance, les autres serveurs du pool qui exécutent le même rôle assument la charge de ce serveur. Cela s’applique aux serveurs frontaux, aux serveurs Edge, aux serveurs de médiation et aux directeurs.

Lync Server 2013 ajoute de nouvelles mesures de récupération d’urgence en vous permettant d’apparier des pools frontaux situés dans deux centres de données. Si l’un des pools appariés n’est plus opérationnel, un administrateur peut effectuer le basculement des utilisateurs de ce pool vers l’autre pool de la paire afin de garantir une continuité du service. Cette fonctionnalité ne nécessite aucune solution réseau ou matérielle coûteuse comme les réseaux de stockage ou les disques partagés.

Lync Server 2013 prend également en charge la haute disponibilité des serveurs principaux. Il s’agit d’une topologie facultative dans laquelle vous déployez deux serveurs principaux pour un pool frontal et où vous configurez une mise en miroir SQL synchrone pour toutes les bases de données Lync qui s’exécutent sur les serveurs principaux. Vous pouvez décider de déployer ou non un serveur témoin pour le miroir.

## Voir aussi

#### Concepts

[Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)

