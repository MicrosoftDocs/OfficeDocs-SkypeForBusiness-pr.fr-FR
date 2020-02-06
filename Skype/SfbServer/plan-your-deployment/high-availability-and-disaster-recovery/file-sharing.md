---
title: Forte disponibilité du partage de fichiers dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: En savoir plus sur la façon de garantir une haute disponibilité des partages de fichiers dans Skype entreprise Server, à l’aide du système de fichiers DFS.
ms.openlocfilehash: c04c3acd009dd59a3894a62d08395db19c6d2368
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815932"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a><span data-ttu-id="f2762-103">Forte disponibilité du partage de fichiers dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="f2762-103">File sharing high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="f2762-104">En savoir plus sur la façon de garantir une haute disponibilité des partages de fichiers dans Skype entreprise Server, à l’aide du système de fichiers DFS.</span><span class="sxs-lookup"><span data-stu-id="f2762-104">Learn about ensuring high availability of your file shares in Skype for Business Server, using DFS.</span></span>
  
<span data-ttu-id="f2762-105">Pour garantir une haute disponibilité du partage de fichiers dans votre déploiement Skype entreprise Server, vous pouvez utiliser le système de fichiers DFS.</span><span class="sxs-lookup"><span data-stu-id="f2762-105">To ensure high availability for file sharing in your Skype for Business Server deployment, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="f2762-106">DFS prend en charge le basculement d’un serveur de fichiers vers un autre dans le même centre de données.</span><span class="sxs-lookup"><span data-stu-id="f2762-106">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="f2762-107">Pour un déploiement à grande échelle, il est recommandé d’utiliser des serveurs de fichiers dédiés associés à l’aide de DFS.</span><span class="sxs-lookup"><span data-stu-id="f2762-107">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span> <span data-ttu-id="f2762-108">Pour plus d’informations sur le système de fichiers DFS dans [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384)Windows Server 2012, voir.</span><span class="sxs-lookup"><span data-stu-id="f2762-108">For more information on DFS in Windows Server 2012, see [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span></span> <span data-ttu-id="f2762-109">Pour plus d’informations sur le système de fichiers DFS [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385)sur Windows Server 2008, voir.</span><span class="sxs-lookup"><span data-stu-id="f2762-109">For information on DFS on Windows Server 2008, see [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span></span>
  
<span data-ttu-id="f2762-110">En fonction de la taille de votre réseau et de la capacité de résilience souhaitée, vous pouvez utiliser une paire de serveurs pour héberger tous les partages de fichiers dans un site, ou utiliser une paire par pool frontal.</span><span class="sxs-lookup"><span data-stu-id="f2762-110">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>
  
<span data-ttu-id="f2762-111">DFS est un mécanisme de réplication de fichiers recommandé, sans engagement d’objectif de temps de récupération (RTO, Recovery Time Objective) ou d’objectif de point de récupération (RPO, Recovery Point Objective) publié.</span><span class="sxs-lookup"><span data-stu-id="f2762-111">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="f2762-112">Un basculement entre serveurs DFS doit être effectué rapidement, mais un délai de réplication des données peut empêcher les utilisateurs de continuer à travailler en cours lorsque le basculement a lieu.</span><span class="sxs-lookup"><span data-stu-id="f2762-112">A failover between DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>
  
<span data-ttu-id="f2762-p103">Si vous utilisez DFS et que le magasin de données sur le partage de fichiers est crucial, vous devez sauvegarder fréquemment les partages de fichiers, par exemple toutes les 4 à 8 heures. Lorsqu’un partage de fichiers ne fonctionne pas et que la réplication n’est pas à jour, vous pouvez utiliser la sauvegarde pour restaurer le contenu du serveur défaillant sur l’autre serveur associé à ce serveur à présent indisponible.</span><span class="sxs-lookup"><span data-stu-id="f2762-p103">If you use DFS and the data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours. When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>
  

