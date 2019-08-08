---
title: Vérification de la coexistence du pool pilote avec le pool hérité
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Processus de vérification de la coexistence du pool pilote avec le pool hérité.
ms.openlocfilehash: e71160a2a20d4a80979e3c3c4875c19db181f2da
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243749"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="b415e-103">Vérification de la coexistence du pool pilote avec le pool hérité</span><span class="sxs-lookup"><span data-stu-id="b415e-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="b415e-104">**Dans cet article**</span><span class="sxs-lookup"><span data-stu-id="b415e-104">**In this article**</span></span>
  
[<span data-ttu-id="b415e-105">Vérifiez que les services 2019 de Skype entreprise Server ont démarré</span><span class="sxs-lookup"><span data-stu-id="b415e-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="b415e-106">Ouverture du panneau de configuration Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="b415e-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="b415e-107">Ne pas essayer d’ouvrir la topologie dans le générateur de topologie hérité</span><span class="sxs-lookup"><span data-stu-id="b415e-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="b415e-108">Après avoir déployé le pool de pilotes, vous devez vérifier la coexistence des deux pools en utilisant les outils d’administration pour afficher les informations sur le pool.</span><span class="sxs-lookup"><span data-stu-id="b415e-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="b415e-109">Pour les pools 2019 de Skype entreprise Server et les versions antérieures, vous devez utiliser les outils du panneau de configuration et du générateur de topologie de Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b415e-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="b415e-110">Vérifiez que les services 2019 de Skype entreprise Server ont démarré</span><span class="sxs-lookup"><span data-stu-id="b415e-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="b415e-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="b415e-111"></span></span>

1. <span data-ttu-id="b415e-112">À partir du serveur frontal Skype entreprise Server 2019, accédez à l’applet d’administration Tools\Services.</span><span class="sxs-lookup"><span data-stu-id="b415e-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="b415e-113">Vérifiez que les services suivants s’exécutent sur le serveur frontal:</span><span class="sxs-lookup"><span data-stu-id="b415e-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="b415e-114">Agent du service de journalisation centralisée</span><span class="sxs-lookup"><span data-stu-id="b415e-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="b415e-115">Partage d’application</span><span class="sxs-lookup"><span data-stu-id="b415e-115">Application Sharing</span></span>
    - <span data-ttu-id="b415e-116">Service de test audio</span><span class="sxs-lookup"><span data-stu-id="b415e-116">Audio Test Service</span></span>
    - <span data-ttu-id="b415e-117">Audioconférence ou visioconférence</span><span class="sxs-lookup"><span data-stu-id="b415e-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="b415e-118">parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="b415e-118">Call Park</span></span>
    - <span data-ttu-id="b415e-119">Annonce de conférence</span><span class="sxs-lookup"><span data-stu-id="b415e-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="b415e-120">Surveillant de conférences</span><span class="sxs-lookup"><span data-stu-id="b415e-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="b415e-121">Frontal</span><span class="sxs-lookup"><span data-stu-id="b415e-121">Front-End</span></span>
    - <span data-ttu-id="b415e-122">Conférences de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="b415e-122">IM Conferencing</span></span>
    - <span data-ttu-id="b415e-123">Serveur(s)</span><span class="sxs-lookup"><span data-stu-id="b415e-123">Mediation</span></span>
    - <span data-ttu-id="b415e-124">Agent réplicateur de réplicas</span><span class="sxs-lookup"><span data-stu-id="b415e-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="b415e-125">Response Group</span><span class="sxs-lookup"><span data-stu-id="b415e-125">Response Group</span></span>
    - <span data-ttu-id="b415e-126">Conférence web</span><span class="sxs-lookup"><span data-stu-id="b415e-126">Web Conferencing</span></span>
    - <span data-ttu-id="b415e-127">Passerelle de traduction XMPP</span><span class="sxs-lookup"><span data-stu-id="b415e-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="b415e-128">Ouverture du panneau de configuration Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="b415e-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="b415e-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="b415e-129"></span></span>

<span data-ttu-id="b415e-130">Sur le serveur frontal de votre déploiement de Skype entreprise Server 2019, ouvrez le panneau de configuration Skype entreprise Server 2019 et sélectionnez le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="b415e-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="b415e-131">Répétez cette procédure pour ouvrir le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b415e-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b415e-132">Dans Skype entreprise Server 2019, vous devez mettre à niveau Silverlight vers Silverlight version 5 avant d’utiliser le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b415e-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="b415e-133">Cette topologie inclut désormais des rôles de serveur anciens et Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b415e-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="b415e-134">Ne pas essayer d’ouvrir la topologie dans le générateur de topologie hérité</span><span class="sxs-lookup"><span data-stu-id="b415e-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="b415e-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="b415e-135"></span></span>

<span data-ttu-id="b415e-136">La topologie ne peut être affichée qu’à l’aide du générateur de topologie 2019 de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b415e-136">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="b415e-137">Le générateur de topologie 2019 de Skype entreprise Server doit être utilisé pour créer des pools pour Skype entreprise Server 2019 et l’installation héritée.</span><span class="sxs-lookup"><span data-stu-id="b415e-137">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

