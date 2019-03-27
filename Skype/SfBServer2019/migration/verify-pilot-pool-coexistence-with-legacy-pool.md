---
title: Vérification de la coexistence du pool pilote avec le pool hérité
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Processus pour vérifier la coexistence du pool pilote avec le pool hérité.
ms.openlocfilehash: ed3809bdde3109bdbd341c42eed0dc1d8cecd11f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875467"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="dc6d0-103">Vérification de la coexistence du pool pilote avec le pool hérité</span><span class="sxs-lookup"><span data-stu-id="dc6d0-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="dc6d0-104">**Dans cet article**</span><span class="sxs-lookup"><span data-stu-id="dc6d0-104">**In this article**</span></span>
  
[<span data-ttu-id="dc6d0-105">Vérifiez que Skype pour Business Server 2019 services ont démarré</span><span class="sxs-lookup"><span data-stu-id="dc6d0-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="dc6d0-106">Ouvrez le Skype pour Business Server 2019 le panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="dc6d0-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="dc6d0-107">Ne pas essayer d’ouvrir la topologie dans le Générateur de topologie hérité</span><span class="sxs-lookup"><span data-stu-id="dc6d0-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="dc6d0-108">Après avoir déployé le pool pilote, vous devez vérifier la coexistence des deux pools en utilisant les outils d’administration pour afficher les informations de pool.</span><span class="sxs-lookup"><span data-stu-id="dc6d0-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="dc6d0-109">Pour Skype pour Business Server 2019 pools et les pools hérités, vous devez utiliser le Skype des outils Business Server 2019 le panneau de configuration et le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="dc6d0-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="dc6d0-110">Vérifiez que Skype pour Business Server 2019 services ont démarré</span><span class="sxs-lookup"><span data-stu-id="dc6d0-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="dc6d0-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="dc6d0-111"></span></span>

1. <span data-ttu-id="dc6d0-112">Skype pour Business Server 2019 serveur frontal, accédez à l’applet outils d’administration.</span><span class="sxs-lookup"><span data-stu-id="dc6d0-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="dc6d0-113">Vérifiez que les services suivants sont en cours d’exécution sur le serveur frontal :</span><span class="sxs-lookup"><span data-stu-id="dc6d0-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="dc6d0-114">Agent du service de journalisation centralisée</span><span class="sxs-lookup"><span data-stu-id="dc6d0-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="dc6d0-115">Partage d’application</span><span class="sxs-lookup"><span data-stu-id="dc6d0-115">Application Sharing</span></span>
    - <span data-ttu-id="dc6d0-116">Service de Test audio</span><span class="sxs-lookup"><span data-stu-id="dc6d0-116">Audio Test Service</span></span>
    - <span data-ttu-id="dc6d0-117">Conférence audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="dc6d0-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="dc6d0-118">parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="dc6d0-118">Call Park</span></span>
    - <span data-ttu-id="dc6d0-119">Annonce de conférence</span><span class="sxs-lookup"><span data-stu-id="dc6d0-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="dc6d0-120">Intendant Conférence</span><span class="sxs-lookup"><span data-stu-id="dc6d0-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="dc6d0-121">Frontal</span><span class="sxs-lookup"><span data-stu-id="dc6d0-121">Front-End</span></span>
    - <span data-ttu-id="dc6d0-122">Conférence par messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="dc6d0-122">IM Conferencing</span></span>
    - <span data-ttu-id="dc6d0-123">Serveur(s)</span><span class="sxs-lookup"><span data-stu-id="dc6d0-123">Mediation</span></span>
    - <span data-ttu-id="dc6d0-124">Agent réplicateur de réplica</span><span class="sxs-lookup"><span data-stu-id="dc6d0-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="dc6d0-125">Response Group</span><span class="sxs-lookup"><span data-stu-id="dc6d0-125">Response Group</span></span>
    - <span data-ttu-id="dc6d0-126">Conférence web</span><span class="sxs-lookup"><span data-stu-id="dc6d0-126">Web Conferencing</span></span>
    - <span data-ttu-id="dc6d0-127">Traduction de la passerelle XMPP</span><span class="sxs-lookup"><span data-stu-id="dc6d0-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="dc6d0-128">Ouvrez le Skype pour Business Server 2019 le panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="dc6d0-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="dc6d0-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="dc6d0-129"></span></span>

<span data-ttu-id="dc6d0-130">Dans le serveur frontal dans votre Skype pour le déploiement de Business Server 2019, ouvrez le Skype pour Business Server 2019 le panneau de configuration, puis sélectionnez le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="dc6d0-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="dc6d0-131">Répétez la procédure pour ouvrir le Skype pour Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="dc6d0-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="dc6d0-132">Sur Skype pour Business Server 2019, vous devez mettre à niveau Silverlight vers Silverlight 5 avant d’utiliser le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="dc6d0-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="dc6d0-133">Cette topologie inclut désormais hérité et Skype pour les rôles de serveur Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="dc6d0-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="dc6d0-134">Ne pas essayer d’ouvrir la topologie dans le Générateur de topologie hérité</span><span class="sxs-lookup"><span data-stu-id="dc6d0-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="dc6d0-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="dc6d0-135"></span></span>

<span data-ttu-id="dc6d0-136">Si vous essayez d’ouvrir la topologie à l’aide du Générateur de topologie hérité, vous rencontrerez l’erreur suivante.</span><span class="sxs-lookup"><span data-stu-id="dc6d0-136">If you attempt to open the topology using the legacy Topology Builder, you will encounter the error below.</span></span> <span data-ttu-id="dc6d0-137">La topologie peut uniquement être affichée à l’aide de Skype pour le Générateur de topologie 2019 Business Server.</span><span class="sxs-lookup"><span data-stu-id="dc6d0-137">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="dc6d0-138">Le Skype pour le Générateur de topologie 2019 Business Server doit être utilisé pour créer des pools pour Skype pour Business Server 2019 et de l’installation héritée.</span><span class="sxs-lookup"><span data-stu-id="dc6d0-138">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

