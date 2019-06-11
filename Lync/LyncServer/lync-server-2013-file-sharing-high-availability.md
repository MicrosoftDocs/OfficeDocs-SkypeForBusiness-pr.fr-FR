---
title: 'Lync Server 2013: haute disponibilité du partage de fichiers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b61a4980c854b6cb79bedbe482bec204a541879f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a><span data-ttu-id="74cc5-102">Forte disponibilité du partage de fichiers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74cc5-102">File sharing high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74cc5-103">_**Dernière modification de la rubrique:** 2012-03-30_</span><span class="sxs-lookup"><span data-stu-id="74cc5-103">_**Topic Last Modified:** 2012-03-30_</span></span>

<span data-ttu-id="74cc5-104">Pour garantir une haute disponibilité du partage de fichiers Lync Server au sein d’un seul centre de données, vous pouvez utiliser le système de fichiers DFS.</span><span class="sxs-lookup"><span data-stu-id="74cc5-104">To ensure high availability for Lync Server file sharing within a single data center, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="74cc5-105">DFS prend en charge le basculement d’un serveur de fichiers vers un autre dans le même centre de données.</span><span class="sxs-lookup"><span data-stu-id="74cc5-105">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="74cc5-106">Pour un déploiement à grande échelle, il est recommandé d’utiliser des serveurs de fichiers dédiés associés à l’aide de DFS.</span><span class="sxs-lookup"><span data-stu-id="74cc5-106">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span>

<span data-ttu-id="74cc5-107">En fonction de la taille de votre réseau et de la capacité de résilience souhaitée, vous pouvez utiliser une paire de serveurs pour héberger tous les partages de fichiers dans un site, ou utiliser une paire par pool frontal.</span><span class="sxs-lookup"><span data-stu-id="74cc5-107">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>

<span data-ttu-id="74cc5-108">DFS est un mécanisme de réplication de fichiers recommandé, sans engagement d’objectif de temps de récupération (RTO, Recovery Time Objective) ou d’objectif de point de récupération (RPO, Recovery Point Objective) publié.</span><span class="sxs-lookup"><span data-stu-id="74cc5-108">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="74cc5-109">Le basculement entre les serveurs DFS doit être effectué rapidement, mais le délai de réplication des données peut empêcher les utilisateurs de continuer à travailler en cours lorsque le basculement a lieu.</span><span class="sxs-lookup"><span data-stu-id="74cc5-109">The failover between the DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>

<span data-ttu-id="74cc5-110">Si vous utilisez le système de fichiers DFS et le magasin de données sur le partage de fichiers est essentiel, il est recommandé de sauvegarder les fichiers partagés, par exemple tous les 4 à 8 heures.</span><span class="sxs-lookup"><span data-stu-id="74cc5-110">If you use DFS and data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours.</span></span> <span data-ttu-id="74cc5-111">Lorsqu’un partage de fichiers ne fonctionne pas et que la réplication n’est pas à jour, vous pouvez utiliser la sauvegarde pour restaurer le contenu du serveur défaillant sur l’autre serveur associé à ce serveur à présent indisponible.</span><span class="sxs-lookup"><span data-stu-id="74cc5-111">When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

