---
title: Ajouter des options IP de serveur Edge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Microsoft Lync Server 2013 vous permet de configurer des adresses IPv4 et IPv6 pour chaque interface pour le serveur Edge et le pool de serveurs Edge. Pour ce faire, procédez comme suit :'
ms.openlocfilehash: 2c68fcfcb2e99759536224889a818639b61d5fcc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219789"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="761f1-104">Ajouter des options IP de serveur Edge</span><span class="sxs-lookup"><span data-stu-id="761f1-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="761f1-105">Microsoft Lync Server 2013 vous permet de configurer des adresses IPv4 et IPv6 pour chaque interface pour le serveur Edge et le pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="761f1-105">Microsoft Lync Server 2013 allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="761f1-106">Pour ce faire, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="761f1-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="761f1-107">**Activer IPv4 sur l’interface interne**: activez cette case à cocher si vous voulez appliquer une adresse IPv4 à l’interface interne du serveur Edge ou du pool de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="761f1-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="761f1-108">**Activer IPv6 sur l’interface interne**: activez cette case à cocher si vous voulez appliquer une adresse IPv6 à l’interface interne du serveur Edge ou du pool de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="761f1-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="761f1-109">**Activer IPv4 sur l’interface externe**: activez cette case à cocher si vous voulez appliquer une adresse IPv4 à l’interface externe du serveur Edge ou du pool de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="761f1-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="761f1-110">**Activer IPv6 sur l’interface externe**: activez cette case à cocher si vous voulez appliquer une adresse IPv6 à l’interface externe du serveur Edge ou du pool de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="761f1-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="761f1-111">Vous pouvez également configurer le serveur Edge ou le pool de serveurs Edge pour utiliser une adresse de traduction d’adresses réseau pour les adresses IP externes.</span><span class="sxs-lookup"><span data-stu-id="761f1-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="761f1-112">Pour ce faire, activez la case à cocher **L’adresse IP externe de ce pool Edge est traduite par NAT**.</span><span class="sxs-lookup"><span data-stu-id="761f1-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="761f1-113">Prise en charge de NAT.</span><span class="sxs-lookup"><span data-stu-id="761f1-113">NAT support.</span></span> <span data-ttu-id="761f1-114">La traduction d’adresses réseau (NAT) n’est pas prise en charge lorsque vous utilisez l’équilibrage de la charge matérielle, donc ne sélectionnez pas l’option NAT si vous déployez un pool de serveurs Edge avec équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="761f1-114">Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

