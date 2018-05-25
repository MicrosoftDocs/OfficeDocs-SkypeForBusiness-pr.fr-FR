---
title: Expanseur des paramètres de serveur pour Lync Server 2010
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
description: 'Pour modifier les propriétés de cet ordinateur, vous procédez comme suit :'
ms.openlocfilehash: 0e5e595382bb92621c1551158edecf736ff0aa6b
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="31ba5-103">Expanseur des paramètres de serveur pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="31ba5-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="31ba5-104">Pour modifier les propriétés de cet ordinateur, vous procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="31ba5-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="31ba5-105">Modifier le **nom de domaine (FQDN) complet** pour cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="31ba5-105">Edit the **Fully qualified domain name (FQDN)** for this computer.</span></span> <span data-ttu-id="31ba5-106">Cette entrée doit correspondre au nom de l’ordinateur tel qu’il est défini dans le système de nom de domaine (DNS) et dans les noms de sujet (SAN) ou le nom du sujet (SN) du certificat associé à cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="31ba5-106">This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="31ba5-107">Vous sélectionnez une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="31ba5-107">You select one of the following:</span></span>
    
    <span data-ttu-id="31ba5-108">**Utiliser toutes les adresses IP configurées**: sélectionnez cette option pour utiliser toutes les adresses IP sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="31ba5-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="31ba5-109">Si l’ordinateur possède plusieurs adresses IP, vous devez être conscient que les services associés à cet ordinateur utilisera toutes les adresses IP pour tous les services.</span><span class="sxs-lookup"><span data-stu-id="31ba5-109">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services.</span></span> <span data-ttu-id="31ba5-110">Si un serveur d’écoute ou un service attend la communication d’une adresse IP spécifique et un port, le service peut rendre pas le meilleur choix de l’adresse IP à l’écoute sur.</span><span class="sxs-lookup"><span data-stu-id="31ba5-110">If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="31ba5-111">**Limitez l’utilisation de service pour les adresses IP sélectionnées**: sélectionnez cette option si vous souhaitez définir des adresses IP spécifiques pour l' **adresse IP principale** qui écoute sur cet ordinateur pour les communications entre les autres ordinateurs et les pools dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="31ba5-111">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment.</span></span> <span data-ttu-id="31ba5-112">Définir **l’adresse IP PSTN** pour l’adresse IP spécifique que l’ordinateur et le service écoute pour les communications et envoyer les communications à la passerelle PSTN ou IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="31ba5-112">Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

