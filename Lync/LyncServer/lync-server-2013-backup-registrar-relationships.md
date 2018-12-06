---
title: Relations des serveurs d’inscriptions de sauvegarde dans Lync Server 2013
TOCTitle: Relations des serveurs d’inscriptions de sauvegarde
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205033(v=OCS.15)
ms:contentKeyID: 49297854
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Relations des serveurs d’inscriptions de sauvegarde dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-06-28_

En plus de fournir une fonctionnalité de récupération d’urgence, deux pools associés jouent le rôle de serveur d’inscriptions de sauvegarde l’un pour l’autre. Dans Lync Server 2013, les relations de serveur d’inscriptions de sauvegarde entre pools de serveurs frontaux sont toujours 1:1 et réciproques. Cela signifie que si P1 est la sauvegarde de P2, alors P2 doit être la sauvegarde de P1, et aucun des deux ne peut servir de sauvegarde pour un autre pool frontal. Cela n’était pas le cas dans Lync Server 2010, où les relations de sauvegarde du pool de serveurs frontaux pouvaient être plusieurs à un.

Même si les relations de sauvegarde entre deux pools de serveurs frontaux doivent être 1:1 et symétriques, chaque pool de serveurs frontaux peut également être le serveur d’inscriptions de sauvegarde de plusieurs serveurs Survivable Branch Appliance, tout comme dans Lync Server 2010.

Remarquez que Lync Server 2013 n’étend pas la prise en charge de la récupération d’urgence aux utilisateurs hébergés sur un serveur Survivable Branch Appliance. Si un pool frontal qui joue le rôle de sauvegarde pour un serveur Survivable Branch Appliance ne fonctionne pas, les utilisateurs connectés au serveur Survivable Branch Appliance passent en mode résistance même après que les utilisateurs hébergés sur le pool frontal sont basculés sur le pool de serveurs frontaux de sauvegarde.

