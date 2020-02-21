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
ms.openlocfilehash: fb165fa762b23bd271dde56c0846ccb18adfbf7f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a><span data-ttu-id="2bbda-102">Temps de récupération pour le basculement de pool et la restauration automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2bbda-102">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bbda-103">_**Dernière modification de la rubrique :** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="2bbda-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="2bbda-p101">Pour le basculement de pool et la restauration de pool, le but à atteindre pour la durée maximale d’interruption admissible (RTO) est de 30 minutes. Il s’agit de la durée nécessaire pour que le basculement ait lieu, une fois que les administrateurs ont identifié une panne et lancé les procédures de basculement. Cette durée ne comprend pas le temps nécessaire aux administrateurs pour évaluer la situation et prendre une décision, ni le temps nécessaire aux utilisateurs pour se connecter une fois le basculement terminé.</span><span class="sxs-lookup"><span data-stu-id="2bbda-p101">For pool failover and pool failback, the engineering target for recovery time objective (RTO) is 30 minutes. This is the time required for the failover to happen, after administrators have determined there was a disaster and initiated the failover procedures. It does not include the time for administrators to assess the situation and make a decision, nor does it include the time for users to sign in again after failover is complete.</span></span>

<span data-ttu-id="2bbda-107">Pour le basculement de pool et la restauration de pool, le but à atteindre pour la perte de données maximale admissible (RPO) est de 30 minutes.</span><span class="sxs-lookup"><span data-stu-id="2bbda-107">For pool failover and pool failback, the engineering target for recovery point objective (RPO) is 30 minutes.</span></span> <span data-ttu-id="2bbda-108">Cela représente une mesure en temps des données qui pourraient être perdues en raison de la panne, en raison de la latence de réplication du service de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="2bbda-108">This represents the time measure of data that could be lost due to the disaster, due to replication latency of the Backup Service.</span></span> <span data-ttu-id="2bbda-109">Par exemple, si un pool tombe à 10:00 du matin et que le RPO est de 30 minutes, les données écrites dans le pool entre 9:30 h 00</span><span class="sxs-lookup"><span data-stu-id="2bbda-109">For example, if a pool goes down at 10:00 A.M., and the RPO is 30 minutes, data written to the pool between 9:30 A.M.</span></span> <span data-ttu-id="2bbda-110">et 10:00 A. M. n’ont peut-être pas été répliqués sur le pool de sauvegarde et seraient perdus.</span><span class="sxs-lookup"><span data-stu-id="2bbda-110">and 10:00 A.M.might not have replicated to the backup pool, and would be lost.</span></span>

<span data-ttu-id="2bbda-111">Les chiffres de RTO et de RPO de ce document considèrent que les deux centres de données sont situés dans la même région du monde avec un transport haute vitesse à faible latence entre les deux sites.</span><span class="sxs-lookup"><span data-stu-id="2bbda-111">All RTO and RPO numbers in this document assume that the two data centers are located within the same world region with high-speed, low-latency transport between the two sites.</span></span> <span data-ttu-id="2bbda-112">Ces chiffres sont mesurés pour un pool avec 40 000 utilisateurs actifs simultanément et 200 000 utilisateurs activés pour Lync par rapport à un modèle utilisateur prédéfini où il n’y a pas de journal en attente de réplication de données.</span><span class="sxs-lookup"><span data-stu-id="2bbda-112">These numbers are measured for a pool with 40,000 concurrently active users and 200,000 users enabled for Lync with respect to a pre-defined user model where there is no backlog in data replication.</span></span> <span data-ttu-id="2bbda-113">Ces chiffres peuvent changer en fonction du test et de la validation des performances.</span><span class="sxs-lookup"><span data-stu-id="2bbda-113">They are subject to change based on performance testing and validation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

