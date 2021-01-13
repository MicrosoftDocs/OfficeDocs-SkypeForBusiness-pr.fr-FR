---
title: Expanseur des paramètres de la jonction
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour modifier les paramètres d’une jonction SIP, procédez comme suit :'
ms.openlocfilehash: 43cce7d0e61cf2e2c4f5fa6e4bcb845fd63fbc03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807534"
---
# <a name="trunk-settings-expander"></a><span data-ttu-id="e1314-103">Expandeur des paramètres de la jonction</span><span class="sxs-lookup"><span data-stu-id="e1314-103">Trunk Settings Expander</span></span>

<span data-ttu-id="e1314-104">Pour modifier les paramètres d’une jonction SIP, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e1314-104">To edit or modify the settings for a SIP trunk, you do the following:</span></span>

 <span data-ttu-id="e1314-105">**Nom de la jonction** est une entrée requise et qui identifie de manière unique la jonction SIP dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="e1314-105">**Trunk name** is a required entry and uniquely identifies the SIP trunk in the deployment.</span></span>

 <span data-ttu-id="e1314-106">**Passerelle PSTN associée** : sélectionnez une passerelle PSTN existante qui a été définie dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="e1314-106">**Associated PSTN gateway**: Select an existing PSTN gateway that has been defined in the deployment.</span></span>

 <span data-ttu-id="e1314-p101">**Port d’écoute pour la passerelle IP/PSTN** : indique que le port TCP/IP de la passerelle écoutera les requêtes. Il se peut que la valeur requise diffère, en fonction du fournisseur de la passerelle, mais le port par défaut est 5067.</span><span class="sxs-lookup"><span data-stu-id="e1314-p101">**Listening port for IP/PSTN gateway**: Indicates what TCP/IP port the gateway will be listening for requests on. The required value may differ, based on the vendor of the gateway, but the default is port 5067.</span></span>

 <span data-ttu-id="e1314-p102">**Protocole de transport SIP** : le protocole utilisé est soit TCP, soit TLS. TLS est le protocole par défaut. Consultez la documentation du fournisseur de la passerelle pour connaître la prise en charge de la passerelle. TLS, protocole par défaut, représente un choix plus sécurisé si la passerelle le prend en charge.</span><span class="sxs-lookup"><span data-stu-id="e1314-p102">**SIP Transport Protocol**: The protocol used is either TCP or TLS. TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>

 <span data-ttu-id="e1314-113">**Serveur de médiation associé**: sélectionnez un serveur de médiation existant dans le déploiement à associer à la ligne SIP.</span><span class="sxs-lookup"><span data-stu-id="e1314-113">**Associated Mediation Server**: Select an existing Mediation Server from the deployment to associate with the SIP trunk.</span></span>

> [!NOTE]
> <span data-ttu-id="e1314-114">Seule la troncation racine peut être associée à un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="e1314-114">Only the root trunk can be associated with a Mediation Server.</span></span>

 <span data-ttu-id="e1314-115">**Port du serveur de médiation** associé : valeur requise, définie sur la valeur que le serveur de médiation est configuré pour écouter.</span><span class="sxs-lookup"><span data-stu-id="e1314-115">**Associated Mediation Server port**: A required value, this is set to the value that the Mediation Server is configured to listen on.</span></span>

![Expandeur des paramètres de la jonction](../../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a><span data-ttu-id="e1314-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e1314-117">See also</span></span>

[<span data-ttu-id="e1314-118">Liste de vérification du déploiement de la trunking SIP</span><span class="sxs-lookup"><span data-stu-id="e1314-118">SIP Trunking Deployment Checklist</span></span>](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[<span data-ttu-id="e1314-119">Composants et topologies pour la jonction SIP</span><span class="sxs-lookup"><span data-stu-id="e1314-119">Components and Topologies for SIP Trunking</span></span>](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
