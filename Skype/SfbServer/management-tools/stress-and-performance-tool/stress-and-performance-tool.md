---
title: Outil Stress and Performance de Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: L’outil Stress and Performance de Skype Entreprise Server 2015 est utilisé lors de la planification de la capacité et de l’optimisation des performances dans les environnements de non-production ou de test.
ms.openlocfilehash: 551e4e5f985fc18439a4f277685034e86c7cdfb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814924"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="4fcff-103">Outil Stress and Performance de Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="4fcff-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="4fcff-104">L’outil Stress and Performance de Skype Entreprise Server 2015 est utilisé lors de la planification de la capacité et de l’optimisation des performances dans les environnements de non-production ou de test.</span><span class="sxs-lookup"><span data-stu-id="4fcff-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="4fcff-105">L’outil Stress and Performance de Skype Entreprise Server 2015 inclut des outils qui simplifieront votre planification de la capacité pour Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4fcff-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="4fcff-106">L’outil Stress and Performance de Skype Entreprise Server 2015 vous aidera à :</span><span class="sxs-lookup"><span data-stu-id="4fcff-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="4fcff-107">Simplifier la planification de votre matériel pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="4fcff-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="4fcff-108">Donnez-vous des connaissances et des meilleures pratiques pour l’optimisation des performances</span><span class="sxs-lookup"><span data-stu-id="4fcff-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="4fcff-109">Mesurer les performances de vos déploiements Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="4fcff-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="4fcff-110">En règle générale, vous utilisez cet outil après avoir utilisé l’outil de planification de Skype Entreprise [Server 2015](../../management-tools/planning-tool/planning-tool.md) pour concevoir la topologie et affiner la topologie avec la calculatrice de planification de la capacité de Skype Entreprise [Server 2015.](../../management-tools/capacity-planning-calculator.md)</span><span class="sxs-lookup"><span data-stu-id="4fcff-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="4fcff-111">Cet outil ne sera pas mis à jour pour Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4fcff-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="4fcff-112">Tests</span><span class="sxs-lookup"><span data-stu-id="4fcff-112">Tests</span></span>

<span data-ttu-id="4fcff-113">L’outil Stress and Performance peut simuler ces types de charge utilisateur :</span><span class="sxs-lookup"><span data-stu-id="4fcff-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4fcff-114">Messagerie instantanée et présence</span><span class="sxs-lookup"><span data-stu-id="4fcff-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="4fcff-115">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="4fcff-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="4fcff-116">Partage d'application</span><span class="sxs-lookup"><span data-stu-id="4fcff-116">Application sharing</span></span>  <br/> |<span data-ttu-id="4fcff-117">Voix sur IP (VoIP), y compris la simulation de réseau téléphonique commuté (PTSN)</span><span class="sxs-lookup"><span data-stu-id="4fcff-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="4fcff-118">Conférence client Web Access</span><span class="sxs-lookup"><span data-stu-id="4fcff-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="4fcff-119">Attendant automatique de conférence</span><span class="sxs-lookup"><span data-stu-id="4fcff-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="4fcff-120">Groupes Response Group</span><span class="sxs-lookup"><span data-stu-id="4fcff-120">Response Groups</span></span>  <br/> |<span data-ttu-id="4fcff-121">Développement de listes de distribution</span><span class="sxs-lookup"><span data-stu-id="4fcff-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="4fcff-122">Téléchargement du carnet d’adresses et requête de carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="4fcff-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="4fcff-123">Appels enhanced 911 (E911) et profil d’emplacement (plan de numérotation)</span><span class="sxs-lookup"><span data-stu-id="4fcff-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="4fcff-124">MultiView</span><span class="sxs-lookup"><span data-stu-id="4fcff-124">MultiView</span></span>  <br/> |<span data-ttu-id="4fcff-125">Collaboration de données</span><span class="sxs-lookup"><span data-stu-id="4fcff-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="4fcff-126">Mobilité</span><span class="sxs-lookup"><span data-stu-id="4fcff-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="4fcff-127">Applications et fichiers inclus avec l’outil Stress and Performance de Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="4fcff-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="4fcff-128">Ces applications font partie de l’outil Stress and Performance de Skype Entreprise Server :</span><span class="sxs-lookup"><span data-stu-id="4fcff-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="4fcff-129">**Outil**</span><span class="sxs-lookup"><span data-stu-id="4fcff-129">**Tool**</span></span>|<span data-ttu-id="4fcff-130">**Description**</span><span class="sxs-lookup"><span data-stu-id="4fcff-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4fcff-131">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="4fcff-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="4fcff-132">Cet outil est utilisé pour créer des utilisateurs et des contacts.</span><span class="sxs-lookup"><span data-stu-id="4fcff-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="4fcff-133">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="4fcff-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="4fcff-134">Permet de configurer les caractéristiques de la charge utilisateur que vous simulez.</span><span class="sxs-lookup"><span data-stu-id="4fcff-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="4fcff-135">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="4fcff-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="4fcff-136">Outil qui simule la charge utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4fcff-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="4fcff-137">Default.tmx</span><span class="sxs-lookup"><span data-stu-id="4fcff-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="4fcff-138">Requis pour utiliser l’outil de journalisation de Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4fcff-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="4fcff-139">Exemples de script d’approvisionnement</span><span class="sxs-lookup"><span data-stu-id="4fcff-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="4fcff-140">Permet de configurer la topologie pour l’exécution de tests de charge, en fonction de scénarios spécifiques.</span><span class="sxs-lookup"><span data-stu-id="4fcff-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="4fcff-141">Vous devrez probablement les modifier pour les rendre pertinentes pour votre environnement particulier.</span><span class="sxs-lookup"><span data-stu-id="4fcff-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="4fcff-142">Rubriques de cette section</span><span class="sxs-lookup"><span data-stu-id="4fcff-142">Topics in this section</span></span>

<span data-ttu-id="4fcff-143">Pour en savoir plus, vous devez consulter les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="4fcff-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="4fcff-144">Conditions préalables et configuration de l’outil Stress and Performance de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="4fcff-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="4fcff-145">Scénarios de performances pour l’outil Stress and Performance de Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="4fcff-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="4fcff-146">Mise en service de la topologie pour exécuter la charge dans les scénarios de contrainte et de performances</span><span class="sxs-lookup"><span data-stu-id="4fcff-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="4fcff-147">Configuration des stratégies pour l’outil Stress and Performance de Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="4fcff-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="4fcff-148">Utilisation de l’outil Stress and Performance de Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="4fcff-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="4fcff-149">FAQ sur l’outil Stress and Performance de Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="4fcff-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

