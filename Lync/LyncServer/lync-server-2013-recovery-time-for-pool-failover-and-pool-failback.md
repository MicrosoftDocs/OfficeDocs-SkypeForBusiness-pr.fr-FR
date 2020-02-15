---
title: Temps de récupération de Lync Server 2013 pour le basculement de pool et la restauration de pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Recovery time for pool failover and pool failback
ms:assetid: 902c658f-8442-4d0d-b3ad-bf795ecd550d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205079(v=OCS.15)
ms:contentKeyID: 48184786
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8692e01ed9691f69da7be78a2e0437e7829594cb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a>Temps de récupération pour le basculement de pool et la restauration automatique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-10_

Pour le basculement de pool et la restauration de pool, le but à atteindre pour la durée maximale d’interruption admissible (RTO) est de 30 minutes. Il s’agit de la durée nécessaire pour que le basculement ait lieu, une fois que les administrateurs ont identifié une panne et lancé les procédures de basculement. Cette durée ne comprend pas le temps nécessaire aux administrateurs pour évaluer la situation et prendre une décision, ni le temps nécessaire aux utilisateurs pour se connecter une fois le basculement terminé.

Pour le basculement de pool et la restauration de pool, le but à atteindre pour la perte de données maximale admissible (RPO) est de 30 minutes. Cela représente une mesure en temps des données qui pourraient être perdues en raison de la panne, en raison de la latence de réplication du service de sauvegarde. Par exemple, si un pool tombe à 10:00 du matin et que le RPO est de 30 minutes, les données écrites dans le pool entre 9:30 h 00 et 10:00 A. M. n’ont peut-être pas été répliqués sur le pool de sauvegarde et seraient perdus.

Les chiffres de RTO et de RPO de ce document considèrent que les deux centres de données sont situés dans la même région du monde avec un transport haute vitesse à faible latence entre les deux sites. Ces chiffres sont mesurés pour un pool avec 40 000 utilisateurs actifs simultanément et 200 000 utilisateurs activés pour Lync par rapport à un modèle utilisateur prédéfini où il n’y a pas de journal en attente de réplication de données. Ces chiffres peuvent changer en fonction du test et de la validation des performances.

</div>

<span> </span>

</div>

</div>

</div>

