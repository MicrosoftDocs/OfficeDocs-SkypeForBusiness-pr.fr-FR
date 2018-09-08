---
title: Déployer l’appel via le bureau dans Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Résumé : Découvrez comment déployer des appels via le bureau dans Skype pour Business Server pour tout ou partie de vos utilisateurs.'
ms.openlocfilehash: 7962e256bcb9bc13bec8353f55c2aa08fce1314c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881922"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="fb2d9-103">Déployer l’appel via le bureau dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="fb2d9-103">Deploy Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="fb2d9-104">**Résumé :** Apprenez à déployer des appels via le bureau dans Skype pour Business Server pour tout ou partie de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fb2d9-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span></span>
  
<span data-ttu-id="fb2d9-105">Utilisez ces étapes pour déployer un appel via le bureau pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fb2d9-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="fb2d9-106">Considérations de planification décrits dans [Plan pour un appel via le bureau dans Skype pour Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span><span class="sxs-lookup"><span data-stu-id="fb2d9-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="fb2d9-107">Dans les versions précédentes d’appel distant Lync Server contrôle est une fonctionnalité qui permettait aux utilisateurs de contrôler leurs téléphones PBX avec Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fb2d9-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="fb2d9-108">Dans Skype pour Business Server, cette fonctionnalité a été remplacée par un appel via le bureau.</span><span class="sxs-lookup"><span data-stu-id="fb2d9-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="fb2d9-109">Conditions requises pour l’appel via le bureau</span><span class="sxs-lookup"><span data-stu-id="fb2d9-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="fb2d9-110">Appel via le bureau utilise Unified Communications Web API (UCWA), qui est installé automatiquement sur tous les Skype pour les serveurs frontaux Business Server.</span><span class="sxs-lookup"><span data-stu-id="fb2d9-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="fb2d9-111">Pour permettre aux utilisateurs d’appeler via le bureau, vous devez également les conditions préalables suivantes en place :</span><span class="sxs-lookup"><span data-stu-id="fb2d9-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="fb2d9-112">Vous devez disposer d’un serveur de médiation déployés, dans le cadre d’un serveur frontal ou d’un rôle autonome.</span><span class="sxs-lookup"><span data-stu-id="fb2d9-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="fb2d9-113">Vous devez également déployer une passerelle IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="fb2d9-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="fb2d9-114">Tous les utilisateurs autorisés pour un appel via le bureau doivent avoir un Direct Inward Dialing (DID) sur le système téléphonique PBX.</span><span class="sxs-lookup"><span data-stu-id="fb2d9-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="fb2d9-115">Vous devez activer tous les utilisateurs d’appeler via le bureau pour Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="fb2d9-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="fb2d9-116">Lorsque vous effectuez cette opération, vous devez configurer le Skype pour numéro d’entreprise n’a pour chaque utilisateur au numéro DID correspondant pour le système téléphonique PBX correspondant.</span><span class="sxs-lookup"><span data-stu-id="fb2d9-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="fb2d9-117">Tous les utilisateurs qui utiliseront des appels via le bureau doivent avoir **La Configuration automatique** sélectionné dans l’option **Connexions avancées** dans leur Skype pour client d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="fb2d9-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="fb2d9-118">Cela permet au client découvrir les URL UCWA.</span><span class="sxs-lookup"><span data-stu-id="fb2d9-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="fb2d9-119">**Configuration automatique** est sélectionné par défaut.</span><span class="sxs-lookup"><span data-stu-id="fb2d9-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="fb2d9-120">Pour chaque utilisateur de l’appel via le bureau, activez le transfert d’appel et la sonnerie simultanée.</span><span class="sxs-lookup"><span data-stu-id="fb2d9-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="fb2d9-121">Pour chaque utilisateur de l’appel via le bureau, assurez-vous que l’option conférence rendez-vous conférence entrants et sortants sont activés.</span><span class="sxs-lookup"><span data-stu-id="fb2d9-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="fb2d9-122">Cela permet à ces utilisateurs de se connecter et se déconnecter de Skype pour des conférences.</span><span class="sxs-lookup"><span data-stu-id="fb2d9-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="fb2d9-123">Assurez-vous que la délégation, l’appel d’équipe et groupe de réponse sont désactivés pour chaque utilisateur de l’appel via le bureau.</span><span class="sxs-lookup"><span data-stu-id="fb2d9-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="fb2d9-124">Déployer l’appel via le bureau</span><span class="sxs-lookup"><span data-stu-id="fb2d9-124">Deploy Call Via Work</span></span>

<span data-ttu-id="fb2d9-125">Une fois les conditions préalables remplies, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="fb2d9-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="fb2d9-126">Créer un numéro de téléphone globale pour votre déploiement qui Skype pour les entreprises affiche l’ID d’appelant PBX d’utilisateurs qui utilisent des appels de l’appel via le bureau.</span><span class="sxs-lookup"><span data-stu-id="fb2d9-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="fb2d9-127">Créer une ou plusieurs stratégies d’appel via le bureau</span><span class="sxs-lookup"><span data-stu-id="fb2d9-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="fb2d9-128">Affecter une stratégie de l’appel via le Bureau à chaque utilisateur qui est activé pour les appels vers le bureau</span><span class="sxs-lookup"><span data-stu-id="fb2d9-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="fb2d9-129">Créez le numéro de téléphone global d’appel via le bureau</span><span class="sxs-lookup"><span data-stu-id="fb2d9-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="fb2d9-130">Saisissez l’applet de commande suivant</span><span class="sxs-lookup"><span data-stu-id="fb2d9-130">Type the following cmdlet</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="fb2d9-131">Par exemple, l’applet de commande suivant définit le numéro de téléphone global sur 1-555-123-4567.</span><span class="sxs-lookup"><span data-stu-id="fb2d9-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="fb2d9-132">Créez une stratégie d’appel via le bureau</span><span class="sxs-lookup"><span data-stu-id="fb2d9-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="fb2d9-133">Saisissez l’applet de commande suivant</span><span class="sxs-lookup"><span data-stu-id="fb2d9-133">Type the following cmdlet</span></span>
    
  ```
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="fb2d9-134">Par exemple, l’applet de commande suivante crée une stratégie d’appel via le bureau appelée ContosoUser1CvWP, oblige l’utilisateur à utiliser un numéro de rappel d’administration et définit ce numéro de rappel 1-555-789-1234.</span><span class="sxs-lookup"><span data-stu-id="fb2d9-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="fb2d9-135">Affecter une stratégie de l’appel via le Bureau à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="fb2d9-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="fb2d9-136">Saisissez l’applet de commande suivant</span><span class="sxs-lookup"><span data-stu-id="fb2d9-136">Type the following cmdlet</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="fb2d9-137">Par exemple, l’applet de commande suivante affecte la stratégie d’appel via le bureau « ContosoUser1CvWP » à l’utilisateur nommé **ContosoUser1**.</span><span class="sxs-lookup"><span data-stu-id="fb2d9-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="fb2d9-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fb2d9-138">See also</span></span>

[<span data-ttu-id="fb2d9-139">Plan pour un appel via le bureau dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="fb2d9-139">Plan for Call Via Work in Skype for Business Server</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

