---
title: Ajouter des options IP de serveur Edge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Microsoft Lync Server 2013 vous permet de configurer des adresses IPv4 et IPv6 pour chaque interface pour le serveur Edge et le pool Edge. Pour cela, procédez comme suit:'
ms.openlocfilehash: de0b0e0c050721a4fb54a450db89e34f65ea7f7f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293972"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="a0634-104">Ajouter des options IP de serveur Edge</span><span class="sxs-lookup"><span data-stu-id="a0634-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="a0634-105">Microsoft Lync Server 2013 vous permet de configurer des adresses IPv4 et IPv6 pour chaque interface pour le serveur Edge et le pool Edge.</span><span class="sxs-lookup"><span data-stu-id="a0634-105">Microsoft Lync Server 2013 allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="a0634-106">Pour cela, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="a0634-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="a0634-107">**Activer IPv4 sur l’interface interne**: activez la case à cocher si vous voulez appliquer une adresse IPv4 à l’interface interne du serveur Edge ou du pool de périphériques</span><span class="sxs-lookup"><span data-stu-id="a0634-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="a0634-108">**Activer IPv6 sur l’interface interne**: activez la case à cocher si vous voulez appliquer une adresse IPv6 à l’interface interne du serveur Edge ou du pool de périphériques</span><span class="sxs-lookup"><span data-stu-id="a0634-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="a0634-109">**Activer IPv4 sur une interface externe**: activez la case à cocher si vous voulez appliquer une adresse IPv4 à l’interface externe du serveur Edge ou du pool de périphériques</span><span class="sxs-lookup"><span data-stu-id="a0634-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="a0634-110">**Activer IPv6 sur une interface externe**: activez la case à cocher si vous voulez appliquer une adresse IPv6 à l’interface externe du serveur Edge ou du pool de périphériques</span><span class="sxs-lookup"><span data-stu-id="a0634-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="a0634-111">Vous pouvez également configurer le serveur de périphérie ou le pool Edge pour utiliser une adresse de traduction d’adresses réseau pour les adresses IP externes.</span><span class="sxs-lookup"><span data-stu-id="a0634-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="a0634-112">Pour ce faire, activez la case à cocher **l’adresse IP externe de ce pool Edge est traduite par tar**.</span><span class="sxs-lookup"><span data-stu-id="a0634-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="a0634-113">Prise en charge de tar.</span><span class="sxs-lookup"><span data-stu-id="a0634-113">NAT support.</span></span> <span data-ttu-id="a0634-114">La traduction d’adresses réseau (NAT) n’est pas prise en charge dans le cadre de l’utilisation de l’équilibrage de charge matérielle, alors ne sélectionnez pas l’option NAT si vous déployez un pool de serveurs de frontière avec l’équilibrage de charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="a0634-114">Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

