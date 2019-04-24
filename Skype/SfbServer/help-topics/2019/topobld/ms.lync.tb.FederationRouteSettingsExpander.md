---
title: Développeur des paramètres d’itinéraire de fédération
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: Pour définir une attribution itinéraire fédération du site, vous devez au préalable avoir fédération activée sur le serveur Edge ou le pool de serveurs Edge. Si la fédération n’est pas activée sur le serveur Edge ou le pool, les paramètres d’affectation fédération itinéraire pour le site ne sera pas disponibles pour la modification.
ms.openlocfilehash: 49709f5c4a91e25efb14cc4b2c321c99fec89b68
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32201898"
---
# <a name="federation-route-settings-expander"></a><span data-ttu-id="73e4a-104">Développeur des paramètres d’itinéraire de fédération</span><span class="sxs-lookup"><span data-stu-id="73e4a-104">Federation Route Settings Expander</span></span>
 
<span data-ttu-id="73e4a-105">Pour définir une attribution itinéraire fédération du site, vous devez au préalable avoir fédération activée sur le serveur Edge ou le pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="73e4a-105">To set a site federation route assignment, you must first have federation enabled on the Edge Server or Edge Server pool.</span></span> <span data-ttu-id="73e4a-106">Si la fédération n’est pas activée sur le serveur Edge ou le pool, les paramètres d’affectation fédération itinéraire pour le site ne sera pas disponibles pour la modification.</span><span class="sxs-lookup"><span data-stu-id="73e4a-106">If federation is not enabled on the Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="73e4a-107">Si le paramètre de fédération au pool ou serveur Edge a été configuré, vous pouvez configurer les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="73e4a-107">If the federation setting at the Edge Server or pool has been configured, you can configure the following options:</span></span> 
  
- <span data-ttu-id="73e4a-108">**Affectations d’itinéraire de fédération autoriser à tous les sites** Ce paramètre affecte tous les sites.</span><span class="sxs-lookup"><span data-stu-id="73e4a-108">**Allow federation route assignments to all sites** This setting will affect all sites.</span></span> <span data-ttu-id="73e4a-109">N’oubliez pas que le paramètre que vous configurez sur ce site est approprié pour tous les sites.</span><span class="sxs-lookup"><span data-stu-id="73e4a-109">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>
    
- <span data-ttu-id="73e4a-110">**Activer la fédération SIP** Sélectionnez cette option pour activer un itinéraire de fédération SIP, puis sélectionnez un pool directeur ou Edge en tant que l’itinéraire de fédération.</span><span class="sxs-lookup"><span data-stu-id="73e4a-110">**Enable SIP federation** Select this option to enable a SIP federation route, and then select a Director or Edge pool as the federation route.</span></span>
    
- <span data-ttu-id="73e4a-111">**Activer la fédération XMPP** Sélectionnez cette option pour activer un itinéraire de fédération XMPP, puis sélectionnez un pool directeur ou Edge en tant que l’itinéraire de fédération.</span><span class="sxs-lookup"><span data-stu-id="73e4a-111">**Enable XMPP federation** Select this option to enable an XMPP federation route, and then select a Director or Edge pool as the federation route.</span></span>
- 
  > [!NOTE]
  > <span data-ttu-id="73e4a-112">XMPP passerelles et les proxys sont disponibles dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="73e4a-112">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="73e4a-113">Pour plus d’informations, voir [la fédération XMPP de migration](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) .</span><span class="sxs-lookup"><span data-stu-id="73e4a-113">See [Migrating XMPP federation](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
    

