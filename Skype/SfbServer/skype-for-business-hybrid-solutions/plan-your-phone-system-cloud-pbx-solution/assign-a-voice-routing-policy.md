---
title: Affectation d’une stratégie de routage des communications vocales
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Résumé : Lisez cette rubrique pour savoir comment attribuer une stratégie de voix pour les utilisateurs à l’aide du système téléphonique dans Office 365 avec une connectivité PSTN sur site.'
ms.openlocfilehash: fc11fabeb7f6a8bacc0f3a6dd48d6ed24edd3403
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="530b9-103">Affectation d’une stratégie de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="530b9-103">Assign a Voice Routing Policy</span></span>
 
<span data-ttu-id="530b9-104">**Résumé :** Lisez cette rubrique pour savoir comment attribuer une stratégie de voix pour les utilisateurs à l’aide du système téléphonique dans Office 365 avec une connectivité PSTN sur site.</span><span class="sxs-lookup"><span data-stu-id="530b9-104">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System in Office 365 with on-premises PSTN connectivity.</span></span>
  
<span data-ttu-id="530b9-105">Une fois qu’un utilisateur est sur Skype Business en ligne et l’utilisation de système téléphonique dans Office 365 avec une connectivité PSTN sur site, deux stratégies de voix leur seront appliquée.</span><span class="sxs-lookup"><span data-stu-id="530b9-105">Once a user is on Skype for Business Online and using Phone System in Office 365 with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="530b9-106">Une est une stratégie de routage voix locale que vous affecterez localement.</span><span class="sxs-lookup"><span data-stu-id="530b9-106">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="530b9-107">Cette stratégie peut être globale ou spécifique à l’utilisateur et définit les enregistrements d’utilisation PSTN associées à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="530b9-107">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="530b9-108">Cette rubrique explique comment affecter cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="530b9-108">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="530b9-109">L’autre stratégie de voix définit les fonctionnalités d’appel sont disponibles à l’utilisateur. Cette stratégie de voix est définie par Microsoft et est identique pour tous les système téléphonique dans Office 365 avec des utilisateurs de connectivité PSTN sur site.</span><span class="sxs-lookup"><span data-stu-id="530b9-109">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System in Office 365 with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="530b9-110">Il est automatiquement affecté au système téléphonique dans les utilisateurs d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="530b9-110">It is automatically assigned to Phone System in Office 365 users.</span></span>
  
||<span data-ttu-id="530b9-111">**Utilisateur local**</span><span class="sxs-lookup"><span data-stu-id="530b9-111">**On-premises user**</span></span>|<span data-ttu-id="530b9-112">**Système téléphonique dans Office 365 avec l’utilisateur de connectivité PSTN sur site**</span><span class="sxs-lookup"><span data-stu-id="530b9-112">**Phone System in Office 365 with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="530b9-113">Fonctionnalités d’appel définies dans</span><span class="sxs-lookup"><span data-stu-id="530b9-113">Calling features defined in</span></span>  <br/> |<span data-ttu-id="530b9-114">Stratégie vocale</span><span class="sxs-lookup"><span data-stu-id="530b9-114">Voice policy</span></span>  <br/> |<span data-ttu-id="530b9-115">Prédéfinis stratégie de voix, affectée automatiquement lorsque l’utilisateur possède une licence de système téléphonique dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="530b9-115">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System in Office 365.</span></span>  <br/> |
|<span data-ttu-id="530b9-116">Enregistrements d’utilisation RTC associés à</span><span class="sxs-lookup"><span data-stu-id="530b9-116">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="530b9-117">Stratégie vocale</span><span class="sxs-lookup"><span data-stu-id="530b9-117">Voice policy</span></span>  <br/> |<span data-ttu-id="530b9-118">Stratégie de routage des communications vocales, affectée alors que l’utilisateur est encore hébergé en local.</span><span class="sxs-lookup"><span data-stu-id="530b9-118">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="530b9-119">Vous effectuez les étapes suivantes à l’aide de votre déploiement sur site, tandis que l’utilisateur est toujours hébergé dans le déploiement local.</span><span class="sxs-lookup"><span data-stu-id="530b9-119">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="530b9-120">Utilisation d’une stratégie globale de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="530b9-120">Using a global voice routing policy</span></span>

<span data-ttu-id="530b9-121">Avant d’utiliser une stratégie de routage voix globale pour votre système téléphonique dans Office 365 avec des utilisateurs de connectivité PSTN sur site, vous devez ajouter des enregistrements d’utilisation PSTN à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="530b9-121">Before using a global voice routing policy for your Phone System in Office 365 with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="530b9-122">Pour affecter des enregistrements d’utilisation RTC à la stratégie globale de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="530b9-122">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="530b9-123">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="530b9-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="530b9-124">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="530b9-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="530b9-125">Ajouter les enregistrements d’utilisation PSTN à la stratégie :</span><span class="sxs-lookup"><span data-stu-id="530b9-125">Add the PSTN usage records to the policy:</span></span>
    
  ```
  Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 

  ```

    <span data-ttu-id="530b9-126">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="530b9-126">For example:</span></span>
    
  ```
  Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 

  ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="530b9-127">Création d’une stratégie de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="530b9-127">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="530b9-128">Pour créer une stratégie de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="530b9-128">To create a new voice routing policy</span></span>

1. <span data-ttu-id="530b9-129">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="530b9-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="530b9-130">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="530b9-130">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="530b9-131">Créez une stratégie de routage des communications vocales :</span><span class="sxs-lookup"><span data-stu-id="530b9-131">Create a new voice routing policy:</span></span>
    
  ```
  New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
  ```

    <span data-ttu-id="530b9-132">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="530b9-132">For example:</span></span>
    
  ```
  New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
  ```

<span data-ttu-id="530b9-133">Cet exemple crée une stratégie de routage des communications vocales appelée « HybridVoice », à laquelle sont associées deux utilisations RTC.</span><span class="sxs-lookup"><span data-stu-id="530b9-133">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="530b9-134">Affectation d’une stratégie de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="530b9-134">Assigning a voice routing policy</span></span>

<span data-ttu-id="530b9-135">Que vous utilisiez la stratégie globale de routage des communications vocales ou des stratégies spécifiques aux utilisateurs, procédez comme suit pour affecter cette stratégie à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="530b9-135">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="530b9-136">Pour affecter la stratégie de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="530b9-136">To assign the voice routing policy</span></span>

1. <span data-ttu-id="530b9-137">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="530b9-137">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="530b9-138">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="530b9-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="530b9-139">Affectez une stratégie de voix existante à un utilisateur :</span><span class="sxs-lookup"><span data-stu-id="530b9-139">Assign an existing voice policy to a user:</span></span>
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
  ```

    <span data-ttu-id="530b9-140">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="530b9-140">For example:</span></span>
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
  ```

<span data-ttu-id="530b9-141">Dans cet exemple, l’utilisateur Bob Kelly est affecté à la stratégie de voix « HybridVoice » créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="530b9-141">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="530b9-142">Pour plus d’informations sur les stratégies de routage voix, voir [créer ou modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Skype pour Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)et [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="530b9-142">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  

