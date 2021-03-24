---
title: Haute disponibilité du partage de fichiers dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Découvrez comment garantir la haute disponibilité de vos partages de fichiers dans Skype Entreprise Server, à l’aide de DFS.
ms.openlocfilehash: f47d8207969063472af23d898ef8a52c2383df0d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093092"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a><span data-ttu-id="23531-103">Haute disponibilité du partage de fichiers dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="23531-103">File sharing high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="23531-104">Découvrez comment garantir la haute disponibilité de vos partages de fichiers dans Skype Entreprise Server, à l’aide de DFS.</span><span class="sxs-lookup"><span data-stu-id="23531-104">Learn about ensuring high availability of your file shares in Skype for Business Server, using DFS.</span></span>
  
<span data-ttu-id="23531-105">Pour garantir la haute disponibilité du partage de fichiers dans votre déploiement Skype Entreprise Server, vous pouvez utiliser le système de fichiers distribués (DFS).</span><span class="sxs-lookup"><span data-stu-id="23531-105">To ensure high availability for file sharing in your Skype for Business Server deployment, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="23531-106">DFS prend en charge le basculement d’un serveur de fichiers vers un autre dans le même centre de données.</span><span class="sxs-lookup"><span data-stu-id="23531-106">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="23531-107">Pour un déploiement à grande échelle, il est recommandé d’utiliser des serveurs de fichiers dédiés qui sont associés à l’aide de DFS.</span><span class="sxs-lookup"><span data-stu-id="23531-107">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span> <span data-ttu-id="23531-108">Pour plus d’informations sur DFS dans Windows Server 2012, voir [https://go.microsoft.com/fwlink/?LinkId=524384](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11)) .</span><span class="sxs-lookup"><span data-stu-id="23531-108">For more information on DFS in Windows Server 2012, see [https://go.microsoft.com/fwlink/?LinkId=524384](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11)).</span></span> <span data-ttu-id="23531-109">Pour plus d’informations sur DFS sur Windows Server 2008, voir [https://go.microsoft.com/fwlink/p/?LinkId=524385](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753479(v=ws.10)) .</span><span class="sxs-lookup"><span data-stu-id="23531-109">For information on DFS on Windows Server 2008, see [https://go.microsoft.com/fwlink/p/?LinkId=524385](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753479(v=ws.10)).</span></span>
  
<span data-ttu-id="23531-110">En fonction de la taille de votre réseau et du niveau de résistance souhaité, vous pouvez utiliser une paire de serveurs pour héberger tous les partages de fichiers d’un site, ou utiliser une paire de serveurs par pool frontal.</span><span class="sxs-lookup"><span data-stu-id="23531-110">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>
  
<span data-ttu-id="23531-111">DFS est un mécanisme de réplication de fichiers recommandé, sans engagement d’objectif de temps de récupération (RTO, Recovery Time Objective) ou d’objectif de point de récupération (RPO, Recovery Point Objective) publié.</span><span class="sxs-lookup"><span data-stu-id="23531-111">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="23531-112">Un failover entre des serveurs DFS doit être effectué rapidement, mais le délai de réplication des données peut empêcher les utilisateurs de poursuivre le travail en cours lorsque le failover se produit.</span><span class="sxs-lookup"><span data-stu-id="23531-112">A failover between DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>
  
<span data-ttu-id="23531-113">Si vous utilisez DFS et que le magasin de données sur le partage de fichiers est essentiel, vous devez les stocker fréquemment, par exemple toutes les 4 à 8 heures.</span><span class="sxs-lookup"><span data-stu-id="23531-113">If you use DFS and the data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours.</span></span> <span data-ttu-id="23531-114">Lorsqu’un partage de fichiers tombe en panne et que la réplication n’est pas à jour, vous pouvez utiliser la sauvegarde pour restaurer le contenu du serveur défaillant sur l’autre serveur qui est associé à ce serveur à présent indisponible.</span><span class="sxs-lookup"><span data-stu-id="23531-114">When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>
