---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: L’outil de stress et de performance de Skype entreprise Server 2015 est utilisé lors de la planification de la capacité et de l’optimisation des performances dans les environnements hors production et de test.
ms.openlocfilehash: d82d5ed33e6dca1303aed9f49150dd6b56fc4e1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299515"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="5fe5c-103">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="5fe5c-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="5fe5c-104">L’outil de stress et de performance de Skype entreprise Server 2015 est utilisé lors de la planification de la capacité et de l’optimisation des performances dans les environnements hors production et de test.</span><span class="sxs-lookup"><span data-stu-id="5fe5c-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="5fe5c-105">L’outil de stress et de performance de Skype entreprise Server 2015 inclut des outils qui simplifient la planification de la capacité de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5fe5c-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="5fe5c-106">L’outil de stress et de performance de Skype entreprise Server 2015 vous aide à effectuer les opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="5fe5c-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="5fe5c-107">Simplification de la planification de votre matériel pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="5fe5c-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="5fe5c-108">Vous offrir des connaissances et des meilleures pratiques en matière d’optimisation des performances</span><span class="sxs-lookup"><span data-stu-id="5fe5c-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="5fe5c-109">Mesurer les performances de vos déploiements Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="5fe5c-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="5fe5c-110">En règle générale, vous devez utiliser cet outil après l’utilisation de l' [outil de planification de Skype entreprise server 2015](../../management-tools/planning-tool/planning-tool.md) pour concevoir la topologie et affiner la topologie avec le [calculateur de planification de capacité de skype entreprise Server 2015](../../management-tools/capacity-planning-calculator.md).</span><span class="sxs-lookup"><span data-stu-id="5fe5c-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="5fe5c-111">Cet outil ne sera pas mis à jour pour Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5fe5c-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="5fe5c-112">Tests</span><span class="sxs-lookup"><span data-stu-id="5fe5c-112">Tests</span></span>

<span data-ttu-id="5fe5c-113">L’outil de stress et de performance peut simuler les types de charge utilisateur suivants:</span><span class="sxs-lookup"><span data-stu-id="5fe5c-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5fe5c-114">Messagerie instantanée et présence</span><span class="sxs-lookup"><span data-stu-id="5fe5c-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="5fe5c-115">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="5fe5c-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="5fe5c-116">Partage d'application</span><span class="sxs-lookup"><span data-stu-id="5fe5c-116">Application sharing</span></span>  <br/> |<span data-ttu-id="5fe5c-117">Voix sur IP (VoIP), y compris la simulation de réseau téléphonique commuté (PTSN)</span><span class="sxs-lookup"><span data-stu-id="5fe5c-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="5fe5c-118">Conférences de clients d’accès Web</span><span class="sxs-lookup"><span data-stu-id="5fe5c-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="5fe5c-119">Standard automatique de conférences</span><span class="sxs-lookup"><span data-stu-id="5fe5c-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="5fe5c-120">Response Groups</span><span class="sxs-lookup"><span data-stu-id="5fe5c-120">Response Groups</span></span>  <br/> |<span data-ttu-id="5fe5c-121">Extension de liste de distribution</span><span class="sxs-lookup"><span data-stu-id="5fe5c-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="5fe5c-122">Requête de téléchargement du carnet d’adresses et du carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="5fe5c-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="5fe5c-123">Le profil d’emplacement et les appels 911 (E911)</span><span class="sxs-lookup"><span data-stu-id="5fe5c-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="5fe5c-124">Multivue</span><span class="sxs-lookup"><span data-stu-id="5fe5c-124">MultiView</span></span>  <br/> |<span data-ttu-id="5fe5c-125">Collaboration sur les données</span><span class="sxs-lookup"><span data-stu-id="5fe5c-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="5fe5c-126">Mobilité</span><span class="sxs-lookup"><span data-stu-id="5fe5c-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="5fe5c-127">Applications et fichiers inclus dans l’outil de stress et de performance de Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5fe5c-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="5fe5c-128">Ces applications font partie intégrante de l’outil de stress et de performance de Skype entreprise Server:</span><span class="sxs-lookup"><span data-stu-id="5fe5c-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="5fe5c-129">**Il**</span><span class="sxs-lookup"><span data-stu-id="5fe5c-129">**Tool**</span></span>|<span data-ttu-id="5fe5c-130">**Description**</span><span class="sxs-lookup"><span data-stu-id="5fe5c-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5fe5c-131">UserProvisioningTool. exe</span><span class="sxs-lookup"><span data-stu-id="5fe5c-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="5fe5c-132">Cet outil permet de créer des utilisateurs et des contacts.</span><span class="sxs-lookup"><span data-stu-id="5fe5c-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="5fe5c-133">UserProfileGenerator. exe</span><span class="sxs-lookup"><span data-stu-id="5fe5c-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="5fe5c-134">Permet de configurer les caractéristiques de la charge utilisateur que vous simulez.</span><span class="sxs-lookup"><span data-stu-id="5fe5c-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="5fe5c-135">LyncPerfTool. exe</span><span class="sxs-lookup"><span data-stu-id="5fe5c-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="5fe5c-136">Outil simulant la charge utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5fe5c-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="5fe5c-137">Default. TMX</span><span class="sxs-lookup"><span data-stu-id="5fe5c-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="5fe5c-138">Requis pour utiliser l’outil de journalisation de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5fe5c-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="5fe5c-139">Exemples de script de mise en service</span><span class="sxs-lookup"><span data-stu-id="5fe5c-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="5fe5c-140">Utilisé pour configurer la topologie pour exécuter des tests de charge, en fonction de scénarios spécifiques.</span><span class="sxs-lookup"><span data-stu-id="5fe5c-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="5fe5c-141">Vous devrez peut-être les modifier pour qu’elles soient pertinentes pour votre environnement particulier.</span><span class="sxs-lookup"><span data-stu-id="5fe5c-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="5fe5c-142">Rubriques de cette section</span><span class="sxs-lookup"><span data-stu-id="5fe5c-142">Topics in this section</span></span>

<span data-ttu-id="5fe5c-143">Pour en savoir plus, consultez les articles suivants:</span><span class="sxs-lookup"><span data-stu-id="5fe5c-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="5fe5c-144">Conditions préalables et configuration pour l'outil Stress and Performance de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="5fe5c-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="5fe5c-145">Scénarios de performances de l’outil de stress et de performances de Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5fe5c-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="5fe5c-146">Approvisionnement de la topologie pour exécuter des scénarios de stress et de performance</span><span class="sxs-lookup"><span data-stu-id="5fe5c-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="5fe5c-147">Configuration des stratégies de l’outil de stress et de performance de Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5fe5c-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="5fe5c-148">Utilisation de l’outil de stress et de performance 2015 de Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="5fe5c-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="5fe5c-149">FAQ sur l’outil de stress et de performances de Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5fe5c-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

