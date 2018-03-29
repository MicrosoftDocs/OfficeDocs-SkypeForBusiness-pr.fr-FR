---
title: Ajouter des Options IP du serveur Edge
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Microsoft Lync Server 2013 vous permet de configurer des adresses IPv4 et IPv6 pour chaque interface pour le serveur de transport Edge et le pool de bord. Pour ce faire, vous effectuez les opérations suivantes :'
ms.openlocfilehash: a6f4dd60355a4e241c70ec28c72fa86d91c66a9e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="11635-104">Ajouter des Options IP du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="11635-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="11635-105">Microsoft Lync Server 2013 vous permet de configurer des adresses IPv4 et IPv6 pour chaque interface pour le serveur de transport Edge et le pool de bord.</span><span class="sxs-lookup"><span data-stu-id="11635-105">Microsoft Lync Server 2013 allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="11635-106">Pour ce faire, vous effectuez les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="11635-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="11635-107">**Activer les IPv4 sur l’interface interne**: activez la case à cocher si vous souhaitez appliquer une adresse IPv4 pour le serveur de transport Edge ou interface de bord pool interne</span><span class="sxs-lookup"><span data-stu-id="11635-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="11635-108">**Activation d’IPv6 sur l’interface interne**: activez la case à cocher si vous souhaitez appliquer une adresse IPv6 pour le serveur de transport Edge ou interface de bord pool interne</span><span class="sxs-lookup"><span data-stu-id="11635-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="11635-109">**Activer les IPv4 sur l’interface externe**: activez la case à cocher si vous souhaitez appliquer une adresse IPv4 pour le serveur de transport Edge ou interface de bord pool externe</span><span class="sxs-lookup"><span data-stu-id="11635-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="11635-110">**Activation d’IPv6 sur l’interface externe**: activez la case à cocher si vous souhaitez appliquer une adresse IPv6 pour le serveur de transport Edge ou interface de bord pool externe</span><span class="sxs-lookup"><span data-stu-id="11635-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="11635-111">Vous pouvez également configurer le serveur de transport Edge ou le pool de bord pour utiliser une adresse de traduction d’adresses réseau pour les adresses IP externes.</span><span class="sxs-lookup"><span data-stu-id="11635-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="11635-112">Pour cela, vous devez en activant la case à cocher **l’adresse IP externe de ce pool de bord est convertie par NAT**.</span><span class="sxs-lookup"><span data-stu-id="11635-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="11635-113">Prise en charge NAT.</span><span class="sxs-lookup"><span data-stu-id="11635-113">NAT support.</span></span> <span data-ttu-id="11635-114">Traduction d’adresses réseau (NAT) n’est pas pris en charge lorsque vous utilisez l’équilibrage de charge matériel, et ne sélectionnez ne pas l’option NAT si vous déployez un pool de serveur de transport Edge avec l’équilibrage de charge matériel.</span><span class="sxs-lookup"><span data-stu-id="11635-114">Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

