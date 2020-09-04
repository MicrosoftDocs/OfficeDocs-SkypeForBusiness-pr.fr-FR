---
title: Affecter une stratégie de routage des communications vocales
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Résumé : consultez cette rubrique pour savoir comment attribuer une stratégie de voix pour les utilisateurs utilisant un système téléphonique avec une connectivité RTC locale.'
ms.openlocfilehash: 5d56d4f88e30b605276296b35cd9f316348342ca
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359320"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="2713c-103">Affecter une stratégie de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="2713c-103">Assign a Voice Routing Policy</span></span>
 
> [!Important]
> <span data-ttu-id="2713c-104">Skype entreprise Online sera supprimé le 31 juillet 2021 après lequel le service ne sera plus accessible.</span><span class="sxs-lookup"><span data-stu-id="2713c-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="2713c-105">De plus, la connectivité PSTN entre votre environnement local, que ce soit via Skype entreprise Server ou Cloud Connector Edition et Skype entreprise Online, ne sera plus prise en charge.</span><span class="sxs-lookup"><span data-stu-id="2713c-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="2713c-106">Découvrez comment connecter votre réseau téléphonique local à teams à l’aide du [routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="2713c-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="2713c-107">**Résumé :** Lisez cette rubrique pour découvrir comment attribuer une stratégie de voix pour les utilisateurs utilisant un système téléphonique avec une connectivité RTC locale.</span><span class="sxs-lookup"><span data-stu-id="2713c-107">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="2713c-108">Une fois qu’un utilisateur est sur Skype entreprise Online et qu’il utilise un système téléphonique avec une connectivité RTC locale, deux stratégies de voix s’appliquent à celles-ci.</span><span class="sxs-lookup"><span data-stu-id="2713c-108">Once a user is on Skype for Business Online and using Phone System with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="2713c-109">L’une est une stratégie de routage des communications vocales locale que vous allez attribuer sur site.</span><span class="sxs-lookup"><span data-stu-id="2713c-109">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="2713c-110">Cette stratégie peut être globale ou spécifique à l’utilisateur et définit les enregistrements d’utilisation PSTN associés à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2713c-110">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="2713c-111">Cette rubrique explique comment affecter cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="2713c-111">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="2713c-112">Les autres stratégies de voix définissent les fonctionnalités d’appel disponibles pour l’utilisateur ; Cette stratégie de voix est définie par Microsoft et est identique pour tous les systèmes téléphoniques avec des utilisateurs de connectivité RTC locale.</span><span class="sxs-lookup"><span data-stu-id="2713c-112">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="2713c-113">Il est automatiquement attribué aux utilisateurs du système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="2713c-113">It is automatically assigned to Phone System users.</span></span>
  
||<span data-ttu-id="2713c-114">**Utilisateur sur site**</span><span class="sxs-lookup"><span data-stu-id="2713c-114">**On-premises user**</span></span>|<span data-ttu-id="2713c-115">**Système téléphonique avec utilisateur de connectivité RTC sur site**</span><span class="sxs-lookup"><span data-stu-id="2713c-115">**Phone System with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2713c-116">Fonctionnalités d’appel définies dans</span><span class="sxs-lookup"><span data-stu-id="2713c-116">Calling features defined in</span></span>  <br/> |<span data-ttu-id="2713c-117">Stratégie de la voix</span><span class="sxs-lookup"><span data-stu-id="2713c-117">Voice policy</span></span>  <br/> |<span data-ttu-id="2713c-118">Stratégie de voix prédéfinie, attribuée automatiquement lorsque l’utilisateur dispose d’une licence pour le système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="2713c-118">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System.</span></span>  <br/> |
|<span data-ttu-id="2713c-119">Enregistrements d’utilisation RTC associés à</span><span class="sxs-lookup"><span data-stu-id="2713c-119">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="2713c-120">Stratégie de la voix</span><span class="sxs-lookup"><span data-stu-id="2713c-120">Voice policy</span></span>  <br/> |<span data-ttu-id="2713c-121">Stratégie de routage des communications vocales, affectée pendant que l’utilisateur est toujours hébergé en local.</span><span class="sxs-lookup"><span data-stu-id="2713c-121">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="2713c-122">Vous effectuez les étapes suivantes à l’aide de votre déploiement local, tandis que l’utilisateur est toujours hébergé dans le déploiement local.</span><span class="sxs-lookup"><span data-stu-id="2713c-122">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="2713c-123">Utilisation d’une stratégie de routage des communications vocales globale</span><span class="sxs-lookup"><span data-stu-id="2713c-123">Using a global voice routing policy</span></span>

<span data-ttu-id="2713c-124">Avant d’utiliser une stratégie globale de routage des communications vocales pour votre système téléphonique avec des utilisateurs de connectivité RTC sur site, vous devez ajouter des enregistrements d’utilisation PSTN à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="2713c-124">Before using a global voice routing policy for your Phone System with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="2713c-125">Pour affecter des enregistrements d’utilisation PSTN à la stratégie globale de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="2713c-125">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="2713c-126">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="2713c-126">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2713c-127">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise 2015**, puis sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2713c-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="2713c-128">Ajoutez les enregistrements d’utilisation RTC à la stratégie :</span><span class="sxs-lookup"><span data-stu-id="2713c-128">Add the PSTN usage records to the policy:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="2713c-129">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="2713c-129">For example:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="2713c-130">Création d’une stratégie de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="2713c-130">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="2713c-131">Pour créer une stratégie de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="2713c-131">To create a new voice routing policy</span></span>

1. <span data-ttu-id="2713c-132">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="2713c-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2713c-133">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise 2015**, puis sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2713c-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="2713c-134">Créez une stratégie de routage des communications vocales :</span><span class="sxs-lookup"><span data-stu-id="2713c-134">Create a new voice routing policy:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="2713c-135">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="2713c-135">For example:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="2713c-136">Cet exemple crée une stratégie de routage des communications vocales appelée HybridVoice, qui a deux utilisations RTC associées.</span><span class="sxs-lookup"><span data-stu-id="2713c-136">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="2713c-137">Affectation d’une stratégie de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="2713c-137">Assigning a voice routing policy</span></span>

<span data-ttu-id="2713c-138">Quelle que soit l’utilisation de la stratégie globale de routage des communications vocales ou de l’utilisateur, procédez comme suit pour affecter la stratégie à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2713c-138">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="2713c-139">Pour affecter la stratégie de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="2713c-139">To assign the voice routing policy</span></span>

1. <span data-ttu-id="2713c-140">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="2713c-140">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2713c-141">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise 2015**, puis sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2713c-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="2713c-142">Affecter une stratégie de voix existante à un utilisateur :</span><span class="sxs-lookup"><span data-stu-id="2713c-142">Assign an existing voice policy to a user:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="2713c-143">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="2713c-143">For example:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="2713c-144">Dans cet exemple, l’utilisateur portant le nom d’affichage Bob Kelly est affecté à la stratégie de voix précédemment créée avec le nom HybridVoice.</span><span class="sxs-lookup"><span data-stu-id="2713c-144">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="2713c-145">Pour plus d’informations sur les stratégies de routage des communications vocales, voir [Create or Modify a Voice Policy and configure PSTN usage Records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)et [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="2713c-145">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  

