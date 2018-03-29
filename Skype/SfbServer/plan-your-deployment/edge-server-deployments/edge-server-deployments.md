---
title: Planification des déploiements de serveur Edge dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Hybrid
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Résumé : Planifier votre Skype pour environnement d’entreprise serveur 2015 serveur Edge. Cette rubrique présente les concepts de bord et vous permet d’organiser avec nos rubriques plus détaillées.'
ms.openlocfilehash: 828bdc52a6c4fe55294768d69c441b9c996fa9a0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server-2015"></a><span data-ttu-id="4623b-104">Planification des déploiements de serveur Edge dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="4623b-104">Plan for Edge Server deployments in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4623b-p102">**Résumé :** planifiez votre environnement Edge Skype Entreprise Server 2015. Cette rubrique présente les concepts se rapportant aux serveurs Edge et vous permet d’organiser votre environnement à l’aide de rubriques plus détaillées.</span><span class="sxs-lookup"><span data-stu-id="4623b-p102">**Summary:** Plan for your Skype for Business Server 2015 Server Edge environment. This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="4623b-107">Lorsque vous avez un Skype pour environnement Business Server 2015 qui fonctionne bien en interne, l’étape suivante vous est peut-être d’introduire un serveur Edge ou un pool d’arête à l’environnement.</span><span class="sxs-lookup"><span data-stu-id="4623b-107">When you have a Skype for Business Server 2015 environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="4623b-108">Ce rôle est essentiel si vous souhaitez que les services fournis par Skype pour 2015 de serveur Business être utilisé par les personnes qui sont en dehors de votre réseau interne.</span><span class="sxs-lookup"><span data-stu-id="4623b-108">This role would be vital if you want the services provided by Skype for Business Server 2015 to be used by people who are outside your internal network.</span></span> <span data-ttu-id="4623b-109">Il peuvent inclure :</span><span class="sxs-lookup"><span data-stu-id="4623b-109">These can potentially include:</span></span>
  
- <span data-ttu-id="4623b-110">Utilisateurs distants : employés qui travaillent hors site, de manière temporaire ou permanente ;</span><span class="sxs-lookup"><span data-stu-id="4623b-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="4623b-111">Fédérés : Les employés des partenaires.</span><span class="sxs-lookup"><span data-stu-id="4623b-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="4623b-112">Utilisateurs d’appareils mobiles ;</span><span class="sxs-lookup"><span data-stu-id="4623b-112">Mobile Users.</span></span>
    
- <span data-ttu-id="4623b-113">Clients potentiels, partenaires et même utilisateurs anonymes que vous souhaitez inviter à des réunions et à des présentations.</span><span class="sxs-lookup"><span data-stu-id="4623b-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="4623b-114">L’accès des utilisateurs externes, qui est ce que fournissent les serveurs Edge, autoriser tout cela se passe.</span><span class="sxs-lookup"><span data-stu-id="4623b-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="4623b-115">Vos utilisateurs internes pourront bénéficier les services suivants hébergés par votre Skype pour le déploiement de Business Server 2015 :</span><span class="sxs-lookup"><span data-stu-id="4623b-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server 2015 deployment:</span></span>
  
- <span data-ttu-id="4623b-116">Messagerie instantanée et présence pour les communications : les utilisateurs externes autorisés peuvent participer à des conversations de messagerie instantanée et des conférences.</span><span class="sxs-lookup"><span data-stu-id="4623b-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="4623b-117">Ils peuvent obtenir des informations de présence pour les autres utilisateurs (qui obtiennent également leurs informations de présence).</span><span class="sxs-lookup"><span data-stu-id="4623b-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="4623b-118">Il se peut que vous ne pourrez pas faire de conférences à plusieurs participants si vous utilisez un fournisseur de messagerie instantanée publique, ce qui est strictement peer-to-peer communication.</span><span class="sxs-lookup"><span data-stu-id="4623b-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="4623b-119">Il s’agit strictement de communications P2P, mais les protocoles SIP (Session Initiation Protocol) et XMPP sont tous deux pris en charge.</span><span class="sxs-lookup"><span data-stu-id="4623b-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="4623b-120">Audio/vidéo (A / V) conférence : utilisateurs externes autorisés peuvent participer à votre Skype pour les conférences audio et vidéo de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4623b-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server 2015 audio and video conferences.</span></span>
    
- <span data-ttu-id="4623b-121">Conférence Web : vos utilisateurs externes autorisés peuvent participer à votre Skype pour des conférences.</span><span class="sxs-lookup"><span data-stu-id="4623b-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="4623b-122">Vous pouvez également activer la participation des utilisateurs distants, les utilisateurs fédérés et les utilisateurs anonymes si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="4623b-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="4623b-123">Les utilisateurs de messagerie instantanée publiques ne peut pas participer aux conférences.</span><span class="sxs-lookup"><span data-stu-id="4623b-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="4623b-124">Il existe également des options pour permettre à ces utilisateurs participer au partage d’application et postes de travail et même agissent comme les organisateurs de la réunion ou présentateurs.</span><span class="sxs-lookup"><span data-stu-id="4623b-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="4623b-125">Accès aux périphériques mobiles est pris en charge, comme des Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="4623b-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="4623b-126">Vous pouvez inviter des utilisateurs externes à participer à ces réunions si vous le souhaitez, ou encore des utilisateurs anonymes, si vous êtes disposé à leur donner les autorisations nécessaires.</span><span class="sxs-lookup"><span data-stu-id="4623b-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="4623b-p108">Si ce scénario peut convenir à votre organisation, la planification d’un environnement Edge facilitera considérablement son déploiement. Pour en savoir plus, consultez les rubriques ci-après.</span><span class="sxs-lookup"><span data-stu-id="4623b-p108">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it. For further reading, we have the topics listed below.</span></span>
  
## <a name="planning-topics"></a><span data-ttu-id="4623b-129">Rubriques concernant la planification :</span><span class="sxs-lookup"><span data-stu-id="4623b-129">Planning topics:</span></span>

<span data-ttu-id="4623b-130">Les articles consacrés à la planification sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="4623b-130">The planning articles are:</span></span>
  
- [<span data-ttu-id="4623b-131">Edge Server requise dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4623b-131">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="4623b-132">Bord des exigences de l’environnement de serveur dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4623b-132">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="4623b-133">Scénarios de serveurs Edge dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4623b-133">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

