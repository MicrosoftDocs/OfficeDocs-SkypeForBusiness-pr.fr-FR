---
title: Composants requis pour Enterprise Voice sur Skype pour Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Un résumé des composants Enterprise Voice dans Skype pour Business Server.
ms.openlocfilehash: 870110c702c36660652fb08cff702453573349a2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206984"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="90abb-103">Composants requis pour Enterprise Voice sur Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="90abb-103">Components required for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="90abb-104">Un résumé des composants Enterprise Voice dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="90abb-104">A summary of the Enterprise Voice components in Skype for Business Server.</span></span>
  
<span data-ttu-id="90abb-105">Pour déployer Enterprise Voice, les composants suivants sont requis dans votre topologie.</span><span class="sxs-lookup"><span data-stu-id="90abb-105">To deploy Enterprise Voice, the following components are required in your topology.</span></span> 
  
- <span data-ttu-id="90abb-106">Un ou plusieurs serveurs de médiation, qui traduit la signalisation et, dans certaines configurations, les médias entre votre interne Skype pour Business Server, l’infrastructure Enterprise Voice et une passerelle de réseau téléphonique commuté ou une Session Initiation Protocol Jonction (SIP).</span><span class="sxs-lookup"><span data-stu-id="90abb-106">One or more Mediation Servers, which translate signaling and, in some configurations, media between your internal Skype for Business Server, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="90abb-107">Les serveurs de médiation sont le plus important composant dans votre déploiement d’Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="90abb-107">The Mediation Servers are the most crucial component in your Enterprise Voice deployment.</span></span> <span data-ttu-id="90abb-108">Pour plus d’informations, voir [composant serveur de médiation dans Skype pour Business Server](mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="90abb-108">For more information, see [Mediation Server component in Skype for Business Server](mediation-server.md).</span></span>
    
    <span data-ttu-id="90abb-109">Serveurs de médiation peuvent être colocalisés avec les serveurs frontaux ou installés en tant que serveurs autonomes.</span><span class="sxs-lookup"><span data-stu-id="90abb-109">Mediation Servers can be collocated with Front End Servers or installed as standalone servers.</span></span>
    
- <span data-ttu-id="90abb-110">Des composants de connectivité PSTN, pouvant inclure des jonctions SIP ou des passerelles PSTN.</span><span class="sxs-lookup"><span data-stu-id="90abb-110">PSTN connectivity components, which can include SIP trunks or PSTN gateways.</span></span> <span data-ttu-id="90abb-111">Pour plus d’informations, consultez [composants de connectivité PSTN dans Skype pour Business Server](pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="90abb-111">For more information, see [PSTN connectivity components in Skype for Business Server](pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="90abb-112">Serveurs de périphérie, qui permet d’utiliser des fonctionnalités d’Enterprise Voice par vos utilisateurs lorsqu’ils sont en dehors du pare-feu de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="90abb-112">Edge Servers, which enables the use of Enterprise Voice features by your users when they are outside your organization's firewall.</span></span> 
    
    <span data-ttu-id="90abb-113">Le service Edge d’accès fournit la signalisation SIP pour les appels Skype pour les utilisateurs professionnels qui sont trouvent en dehors du pare-feu de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="90abb-113">The Access Edge service provides SIP signaling for calls from Skype for Business users who are outside your organization's firewall.</span></span> <span data-ttu-id="90abb-114">Le service Edge A/V permet aux médias de traverser les NAT et les pare-feu.</span><span class="sxs-lookup"><span data-stu-id="90abb-114">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="90abb-115">Un appelant qui utilise un client de communications unifiées en dehors du pare-feu de l’entreprise compte sur le service Edge A/V pour les appels individuels et téléconférences.</span><span class="sxs-lookup"><span data-stu-id="90abb-115">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>
    
    <span data-ttu-id="90abb-p104">Le service d’authentification A/V est colocalisé avec le service Edge A/V et fournit des services d’authentification pour ce service. Les utilisateurs extérieurs qui tentent de se connecter au service Edge A/V ont besoin d’un jeton d’authentification fourni par le service d’authentification A/V pour que leurs appels puissent aboutir.</span><span class="sxs-lookup"><span data-stu-id="90abb-p104">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>
    
- <span data-ttu-id="90abb-118">En outre, certains composants d’Enterprise Voice s’exécuter sur les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="90abb-118">Additionally, some Enterprise Voice components run on Front End Servers.</span></span> <span data-ttu-id="90abb-119">Pour plus d’informations sur ces composants, consultez [composants VoIP du serveur frontal pour Skype pour Business Server](front-end-server-voip.md)</span><span class="sxs-lookup"><span data-stu-id="90abb-119">For details about these components, see [Front End Server VoIP components for Skype for Business Server](front-end-server-voip.md)</span></span>
    

