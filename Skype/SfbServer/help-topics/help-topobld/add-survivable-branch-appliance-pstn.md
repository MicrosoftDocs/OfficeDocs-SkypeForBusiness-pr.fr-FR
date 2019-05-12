---
title: Ajouter la passerelle PSTN pour le Survivable Branch Appliance
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 'Pour définir la passerelle de réseau téléphonique commuté pour un Survivable Branch Appliance sur un site de succursale, spécifiez les éléments suivants :'
ms.openlocfilehash: da7144d9674bd7a02ef5ca144d20dcd419ad9ae4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897477"
---
# <a name="add-survivable-branch-appliance-pstn"></a><span data-ttu-id="074c7-103">Ajouter la passerelle PSTN pour le Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="074c7-103">Add Survivable Branch Appliance PSTN</span></span>
 
<span data-ttu-id="074c7-104">Pour définir la passerelle de réseau téléphonique commuté pour un Survivable Branch Appliance sur un site de succursale, spécifiez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="074c7-104">To define the public switched telephone network (PSTN) gateway for a Survivable Branch Appliance at a branch site, specify the following:</span></span> 
  
- <span data-ttu-id="074c7-105">Un nom de domaine complet (FQDN) ou l’adresse IP de l’homologue de passerelle que le Survivable Branch Appliance ou serveur Survivable Branch Server est associé pour le routage entrant et sortant d’appels PSTN.</span><span class="sxs-lookup"><span data-stu-id="074c7-105">A fully qualified domain name (FQDN) or IP address for the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound and outbound PSTN calls.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="074c7-106">Si vous définissez un Survivable Branch Appliance, il s’agit de la passerelle à laquelle le serveur de médiation à l’intérieur du Survivable Branch Appliance se connectera pour la connectivité PSTN.</span><span class="sxs-lookup"><span data-stu-id="074c7-106">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span> 
  
- <span data-ttu-id="074c7-p101">Le port d’écoute à utiliser pour les messages SIP (Session Initiation Protocol). Par défaut, il s’agit des ports 5066 pour le protocole TCP (Transmission Control Protocol) et 5067 pour le protocole TLS (Transport Layer Security) sur une passerelle, un PBX (Private Branch Exchange) ou un contrôleur SBC. Sur un Survivable Branch Appliance sur un site de succursale, les ports par défaut sont le port 5081 pour le protocole TCP et le port 5082 pour le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="074c7-p101">The listening port to be used for Session Initiation Protocol (SIP) messages. By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a gateway, private branch exchange (PBX), or Session Border Controller (SBC). On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.</span></span>
    
- <span data-ttu-id="074c7-110">Pour des raisons de sécurité, nous vous conseillons vivement d’utiliser le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="074c7-110">For security reasons, we strongly recommend that you use TLS.</span></span> <span data-ttu-id="074c7-111">Si vous définissez un Survivable Branch Appliance, reportez-vous à la documentation de votre fournisseur Survivable Branch Appliance pour vérifier que votre serveur Survivable Branch Appliance prend en charge le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="074c7-111">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="074c7-112">Pour des raisons de sécurité, nous vous recommandons vivement de déployer une passerelle pouvant utiliser le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="074c7-112">For security reasons, we strongly recommended that you deploy a gateway that can use TLS.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="074c7-113">Si vous souhaitez ajouter une passerelle RTC, vous pouvez la configurer ultérieurement, mais son fonctionnement reste limité tant qu’elle n’a pas été définie et configurée.</span><span class="sxs-lookup"><span data-stu-id="074c7-113">If you want to add a PSTN gateway, you can set it up later, but full functionality will be limited until the PSTN gateway is defined and configured.</span></span> 
  

