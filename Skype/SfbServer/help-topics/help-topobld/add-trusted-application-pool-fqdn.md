---
title: Ajouter un nom de domaine complet du pool d’applications approuvées
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 'Pour définir un nom de domaine complet (FQDN) du pool d’applications approuvé, spécifiez les éléments suivants:'
ms.openlocfilehash: 27957348d4c6dc6b277a37d458ff21bb5efabc17
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303623"
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="f9c19-103">Ajouter un nom de domaine complet du pool d’applications approuvées</span><span class="sxs-lookup"><span data-stu-id="f9c19-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="f9c19-104">Pour définir un nom de domaine complet (FQDN) du pool d’applications approuvé, spécifiez les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="f9c19-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="f9c19-105">Nom de domaine complet du serveur ou du pool de serveurs qui hébergeront les applications approuvées.</span><span class="sxs-lookup"><span data-stu-id="f9c19-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="f9c19-106">Sélectionner **plusieurs pools d’ordinateurs** si vous déployez un pool de serveurs pour les applications approuvées d’équilibrage de charge et de haute \*\*\*\* disponibilité, ou si vous n’avez pas besoin d’équilibrage de charge ou de haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f9c19-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f9c19-107">Un serveur d’applications de confiance unique ne peut pas être converti en pool de serveurs ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="f9c19-107">A single Trusted Applications Server cannot be converted to a pool of servers later.</span></span> <span data-ttu-id="f9c19-108">Si vous pensez que vous aurez peut-être besoin d’un regroupement à l’avenir, vous pouvez déployer un pool de serveurs multiples contenant un seul ordinateur et ajouter des serveurs si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="f9c19-108">If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="f9c19-109">Pour plus d’informations sur les pools d’applications de confiance, voir [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f9c19-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
  

