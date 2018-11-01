---
title: Remarques liées à la coexistence
TOCTitle: Remarques liées à la coexistence
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205131(v=OCS.15)
ms:contentKeyID: 49298361
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remarques liées à la coexistence

 

_**Dernière rubrique modifiée :** 2012-10-06_

À l’issue de la migration, seul un pool de serveurs de conversations permanentesLync Server 2013 existera et vous pourrez mettre hors service votre déploiement hérité.

Avant la fin de la migration et avant la mise hors service complète de votre déploiement de serveur Group Chat, il se peut que vous ayez l’un des déploiements suivants :

  - pool de serveurs de conversations permanentesLync Server 2013, qui doit être hébergé sur un pool Lync Server 2013 ;

  - pool Lync Server 2010, conversation de groupe, qui doit être hébergé sur un pool Lync Server 2010 ;

  - pool Group ChatOffice Communications Server 2007 R2, qui doit être hébergé sur un pool Office Communications Server 2007 R2.

Ces déploiements peuvent exister côte à côte. Cependant, les catégories, salles et compléments d’un déploiement n’interagissent pas avec ceux du déploiement associé.

À l’aide d’une configuration manuelle, un client hérité (client Group Chat) peut se connecter à un pool à la fois pour Office Communications Server 2007 R2, Lync Server 2010, conversation de groupe ou Lync Server 2013.

Le client Lync 2013 peut interagir uniquement avec le Lync Server 2013, pool de serveurs de conversations permanentes, et non avec les pools serveur Group Chat hérités. Pour utiliser conversation permanente sur un client Lync 2013, l’utilisateur doit être hébergé sur Lync 2013 et être activé par stratégie.

