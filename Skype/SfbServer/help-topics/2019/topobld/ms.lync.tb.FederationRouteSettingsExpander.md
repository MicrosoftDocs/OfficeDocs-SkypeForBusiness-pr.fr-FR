---
title: Développeur des paramètres d’itinéraire de fédération
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: Pour définir une affectation de routage de Fédération de site, vous devez d’abord disposer de la Fédération sur le serveur Edge ou le pool de serveurs Edge. Si la Fédération n’est pas activée sur le serveur Edge ou le pool, les paramètres d’attribution de l’itinéraire de Fédération pour le site ne seront pas disponibles à des fins de modification.
ms.openlocfilehash: 6e68bc7cb2f5a9f04e208dc2f27ce7724aa7e793
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292723"
---
# <a name="federation-route-settings-expander"></a><span data-ttu-id="0ffd0-104">Développeur des paramètres d’itinéraire de fédération</span><span class="sxs-lookup"><span data-stu-id="0ffd0-104">Federation Route Settings Expander</span></span>
 
<span data-ttu-id="0ffd0-105">Pour définir une affectation de routage de Fédération de site, vous devez d’abord disposer de la Fédération sur le serveur Edge ou le pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="0ffd0-105">To set a site federation route assignment, you must first have federation enabled on the Edge Server or Edge Server pool.</span></span> <span data-ttu-id="0ffd0-106">Si la Fédération n’est pas activée sur le serveur Edge ou le pool, les paramètres d’attribution de l’itinéraire de Fédération pour le site ne seront pas disponibles à des fins de modification.</span><span class="sxs-lookup"><span data-stu-id="0ffd0-106">If federation is not enabled on the Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="0ffd0-107">Si le paramètre de Fédération sur le serveur Edge ou le pool a été configuré, vous pouvez configurer les options suivantes:</span><span class="sxs-lookup"><span data-stu-id="0ffd0-107">If the federation setting at the Edge Server or pool has been configured, you can configure the following options:</span></span> 
  
- <span data-ttu-id="0ffd0-108">**Autoriser les affectations de routage de Fédération à tous les sites** Ce paramètre affecte tous les sites.</span><span class="sxs-lookup"><span data-stu-id="0ffd0-108">**Allow federation route assignments to all sites** This setting will affect all sites.</span></span> <span data-ttu-id="0ffd0-109">Assurez-vous que le paramètre que vous configurez sur ce site est approprié pour tous les sites.</span><span class="sxs-lookup"><span data-stu-id="0ffd0-109">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>
    
- <span data-ttu-id="0ffd0-110">**Activer la Fédération SIP** Sélectionnez cette option pour activer un itinéraire de Fédération SIP, puis sélectionnez un directeur ou un pool d’arêtes en tant qu’itinéraire de Fédération.</span><span class="sxs-lookup"><span data-stu-id="0ffd0-110">**Enable SIP federation** Select this option to enable a SIP federation route, and then select a Director or Edge pool as the federation route.</span></span>
    
- <span data-ttu-id="0ffd0-111">**Activer la Fédération XMPP** Sélectionnez cette option pour activer un itinéraire de Fédération XMPP, puis sélectionnez un réalisateur ou un pool d’arêtes en tant qu’itinéraire de Fédération.</span><span class="sxs-lookup"><span data-stu-id="0ffd0-111">**Enable XMPP federation** Select this option to enable an XMPP federation route, and then select a Director or Edge pool as the federation route.</span></span>
- 
  > [!NOTE]
  > <span data-ttu-id="0ffd0-112">Les passerelles et les proxys XMPP sont disponibles dans Skype entreprise Server 2015, mais ne sont plus pris en charge dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0ffd0-112">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="0ffd0-113">Pour plus d’informations, consultez la section migration de la [Fédération XMPP](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) .</span><span class="sxs-lookup"><span data-stu-id="0ffd0-113">See [Migrating XMPP federation](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
    

