---
title: Skype pour Business Server 2015 Stress et l’outil performances
ms.author: heidip
author: microsoftheidi
ms.date: 4/6/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Le Skype pour Business Server 2015 Stress et l’outil performances est utilisé lors de la planification de la capacité et le réglage des performances dans les environnements non-production ou de test.
ms.openlocfilehash: 0a0a5b17a6e45b2e8944e0e0dd4b3840fc62e102
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="95d77-103">Skype pour Business Server 2015 Stress et l’outil performances</span><span class="sxs-lookup"><span data-stu-id="95d77-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="95d77-104">Le Skype pour Business Server 2015 Stress et l’outil performances est utilisé lors de la planification de la capacité et le réglage des performances dans les environnements non-production ou de test.</span><span class="sxs-lookup"><span data-stu-id="95d77-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="95d77-105">Le Skype pour Business Server 2015 Stress et l’outil performances inclut des outils qui simplifient votre planification des capacités pour Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="95d77-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="95d77-106">Le Skype pour Business Server 2015 Stress et l’outil performances vous aidera à :</span><span class="sxs-lookup"><span data-stu-id="95d77-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="95d77-107">Simplifier votre planification pour Skype pour Business Server de matériel</span><span class="sxs-lookup"><span data-stu-id="95d77-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="95d77-108">Améliorent connaissances et meilleures pratiques pour l’optimisation des performances</span><span class="sxs-lookup"><span data-stu-id="95d77-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="95d77-109">Mesurer les performances de votre Skype pour les déploiements de serveur d’entreprise</span><span class="sxs-lookup"><span data-stu-id="95d77-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="95d77-110">Vous utiliserez en général cet outil après que le [Skype pour outil de planification de 2015 Business Server](../../management-tools/planning-tool/planning-tool.md) vous permet de concevoir la topologie et l’affinage de la topologie avec le [Skype pour le calculateur de planification de capacité Business Server 2015](../../management-tools/capacity-planning-calculator.md).</span><span class="sxs-lookup"><span data-stu-id="95d77-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 
  
## <a name="tests"></a><span data-ttu-id="95d77-111">Tests</span><span class="sxs-lookup"><span data-stu-id="95d77-111">Tests</span></span>

<span data-ttu-id="95d77-112">Le Stress et l’outil performances peuvent de simuler ces types de charge de l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="95d77-112">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="95d77-113">Instant Messaging (IM) et présence</span><span class="sxs-lookup"><span data-stu-id="95d77-113">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="95d77-114">Conférence audio</span><span class="sxs-lookup"><span data-stu-id="95d77-114">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="95d77-115">Partage d'application</span><span class="sxs-lookup"><span data-stu-id="95d77-115">Application sharing</span></span>  <br/> |<span data-ttu-id="95d77-116">Voix sur IP (VoIP), y compris le réseau téléphonique public commuté, simulation de (PTSN)</span><span class="sxs-lookup"><span data-stu-id="95d77-116">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="95d77-117">Conférence sur le Client d’accès Web</span><span class="sxs-lookup"><span data-stu-id="95d77-117">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="95d77-118">Surveillance automatique de conférence</span><span class="sxs-lookup"><span data-stu-id="95d77-118">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="95d77-119">Groupes de réponse</span><span class="sxs-lookup"><span data-stu-id="95d77-119">Response Groups</span></span>  <br/> |<span data-ttu-id="95d77-120">Extension des listes de distribution</span><span class="sxs-lookup"><span data-stu-id="95d77-120">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="95d77-121">Téléchargement du carnet d’adresse et de requête de carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="95d77-121">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="95d77-122">Enhanced 911 (E911 Enhanced) appels et profil d’emplacement (plan de numérotation)</span><span class="sxs-lookup"><span data-stu-id="95d77-122">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="95d77-123">MultiView</span><span class="sxs-lookup"><span data-stu-id="95d77-123">MultiView</span></span>  <br/> |<span data-ttu-id="95d77-124">Collaboration de données</span><span class="sxs-lookup"><span data-stu-id="95d77-124">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="95d77-125">Mobilité</span><span class="sxs-lookup"><span data-stu-id="95d77-125">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="95d77-126">Les applications et fichiers inclus avec le Skype pour Business Server 2015 Stress et l’outil performances</span><span class="sxs-lookup"><span data-stu-id="95d77-126">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="95d77-127">Ces applications sont une partie de la Skype pour Business Server Stress et l’outil de Performance :</span><span class="sxs-lookup"><span data-stu-id="95d77-127">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="95d77-128">**Outil**</span><span class="sxs-lookup"><span data-stu-id="95d77-128">**Tool**</span></span>|<span data-ttu-id="95d77-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="95d77-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="95d77-130">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="95d77-130">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="95d77-131">Cet outil est utilisé pour créer des utilisateurs et des contacts.</span><span class="sxs-lookup"><span data-stu-id="95d77-131">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="95d77-132">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="95d77-132">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="95d77-133">Permet de configurer les caractéristiques de la charge utilisateur simulée.</span><span class="sxs-lookup"><span data-stu-id="95d77-133">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="95d77-134">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="95d77-134">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="95d77-135">L’outil qui simule la charge utilisateur.</span><span class="sxs-lookup"><span data-stu-id="95d77-135">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="95d77-136">Default.TMX</span><span class="sxs-lookup"><span data-stu-id="95d77-136">Default.tmx</span></span>  <br/> |<span data-ttu-id="95d77-137">Requise pour utiliser le Skype pour outil de journalisation Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="95d77-137">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="95d77-138">Mise en service des exemples de scripts</span><span class="sxs-lookup"><span data-stu-id="95d77-138">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="95d77-139">Permet de configurer la topologie pour l’exécution des tests de charge basés sur des scénarios spécifiques.</span><span class="sxs-lookup"><span data-stu-id="95d77-139">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="95d77-140">Vous devrez probablement les modifier pour qu’elles soient adaptées à votre environnement particulier.</span><span class="sxs-lookup"><span data-stu-id="95d77-140">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="95d77-141">Rubriques de cette section.</span><span class="sxs-lookup"><span data-stu-id="95d77-141">Topics in this section</span></span>

<span data-ttu-id="95d77-142">Si vous avez besoin pour en savoir plus, consultez les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="95d77-142">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="95d77-143">Conditions préalables et le programme d’installation pour le Skype pour Busines Stress et l’outil performances</span><span class="sxs-lookup"><span data-stu-id="95d77-143">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="95d77-144">Scénarios de performances pour le Skype pour Business Server 2015 Stress et l’outil performances</span><span class="sxs-lookup"><span data-stu-id="95d77-144">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="95d77-145">Mise en service de la topologie pour exécuter la charge dans les scénarios de contrainte et de performances</span><span class="sxs-lookup"><span data-stu-id="95d77-145">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="95d77-146">Configuration des stratégies pour le Skype pour Business Server 2015 Stress et l’outil performances</span><span class="sxs-lookup"><span data-stu-id="95d77-146">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="95d77-147">À l’aide de la Skype pour Business Server 2015 Stress et l’outil performances</span><span class="sxs-lookup"><span data-stu-id="95d77-147">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="95d77-148">Forum aux questions concernant la Skype pour Business Server 2015 Stress et l’outil performances</span><span class="sxs-lookup"><span data-stu-id="95d77-148">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

