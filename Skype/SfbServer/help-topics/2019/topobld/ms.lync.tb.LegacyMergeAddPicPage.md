---
title: Fusion héritée
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: Le nom de domaine complet pour les conférences Web autorise les utilisateurs externes à participer à des réunions locales. Entrez le nom de domaine complet (FQDN) de l’interface externe de conférence Web du serveur Edge hérité.
ms.openlocfilehash: 1f2a1e9ca3d3ca20b7b0fe6832a0e394d7fac5ce
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41688337"
---
# <a name="legacy-merge"></a><span data-ttu-id="02aec-104">Fusion héritée</span><span class="sxs-lookup"><span data-stu-id="02aec-104">Legacy Merge</span></span>

<span data-ttu-id="02aec-105">Le **nom de domaine complet pour les conférences Web** autorise les utilisateurs externes à participer à des réunions locales.</span><span class="sxs-lookup"><span data-stu-id="02aec-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="02aec-106">Entrez le nom de domaine complet (FQDN) de l’interface externe de conférence Web du serveur Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="02aec-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="02aec-107">La valeur de **port externe de conférence Web externe** de **443** est le port SIP (Session Initiation Protocol) par défaut configuré pour les clients de conférence.</span><span class="sxs-lookup"><span data-stu-id="02aec-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="02aec-108">Si la valeur par défaut n’a pas été utilisée, mettez à jour la valeur **port externe de conférence Web externe** .</span><span class="sxs-lookup"><span data-stu-id="02aec-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="02aec-109">Activez la case à cocher **ce pool Edge est utilisé pour la connectivité de Fédération et de messagerie instantanée publique** si vous prévoyez d’utiliser ce serveur Edge pour la Fédération.</span><span class="sxs-lookup"><span data-stu-id="02aec-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="02aec-110">Si vous avez déployé plusieurs serveurs Edge, seul l’un d’eux sera activé pour la Fédération.</span><span class="sxs-lookup"><span data-stu-id="02aec-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="02aec-111">Si vous n’activez pas cette case à cocher et que vous décidez par la suite d’activer la Fédération, vous devez exécuter de nouveau l’Assistant Fusion du générateur de topologie, et publier votre topologie.</span><span class="sxs-lookup"><span data-stu-id="02aec-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="02aec-112">Pour plus d’informations, voir [phase 4 : fusionner des topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span><span class="sxs-lookup"><span data-stu-id="02aec-112">For details, see [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>


