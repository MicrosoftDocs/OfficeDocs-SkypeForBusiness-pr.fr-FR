---
title: 'Lync Server 2013 : Vue d’ensemble du directeur'
TOCTitle: Vue d’ensemble du directeur
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398879(v=OCS.15)
ms:contentKeyID: 49298915
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue d’ensemble du directeur dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-08_

Un directeur est un serveur exécutant Lync Server 2013 qui authentifie les demandes des utilisateurs, mais qui n’héberge aucun compte d’utilisateur. Vous pouvez déployer un directeur dans les deux cas suivants :

  - Si vous autorisez l’accès des utilisateurs externes en déployant des serveurs Edge, vous devez également déployer un directeur. Dans ce scénario, le directeur authentifie les utilisateurs externes, puis achemine leur trafic vers des serveurs internes. Lorsqu’un directeur est utilisé pour authentifier les utilisateurs externes, il décharge les serveurs de pool de serveurs frontaux de la charge supplémentaire occasionnée par les procédures d’authentification de ces utilisateurs. Cela permet en outre de protéger les pools de serveurs frontaux internes contre le trafic malveillant, tel que les attaques par déni de service. Si le réseau est saturé par du trafic externe non valide dans le cadre d’une telle attaque, tout ce trafic s’arrête au niveau du directeur.

  - Si vous déployez plusieurs pools de serveurs frontaux sur un site central, vous pouvez rationaliser les demandes d’authentification et améliorer les performances en ajoutant un directeur à ce site. Dans ce scénario, toutes les demandes sont transmises au directeur qui les achemine ensuite vers le pool de serveurs frontaux approprié.

