---
title: Ajouter un Pool d’Application de confiance nom de domaine complet
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 'Pour définir un nom de domaine complet du pool Applications sécurisées (FQDN), spécifiez les éléments suivants :'
ms.openlocfilehash: af21ab09797a5b81f2071a37a2668d556f0a4012
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="1e667-103">Ajouter un Pool d’Application de confiance nom de domaine complet</span><span class="sxs-lookup"><span data-stu-id="1e667-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="1e667-104">Pour définir un nom de domaine complet du pool Applications sécurisées (FQDN), spécifiez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="1e667-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="1e667-105">Un nom de domaine complet du serveur ou du pool de serveurs qui hébergeront les applications approuvées.</span><span class="sxs-lookup"><span data-stu-id="1e667-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="1e667-106">Sélectionnez le **pool d’ordinateur plusieurs** si vous déployez un pool de serveurs pour l’équilibrage de la charge et la disponibilité des applications fiables, ou sélectionnez le **pool d’un seul ordinateur** si vous n’avez pas besoin de charger de contrepartie ou de haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="1e667-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1e667-107">Un seul serveur d’Applications de confiance ne peut pas être converti en un pool de serveurs plus tard.</span><span class="sxs-lookup"><span data-stu-id="1e667-107">A single Trusted Applications Server cannot be converted to a pool of servers later.</span></span> <span data-ttu-id="1e667-108">Si vous pensez qu'avoir besoin d’un pool à l’avenir, vous pouvez déployer un pool de serveurs multiples contenant un seul ordinateur maintenant et ajouter des serveurs, lorsque cela est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="1e667-108">If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="1e667-109">Pour plus d’informations sur les pools d’Applications sécurisées, consultez [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1e667-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
  

