---
title: Expanseur des paramètres d’itinéraire de fédération
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: Pour configurer l’affectation d’itinéraire de fédération d’un site, vous devez d’abord activer la fédération sur le serveur Edge ou le pool de serveurs Edge. Si la fédération n’est pas activée sur le serveur ou pool de serveurs Edge, il ne sera pas possible de modifier les paramètres d’affectation de l’itinéraire de fédération du site.
ms.openlocfilehash: 9e453eae2ca44b0e6f406aa6767bc44b741bd3b6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819464"
---
# <a name="federation-route-settings-expander"></a><span data-ttu-id="1f9ee-104">Expandeur des paramètres d’itinéraire de fédération</span><span class="sxs-lookup"><span data-stu-id="1f9ee-104">Federation Route Settings Expander</span></span>
 
<span data-ttu-id="1f9ee-p102">Pour configurer l’affectation d’itinéraire de fédération d’un site, vous devez d’abord activer la fédération sur le serveur Edge ou le pool de serveurs Edge. Si la fédération n’est pas activée sur le serveur ou pool de serveurs Edge, il ne sera pas possible de modifier les paramètres d’affectation de l’itinéraire de fédération du site.</span><span class="sxs-lookup"><span data-stu-id="1f9ee-p102">To set a site federation route assignment, you must first have federation enabled on the Edge Server or Edge Server pool. If federation is not enabled on the Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="1f9ee-107">Si le paramètre de fédération du serveur Edge ou pool de serveurs Edge a été configuré, vous pouvez configurer les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="1f9ee-107">If the federation setting at the Edge Server or pool has been configured, you can configure the following options:</span></span> 
  
- <span data-ttu-id="1f9ee-108">**Autoriser les affectations d’itinéraires de fédération à tous les sites** Ce paramètre affectera tous les sites.</span><span class="sxs-lookup"><span data-stu-id="1f9ee-108">**Allow federation route assignments to all sites** This setting will affect all sites.</span></span> <span data-ttu-id="1f9ee-109">Assurez-vous que le paramètre que vous configurez pour ce site s’adapte à tous les sites.</span><span class="sxs-lookup"><span data-stu-id="1f9ee-109">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>
    
- <span data-ttu-id="1f9ee-110">**Activer la fédération SIP** Sélectionnez cette option pour activer un itinéraire de fédération SIP, puis sélectionnez un directeur ou un pool edge comme itinéraire de fédération.</span><span class="sxs-lookup"><span data-stu-id="1f9ee-110">**Enable SIP federation** Select this option to enable a SIP federation route, and then select a Director or Edge pool as the federation route.</span></span>
    
- <span data-ttu-id="1f9ee-111">**Activer la fédération XMPP** Sélectionnez cette option pour activer un itinéraire de fédération XMPP, puis sélectionnez un directeur ou un pool edge comme itinéraire de fédération.</span><span class="sxs-lookup"><span data-stu-id="1f9ee-111">**Enable XMPP federation** Select this option to enable an XMPP federation route, and then select a Director or Edge pool as the federation route.</span></span>
- 
  > [!NOTE]
  > <span data-ttu-id="1f9ee-112">Les passerelles et proxys XMPP sont disponibles dans Skype Entreprise Server 2015, mais ne sont plus pris en charge dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1f9ee-112">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="1f9ee-113">Pour [plus d’informations, voir](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) Migration de la fédération XMPP.</span><span class="sxs-lookup"><span data-stu-id="1f9ee-113">See [Migrating XMPP federation](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
    

