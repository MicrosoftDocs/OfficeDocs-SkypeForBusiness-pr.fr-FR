---
title: Ajouter un nom de domaine complet du pool d’applications approuvées
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour définir un nom de domaine complet du pool Applications approuvées (FQDN), spécifiez les éléments suivants :'
ms.openlocfilehash: 12ea56f285dfffbe78b74c8eece8211a8676333e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895830"
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="5a388-103">Ajouter un nom de domaine complet du pool d’applications approuvées</span><span class="sxs-lookup"><span data-stu-id="5a388-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="5a388-104">Pour définir un nom de domaine complet du pool Applications approuvées (FQDN), spécifiez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="5a388-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="5a388-105">Nom de domaine complet du serveur ou du pool de serveurs qui hébergent les applications approuvées.</span><span class="sxs-lookup"><span data-stu-id="5a388-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="5a388-106">Sélectionnez le **pool de plusieurs ordinateurs** si vous déployez un pool de serveurs pour les applications approuvées à partir de l’équilibrage de charge et une haute disponibilité ou sélectionnez le **pool à ordinateur unique** si vous n’avez pas besoin de charger équilibrage ou haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="5a388-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5a388-107">Un seul serveur d’Applications approuvées ne peut pas être converti en un pool de serveurs ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="5a388-107">A single Trusted Applications Server cannot be converted to a pool of servers later.</span></span> <span data-ttu-id="5a388-108">Si vous pensez que vous devrez peut-être un pool à l’avenir, vous pouvez déployer un pool de serveurs multiples contenant un seul ordinateur maintenant et ajouter des serveurs cas.</span><span class="sxs-lookup"><span data-stu-id="5a388-108">If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="5a388-109">Pour plus d’informations sur les pools d’Applications approuvées, voir [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5a388-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
  

