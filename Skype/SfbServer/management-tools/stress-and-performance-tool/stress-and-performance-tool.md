---
title: Skype pour Business Server 2015 Stress and Performance Tool
ms.author: heidip
author: microsoftheidi
ms.date: 4/6/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Le Skype pour Business Server 2015 Stress and Performance Tool est utilisé lors de la planification de capacité et de réglage des performances dans un environnement hors production ou de test.
ms.openlocfilehash: 9ccd4b851ad64f829a15bd6138764995f789dbf6
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20984462"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="a2d84-103">Skype pour Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="a2d84-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="a2d84-104">Le Skype pour Business Server 2015 Stress and Performance Tool est utilisé lors de la planification de capacité et de réglage des performances dans un environnement hors production ou de test.</span><span class="sxs-lookup"><span data-stu-id="a2d84-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="a2d84-105">Le Skype pour Business Server 2015 Stress and Performance Tool inclut des outils qui simplifient votre planification de capacité pour Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a2d84-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="a2d84-106">Le Skype pour Business Server 2015 Stress and Performance Tool vous aideront à :</span><span class="sxs-lookup"><span data-stu-id="a2d84-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="a2d84-107">Simplifiez votre matériel planification de Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="a2d84-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="a2d84-108">Améliorent la base de connaissances et meilleures pratiques pour l’optimisation des performances</span><span class="sxs-lookup"><span data-stu-id="a2d84-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="a2d84-109">Mesurer les performances de votre Skype pour les déploiements de serveur d’entreprise</span><span class="sxs-lookup"><span data-stu-id="a2d84-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="a2d84-110">Vous utiliserez généralement cet outil après que le [Skype pour l’outil de planification de 2015 Business Server](../../management-tools/planning-tool/planning-tool.md) vous permet de concevoir la topologie et affiner la topologie avec le [Skype pour Business Server 2015 planification des capacités](../../management-tools/capacity-planning-calculator.md).</span><span class="sxs-lookup"><span data-stu-id="a2d84-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="a2d84-111">Cet outil ne système pas mis à jour pour Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a2d84-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="a2d84-112">Tests</span><span class="sxs-lookup"><span data-stu-id="a2d84-112">Tests</span></span>

<span data-ttu-id="a2d84-113">Le Stress and Performance Tool peuvent de simuler ces types de charge utilisateur :</span><span class="sxs-lookup"><span data-stu-id="a2d84-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a2d84-114">Messagerie instantanée et présence</span><span class="sxs-lookup"><span data-stu-id="a2d84-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="a2d84-115">Services d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="a2d84-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="a2d84-116">Partage d'application</span><span class="sxs-lookup"><span data-stu-id="a2d84-116">Application sharing</span></span>  <br/> |<span data-ttu-id="a2d84-117">Voix sur IP (VoIP), y compris le réseau téléphonique commuté simulation (PTSN)</span><span class="sxs-lookup"><span data-stu-id="a2d84-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="a2d84-118">Conférences Web Client Access</span><span class="sxs-lookup"><span data-stu-id="a2d84-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="a2d84-119">Standard automatique de conférence</span><span class="sxs-lookup"><span data-stu-id="a2d84-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="a2d84-120">Groupes de réponses</span><span class="sxs-lookup"><span data-stu-id="a2d84-120">Response Groups</span></span>  <br/> |<span data-ttu-id="a2d84-121">Développement de listes de distribution</span><span class="sxs-lookup"><span data-stu-id="a2d84-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="a2d84-122">Téléchargement du carnet d’adresses et l’interrogation du carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="a2d84-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="a2d84-123">Enhanced 911 (E911) appels et le profil d’emplacement (plan de numérotation)</span><span class="sxs-lookup"><span data-stu-id="a2d84-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="a2d84-124">MultiView</span><span class="sxs-lookup"><span data-stu-id="a2d84-124">MultiView</span></span>  <br/> |<span data-ttu-id="a2d84-125">Collaboration de données</span><span class="sxs-lookup"><span data-stu-id="a2d84-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="a2d84-126">Mobilité</span><span class="sxs-lookup"><span data-stu-id="a2d84-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="a2d84-127">Applications et fichiers inclus dans le Skype pour Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="a2d84-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="a2d84-128">Ces applications font partie de la Skype pour Business Server Stress and Performance Tool :</span><span class="sxs-lookup"><span data-stu-id="a2d84-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="a2d84-129">**Outil**</span><span class="sxs-lookup"><span data-stu-id="a2d84-129">**Tool**</span></span>|<span data-ttu-id="a2d84-130">**Description**</span><span class="sxs-lookup"><span data-stu-id="a2d84-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a2d84-131">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="a2d84-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="a2d84-132">Cet outil est utilisé pour créer des utilisateurs et des contacts.</span><span class="sxs-lookup"><span data-stu-id="a2d84-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="a2d84-133">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="a2d84-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="a2d84-134">Utilisé pour configurer les caractéristiques de la charge utilisateur que vous êtes simulation.</span><span class="sxs-lookup"><span data-stu-id="a2d84-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="a2d84-135">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="a2d84-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="a2d84-136">L’outil qui simule la charge utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a2d84-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="a2d84-137">Default.TMX</span><span class="sxs-lookup"><span data-stu-id="a2d84-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="a2d84-138">Requis pour utiliser le Skype pour l’outil de journalisation Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a2d84-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="a2d84-139">Exemples de scripts de mise en service</span><span class="sxs-lookup"><span data-stu-id="a2d84-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="a2d84-140">Utilisé pour configurer la topologie pour l’exécution des tests de charge basés sur des scénarios spécifiques.</span><span class="sxs-lookup"><span data-stu-id="a2d84-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="a2d84-141">Vous devrez probablement les modifier pour qu’elles soient adaptées à votre environnement.</span><span class="sxs-lookup"><span data-stu-id="a2d84-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="a2d84-142">Rubriques de cette section</span><span class="sxs-lookup"><span data-stu-id="a2d84-142">Topics in this section</span></span>

<span data-ttu-id="a2d84-143">Si vous avez besoin pour en savoir plus, consultez les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="a2d84-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="a2d84-144">Conditions préalables et configuration pour l'outil Stress and Performance de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="a2d84-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="a2d84-145">Scénarios de performances pour le Skype pour Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="a2d84-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="a2d84-146">Mise en service de la topologie pour exécuter la charge dans les scénarios de Stress and Performance</span><span class="sxs-lookup"><span data-stu-id="a2d84-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="a2d84-147">Configuration des stratégies pour le Skype pour Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="a2d84-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="a2d84-148">À l’aide de la Skype pour Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="a2d84-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="a2d84-149">Forum aux questions concernant la Skype pour Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="a2d84-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

