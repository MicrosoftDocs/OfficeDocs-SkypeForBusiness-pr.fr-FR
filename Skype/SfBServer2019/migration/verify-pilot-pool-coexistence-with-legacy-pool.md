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
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="b9d22-103">Vérification de la coexistence du pool pilote avec le pool hérité</span><span class="sxs-lookup"><span data-stu-id="b9d22-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="b9d22-104">**Contenu de cet article :**</span><span class="sxs-lookup"><span data-stu-id="b9d22-104">**In this article**</span></span>
  
[<span data-ttu-id="b9d22-105">Vérifier que les services Skype Entreprise Server 2019 ont démarré</span><span class="sxs-lookup"><span data-stu-id="b9d22-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="b9d22-106">Ouvrir le Panneau de commande Skype Entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="b9d22-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="b9d22-107">N’essayez pas d’ouvrir la topologie dans le Générateur de topologie hérité</span><span class="sxs-lookup"><span data-stu-id="b9d22-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="b9d22-108">Après avoir déployé le premier pool, vous devez vérifier la coexistence des deux pools à l’aide des outils d’administration pour afficher les informations des pools.</span><span class="sxs-lookup"><span data-stu-id="b9d22-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="b9d22-109">Pour les pools Skype Entreprise Server 2019 et les pools hérités, vous devez utiliser le Panneau de contrôle skype entreprise Server 2019 et les outils de générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="b9d22-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="b9d22-110">Vérifier que les services Skype Entreprise Server 2019 ont démarré</span><span class="sxs-lookup"><span data-stu-id="b9d22-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="b9d22-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="b9d22-111"><a name="sectionSection0"> </a></span></span>

1. <span data-ttu-id="b9d22-112">À partir du serveur frontal Skype Entreprise Server 2019, accédez à l’applet Outils d’administration\Services.</span><span class="sxs-lookup"><span data-stu-id="b9d22-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="b9d22-113">Vérifiez que les services suivants sont exécutés sur le serveur frontal :</span><span class="sxs-lookup"><span data-stu-id="b9d22-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="b9d22-114">Agent du service de journalisation centralisée</span><span class="sxs-lookup"><span data-stu-id="b9d22-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="b9d22-115">Partage d’application</span><span class="sxs-lookup"><span data-stu-id="b9d22-115">Application Sharing</span></span>
    - <span data-ttu-id="b9d22-116">Audio Test Service</span><span class="sxs-lookup"><span data-stu-id="b9d22-116">Audio Test Service</span></span>
    - <span data-ttu-id="b9d22-117">Conférence audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="b9d22-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="b9d22-118">Parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="b9d22-118">Call Park</span></span>
    - <span data-ttu-id="b9d22-119">Annonce de conférence</span><span class="sxs-lookup"><span data-stu-id="b9d22-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="b9d22-120">Attendant de conférence</span><span class="sxs-lookup"><span data-stu-id="b9d22-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="b9d22-121">Serveur frontal</span><span class="sxs-lookup"><span data-stu-id="b9d22-121">Front-End</span></span>
    - <span data-ttu-id="b9d22-122">Conférence de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="b9d22-122">IM Conferencing</span></span>
    - <span data-ttu-id="b9d22-123">Médiation</span><span class="sxs-lookup"><span data-stu-id="b9d22-123">Mediation</span></span>
    - <span data-ttu-id="b9d22-124">Agent réplicateur de réplicas</span><span class="sxs-lookup"><span data-stu-id="b9d22-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="b9d22-125">Response Group</span><span class="sxs-lookup"><span data-stu-id="b9d22-125">Response Group</span></span>
    - <span data-ttu-id="b9d22-126">Conférence web</span><span class="sxs-lookup"><span data-stu-id="b9d22-126">Web Conferencing</span></span>
    - <span data-ttu-id="b9d22-127">Passerelle de traduction XMPP</span><span class="sxs-lookup"><span data-stu-id="b9d22-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="b9d22-128">Ouvrir le Panneau de commande Skype Entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="b9d22-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="b9d22-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="b9d22-129"><a name="sectionSection1"> </a></span></span>

<span data-ttu-id="b9d22-130">À partir du serveur frontal de votre déploiement Skype Entreprise Server 2019, ouvrez le Panneau de contrôle Skype Entreprise Server 2019 et sélectionnez le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="b9d22-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="b9d22-131">Répétez la procédure pour ouvrir le pool Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b9d22-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b9d22-132">Sur Skype Entreprise Server 2019, vous devez mettre à niveau Silverlight vers Silverlight version 5 avant d’utiliser le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b9d22-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="b9d22-133">Cette topologie inclut désormais les rôles serveur hérités et Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b9d22-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="b9d22-134">N’essayez pas d’ouvrir la topologie dans le Générateur de topologie hérité</span><span class="sxs-lookup"><span data-stu-id="b9d22-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="b9d22-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="b9d22-135"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="b9d22-136">La topologie peut uniquement être vue à l’aide du Générateur de topologies Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b9d22-136">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="b9d22-137">Le Générateur de topologie Skype Entreprise Server 2019 doit être utilisé pour créer des pools pour Skype Entreprise Server 2019 et l’installation héritée.</span><span class="sxs-lookup"><span data-stu-id="b9d22-137">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

