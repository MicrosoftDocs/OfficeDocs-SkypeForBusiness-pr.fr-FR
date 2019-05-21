---
title: Ajouter la passerelle PSTN pour le Survivable Branch Appliance
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 'Pour définir la passerelle RTC (réseau téléphonique commuté) pour une branche Survivable sur un site de succursale, spécifiez les éléments suivants:'
ms.openlocfilehash: 3a146a5bf9b879681b0d490a1d03198853c72305
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303665"
---
# <a name="add-survivable-branch-appliance-pstn"></a><span data-ttu-id="c10d9-103">Ajouter la passerelle PSTN pour le Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="c10d9-103">Add Survivable Branch Appliance PSTN</span></span>
 
<span data-ttu-id="c10d9-104">Pour définir la passerelle RTC (réseau téléphonique commuté) pour une branche Survivable sur un site de succursale, spécifiez les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="c10d9-104">To define the public switched telephone network (PSTN) gateway for a Survivable Branch Appliance at a branch site, specify the following:</span></span> 
  
- <span data-ttu-id="c10d9-105">Le nom de domaine complet (FQDN) ou l’adresse IP de l’homologue de la passerelle qui est associé à l’unité de messagerie ou au serveur de succursales survivant est associé pour le routage des appels RTC entrants et sortants.</span><span class="sxs-lookup"><span data-stu-id="c10d9-105">A fully qualified domain name (FQDN) or IP address for the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound and outbound PSTN calls.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c10d9-106">S’il s’agit de la définition d’une unité de branchement survivant, il s’agit de la passerelle à laquelle le serveur de médiation de l’appareil de branchement survivant se connecte pour la connectivité PSTN.</span><span class="sxs-lookup"><span data-stu-id="c10d9-106">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span> 
  
- <span data-ttu-id="c10d9-p101">Le port d’écoute à utiliser pour les messages SIP (Session Initiation Protocol). Par défaut, il s’agit des ports 5066 pour le protocole TCP (Transmission Control Protocol) et 5067 pour le protocole TLS (Transport Layer Security) sur une passerelle, un PBX (Private Branch Exchange) ou un contrôleur SBC. Sur un Survivable Branch Appliance sur un site de succursale, les ports par défaut sont le port 5081 pour le protocole TCP et le port 5082 pour le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="c10d9-p101">The listening port to be used for Session Initiation Protocol (SIP) messages. By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a gateway, private branch exchange (PBX), or Session Border Controller (SBC). On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.</span></span>
    
- <span data-ttu-id="c10d9-110">Pour des raisons de sécurité, nous vous conseillons vivement d’utiliser le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="c10d9-110">For security reasons, we strongly recommend that you use TLS.</span></span> <span data-ttu-id="c10d9-111">Si vous définissez une application branche Survivable, consultez la documentation fournie par le fabricant de votre appareil pour vérifier que votre application de branchement Survivable prend en charge le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="c10d9-111">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c10d9-112">Pour des raisons de sécurité, nous vous recommandons vivement de déployer une passerelle pouvant utiliser le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="c10d9-112">For security reasons, we strongly recommended that you deploy a gateway that can use TLS.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c10d9-113">Si vous souhaitez ajouter une passerelle RTC, vous pouvez la configurer ultérieurement, mais son fonctionnement reste limité tant qu’elle n’a pas été définie et configurée.</span><span class="sxs-lookup"><span data-stu-id="c10d9-113">If you want to add a PSTN gateway, you can set it up later, but full functionality will be limited until the PSTN gateway is defined and configured.</span></span> 
  

