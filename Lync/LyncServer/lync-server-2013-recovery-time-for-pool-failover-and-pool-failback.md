---
title: Temps de récupération nécessaire pour basculer et restaurer les pools dans Lync Server 2013
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
ms.openlocfilehash: 3fff6f74b5d486c05d01bcd3a911ae674b4f0708
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a>Temps de récupération nécessaire pour basculer et restaurer les pools dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-10_

Pour le basculement de pool et la restauration de pool, le Target Engineering pour l’objectif de temps de récupération (RTO) est de 30 minutes. Il s’agit du temps nécessaire au basculement, une fois que les administrateurs ont déterminé qu’il y a eu un sinistre et démarré les procédures de basculement. Cette durée ne comprend pas le temps nécessaire aux administrateurs pour évaluer la situation et prendre une décision, ni le temps nécessaire aux utilisateurs pour se connecter une fois le basculement terminé.

Pour le basculement de pool et la restauration de pool, le ciblage d’ingénierie pour l’objectif de point de récupération (RPO) est de 30 minutes. Cela représente une mesure en temps des données qui pourraient être perdues en raison de la panne, en raison de la latence de réplication du service de sauvegarde. Par exemple, si un pool est arrêté à 10:00 AM et que le RPO est de 30 minutes, les données écrites dans le pool entre 9:30 AM Il est possible que la 10:00 A n’ayant pas été répliquée vers le pool de sauvegarde et qu’elle soit perdue.

Les chiffres de RTO et de RPO de ce document considèrent que les deux centres de données sont situés dans la même région du monde avec un transport haute vitesse à faible latence entre les deux sites. Ces chiffres sont mesurés pour un pool avec 40 000 utilisateurs actifs et 200 000 utilisateurs activés pour Lync par rapport à un modèle utilisateur prédéfini pour lequel il n’y a pas de journal des travaux en souffrance dans la réplication des données. Ces chiffres peuvent changer en fonction du test et de la validation des performances.

</div>

<span> </span>

</div>

</div>

</div>

