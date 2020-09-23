---
title: Expanseur des paramètres de la jonction
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: 'Pour modifier les paramètres d’une jonction SIP, procédez comme suit :'
ms.openlocfilehash: 6393ef52859f32ad93d363faf36af3bd34530a9b
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215935"
---
# <a name="trunk-settings-expander"></a><span data-ttu-id="f1081-103">Expanseur des paramètres de la jonction</span><span class="sxs-lookup"><span data-stu-id="f1081-103">Trunk Settings Expander</span></span>

<span data-ttu-id="f1081-104">Pour modifier les paramètres d’une jonction SIP, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f1081-104">To edit or modify the settings for a SIP trunk, you do the following:</span></span>

 <span data-ttu-id="f1081-105">**Nom de la jonction** est une entrée requise et qui identifie de manière unique la jonction SIP dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="f1081-105">**Trunk name** is a required entry and uniquely identifies the SIP trunk in the deployment.</span></span>

 <span data-ttu-id="f1081-106">**Passerelle PSTN associée** : sélectionnez une passerelle PSTN existante qui a été définie dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="f1081-106">**Associated PSTN gateway**: Select an existing PSTN gateway that has been defined in the deployment.</span></span>

 <span data-ttu-id="f1081-p101">**Port d’écoute pour la passerelle IP/PSTN** : indique que le port TCP/IP de la passerelle écoutera les requêtes. Il se peut que la valeur requise diffère, en fonction du fournisseur de la passerelle, mais le port par défaut est 5067.</span><span class="sxs-lookup"><span data-stu-id="f1081-p101">**Listening port for IP/PSTN gateway**: Indicates what TCP/IP port the gateway will be listening for requests on. The required value may differ, based on the vendor of the gateway, but the default is port 5067.</span></span>

 <span data-ttu-id="f1081-p102">**Protocole de transport SIP** : le protocole utilisé est soit TCP, soit TLS. TLS est le protocole par défaut. Consultez la documentation du fournisseur de la passerelle pour connaître la prise en charge de la passerelle. TLS, protocole par défaut, représente un choix plus sécurisé si la passerelle le prend en charge.</span><span class="sxs-lookup"><span data-stu-id="f1081-p102">**SIP Transport Protocol**: The protocol used is either TCP or TLS. TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>

 <span data-ttu-id="f1081-113">**Serveur de médiation associé**: sélectionnez un serveur de médiation existant dans le déploiement à associer à la jonction SIP.</span><span class="sxs-lookup"><span data-stu-id="f1081-113">**Associated Mediation Server**: Select an existing Mediation Server from the deployment to associate with the SIP trunk.</span></span>

> [!NOTE]
> <span data-ttu-id="f1081-114">Seule la jonction racine peut être associée à un serveur de médiation Lync Server 2010 ou Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f1081-114">Only the root trunk can be associated with a Lync Server 2010 or Lync Server 2013 Mediation Server.</span></span>

 <span data-ttu-id="f1081-115">**Port du serveur de médiation associé**: valeur requise, définie sur la valeur que le serveur de médiation est configuré pour écouter.</span><span class="sxs-lookup"><span data-stu-id="f1081-115">**Associated Mediation Server port**: A required value, this is set to the value that the Mediation Server is configured to listen on.</span></span>

![Expanseur des paramètres de la jonction](../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a><span data-ttu-id="f1081-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f1081-117">See also</span></span>

[<span data-ttu-id="f1081-118">Liste de vérification du déploiement de la jonction SIP</span><span class="sxs-lookup"><span data-stu-id="f1081-118">SIP Trunking Deployment Checklist</span></span>](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[<span data-ttu-id="f1081-119">Composants et topologies pour la jonction SIP</span><span class="sxs-lookup"><span data-stu-id="f1081-119">Components and Topologies for SIP Trunking</span></span>](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
