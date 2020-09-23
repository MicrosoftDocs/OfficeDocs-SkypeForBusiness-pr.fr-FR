---
title: Fusion héritée
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
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: Le Nom de domaine complet externe de conférence Web permet à des utilisateurs externes de participer à des réunions sur site. Entrez le nom de domaine complet (FQDN) de l'interface de conférence Web externe du serveur Edge hérité.
ms.openlocfilehash: 984d40f8797a974a5865cca37ba1057dc638d886
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217995"
---
# <a name="legacy-merge"></a><span data-ttu-id="d5277-104">Fusion héritée</span><span class="sxs-lookup"><span data-stu-id="d5277-104">Legacy Merge</span></span>

<span data-ttu-id="d5277-p102">Le **Nom de domaine complet externe de conférence Web** permet à des utilisateurs externes de participer à des réunions sur site. Entrez le nom de domaine complet (FQDN) de l'interface de conférence Web externe du serveur Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="d5277-p102">The **Web Conferencing external FQDN** permits external users to join on-premises meetings. Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="d5277-p103">La valeur **443** du **Port externe de conférence Web externe** est le port TCP SIP (Transmission Control Protocol Session Initiation Protocol) configuré par défaut pour les clients de conférences. Si la valeur par défaut n'est pas utilisée, mettez à jour la valeur du **Port externe de conférence Web externe**.</span><span class="sxs-lookup"><span data-stu-id="d5277-p103">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients. If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="d5277-109">Activez la case à cocher **Ce serveur Edge d’accès est utilisé pour la fédération et la solution PIC** si vous planifiez d’utiliser ce serveur Edge pour la fédération.</span><span class="sxs-lookup"><span data-stu-id="d5277-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="d5277-110">Si vous disposez d’un déploiement de plusieurs serveurs Edge, un seul d’entre eux sera activé pour la fédération.</span><span class="sxs-lookup"><span data-stu-id="d5277-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="d5277-111">Si vous n’activez pas cette case à cocher et que vous décidez d’activer une fédération ultérieurement, vous devez exécuter de nouveau l’Assistant Fusion du Générateur de topologies et publier votre topologie.</span><span class="sxs-lookup"><span data-stu-id="d5277-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="d5277-112">Pour plus d’informations, voir [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span><span class="sxs-lookup"><span data-stu-id="d5277-112">For details, see [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>


