---
title: Déployer l’appel via le travail dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Résumé : Découvrez comment déployer l’appel via le travail dans Skype Entreprise Server pour tout ou partie de vos utilisateurs.'
ms.openlocfilehash: 41a0ae8462b12cabf735a2501e5b22eac64abe42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825004"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="11ccb-103">Déployer l’appel via le travail dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="11ccb-103">Deploy Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="11ccb-104">**Résumé :** Découvrez comment déployer appel via le travail dans Skype Entreprise Server pour tout ou partie de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="11ccb-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span></span>
  
<span data-ttu-id="11ccb-105">Utilisez ces étapes pour déployer Appel via le travail pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="11ccb-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="11ccb-106">Les considérations de planification sont abordées dans [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span><span class="sxs-lookup"><span data-stu-id="11ccb-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="11ccb-107">Dans les versions précédentes de Lync Server, le contrôle d’appel distant était une fonctionnalité qui permettait aux utilisateurs de contrôler leurs téléphones PBX avec Lync Server.</span><span class="sxs-lookup"><span data-stu-id="11ccb-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="11ccb-108">Dans Skype Entreprise Server, cette fonctionnalité a été remplacée par Appel via le travail.</span><span class="sxs-lookup"><span data-stu-id="11ccb-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="11ccb-109">Conditions préalables pour l’appel via le travail</span><span class="sxs-lookup"><span data-stu-id="11ccb-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="11ccb-110">L’appel via le travail utilise l’API web de communications unifiées (UCWA), qui est automatiquement installée sur tous les serveurs frontux Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="11ccb-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="11ccb-111">Pour activer les utilisateurs pour l’appel via le travail, vous devez également avoir les conditions préalables suivantes en place :</span><span class="sxs-lookup"><span data-stu-id="11ccb-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="11ccb-112">Vous devez avoir déployé un serveur de médiation, soit dans le cadre d’un serveur frontal, soit en tant que rôle autonome.</span><span class="sxs-lookup"><span data-stu-id="11ccb-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="11ccb-113">Vous devez également déployer une passerelle IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="11ccb-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="11ccb-114">Tous les utilisateurs qui seront activés pour l’appel via le travail doivent avoir un SDN (Direct Inward Dialing) sur le système téléphonique PBX.</span><span class="sxs-lookup"><span data-stu-id="11ccb-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="11ccb-115">Vous devez activer tous les utilisateurs de l’appel via le Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="11ccb-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="11ccb-116">Lorsque vous faites cela, vous devez configurer le numéro DID de Skype Entreprise pour chaque utilisateur sur le numéro DID correspondant pour le système téléphonique PBX correspondant.</span><span class="sxs-lookup"><span data-stu-id="11ccb-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="11ccb-117">La **configuration** automatique doit être sélectionnée dans l’option Connexions avancées de leur client Skype Entreprise pour tous les **utilisateurs** qui utiliseront l’appel via le travail.</span><span class="sxs-lookup"><span data-stu-id="11ccb-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="11ccb-118">Cela permet au client de découvrir les URL UCWA.</span><span class="sxs-lookup"><span data-stu-id="11ccb-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="11ccb-119">**La sélection automatique** est la sélection par défaut.</span><span class="sxs-lookup"><span data-stu-id="11ccb-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="11ccb-120">Pour chaque utilisateur Appel via le travail, activez le forwarding d’appel et la sonnerie simultanée.</span><span class="sxs-lookup"><span data-stu-id="11ccb-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="11ccb-121">Pour chaque utilisateur Appel via le travail, assurez-vous que les appels sortants et de conférences sont activés.</span><span class="sxs-lookup"><span data-stu-id="11ccb-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="11ccb-122">Cela permet à ces utilisateurs d’entrer et de sortir des conférences Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="11ccb-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="11ccb-123">Assurez-vous que la délégation, l’appel d’équipe et le groupe Response Group sont désactivés pour chaque utilisateur Appel via le travail.</span><span class="sxs-lookup"><span data-stu-id="11ccb-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="11ccb-124">Déployer l’appel via le bureau</span><span class="sxs-lookup"><span data-stu-id="11ccb-124">Deploy Call Via Work</span></span>

<span data-ttu-id="11ccb-125">Une fois les conditions préalables en place, faites les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="11ccb-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="11ccb-126">Créez un numéro de téléphone global pour votre déploiement, que Skype Entreprise affiche sur l’ID d’appelant PBX des utilisateurs qui effectuent des appels via le réseau téléphonique.</span><span class="sxs-lookup"><span data-stu-id="11ccb-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="11ccb-127">Créer une ou plusieurs stratégies d’appel via le travail</span><span class="sxs-lookup"><span data-stu-id="11ccb-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="11ccb-128">Affecter une stratégie Appel via le travail à chaque utilisateur qui sera activé pour l’appel via le travail</span><span class="sxs-lookup"><span data-stu-id="11ccb-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="11ccb-129">Créer le numéro de téléphone global Appel via le travail</span><span class="sxs-lookup"><span data-stu-id="11ccb-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="11ccb-130">Tapez l’cmdlet suivante</span><span class="sxs-lookup"><span data-stu-id="11ccb-130">Type the following cmdlet</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="11ccb-131">Par exemple, l’cmdlet suivante définit le numéro de téléphone global sur 1-555-123-4567.</span><span class="sxs-lookup"><span data-stu-id="11ccb-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="11ccb-132">Créer une stratégie Appel via le travail</span><span class="sxs-lookup"><span data-stu-id="11ccb-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="11ccb-133">Tapez l’cmdlet suivante</span><span class="sxs-lookup"><span data-stu-id="11ccb-133">Type the following cmdlet</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="11ccb-134">Par exemple, l’cmdlet suivante crée une stratégie Appel via le bureau appelée ContosoUser1CvWP, oblige l’utilisateur à utiliser un numéro de rappel d’administrateur et définit ce numéro de rappel sur 1-555-789-1234.</span><span class="sxs-lookup"><span data-stu-id="11ccb-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="11ccb-135">Affecter une stratégie Appel via le travail à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="11ccb-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="11ccb-136">Tapez l’cmdlet suivante</span><span class="sxs-lookup"><span data-stu-id="11ccb-136">Type the following cmdlet</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="11ccb-137">Par exemple, l’cmdlet suivante affecte la stratégie Appel via le travail « ContosoUser1CvWP » à l’utilisateur nommé **ContosoUser1**.</span><span class="sxs-lookup"><span data-stu-id="11ccb-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="11ccb-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="11ccb-138">See also</span></span>

[<span data-ttu-id="11ccb-139">Planifier l’appel via le travail dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="11ccb-139">Plan for Call Via Work in Skype for Business Server</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

