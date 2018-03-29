---
title: Haute disponibilité du partage de fichiers dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Obtenir des informations sur la disponibilité élevée de vos partages de fichiers dans Skype pour Business Server, à l’aide de DFS.
ms.openlocfilehash: f96e4aaca70c501425528b12207eeab01027c9a9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="file-sharing-high-availability-in-skype-for-business-server-2015"></a><span data-ttu-id="b9195-103">Haute disponibilité du partage de fichiers dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="b9195-103">File sharing high availability in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b9195-104">Obtenir des informations sur la disponibilité élevée de vos partages de fichiers dans Skype pour Business Server, à l’aide de DFS.</span><span class="sxs-lookup"><span data-stu-id="b9195-104">Learn about ensuring high availability of your file shares in Skype for Business Server, using DFS.</span></span>
  
<span data-ttu-id="b9195-105">Pour garantir une haute disponibilité pour le partage de fichiers dans votre Skype pour le déploiement du serveur de l’entreprise, vous pouvez utiliser le système de fichiers distribués (DFS).</span><span class="sxs-lookup"><span data-stu-id="b9195-105">To ensure high availability for file sharing in your Skype for Business Server deployment, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="b9195-106">DFS prend en charge le basculement d’un serveur de fichiers vers un autre dans le même centre de données.</span><span class="sxs-lookup"><span data-stu-id="b9195-106">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="b9195-107">Pour un déploiement à grande échelle, il est recommandé d’utiliser des serveurs de fichiers dédiés associés à l’aide de DFS.</span><span class="sxs-lookup"><span data-stu-id="b9195-107">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span> <span data-ttu-id="b9195-108">Pour plus d’informations sur DFS dans Windows Server 2012, consultez [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span><span class="sxs-lookup"><span data-stu-id="b9195-108">For more information on DFS in Windows Server 2012, see [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span></span> <span data-ttu-id="b9195-109">Pour plus d’informations sur le système DFS sur Windows Server 2008, voir [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span><span class="sxs-lookup"><span data-stu-id="b9195-109">For information on DFS on Windows Server 2008, see [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span></span>
  
<span data-ttu-id="b9195-110">En fonction de la taille de votre réseau et le montant de résilience que vous le souhaitez, vous pouvez utiliser une paire de serveurs pour héberger tous les partages de fichiers dans un site, ou utilisez une paire par pool frontal.</span><span class="sxs-lookup"><span data-stu-id="b9195-110">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>
  
<span data-ttu-id="b9195-111">DFS est un mécanisme de réplication de fichiers recommandé, sans engagement d’objectif de temps de récupération (RTO, Recovery Time Objective) ou d’objectif de point de récupération (RPO, Recovery Point Objective) publié.</span><span class="sxs-lookup"><span data-stu-id="b9195-111">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="b9195-112">Un basculement entre les serveurs DFS doit être effectué rapidement, mais les délais de réplication de données peuvent empêcher les utilisateurs d’être en mesure de continuer les travaux en cours lorsque le basculement se produit.</span><span class="sxs-lookup"><span data-stu-id="b9195-112">A failover between DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>
  
<span data-ttu-id="b9195-p103">Si vous utilisez DFS et que le magasin de données sur le partage de fichiers est crucial, vous devez sauvegarder fréquemment les partages de fichiers, par exemple toutes les 4 à 8 heures. Lorsqu’un partage de fichiers ne fonctionne pas et que la réplication n’est pas à jour, vous pouvez utiliser la sauvegarde pour restaurer le contenu du serveur défaillant sur l’autre serveur associé à ce serveur à présent indisponible.</span><span class="sxs-lookup"><span data-stu-id="b9195-p103">If you use DFS and the data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours. When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>
  

