---
title: Ajouter la passerelle PSTN pour le Survivable Branch Appliance
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 'Pour définir la passerelle de réseau téléphonique commuté (PSTN) pour un Survivable Branch Appliance sur un site de succursale, spécifiez les éléments suivants :'
ms.openlocfilehash: a911e94306999645b9f631f1e9b37d405bd1d155
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828604"
---
# <a name="add-survivable-branch-appliance-pstn"></a><span data-ttu-id="c39e7-103">Ajouter la passerelle PSTN pour le Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="c39e7-103">Add Survivable Branch Appliance PSTN</span></span>
 
<span data-ttu-id="c39e7-104">Pour définir la passerelle de réseau téléphonique commuté (PSTN) pour un Survivable Branch Appliance sur un site de succursale, spécifiez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="c39e7-104">To define the public switched telephone network (PSTN) gateway for a Survivable Branch Appliance at a branch site, specify the following:</span></span> 
  
- <span data-ttu-id="c39e7-105">Un nom de domaine complet (FQDN) ou une adresse IP pour l’homologue de passerelle qui est associé au Survivable Branch Appliance ou au serveur Survivable Branch Server pour le routage des appels PSTN entrants et sortants.</span><span class="sxs-lookup"><span data-stu-id="c39e7-105">A fully qualified domain name (FQDN) or IP address for the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound and outbound PSTN calls.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c39e7-106">Si vous définissez un Survivable Branch Appliance, il s’agit de la passerelle à laquelle le serveur de médiation qui se trouve à l’intérieur du Survivable Branch Appliance se connectera pour la connectivité PSTN.</span><span class="sxs-lookup"><span data-stu-id="c39e7-106">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span> 
  
- <span data-ttu-id="c39e7-p101">Le port d’écoute à utiliser pour les messages SIP (Session Initiation Protocol). Par défaut, il s’agit des ports 5066 pour TCP (Transmission Control Protocol) et 5067 pour TLS (Transport Layer Security) sur une passerelle, un PBX (Private Branch Exchange) ou un contrôleur SBC. Sur un Survivable Branch Appliance sur un site de succursale, les ports par défaut sont 5081 pour TCP et 5082 pour TLS.</span><span class="sxs-lookup"><span data-stu-id="c39e7-p101">The listening port to be used for Session Initiation Protocol (SIP) messages. By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a gateway, private branch exchange (PBX), or Session Border Controller (SBC). On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.</span></span>
    
- <span data-ttu-id="c39e7-p102">Pour des raisons de sécurité, nous vous recommandons fortement d’utiliser TLS. Si vous définissez un Survivable Branch Appliance, consultez la documentation du fournisseur de votre Survivable Branch Appliance pour vérifier que ce dernier prend en charge le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="c39e7-p102">For security reasons, we strongly recommend that you use TLS. If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c39e7-112">Pour des raisons de sécurité, nous vous recommandons fortement de déployer une passerelle pouvant utiliser TLS.</span><span class="sxs-lookup"><span data-stu-id="c39e7-112">For security reasons, we strongly recommended that you deploy a gateway that can use TLS.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c39e7-113">Si vous souhaitez ajouter une passerelle PSTN, vous pouvez la configurer ultérieurement, mais son fonctionnement reste limité tant qu’elle n’a pas été définie et configurée.</span><span class="sxs-lookup"><span data-stu-id="c39e7-113">If you want to add a PSTN gateway, you can set it up later, but full functionality will be limited until the PSTN gateway is defined and configured.</span></span> 
  

