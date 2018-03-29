---
title: Déployer l’appel via le bureau dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 10/31/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Résumé : Apprenez à déployer appeler Via le travail dans Skype pour Business Server 2015, pour tout ou partie de vos utilisateurs.'
ms.openlocfilehash: 325134bd4e24621bbb223ccc47180274256eaca2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-call-via-work-in-skype-for-business-server-2015"></a><span data-ttu-id="7346c-103">Déployer l’appel via le bureau dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="7346c-103">Deploy Call Via Work in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7346c-104">**Résumé :** Découvrez comment déployer appeler Via le travail dans Skype pour Business Server 2015, pour tout ou partie de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7346c-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server 2015 for some or all of your users.</span></span>
  
<span data-ttu-id="7346c-105">Suivez ces étapes pour déployer l’appeler Via le travail de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7346c-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="7346c-106">Considérations relatives à la planification sont décrits dans le [Plan pour appeler Via le travail dans Skype pour Business Server 2015](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span><span class="sxs-lookup"><span data-stu-id="7346c-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server 2015](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="7346c-107">Dans les versions précédentes d’appel à distance de Lync Server contrôle était une fonctionnalité qui a permis aux utilisateurs de contrôler leur téléphone PBX avec Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7346c-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="7346c-108">Dans Skype pour le serveur de l’entreprise, cette fonctionnalité a été remplacée à appeler Via le travail.</span><span class="sxs-lookup"><span data-stu-id="7346c-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="7346c-109">Conditions requises pour un appel Via le travail</span><span class="sxs-lookup"><span data-stu-id="7346c-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="7346c-110">Appeler Via le travail utilise Unified Communications Web API (UCWA), qui est automatiquement installé sur tous les Skype pour Business Server serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="7346c-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="7346c-111">Pour permettre aux utilisateurs d’appeler Via le travail, vous devez également les conditions préalables suivantes en place :</span><span class="sxs-lookup"><span data-stu-id="7346c-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="7346c-112">Vous devez disposer d’un serveur de médiation déployé, dans le cadre d’un serveur frontal ou d’un rôle autonome.</span><span class="sxs-lookup"><span data-stu-id="7346c-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="7346c-113">Vous devez également déployer une passerelle IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="7346c-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="7346c-114">Tous les utilisateurs qui seront activés pour appeler Via le travail doivent avoir un appel vers l’intérieur directe (DID) sur le système téléphonique PBX.</span><span class="sxs-lookup"><span data-stu-id="7346c-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="7346c-115">Vous devez activer tous les utilisateurs d’appeler Via le travail de Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="7346c-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="7346c-116">Lorsque vous effectuez cette opération, vous devez configurer le Skype pour entreprise n’a un numéro pour chaque utilisateur au numéro DID correspondant pour le système téléphonique PBX correspondant.</span><span class="sxs-lookup"><span data-stu-id="7346c-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="7346c-117">Tous les utilisateurs qui utiliseront appeler Via le travail doivent avoir **La Configuration automatique** est sélectionnée dans l’option **Avancée de connexions** dans leur Skype pour client d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="7346c-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="7346c-118">Cela permet au client de découvrir les URL UCWA.</span><span class="sxs-lookup"><span data-stu-id="7346c-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="7346c-119">**Configuration automatique** est sélectionné par défaut.</span><span class="sxs-lookup"><span data-stu-id="7346c-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="7346c-120">Pour chaque utilisateur d’appeler Via le travail, activer le transfert d’appel et les appels simultanés.</span><span class="sxs-lookup"><span data-stu-id="7346c-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="7346c-121">Pour chaque utilisateur d’appeler Via le travail, vérifiez que l’option dans l’accès à la conférence et les conférences à distance sont activées.</span><span class="sxs-lookup"><span data-stu-id="7346c-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="7346c-122">Cela permet à ces utilisateurs d’obtenir d’et vers Skype pour des conférences.</span><span class="sxs-lookup"><span data-stu-id="7346c-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="7346c-123">Assurez-vous que le groupe réponse, appel d’équipe et la délégation sont désactivés pour chaque utilisateur d’appeler Via le travail.</span><span class="sxs-lookup"><span data-stu-id="7346c-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="7346c-124">Déployer l’appel via le bureau</span><span class="sxs-lookup"><span data-stu-id="7346c-124">Deploy Call Via Work</span></span>

<span data-ttu-id="7346c-125">Une fois les conditions préalables remplies, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="7346c-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="7346c-126">Créer un numéro de téléphone de global pour votre déploiement Skype pour entreprise affiche l’ID d’appelant PBX d’utilisateurs qui utilisent des appels de l’appeler Via le travail.</span><span class="sxs-lookup"><span data-stu-id="7346c-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="7346c-127">Créer une ou plusieurs stratégies d’appeler Via le travail</span><span class="sxs-lookup"><span data-stu-id="7346c-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="7346c-128">Affecter une stratégie de l’appeler Via le travail à chaque utilisateur qui est activé pour les appeler Via le travail</span><span class="sxs-lookup"><span data-stu-id="7346c-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="7346c-129">Créez le numéro de téléphone global d’appel via le bureau</span><span class="sxs-lookup"><span data-stu-id="7346c-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="7346c-130">Saisissez l’applet de commande suivant</span><span class="sxs-lookup"><span data-stu-id="7346c-130">Type the following cmdlet</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="7346c-131">Par exemple, l’applet de commande suivant définit le numéro de téléphone global sur 1-555-123-4567.</span><span class="sxs-lookup"><span data-stu-id="7346c-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="7346c-132">Créez une stratégie d’appel via le bureau</span><span class="sxs-lookup"><span data-stu-id="7346c-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="7346c-133">Saisissez l’applet de commande suivant</span><span class="sxs-lookup"><span data-stu-id="7346c-133">Type the following cmdlet</span></span>
    
  ```
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber
    <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

  ```

    <span data-ttu-id="7346c-134">Par exemple, l’applet de commande suivant crée une stratégie d’appeler Via le travail appelée ContosoUser1CvWP, l’utilisateur doit utiliser un numéro de rappel admin et définit ce numéro de rappel à 1-555-789-1234.</span><span class="sxs-lookup"><span data-stu-id="7346c-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="7346c-135">Affecter une stratégie à appeler Via le travail à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="7346c-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="7346c-136">Saisissez l’applet de commande suivant</span><span class="sxs-lookup"><span data-stu-id="7346c-136">Type the following cmdlet</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="7346c-137">Par exemple, l’applet de commande suivante affecte la stratégie de l’appeler Via le travail « ContosoUser1CvWP » à l’utilisateur nommé **ContosoUser1**.</span><span class="sxs-lookup"><span data-stu-id="7346c-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="7346c-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7346c-138">See also</span></span>

#### 

[<span data-ttu-id="7346c-139">Plan pour un appel Via le travail dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7346c-139">Plan for Call Via Work in Skype for Business Server 2015</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

