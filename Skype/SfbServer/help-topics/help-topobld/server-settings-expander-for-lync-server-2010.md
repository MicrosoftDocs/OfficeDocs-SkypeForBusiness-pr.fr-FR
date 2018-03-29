---
title: Server Settings Expander for Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'To edit the properties for this computer, you do the following:'
ms.openlocfilehash: 0e5e595382bb92621c1551158edecf736ff0aa6b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="e7048-103">Server Settings Expander for Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e7048-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="e7048-104">To edit the properties for this computer, you do the following:</span><span class="sxs-lookup"><span data-stu-id="e7048-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="e7048-105">Edit the **Fully qualified domain name (FQDN)** for this computer.</span><span class="sxs-lookup"><span data-stu-id="e7048-105">Edit the **Fully qualified domain name (FQDN)** for this computer.</span></span> <span data-ttu-id="e7048-106">This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span><span class="sxs-lookup"><span data-stu-id="e7048-106">This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="e7048-107">You select one of the following:</span><span class="sxs-lookup"><span data-stu-id="e7048-107">You select one of the following:</span></span>
    
    <span data-ttu-id="e7048-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span><span class="sxs-lookup"><span data-stu-id="e7048-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e7048-109">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services.</span><span class="sxs-lookup"><span data-stu-id="e7048-109">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services.</span></span> <span data-ttu-id="e7048-110">If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span><span class="sxs-lookup"><span data-stu-id="e7048-110">If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="e7048-111">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment.</span><span class="sxs-lookup"><span data-stu-id="e7048-111">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment.</span></span> <span data-ttu-id="e7048-112">Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="e7048-112">Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

