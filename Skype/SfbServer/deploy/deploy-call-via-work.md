---
title: Déploiement d’un appel via le travail dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Résumé : Découvrez comment déployer un appel via le travail dans Skype entreprise Server pour tout ou partie de vos utilisateurs.'
ms.openlocfilehash: 9b77207d6618e4a869ae369697bc8395aba81673
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791082"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="38fd1-103">Déploiement d’un appel via le travail dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="38fd1-103">Deploy Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="38fd1-104">**Résumé :** Découvrez comment déployer un appel via votre travail dans Skype entreprise Server pour tout ou partie de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="38fd1-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span></span>
  
<span data-ttu-id="38fd1-105">Suivez ces étapes pour déployer l’appel via le Bureau pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="38fd1-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="38fd1-106">Les considérations en matière de planification sont décrites dans la rubrique [planifier un appel via le travail dans Skype entreprise Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span><span class="sxs-lookup"><span data-stu-id="38fd1-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="38fd1-107">Dans les versions précédentes du contrôle d’appel distant de Lync Server est une fonctionnalité qui permettait aux utilisateurs de contrôler leurs téléphones PBX avec Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38fd1-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="38fd1-108">Dans Skype entreprise Server, cette fonction a été remplacée par un appel via le travail.</span><span class="sxs-lookup"><span data-stu-id="38fd1-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="38fd1-109">Prérequis pour les appels via le Bureau</span><span class="sxs-lookup"><span data-stu-id="38fd1-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="38fd1-110">L’appel par le biais de l’utilisation utilise Unified Communications Web API (UCWA), qui est automatiquement installé sur tous les serveurs frontaux Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="38fd1-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="38fd1-111">Pour permettre aux utilisateurs d’effectuer des appels par le biais de leur bureau, vous devez également disposer de la configuration requise suivante :</span><span class="sxs-lookup"><span data-stu-id="38fd1-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="38fd1-112">Un serveur de médiation doit être déployé par le biais d’un serveur frontal ou d’un rôle autonome.</span><span class="sxs-lookup"><span data-stu-id="38fd1-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="38fd1-113">Vous devez également déployer une passerelle IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="38fd1-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="38fd1-114">Tous les utilisateurs qui seront activés pour les appels via le professionnel doivent disposer d’une numérotation directe vers l’intérieur du système téléphonique PBX.</span><span class="sxs-lookup"><span data-stu-id="38fd1-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="38fd1-115">Vous devez activer tous les appels via les utilisateurs professionnels pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="38fd1-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="38fd1-116">Lorsque vous procédez ainsi, vous devez configurer le numéro Skype entreprise pour chaque utilisateur sur le numéro de téléphone PBX correspondant au système PBX correspondant.</span><span class="sxs-lookup"><span data-stu-id="38fd1-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="38fd1-117">La **configuration automatique** de tous les utilisateurs qui utiliseront un appel via le Bureau doit être sélectionnée dans l’option de **connexion avancée** du client Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="38fd1-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="38fd1-118">Cela permet au client de découvrir les URL UCWA.</span><span class="sxs-lookup"><span data-stu-id="38fd1-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="38fd1-119">**Configuration automatique** est sélectionné par défaut.</span><span class="sxs-lookup"><span data-stu-id="38fd1-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="38fd1-120">Pour chaque appel via l’utilisateur de votre entreprise, activez le transfert d’appel et la sonnerie simultanée.</span><span class="sxs-lookup"><span data-stu-id="38fd1-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="38fd1-121">Pour chaque appel par le biais de l’utilisateur travaillant, assurez-vous que les appels entrants et les conférences rendez-vous sont activés.</span><span class="sxs-lookup"><span data-stu-id="38fd1-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="38fd1-122">Cela permet aux utilisateurs d’accéder à des conférences Skype entreprise et de les se déconnecter.</span><span class="sxs-lookup"><span data-stu-id="38fd1-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="38fd1-123">Assurez-vous que la délégation, l’appel d’équipe et le groupe de réponse sont désactivés pour chaque appel via l’utilisateur de travail.</span><span class="sxs-lookup"><span data-stu-id="38fd1-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="38fd1-124">Déployer l’appel via le bureau</span><span class="sxs-lookup"><span data-stu-id="38fd1-124">Deploy Call Via Work</span></span>

<span data-ttu-id="38fd1-125">Une fois les conditions préalables remplies, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="38fd1-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="38fd1-126">Créez un numéro de téléphone global pour votre déploiement, que Skype entreprise affiche sur l’IDENTIFIant de l’appelant PBX des utilisateurs effectuant un appel par le biais d’appels professionnels.</span><span class="sxs-lookup"><span data-stu-id="38fd1-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="38fd1-127">Créer un ou plusieurs appels via une stratégie de bureau</span><span class="sxs-lookup"><span data-stu-id="38fd1-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="38fd1-128">Assigner un appel via une stratégie de bureau à chaque utilisateur qui sera activé pour appel via le Bureau</span><span class="sxs-lookup"><span data-stu-id="38fd1-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="38fd1-129">Créez le numéro de téléphone global d’appel via le bureau</span><span class="sxs-lookup"><span data-stu-id="38fd1-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="38fd1-130">Saisissez l’applet de commande suivant</span><span class="sxs-lookup"><span data-stu-id="38fd1-130">Type the following cmdlet</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="38fd1-131">Par exemple, l’applet de commande suivant définit le numéro de téléphone global sur 1-555-123-4567.</span><span class="sxs-lookup"><span data-stu-id="38fd1-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="38fd1-132">Créez une stratégie d’appel via le bureau</span><span class="sxs-lookup"><span data-stu-id="38fd1-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="38fd1-133">Saisissez l’applet de commande suivant</span><span class="sxs-lookup"><span data-stu-id="38fd1-133">Type the following cmdlet</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="38fd1-134">Par exemple, l’applet de commande suivante crée un appel via une stratégie de bureau appelée ContosoUser1CvWP, exige que l’utilisateur utilise un numéro de rappel d’administration et définit ce numéro de rappel sur 1-555-789-1234.</span><span class="sxs-lookup"><span data-stu-id="38fd1-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="38fd1-135">Assigner un appel via une stratégie de bureau à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="38fd1-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="38fd1-136">Saisissez l’applet de commande suivant</span><span class="sxs-lookup"><span data-stu-id="38fd1-136">Type the following cmdlet</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="38fd1-137">Par exemple, l’applet de commande suivante affecte l’appel via la stratégie de bureau « ContosoUser1CvWP » à l’utilisateur nommé **ContosoUser1**.</span><span class="sxs-lookup"><span data-stu-id="38fd1-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="38fd1-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="38fd1-138">See also</span></span>

[<span data-ttu-id="38fd1-139">Planifier un appel via le travail dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="38fd1-139">Plan for Call Via Work in Skype for Business Server</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

