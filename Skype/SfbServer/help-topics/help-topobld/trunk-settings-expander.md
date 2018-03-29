---
title: Expanseur des paramètres de la jonction
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: 'Pour modifier les paramètres d’une jonction SIP, procédez comme suit :'
ms.openlocfilehash: 13ea9abfb6d53b57333c2c96b8a2f8adde963ebf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="trunk-settings-expander"></a><span data-ttu-id="011ab-103">Expanseur des paramètres de la jonction</span><span class="sxs-lookup"><span data-stu-id="011ab-103">Trunk Settings Expander</span></span>
 
<span data-ttu-id="011ab-104">Pour modifier les paramètres d’une jonction SIP, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="011ab-104">To edit or modify the settings for a SIP trunk, you do the following:</span></span>
  
 <span data-ttu-id="011ab-105">**Nom de la jonction** : entrée requise, qui identifie de manière unique la jonction SIP dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="011ab-105">**Trunk name** is a required entry and uniquely identifies the SIP trunk in the deployment.</span></span>
  
 <span data-ttu-id="011ab-106">**Passerelle RTC associée** : sélectionnez une passerelle RTC existante définie dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="011ab-106">**Associated PSTN gateway**: Select an existing PSTN gateway that has been defined in the deployment.</span></span>
  
 <span data-ttu-id="011ab-p101">**Port d’écoute pour la passerelle IP/RTC** : indique le port TCP/IP de la passerelle sur lequel les requêtes seront écoutées. La valeur obligatoire peut différer en fonction du fournisseur de la passerelle, mais le port par défaut est le port 5067.</span><span class="sxs-lookup"><span data-stu-id="011ab-p101">**Listening port for IP/PSTN gateway**: Indicates what TCP/IP port the gateway will be listening for requests on. The required value may differ, based on the vendor of the gateway, but the default is port 5067.</span></span>
  
 <span data-ttu-id="011ab-p102">**Protocole de transport SIP** : le protocole utilisé est le protocole TCP ou le protocole TLS. Le protocole TLS est le protocole par défaut. Pour connaître la prise en charge de la passerelle, reportez-vous à la documentation du fournisseur de la passerelle. Le protocole par défaut, le protocole TLS, est un choix plus sécurisé si la passerelle le prend en charge.</span><span class="sxs-lookup"><span data-stu-id="011ab-p102">**SIP Transport Protocol**: The protocol used is either TCP or TLS. TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>
  
 <span data-ttu-id="011ab-113">**Associé à un serveur de médiation**: sélectionnez un serveur de médiation existant dans le déploiement à associer à la jonction SIP.</span><span class="sxs-lookup"><span data-stu-id="011ab-113">**Associated Mediation Server**: Select an existing Mediation Server from the deployment to associate with the SIP trunk.</span></span>
  
> [!NOTE]
> <span data-ttu-id="011ab-114">Uniquement le tronc racine peut être associé à un Microsoft Lync Server 2010 ou un serveur de médiation de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="011ab-114">Only the root trunk can be associated with a Lync Server 2010 or Lync Server 2013 Mediation Server.</span></span> 
  
 <span data-ttu-id="011ab-115">**Port de serveur de médiation associé**: une valeur requise, il est défini à la valeur configurée pour le serveur de médiation écoutent.</span><span class="sxs-lookup"><span data-stu-id="011ab-115">**Associated Mediation Server port**: A required value, this is set to the value that the Mediation Server is configured to listen on.</span></span>
  
![Expanseur des paramètres de la jonction](../../media/Trunk_Settings_Expander.jpg)
  
## <a name="see-also"></a><span data-ttu-id="011ab-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="011ab-117">See also</span></span>

#### 

[<span data-ttu-id="011ab-118">Liste de vérification de déploiement SIP Trunking</span><span class="sxs-lookup"><span data-stu-id="011ab-118">SIP Trunking Deployment Checklist</span></span>](http://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)
  
[<span data-ttu-id="011ab-119">Les composants et les Topologies pour SIP Trunking</span><span class="sxs-lookup"><span data-stu-id="011ab-119">Components and Topologies for SIP Trunking</span></span>](http://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)

