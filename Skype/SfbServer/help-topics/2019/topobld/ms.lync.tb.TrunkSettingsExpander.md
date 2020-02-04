---
title: Expanseur des paramètres de la jonction
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour modifier les paramètres d’une jonction SIP, procédez comme suit :'
ms.openlocfilehash: b2401dd561891b5c54f22003b0a29f61933b0277
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687937"
---
# <a name="trunk-settings-expander"></a><span data-ttu-id="c40ca-103">Expanseur des paramètres de la jonction</span><span class="sxs-lookup"><span data-stu-id="c40ca-103">Trunk Settings Expander</span></span>

<span data-ttu-id="c40ca-104">Pour modifier les paramètres d’une jonction SIP, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c40ca-104">To edit or modify the settings for a SIP trunk, you do the following:</span></span>

 <span data-ttu-id="c40ca-105">**Nom de la jonction** : entrée requise, qui identifie de manière unique la jonction SIP dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="c40ca-105">**Trunk name** is a required entry and uniquely identifies the SIP trunk in the deployment.</span></span>

 <span data-ttu-id="c40ca-106">**Passerelle RTC associée** : sélectionnez une passerelle RTC existante définie dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="c40ca-106">**Associated PSTN gateway**: Select an existing PSTN gateway that has been defined in the deployment.</span></span>

 <span data-ttu-id="c40ca-p101">**Port d’écoute pour la passerelle IP/RTC** : indique le port TCP/IP de la passerelle sur lequel les requêtes seront écoutées. La valeur obligatoire peut différer en fonction du fournisseur de la passerelle, mais le port par défaut est le port 5067.</span><span class="sxs-lookup"><span data-stu-id="c40ca-p101">**Listening port for IP/PSTN gateway**: Indicates what TCP/IP port the gateway will be listening for requests on. The required value may differ, based on the vendor of the gateway, but the default is port 5067.</span></span>

 <span data-ttu-id="c40ca-p102">**Protocole de transport SIP** : le protocole utilisé est le protocole TCP ou le protocole TLS. Le protocole TLS est le protocole par défaut. Pour connaître la prise en charge de la passerelle, reportez-vous à la documentation du fournisseur de la passerelle. Le protocole par défaut, le protocole TLS, est un choix plus sécurisé si la passerelle le prend en charge.</span><span class="sxs-lookup"><span data-stu-id="c40ca-p102">**SIP Transport Protocol**: The protocol used is either TCP or TLS. TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>

 <span data-ttu-id="c40ca-113">**Serveur de médiation associé**: sélectionnez un serveur de médiation existant du déploiement à associer à la ligne SIP.</span><span class="sxs-lookup"><span data-stu-id="c40ca-113">**Associated Mediation Server**: Select an existing Mediation Server from the deployment to associate with the SIP trunk.</span></span>

> [!NOTE]
> <span data-ttu-id="c40ca-114">Seul le Trunk racine peut être associé à un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="c40ca-114">Only the root trunk can be associated with a Mediation Server.</span></span>

 <span data-ttu-id="c40ca-115">**Port du serveur de médiation associé**: une valeur requise, qui est définie sur la valeur sur laquelle le serveur de médiation est configuré pour l’écoute.</span><span class="sxs-lookup"><span data-stu-id="c40ca-115">**Associated Mediation Server port**: A required value, this is set to the value that the Mediation Server is configured to listen on.</span></span>

![Expanseur des paramètres de la jonction](../../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a><span data-ttu-id="c40ca-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c40ca-117">See also</span></span>

[<span data-ttu-id="c40ca-118">Liste de vérification du déploiement SIP</span><span class="sxs-lookup"><span data-stu-id="c40ca-118">SIP Trunking Deployment Checklist</span></span>](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[<span data-ttu-id="c40ca-119">Composants et topologies pour le trunking SIP</span><span class="sxs-lookup"><span data-stu-id="c40ca-119">Components and Topologies for SIP Trunking</span></span>](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
