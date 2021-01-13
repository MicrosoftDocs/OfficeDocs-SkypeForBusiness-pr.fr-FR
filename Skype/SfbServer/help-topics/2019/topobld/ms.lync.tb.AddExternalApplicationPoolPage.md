---
title: Ajouter un nom de domaine complet du pool d’applications approuvées
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour définir le nom de domaine complet (FQDN) du pool d’applications approuvées, vous précisez les éléments suivants :'
ms.openlocfilehash: e34c3ba68a90e292da9441465d9077112b1ce173
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811814"
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="6bcc7-103">Ajouter un nom de domaine complet du pool d’applications approuvées</span><span class="sxs-lookup"><span data-stu-id="6bcc7-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="6bcc7-104">Pour définir le nom de domaine complet (FQDN) du pool d’applications approuvées, vous précisez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="6bcc7-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="6bcc7-105">Le nom de domaine complet du serveur ou du pool de serveurs qui hébergent les applications approuvées.</span><span class="sxs-lookup"><span data-stu-id="6bcc7-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="6bcc7-106">Sélectionnez **Pool de plusieurs ordinateurs** si vous déployez un pool de serveurs pour les applications approuvées d’équilibrage de charge et de haute disponibilité, ou bien sélectionnez **Pool d’un seul ordinateur** si vous n’avez pas besoin d’équilibrage de charge ou de haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="6bcc7-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6bcc7-p101">Un seul serveur d’applications approuvées ne peut pas se convertir en pool de serveurs par la suite. Si vous pensez avoir besoin d’un pool dans le futur, vous pouvez déployer dès maintenant un pool de plusieurs serveurs ne contenant qu’un seul ordinateur, puis ajouter des serveurs le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="6bcc7-p101">A single Trusted Applications Server cannot be converted to a pool of servers later. If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="6bcc7-109">Pour plus d’informations sur les pools d’applications approuvées, voir [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6bcc7-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
  

