---
title: Planification des déploiements de serveur Edge dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Résumé : Planifiez votre Skype pour environnement Business Server 2015 serveur Edge. Cette rubrique présente les concepts de périphérie et vous permet d’organiser avec notre rubriques plus détaillées.'
ms.openlocfilehash: 973cda4f049f4d9d606ba1fe047c99f671ed2e86
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server-2015"></a><span data-ttu-id="7ac60-104">Planification des déploiements de serveur Edge dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="7ac60-104">Plan for Edge Server deployments in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7ac60-p102">**Résumé :** planifiez votre environnement Edge Skype Entreprise Server 2015. Cette rubrique présente les concepts se rapportant aux serveurs Edge et vous permet d’organiser votre environnement à l’aide de rubriques plus détaillées.</span><span class="sxs-lookup"><span data-stu-id="7ac60-p102">**Summary:** Plan for your Skype for Business Server 2015 Server Edge environment. This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="7ac60-107">Lorsque vous avez un Skype pour environnement Business Server 2015 qui fonctionne bien en interne, l’étape suivante vous est peut-être d’introduire un serveur Edge ou un pool de serveurs Edge à l’environnement.</span><span class="sxs-lookup"><span data-stu-id="7ac60-107">When you have a Skype for Business Server 2015 environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="7ac60-108">Ce rôle est essentiel si vous souhaitez que les services fournis par Skype pour Business Server 2015 devant être utilisé par les personnes qui sont trouvent en dehors de votre réseau interne.</span><span class="sxs-lookup"><span data-stu-id="7ac60-108">This role would be vital if you want the services provided by Skype for Business Server 2015 to be used by people who are outside your internal network.</span></span> <span data-ttu-id="7ac60-109">Il peuvent inclure :</span><span class="sxs-lookup"><span data-stu-id="7ac60-109">These can potentially include:</span></span>
  
- <span data-ttu-id="7ac60-110">Utilisateurs distants : employés qui travaillent hors site, de manière temporaire ou permanente ;</span><span class="sxs-lookup"><span data-stu-id="7ac60-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="7ac60-111">Fédérés : Les employés les partenaires.</span><span class="sxs-lookup"><span data-stu-id="7ac60-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="7ac60-112">Utilisateurs d’appareils mobiles ;</span><span class="sxs-lookup"><span data-stu-id="7ac60-112">Mobile Users.</span></span>
    
- <span data-ttu-id="7ac60-113">Clients potentiels, partenaires et même utilisateurs anonymes que vous souhaitez inviter à des réunions et à des présentations.</span><span class="sxs-lookup"><span data-stu-id="7ac60-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="7ac60-114">Accès des utilisateurs externes, c'est-à-dire que les serveurs Edge permettent autoriser tout ceci se produire.</span><span class="sxs-lookup"><span data-stu-id="7ac60-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="7ac60-115">Les utilisateurs internes pourront bénéficient des services qui sont hébergés par votre Skype pour le déploiement de Business Server 2015 suivantes :</span><span class="sxs-lookup"><span data-stu-id="7ac60-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server 2015 deployment:</span></span>
  
- <span data-ttu-id="7ac60-116">Messagerie instantanée et présence pour les communications : les utilisateurs externes autorisés peuvent participer à des conversations de messagerie instantanée et des conférences.</span><span class="sxs-lookup"><span data-stu-id="7ac60-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="7ac60-117">Ils peuvent obtenir des informations de présence pour les autres utilisateurs (qui obtiennent également leurs informations de présence).</span><span class="sxs-lookup"><span data-stu-id="7ac60-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="7ac60-118">Vous ne pourrez pas effectuer des conférences si vous utilisez un fournisseur de messagerie instantanée publique, qui est la communication d’égal à égal strictement.</span><span class="sxs-lookup"><span data-stu-id="7ac60-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="7ac60-119">Il s’agit strictement de communications P2P, mais les protocoles SIP (Session Initiation Protocol) et XMPP sont tous deux pris en charge.</span><span class="sxs-lookup"><span data-stu-id="7ac60-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="7ac60-120">Audio/vidéo (A / V) conférence : les utilisateurs externes autorisés peuvent participer à votre Skype pour les conférences audio et vidéo Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7ac60-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server 2015 audio and video conferences.</span></span>
    
- <span data-ttu-id="7ac60-121">Conférence Web : vos utilisateurs externes autorisés peuvent participer à votre Skype pour des conférences.</span><span class="sxs-lookup"><span data-stu-id="7ac60-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="7ac60-122">Vous pouvez également activer la participation des utilisateurs distants, les utilisateurs fédérés et les utilisateurs anonymes si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="7ac60-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="7ac60-123">Les utilisateurs de messagerie instantanée publique ne peut pas participer à des conférences.</span><span class="sxs-lookup"><span data-stu-id="7ac60-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="7ac60-124">Il existe également des options pour permettre à ces utilisateurs participer à des applications et le partage du bureau et même agir en tant que les organisateurs de réunion ou sur présentateurs.</span><span class="sxs-lookup"><span data-stu-id="7ac60-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="7ac60-125">Accès aux appareils mobiles est pris en charge, comme c’est Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="7ac60-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="7ac60-126">Vous pouvez inviter des utilisateurs externes à participer à ces réunions si vous le souhaitez, ou encore des utilisateurs anonymes, si vous êtes disposé à leur donner les autorisations nécessaires.</span><span class="sxs-lookup"><span data-stu-id="7ac60-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="7ac60-p108">Si ce scénario peut convenir à votre organisation, la planification d’un environnement Edge facilitera considérablement son déploiement. Pour en savoir plus, consultez les rubriques ci-après.</span><span class="sxs-lookup"><span data-stu-id="7ac60-p108">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it. For further reading, we have the topics listed below.</span></span>
  
## <a name="planning-topics"></a><span data-ttu-id="7ac60-129">Rubriques concernant la planification :</span><span class="sxs-lookup"><span data-stu-id="7ac60-129">Planning topics:</span></span>

<span data-ttu-id="7ac60-130">Les articles consacrés à la planification sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="7ac60-130">The planning articles are:</span></span>
  
- [<span data-ttu-id="7ac60-131">Edge Server requise dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7ac60-131">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="7ac60-132">Edge Server exigences dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7ac60-132">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="7ac60-133">Scénarios de serveur Edge dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7ac60-133">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

