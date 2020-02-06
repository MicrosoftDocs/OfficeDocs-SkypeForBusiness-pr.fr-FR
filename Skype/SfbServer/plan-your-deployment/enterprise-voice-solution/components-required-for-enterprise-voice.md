---
title: Composants requis pour l’entreprise voix dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Un résumé des composants voix entreprise dans Skype entreprise Server.
ms.openlocfilehash: a2e32e2301a404afd06038d438fbb62a13235d65
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803104"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="db0b7-103">Composants requis pour l’entreprise voix dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="db0b7-103">Components required for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="db0b7-104">Un résumé des composants voix entreprise dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="db0b7-104">A summary of the Enterprise Voice components in Skype for Business Server.</span></span>
  
<span data-ttu-id="db0b7-105">Pour déployer Enterprise Voice, les composants suivants sont requis dans votre topologie.</span><span class="sxs-lookup"><span data-stu-id="db0b7-105">To deploy Enterprise Voice, the following components are required in your topology.</span></span> 
  
- <span data-ttu-id="db0b7-106">Un ou plusieurs serveurs de médiation qui convertissent le signalement et, dans certaines configurations, des contenus multimédias entre votre serveur interne Skype entreprise Server, l’infrastructure voix entreprise et une passerelle réseau téléphonique commuté (PSTN) ou un protocole d’initiation de session (SIP) Trunk.</span><span class="sxs-lookup"><span data-stu-id="db0b7-106">One or more Mediation Servers, which translate signaling and, in some configurations, media between your internal Skype for Business Server, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="db0b7-107">Les serveurs de médiation sont les composants les plus cruciaux du déploiement voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="db0b7-107">The Mediation Servers are the most crucial component in your Enterprise Voice deployment.</span></span> <span data-ttu-id="db0b7-108">Pour plus d’informations, reportez-vous à la rubrique [composant serveur de médiation dans Skype entreprise Server](mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="db0b7-108">For more information, see [Mediation Server component in Skype for Business Server](mediation-server.md).</span></span>
    
    <span data-ttu-id="db0b7-109">Les serveurs de médiation peuvent être colocalisés avec des serveurs frontaux ou installés en tant que serveurs autonomes.</span><span class="sxs-lookup"><span data-stu-id="db0b7-109">Mediation Servers can be collocated with Front End Servers or installed as standalone servers.</span></span>
    
- <span data-ttu-id="db0b7-110">Des composants de connectivité PSTN, pouvant inclure des jonctions SIP ou des passerelles PSTN.</span><span class="sxs-lookup"><span data-stu-id="db0b7-110">PSTN connectivity components, which can include SIP trunks or PSTN gateways.</span></span> <span data-ttu-id="db0b7-111">Pour plus d’informations, reportez-vous à la rubrique [composants de connectivité PSTN dans Skype entreprise Server](pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="db0b7-111">For more information, see [PSTN connectivity components in Skype for Business Server](pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="db0b7-112">Serveur Edge, qui permet d’utiliser les fonctionnalités voix entreprise de vos utilisateurs lorsqu’ils se trouvent en dehors du pare-feu de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="db0b7-112">Edge Servers, which enables the use of Enterprise Voice features by your users when they are outside your organization's firewall.</span></span> 
    
    <span data-ttu-id="db0b7-113">Le service Edge d’accès fournit la signalisation SIP pour les appels d’utilisateurs Skype entreprise extérieurs au pare-feu de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="db0b7-113">The Access Edge service provides SIP signaling for calls from Skype for Business users who are outside your organization's firewall.</span></span> <span data-ttu-id="db0b7-114">Le service Edge A/V permet aux médias de traverser les NAT et les pare-feu.</span><span class="sxs-lookup"><span data-stu-id="db0b7-114">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="db0b7-115">Un appelant qui utilise un client de communications unifiées en dehors du pare-feu de l’entreprise compte sur le service Edge A/V pour les appels individuels et téléconférences.</span><span class="sxs-lookup"><span data-stu-id="db0b7-115">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>
    
    <span data-ttu-id="db0b7-p104">Le service d’authentification A/V est colocalisé avec le service Edge A/V et fournit des services d’authentification pour ce service. Les utilisateurs extérieurs qui tentent de se connecter au service Edge A/V ont besoin d’un jeton d’authentification fourni par le service d’authentification A/V pour que leurs appels puissent aboutir.</span><span class="sxs-lookup"><span data-stu-id="db0b7-p104">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>
    
- <span data-ttu-id="db0b7-118">De plus, certains composants voix entreprise s’exécutent sur des serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="db0b7-118">Additionally, some Enterprise Voice components run on Front End Servers.</span></span> <span data-ttu-id="db0b7-119">Pour plus d’informations sur ces composants, reportez-vous à la rubrique [composants VoIP du serveur frontal pour Skype entreprise Server](front-end-server-voip.md)</span><span class="sxs-lookup"><span data-stu-id="db0b7-119">For details about these components, see [Front End Server VoIP components for Skype for Business Server](front-end-server-voip.md)</span></span>
    

