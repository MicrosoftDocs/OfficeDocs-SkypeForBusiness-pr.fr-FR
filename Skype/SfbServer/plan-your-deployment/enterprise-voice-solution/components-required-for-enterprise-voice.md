---
title: Composants requis pour Voix Entreprise dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Résumé des composants Voix Entreprise dans Skype Entreprise Server.
ms.openlocfilehash: 1a7f13cc171af44ecbd0f48706ec12d882e50b33
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825824"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="75774-103">Composants requis pour Voix Entreprise dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="75774-103">Components required for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="75774-104">Résumé des composants Voix Entreprise dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="75774-104">A summary of the Enterprise Voice components in Skype for Business Server.</span></span>
  
<span data-ttu-id="75774-105">Pour déployer Voix Entreprise, les composants suivants sont requis dans votre topologie.</span><span class="sxs-lookup"><span data-stu-id="75774-105">To deploy Enterprise Voice, the following components are required in your topology.</span></span> 
  
- <span data-ttu-id="75774-106">Un ou plusieurs serveurs de médiation, qui traduisent la signalisation et, dans certaines configurations, les médias entre votre infrastructure skype entreprise interne, votre infrastructure Voix Entreprise et une passerelle PSTN (réseau téléphonique commuté) ou une session SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="75774-106">One or more Mediation Servers, which translate signaling and, in some configurations, media between your internal Skype for Business Server, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="75774-107">Les serveurs de médiation sont le composant le plus crucial de votre déploiement Voix Entreprise de médiation.</span><span class="sxs-lookup"><span data-stu-id="75774-107">The Mediation Servers are the most crucial component in your Enterprise Voice deployment.</span></span> <span data-ttu-id="75774-108">Pour plus d’informations, [voir composant serveur de médiation dans Skype Entreprise Server.](mediation-server.md)</span><span class="sxs-lookup"><span data-stu-id="75774-108">For more information, see [Mediation Server component in Skype for Business Server](mediation-server.md).</span></span>
    
    <span data-ttu-id="75774-109">Les serveurs de médiation peuvent être cocalisé avec des serveurs frontaux ou installés en tant que serveurs autonomes.</span><span class="sxs-lookup"><span data-stu-id="75774-109">Mediation Servers can be collocated with Front End Servers or installed as standalone servers.</span></span>
    
- <span data-ttu-id="75774-110">Composants de connectivité PSTN, qui peuvent inclure des passerelles SIP ou PSTN.</span><span class="sxs-lookup"><span data-stu-id="75774-110">PSTN connectivity components, which can include SIP trunks or PSTN gateways.</span></span> <span data-ttu-id="75774-111">Pour plus d’informations, voir composants de connectivité [PSTN dans Skype Entreprise Server.](pstn-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="75774-111">For more information, see [PSTN connectivity components in Skype for Business Server](pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="75774-112">Les serveurs Edge, qui permettent à vos utilisateurs d’utiliser Voix Entreprise fonctionnalités de sécurité lorsqu’ils sont en dehors du pare-feu de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="75774-112">Edge Servers, which enables the use of Enterprise Voice features by your users when they are outside your organization's firewall.</span></span> 
    
    <span data-ttu-id="75774-113">Le service Edge d’accès fournit une signalisation SIP pour les appels provenant d’utilisateurs Skype Entreprise qui se sont produits à l’extérieur du pare-feu de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="75774-113">The Access Edge service provides SIP signaling for calls from Skype for Business users who are outside your organization's firewall.</span></span> <span data-ttu-id="75774-114">Le service Edge A/V permet aux médias de traverser les NAT et les pare-feu.</span><span class="sxs-lookup"><span data-stu-id="75774-114">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="75774-115">Un appelant qui utilise un client de communications unifiées en dehors du pare-feu de l’entreprise compte sur le service Edge A/V pour les appels individuels et téléconférences.</span><span class="sxs-lookup"><span data-stu-id="75774-115">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>
    
    <span data-ttu-id="75774-p104">Le service d’authentification A/V est colocalisé avec le service Edge A/V et fournit des services d’authentification pour ce service. Les utilisateurs extérieurs qui tentent de se connecter au service Edge A/V ont besoin d’un jeton d’authentification fourni par le service d’authentification A/V pour que leurs appels puissent aboutir.</span><span class="sxs-lookup"><span data-stu-id="75774-p104">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>
    
- <span data-ttu-id="75774-118">En outre, certains composants Voix Entreprise s’exécutent sur des serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="75774-118">Additionally, some Enterprise Voice components run on Front End Servers.</span></span> <span data-ttu-id="75774-119">Pour plus d’informations sur ces composants, voir [Composants VoIP](front-end-server-voip.md) du serveur frontal pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="75774-119">For details about these components, see [Front End Server VoIP components for Skype for Business Server](front-end-server-voip.md)</span></span>
    

