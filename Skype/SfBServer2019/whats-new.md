---
title: Quelles sont les nouveautés dans Skype pour Business Server 2019 | Fonctionnalités
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Résumé : Ces fonctionnalités sont nouvelles dans Skype pour Business Server 2019.'
ms.openlocfilehash: 044901b134c71c1cae004f9930bedeae0057578d
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2019
ms.locfileid: "29348883"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="f070f-103">Nouveautés dans Skype pour Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="f070f-103">What's in Skype for Business Server 2019</span></span>

<span data-ttu-id="f070f-104">**Résumé :** Lisez cette rubrique pour en savoir plus sur les nouvelles fonctionnalités de Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f070f-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

<span data-ttu-id="f070f-105">Nouvelles fonctionnalités de Skype pour Business Server 2019 sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="f070f-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="f070f-106">Messagerie vocale dans le nuage</span><span class="sxs-lookup"><span data-stu-id="f070f-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="f070f-107">Connecteur de données d’appel</span><span class="sxs-lookup"><span data-stu-id="f070f-107">Call Data Connector</span></span>
- <span data-ttu-id="f070f-108">Migration côte à côte</span><span class="sxs-lookup"><span data-stu-id="f070f-108">Side-by-side migration</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="f070f-109">Les services de messagerie unifiés : messagerie vocale dans le nuage</span><span class="sxs-lookup"><span data-stu-id="f070f-109">Unified messaging services: Cloud Voicemail</span></span>

<span data-ttu-id="f070f-110">Messagerie unifiée Exchange reste disponible dans Skype pour Business Server 2019 lorsque vous intégrez Skype pour les entreprises 2019 avec Exchange 2013 ou 2016 Exchange.</span><span class="sxs-lookup"><span data-stu-id="f070f-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="f070f-111">En raison des modifications apportées à la prise en charge dans Exchange 2019, l’intégration de la messagerie unifiée Exchange est la déduplication emphasised au profit des fonctionnalités de la messagerie vocale dans le nuage et de standard automatique de nuage.</span><span class="sxs-lookup"><span data-stu-id="f070f-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasised in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="f070f-112">Messagerie vocale dans le nuage permet à tous vos Skype pour Business 2019 users& #x 2014 ; si elles sont hébergés sur site ou online& #x 2014 ; pour accéder au même service de messagerie vocale dans le Cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f070f-112">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="f070f-113">Messagerie vocale dans le nuage offre les avantages suivants pour vos utilisateurs en ligne et sur site :</span><span class="sxs-lookup"><span data-stu-id="f070f-113">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="f070f-114">Accès à la messagerie vocale dans leur boîte aux lettres Exchange à l’aide de la Skype pour les clients professionnels en ligne, équipes ou Outlook</span><span class="sxs-lookup"><span data-stu-id="f070f-114">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span>
- <span data-ttu-id="f070f-115">Possibilité d’utiliser le portail web afin de gérer leurs options de la messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="f070f-115">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="f070f-116">Pour plus d’informations, voir [service de planification de la messagerie vocale dans le nuage](hybrid/plan-cloud-voicemail.md) et la [planification de Skype pour Business Server et de migration d’Exchange Server](hybrid/plan-um-migration.md) .</span><span class="sxs-lookup"><span data-stu-id="f070f-116">See [Plan Cloud Voicemail service](hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="f070f-117">Surveillance des appels : connecteur de données d’appel</span><span class="sxs-lookup"><span data-stu-id="f070f-117">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="f070f-118">Connecteur de données d’appel simplifie grandement la surveillance de l’appel dans un environnement hybride, car vous n’avez plus besoin d’utiliser différentes sur site et les outils en ligne pour contrôler l’ensemble de vos utilisateurs la qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="f070f-118">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="f070f-119">Si vos utilisateurs sont hébergés sur site ou en ligne, vous pouvez choisir d’afficher la qualité des appels pour votre organisation en ligne.</span><span class="sxs-lookup"><span data-stu-id="f070f-119">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="f070f-120">Avec le connecteur de données d’appel, vous pouvez effectuer les tâches suivantes à l’aide d’un seul ensemble d’outils :</span><span class="sxs-lookup"><span data-stu-id="f070f-120">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="f070f-121">Surveiller votre expérience utilisateur dans Microsoft Teams, Skype pour Business Online et Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="f070f-121">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="f070f-122">Afficher et résoudre les problèmes de votre réseau</span><span class="sxs-lookup"><span data-stu-id="f070f-122">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="f070f-123">Assigner des rôles de support technique et administrateur appeler Analytique, afin que vous donner des travailleurs de support technique pour afficher et résoudre les problèmes de leurs domaines de responsabilité.</span><span class="sxs-lookup"><span data-stu-id="f070f-123">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="f070f-124">Pour plus d’informations, voir [Planification de connecteur de données d’appel](hybrid/plan-call-data-connector.md) .</span><span class="sxs-lookup"><span data-stu-id="f070f-124">See [Plan Call Data Connector](hybrid/plan-call-data-connector.md) for more information.</span></span>

### <a name="see-also"></a><span data-ttu-id="f070f-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f070f-125">See also</span></span>

[<span data-ttu-id="f070f-126">Ce qui est déconseillé de Skype pour Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="f070f-126">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)