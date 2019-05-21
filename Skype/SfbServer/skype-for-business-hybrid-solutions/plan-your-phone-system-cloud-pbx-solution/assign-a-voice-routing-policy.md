---
title: Affectation d’une stratégie de routage des communications vocales
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Résumé: cette rubrique vous explique comment affecter une stratégie vocale aux utilisateurs de l’utilisation d’un système téléphonique dans Office 365 avec une connectivité PSTN locale.'
ms.openlocfilehash: 0d310378b77c09b427836f0d9bceb60a14982071
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294431"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="d5887-103">Affectation d’une stratégie de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="d5887-103">Assign a Voice Routing Policy</span></span>
 
<span data-ttu-id="d5887-104">**Résumé:** Pour plus d’informations sur l’affectation d’une stratégie vocale aux utilisateurs de l’utilisation d’un système téléphonique dans Office 365 avec une connectivité PSTN locale, lisez cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="d5887-104">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System in Office 365 with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="d5887-105">Une fois qu’un utilisateur est connecté à Skype entreprise Online et utilise le système téléphonique dans Office 365 avec la connectivité PSTN locale, deux politiques vocales y sont appliquées.</span><span class="sxs-lookup"><span data-stu-id="d5887-105">Once a user is on Skype for Business Online and using Phone System in Office 365 with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="d5887-106">Il s’agit d’une stratégie de routage téléphonique locale que vous allez attribuer en local.</span><span class="sxs-lookup"><span data-stu-id="d5887-106">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="d5887-107">Ce paramètre peut être défini sur le niveau global ou spécifique de l’utilisateur et définit les enregistrements d’utilisation RTC associés à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d5887-107">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="d5887-108">Cette rubrique explique comment affecter cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="d5887-108">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="d5887-109">L’autre stratégie vocale définit les fonctionnalités d’appel qui sont disponibles pour l’utilisateur; Cette politique vocale est définie par Microsoft et est identique pour tous les systèmes téléphoniques dans Office 365 avec les utilisateurs de connectivité RTC sur site.</span><span class="sxs-lookup"><span data-stu-id="d5887-109">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System in Office 365 with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="d5887-110">Ce service est automatiquement attribué au système téléphonique des utilisateurs d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="d5887-110">It is automatically assigned to Phone System in Office 365 users.</span></span>
  
||<span data-ttu-id="d5887-111">**Utilisateur du déploiement local**</span><span class="sxs-lookup"><span data-stu-id="d5887-111">**On-premises user**</span></span>|<span data-ttu-id="d5887-112">**Système téléphonique dans Office 365 avec un utilisateur de connectivité RTC sur site**</span><span class="sxs-lookup"><span data-stu-id="d5887-112">**Phone System in Office 365 with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d5887-113">Fonctionnalités d’appel définies dans</span><span class="sxs-lookup"><span data-stu-id="d5887-113">Calling features defined in</span></span>  <br/> |<span data-ttu-id="d5887-114">Stratégie de voix</span><span class="sxs-lookup"><span data-stu-id="d5887-114">Voice policy</span></span>  <br/> |<span data-ttu-id="d5887-115">Politique vocale prédéfinie, attribuée automatiquement lorsque l’utilisateur est titulaire d’une licence pour un système téléphonique dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="d5887-115">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System in Office 365.</span></span>  <br/> |
|<span data-ttu-id="d5887-116">Enregistrements d’utilisation RTC associés à</span><span class="sxs-lookup"><span data-stu-id="d5887-116">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="d5887-117">Stratégie vocale</span><span class="sxs-lookup"><span data-stu-id="d5887-117">Voice policy</span></span>  <br/> |<span data-ttu-id="d5887-118">Stratégie de routage des communications vocales, affectée alors que l’utilisateur est encore hébergé en local.</span><span class="sxs-lookup"><span data-stu-id="d5887-118">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="d5887-119">Pour effectuer les étapes suivantes à l’aide de votre déploiement local, l’utilisateur est toujours hébergé dans le déploiement local.</span><span class="sxs-lookup"><span data-stu-id="d5887-119">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="d5887-120">Utilisation d’une stratégie globale de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="d5887-120">Using a global voice routing policy</span></span>

<span data-ttu-id="d5887-121">Avant d’utiliser une politique générale de routage de la voix pour votre système téléphonique dans Office 365 avec les utilisateurs de connectivité PSTN locale, vous devez ajouter des enregistrements d’utilisation RTC à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="d5887-121">Before using a global voice routing policy for your Phone System in Office 365 with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="d5887-122">Pour affecter des enregistrements d’utilisation RTC à la stratégie globale de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="d5887-122">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="d5887-123">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="d5887-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d5887-124">Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d5887-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="d5887-125">Ajoutez les enregistrements d’utilisation RTC à la stratégie:</span><span class="sxs-lookup"><span data-stu-id="d5887-125">Add the PSTN usage records to the policy:</span></span>
    
   ```
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="d5887-126">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d5887-126">For example:</span></span>
    
   ```
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="d5887-127">Création d’une stratégie de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="d5887-127">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="d5887-128">Pour créer une stratégie de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="d5887-128">To create a new voice routing policy</span></span>

1. <span data-ttu-id="d5887-129">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="d5887-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d5887-130">Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d5887-130">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="d5887-131">Créez une stratégie de routage des communications vocales :</span><span class="sxs-lookup"><span data-stu-id="d5887-131">Create a new voice routing policy:</span></span>
    
   ```
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="d5887-132">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d5887-132">For example:</span></span>
    
   ```
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="d5887-133">Cet exemple crée une stratégie de routage des communications vocales appelée « HybridVoice », à laquelle sont associées deux utilisations RTC.</span><span class="sxs-lookup"><span data-stu-id="d5887-133">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="d5887-134">Affectation d’une stratégie de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="d5887-134">Assigning a voice routing policy</span></span>

<span data-ttu-id="d5887-135">Que vous utilisiez la stratégie globale de routage des communications vocales ou des stratégies spécifiques aux utilisateurs, procédez comme suit pour affecter cette stratégie à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d5887-135">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="d5887-136">Pour affecter la stratégie de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="d5887-136">To assign the voice routing policy</span></span>

1. <span data-ttu-id="d5887-137">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="d5887-137">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d5887-138">Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d5887-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="d5887-139">Affectez une stratégie de voix existante à un utilisateur :</span><span class="sxs-lookup"><span data-stu-id="d5887-139">Assign an existing voice policy to a user:</span></span>
    
   ```
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="d5887-140">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d5887-140">For example:</span></span>
    
   ```
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="d5887-141">Dans cet exemple, l’utilisateur Bob Kelly est affecté à la stratégie de voix « HybridVoice » créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="d5887-141">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="d5887-142">Pour plus d’informations sur les stratégies de routage de messagerie vocale, consultez [la rubrique créer ou modifier une stratégie vocale et configurer les enregistrements d’utilisation RTC dans Skype entreprise 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [nouveau-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)et [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d5887-142">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  

