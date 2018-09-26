---
title: Nouveautés de Skype Entreprise Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/10/2018
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Résumé : Ces fonctionnalités sont nouvelles dans Skype pour Business Server 2019.'
ms.openlocfilehash: 7b4e07ab6fbb7bfddcd056c9d6c4cd9d836d9a8e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027325"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="64a58-103">Nouveautés dans Skype pour Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="64a58-103">What's in Skype for Business Server 2019</span></span> 

<span data-ttu-id="64a58-104">**Résumé :** Lisez cette rubrique pour en savoir plus sur les nouvelles fonctionnalités de Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="64a58-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

[!INCLUDE [disclaimer](disclaimer.md)]

<span data-ttu-id="64a58-105">Nouvelles fonctionnalités de Skype pour Business Server 2019 sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="64a58-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="64a58-106">Messagerie vocale dans le nuage</span><span class="sxs-lookup"><span data-stu-id="64a58-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="64a58-107">Connecteur de données d’appel</span><span class="sxs-lookup"><span data-stu-id="64a58-107">Call Data Connector</span></span>
- <span data-ttu-id="64a58-108">Migration côte à côte</span><span class="sxs-lookup"><span data-stu-id="64a58-108">Side-by-side migration</span></span>
- <span data-ttu-id="64a58-109">Migration vers des équipes</span><span class="sxs-lookup"><span data-stu-id="64a58-109">Migration to Teams</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="64a58-110">Les services de messagerie unifiés : messagerie vocale dans le nuage</span><span class="sxs-lookup"><span data-stu-id="64a58-110">Unified messaging services: Cloud Voicemail</span></span> 

<span data-ttu-id="64a58-111">Messagerie unifiée Exchange reste disponible dans Skype pour Business Server 2019 lorsque vous intégrez Skype pour les entreprises 2019 avec Exchange 2013 ou 2016 Exchange.</span><span class="sxs-lookup"><span data-stu-id="64a58-111">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="64a58-112">En raison des modifications apportées à la prise en charge dans Exchange 2019, l’intégration de la messagerie unifiée Exchange est la déduplication emphasised au profit des fonctionnalités de la messagerie vocale dans le nuage et de standard automatique de nuage.</span><span class="sxs-lookup"><span data-stu-id="64a58-112">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasised in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="64a58-113">Messagerie vocale dans le nuage permet à tous vos Skype pour les utilisateurs professionnels 2019 & #x 2014 ; si elles sont hébergés sur site ou en ligne & #x 2014 ; d’avoir accès au même service de messagerie vocale dans le Cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="64a58-113">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="64a58-114">Messagerie vocale dans le nuage offre les avantages suivants pour vos utilisateurs en ligne et sur site :</span><span class="sxs-lookup"><span data-stu-id="64a58-114">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="64a58-115">Accès à la messagerie vocale dans leur boîte aux lettres Exchange à l’aide de la Skype pour les clients professionnels en ligne, équipes ou Outlook</span><span class="sxs-lookup"><span data-stu-id="64a58-115">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span> 
- <span data-ttu-id="64a58-116">Possibilité d’utiliser le portail web afin de gérer leurs options de la messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="64a58-116">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="64a58-117">Pour plus d’informations, voir [service de planification de la messagerie vocale dans le nuage](hybrid/plan-cloud-voicemail.md) et la [planification de Skype pour Business Server et de migration d’Exchange Server](hybrid/plan-um-migration.md) .</span><span class="sxs-lookup"><span data-stu-id="64a58-117">See [Plan Cloud Voicemail service](hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="64a58-118">Surveillance des appels : connecteur de données d’appel</span><span class="sxs-lookup"><span data-stu-id="64a58-118">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="64a58-119">Connecteur de données d’appel simplifie grandement la surveillance de l’appel dans un environnement hybride, car vous n’avez plus besoin d’utiliser différentes sur site et les outils en ligne pour contrôler l’ensemble de vos utilisateurs la qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="64a58-119">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="64a58-120">Si vos utilisateurs sont hébergés sur site ou en ligne, vous pouvez choisir d’afficher la qualité des appels pour votre organisation en ligne.</span><span class="sxs-lookup"><span data-stu-id="64a58-120">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="64a58-121">Avec le connecteur de données d’appel, vous pouvez effectuer les tâches suivantes à l’aide d’un seul ensemble d’outils :</span><span class="sxs-lookup"><span data-stu-id="64a58-121">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="64a58-122">Surveiller votre expérience utilisateur dans Microsoft Teams, Skype pour Business Online et Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="64a58-122">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="64a58-123">Afficher et résoudre les problèmes de votre réseau</span><span class="sxs-lookup"><span data-stu-id="64a58-123">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="64a58-124">Assigner des rôles de support technique et administrateur appeler Analytique, afin que vous donner des travailleurs de support technique pour afficher et résoudre les problèmes de leurs domaines de responsabilité.</span><span class="sxs-lookup"><span data-stu-id="64a58-124">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span> 

<span data-ttu-id="64a58-125">Pour plus d’informations, voir [Planification de connecteur de données d’appel](hybrid/plan-call-data-connector.md) .</span><span class="sxs-lookup"><span data-stu-id="64a58-125">See [Plan Call Data Connector](hybrid/plan-call-data-connector.md) for more information.</span></span>
  


## <a name="installation-and-upgrade-side-by-side-migration"></a><span data-ttu-id="64a58-126">Installation et mise à niveau : migration côte à côte</span><span class="sxs-lookup"><span data-stu-id="64a58-126">Installation and Upgrade: Side-by-side migration</span></span>

<span data-ttu-id="64a58-127">Dans une migration côte à côte, vous déployez un nouveau serveur exécutant Skype pour Business Server 2019 parallèlement à un serveur qui exécute une version précédente (Skype pour Business Server 2015 ou Lync Server 2013) correspondant et opérations transférez vers le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="64a58-127">In a side-by-side migration, you deploy a new server running Skype for Business Server 2019 alongside a corresponding server that is running a previous version (Skype for Business Server 2015 or Lync Server 2013), and then transfer operations to the new server.</span></span> <span data-ttu-id="64a58-128">Si vous devez revenir à la version précédente, vous devez uniquement retransférer les opérations vers les serveurs d’origine.</span><span class="sxs-lookup"><span data-stu-id="64a58-128">If it becomes necessary to roll back to the previous version, you have only to shift operations back to the original servers.</span></span> 

<span data-ttu-id="64a58-129">Pour plus d’informations, voir [Migration to Skype pour Business Server 2019](migration/migration-to-skype-for-business-server-2019.md).</span><span class="sxs-lookup"><span data-stu-id="64a58-129">For complete details, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md).</span></span>

### <a name="see-also"></a><span data-ttu-id="64a58-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="64a58-130">See also</span></span>

[<span data-ttu-id="64a58-131">Ce qui est déconseillé de Skype pour Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="64a58-131">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)