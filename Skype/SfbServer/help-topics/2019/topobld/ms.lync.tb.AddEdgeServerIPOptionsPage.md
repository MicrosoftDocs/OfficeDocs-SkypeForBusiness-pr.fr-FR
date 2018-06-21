---
title: Ajouter des Options IP de serveur Edge
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Microsoft Lync Server 2013 vous permet de configurer les adresses IPv4 et IPv6 pour chaque interface pour le serveur de périphérie et un pool de serveurs Edge. Pour ce faire, vous procédez comme suit :'
ms.openlocfilehash: a303c4dc3d6fe82617449795507ef87017676a4a
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/20/2018
ms.locfileid: "19974956"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="c444e-104">Ajouter des Options IP de serveur Edge</span><span class="sxs-lookup"><span data-stu-id="c444e-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="c444e-105">Microsoft Lync Server 2013 vous permet de configurer les adresses IPv4 et IPv6 pour chaque interface pour le serveur de périphérie et un pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="c444e-105">Microsoft Lync Server 2013 allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="c444e-106">Pour ce faire, vous procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c444e-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="c444e-107">**Activer les IPv4 sur l’interface interne**: activez la case à cocher si vous souhaitez appliquer une adresse IPv4 pour le serveur Edge ou l’interface interne du pool Edge</span><span class="sxs-lookup"><span data-stu-id="c444e-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="c444e-108">**Activer le protocole IPv6 sur l’interface interne**: activez la case à cocher si vous souhaitez appliquer une adresse IPv6 pour le serveur Edge ou l’interface interne du pool Edge</span><span class="sxs-lookup"><span data-stu-id="c444e-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="c444e-109">**Activer les IPv4 sur l’interface externe**: activez la case à cocher si vous souhaitez appliquer une adresse IPv4 pour le serveur Edge ou l’interface externe du pool Edge</span><span class="sxs-lookup"><span data-stu-id="c444e-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="c444e-110">**Activer le protocole IPv6 sur l’interface externe**: activez la case à cocher si vous souhaitez appliquer une adresse IPv6 pour le serveur Edge ou l’interface externe du pool Edge</span><span class="sxs-lookup"><span data-stu-id="c444e-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="c444e-111">Vous pouvez également configurer le serveur Edge ou le pool de serveurs Edge pour utiliser une adresse de traduction d’adresses réseau pour les adresses IP externes.</span><span class="sxs-lookup"><span data-stu-id="c444e-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="c444e-112">Pour cela, en activant la case à cocher **l’adresse IP externe de ce pool Edge est traduit par NAT**.</span><span class="sxs-lookup"><span data-stu-id="c444e-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="c444e-113">Prise en charge NAT.</span><span class="sxs-lookup"><span data-stu-id="c444e-113">NAT support.</span></span> <span data-ttu-id="c444e-114">Traduction d’adresses réseau (NAT) n’est pas pris en charge lorsque vous utilisez l’équilibrage de charge matériel, afin de n’activez ne pas l’option NAT si vous déployez un pool de serveurs Edge avec l’équilibrage de charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="c444e-114">Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

