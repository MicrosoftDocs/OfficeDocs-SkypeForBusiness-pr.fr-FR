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
description: 'Skype pour Business Server vous permet de configurer les adresses IPv4 et IPv6 pour chaque interface pour le serveur de périphérie et un pool de serveurs Edge. Pour ce faire, vous procédez comme suit :'
ms.openlocfilehash: 5ddad12c17041b84c36ccdd99ee4ed76d27fb553
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21016987"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="1cf9d-104">Ajouter des Options IP de serveur Edge</span><span class="sxs-lookup"><span data-stu-id="1cf9d-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="1cf9d-105">Skype pour Business Server vous permet de configurer les adresses IPv4 et IPv6 pour chaque interface pour le serveur de périphérie et un pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="1cf9d-105">Skype for Business Server allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="1cf9d-106">Pour ce faire, vous procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="1cf9d-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="1cf9d-107">**Activer les IPv4 sur l’interface interne**: activez la case à cocher si vous souhaitez appliquer une adresse IPv4 pour le serveur Edge ou l’interface interne du pool Edge</span><span class="sxs-lookup"><span data-stu-id="1cf9d-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="1cf9d-108">**Activer le protocole IPv6 sur l’interface interne**: activez la case à cocher si vous souhaitez appliquer une adresse IPv6 pour le serveur Edge ou l’interface interne du pool Edge</span><span class="sxs-lookup"><span data-stu-id="1cf9d-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="1cf9d-109">**Activer les IPv4 sur l’interface externe**: activez la case à cocher si vous souhaitez appliquer une adresse IPv4 pour le serveur Edge ou l’interface externe du pool Edge</span><span class="sxs-lookup"><span data-stu-id="1cf9d-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="1cf9d-110">**Activer le protocole IPv6 sur l’interface externe**: activez la case à cocher si vous souhaitez appliquer une adresse IPv6 pour le serveur Edge ou l’interface externe du pool Edge</span><span class="sxs-lookup"><span data-stu-id="1cf9d-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="1cf9d-111">Vous pouvez également configurer le serveur Edge ou le pool de serveurs Edge pour utiliser une adresse de traduction d’adresses réseau pour les adresses IP externes.</span><span class="sxs-lookup"><span data-stu-id="1cf9d-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="1cf9d-112">Pour cela, en activant la case à cocher **l’adresse IP externe de ce pool Edge est traduit par NAT**.</span><span class="sxs-lookup"><span data-stu-id="1cf9d-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="1cf9d-113">Prise en charge NAT.</span><span class="sxs-lookup"><span data-stu-id="1cf9d-113">NAT support.</span></span> <span data-ttu-id="1cf9d-114">Traduction d’adresses réseau (NAT) n’est pas pris en charge lorsque vous utilisez l’équilibrage de charge matériel, afin de n’activez ne pas l’option NAT si vous déployez un pool de serveurs Edge avec l’équilibrage de charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="1cf9d-114">Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

