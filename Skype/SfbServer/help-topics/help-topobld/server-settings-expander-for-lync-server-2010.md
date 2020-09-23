---
title: Expandeur des paramètres du serveur pour Lync Server 2010
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
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Pour modifier les propriétés de cet ordinateur, procédez comme suit :'
ms.openlocfilehash: c0eb39a516cbcce18940abe7936747fc18db9761
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215695"
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="0055e-103">Expandeur des paramètres du serveur pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="0055e-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="0055e-104">Pour modifier les propriétés de cet ordinateur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0055e-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="0055e-105">Modifiez le **nom de domaine complet (FQDN)** de cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="0055e-105">Edit the **Fully qualified domain name (FQDN)** for this computer.</span></span> <span data-ttu-id="0055e-106">Cette entrée doit correspondre au nom de l’ordinateur, tel qu’il est défini dans le DNS (Domain Name System), et dans les autres noms du sujet (SAN) ou le nom de l’objet (SN) du certificat associé à cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="0055e-106">This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="0055e-107">Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="0055e-107">You select one of the following:</span></span>
    
    <span data-ttu-id="0055e-108">**Utiliser toutes les adresses IP configurées**: sélectionnez cette option pour utiliser toutes les adresses IP configurées sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="0055e-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0055e-109">Si l’ordinateur est doté de plusieurs adresses IP, vous devez savoir que les services associés à cet ordinateur utiliseront toutes les adresses IP de tous les services.</span><span class="sxs-lookup"><span data-stu-id="0055e-109">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services.</span></span> <span data-ttu-id="0055e-110">Si un serveur ou un service d’écoute attend la communication d’une adresse IP et d’un port spécifiques, le service n’est peut-être pas le meilleur choix de l’adresse IP à écouter.</span><span class="sxs-lookup"><span data-stu-id="0055e-110">If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="0055e-111">**Limiter l’utilisation des services aux adresses IP sélectionnées**: sélectionnez cette option si vous souhaitez définir des adresses IP spécifiques pour l' **adresse IP principale** que cet ordinateur écoute pour la communication à partir d’autres ordinateurs et pools dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="0055e-111">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment.</span></span> <span data-ttu-id="0055e-112">Définissez l' **adresse IP PSTN** pour l’adresse IP spécifique que l’ordinateur et le service écoutent pour les communications et qui envoient des communications à la passerelle PSTN ou au PBX IP défini.</span><span class="sxs-lookup"><span data-stu-id="0055e-112">Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

