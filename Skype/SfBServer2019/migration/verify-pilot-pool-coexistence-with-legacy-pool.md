---
title: Vérification de la coexistence du pool pilote avec le pool hérité
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Processus de vérification de la coexistence du pool pilote avec le pool hérité.
ms.openlocfilehash: e9fe944c03c88aad2ca2b40f0e995842363e7a85
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751656"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="93731-103">Vérification de la coexistence du pool pilote avec le pool hérité</span><span class="sxs-lookup"><span data-stu-id="93731-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="93731-104">**Contenu de cet article :**</span><span class="sxs-lookup"><span data-stu-id="93731-104">**In this article**</span></span>
  
[<span data-ttu-id="93731-105">Vérifier que les services Skype entreprise Server 2019 ont démarré</span><span class="sxs-lookup"><span data-stu-id="93731-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="93731-106">Ouvrir le panneau de configuration de Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="93731-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="93731-107">N’essayez pas d’ouvrir la topologie dans le générateur de topologies hérité</span><span class="sxs-lookup"><span data-stu-id="93731-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="93731-108">Après avoir déployé le premier pool, vous devez vérifier la coexistence des deux pools à l’aide des outils d’administration pour afficher les informations des pools.</span><span class="sxs-lookup"><span data-stu-id="93731-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="93731-109">Pour les pools hérités et les pools Skype entreprise Server 2019, vous devez utiliser le panneau de configuration de Skype entreprise Server 2019 et les outils du générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="93731-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="93731-110">Vérifier que les services Skype entreprise Server 2019 ont démarré</span><span class="sxs-lookup"><span data-stu-id="93731-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="93731-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="93731-111"><a name="sectionSection0"> </a></span></span>

1. <span data-ttu-id="93731-112">À partir du serveur frontal Skype entreprise Server 2019, accédez à l’applet Administration\services. d’administration.</span><span class="sxs-lookup"><span data-stu-id="93731-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="93731-113">Vérifiez que les services suivants sont exécutés sur le serveur frontal :</span><span class="sxs-lookup"><span data-stu-id="93731-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="93731-114">Agent du service de journalisation centralisée</span><span class="sxs-lookup"><span data-stu-id="93731-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="93731-115">Partage d’application</span><span class="sxs-lookup"><span data-stu-id="93731-115">Application Sharing</span></span>
    - <span data-ttu-id="93731-116">Service de test audio</span><span class="sxs-lookup"><span data-stu-id="93731-116">Audio Test Service</span></span>
    - <span data-ttu-id="93731-117">Conférence audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="93731-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="93731-118">Parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="93731-118">Call Park</span></span>
    - <span data-ttu-id="93731-119">Annonce de conférence</span><span class="sxs-lookup"><span data-stu-id="93731-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="93731-120">Surveillant de conférence</span><span class="sxs-lookup"><span data-stu-id="93731-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="93731-121">Serveur frontal</span><span class="sxs-lookup"><span data-stu-id="93731-121">Front-End</span></span>
    - <span data-ttu-id="93731-122">Conférence par messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="93731-122">IM Conferencing</span></span>
    - <span data-ttu-id="93731-123">Élaboration</span><span class="sxs-lookup"><span data-stu-id="93731-123">Mediation</span></span>
    - <span data-ttu-id="93731-124">Agent réplicateur de réplicas</span><span class="sxs-lookup"><span data-stu-id="93731-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="93731-125">Response Group</span><span class="sxs-lookup"><span data-stu-id="93731-125">Response Group</span></span>
    - <span data-ttu-id="93731-126">Conférence Web</span><span class="sxs-lookup"><span data-stu-id="93731-126">Web Conferencing</span></span>
    - <span data-ttu-id="93731-127">Passerelle de traduction XMPP</span><span class="sxs-lookup"><span data-stu-id="93731-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="93731-128">Ouvrir le panneau de configuration de Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="93731-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="93731-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="93731-129"><a name="sectionSection1"> </a></span></span>

<span data-ttu-id="93731-130">À partir du serveur frontal de votre déploiement de Skype entreprise Server 2019, ouvrez le panneau de configuration de Skype entreprise Server 2019 et sélectionnez le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="93731-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="93731-131">Répétez la procédure pour ouvrir le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="93731-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="93731-132">Sur Skype entreprise Server 2019, vous devez mettre à niveau Silverlight vers Silverlight version 5 avant d’utiliser le panneau de configuration de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="93731-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="93731-133">Cette topologie inclut désormais les rôles serveur hérités et Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="93731-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="93731-134">N’essayez pas d’ouvrir la topologie dans le générateur de topologies hérité</span><span class="sxs-lookup"><span data-stu-id="93731-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="93731-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="93731-135"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="93731-136">La topologie peut uniquement être affichée à l’aide du générateur de topologies Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="93731-136">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="93731-137">Le générateur de topologie Skype entreprise Server 2019 doit être utilisé pour créer des pools pour Skype entreprise Server 2019 et l’installation héritée.</span><span class="sxs-lookup"><span data-stu-id="93731-137">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

