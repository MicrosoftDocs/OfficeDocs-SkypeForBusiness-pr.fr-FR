---
title: Déployer une apparence de ligne partagée dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: Consultez cette rubrique pour découvrir comment déployer l’apparence de ligne partagée (SLA) dans la mise à jour cumulative de Skype entreprise Server 2015, novembre 2015. Le contrat SLA est une fonctionnalité permettant de gérer plusieurs appels sur un numéro spécifique appelé « numéro partagé ».
ms.openlocfilehash: 6ad7d6fca40975990fdd6f6ed01bbb89c185e9e7
ms.sourcegitcommit: a34a827dfdad05b281e2e5ec5a80fc4e67fc89e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604221"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="4fb70-104">Déployer une apparence de ligne partagée dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="4fb70-104">Deploy Shared Line Appearance in Skype for Business Server 2015</span></span>

<span data-ttu-id="4fb70-105">Consultez cette rubrique pour découvrir comment déployer l’apparence de ligne partagée (SLA) dans la mise à jour cumulative de Skype entreprise Server 2015, novembre 2015.</span><span class="sxs-lookup"><span data-stu-id="4fb70-105">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> <span data-ttu-id="4fb70-106">Le contrat SLA est une fonctionnalité permettant de gérer plusieurs appels sur un numéro spécifique appelé « numéro partagé ».</span><span class="sxs-lookup"><span data-stu-id="4fb70-106">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="4fb70-107">Pour plus d’informations sur cette fonctionnalité, reportez-vous à la rubrique [plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="4fb70-107">For more information about this feature, see [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span></span>

<span data-ttu-id="4fb70-108">L’apparence de ligne partagée (SLA) est une nouvelle fonctionnalité de Skype entreprise Server, mise à jour cumulative de novembre 2015.</span><span class="sxs-lookup"><span data-stu-id="4fb70-108">Shared Line Appearance (SLA) is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> <span data-ttu-id="4fb70-109">Pour activer cette fonctionnalité, vous devez d’abord déployer cette mise à jour cumulative.</span><span class="sxs-lookup"><span data-stu-id="4fb70-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

### <a name="install-shared-line-appearance"></a><span data-ttu-id="4fb70-110">Installation de l’apparence des lignes partagées</span><span class="sxs-lookup"><span data-stu-id="4fb70-110">Install Shared Line Appearance</span></span>

1. <span data-ttu-id="4fb70-111">Après le déploiement de la mise à jour cumulative de Skype entreprise Server, novembre `SkypeServerUpdateInstaller.exe` 2015, exécutez le correctif sur chaque serveur frontal du pool.</span><span class="sxs-lookup"><span data-stu-id="4fb70-111">After Skype for Business Server, November 2015 Cumulative Update is deployed, run the  `SkypeServerUpdateInstaller.exe` patch on each Front End Server in the pool.</span></span>

2. <span data-ttu-id="4fb70-112">Le programme d’installation déploiera la dernière version de l’application SLA, mais l’application n’est pas activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="4fb70-112">The installer will deploy the latest version of the SLA application, however, the application is not enabled by default.</span></span> <span data-ttu-id="4fb70-113">Pour l’activer, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="4fb70-113">It is enabled by following the steps outlined below:</span></span>

    <span data-ttu-id="4fb70-114">a.</span><span class="sxs-lookup"><span data-stu-id="4fb70-114">a.</span></span> <span data-ttu-id="4fb70-115">Inscrivez le contrat SLA en tant qu’application serveur en exécutant la commande suivante pour chaque pool :</span><span class="sxs-lookup"><span data-stu-id="4fb70-115">Register SLA as a server application by running the following command for each pool:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   <span data-ttu-id="4fb70-116">où% FQDN% est le nom de domaine complet du pool.</span><span class="sxs-lookup"><span data-stu-id="4fb70-116">where %FQDN% is the fully qualified domain name of the pool.</span></span>

    <span data-ttu-id="4fb70-117">b.</span><span class="sxs-lookup"><span data-stu-id="4fb70-117">b.</span></span> <span data-ttu-id="4fb70-118">Exécutez la commande suivante pour mettre à jour les rôles RBAC pour les cmdlets SLA :</span><span class="sxs-lookup"><span data-stu-id="4fb70-118">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

    <span data-ttu-id="4fb70-119">c.</span><span class="sxs-lookup"><span data-stu-id="4fb70-119">c.</span></span> <span data-ttu-id="4fb70-120">Redémarrez tous les serveurs frontaux (RTCSRV service) dans tous les pools où le contrat SLA a été installé et activé :</span><span class="sxs-lookup"><span data-stu-id="4fb70-120">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="4fb70-121">Créer un groupe de SLA et y ajouter des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="4fb70-121">Create an SLA group and add users to it</span></span>

1. <span data-ttu-id="4fb70-122">Créez le groupe SLA à l’aide de l’applet de commande [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="4fb70-122">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    <span data-ttu-id="4fb70-123">La cmdlet Set-CsSlaConfiguration marque le compte voix entreprise SLAGroup1 comme entité SLA et le nombre d’SLAGroup1 devient le numéro du groupe SLA.</span><span class="sxs-lookup"><span data-stu-id="4fb70-123">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="4fb70-124">Tous les appels vers SLAGroup1 sonneront dans l’ensemble du groupe SLA.</span><span class="sxs-lookup"><span data-stu-id="4fb70-124">All calls to SLAGroup1 will ring the entire SLA group.</span></span>

    <span data-ttu-id="4fb70-125">L’exemple suivant crée un groupe de SLA pour un utilisateur voix entreprise existant, SLAGroup1, et utilise le numéro attribué à SLAGroup1 comme numéro de la forme de service SLA.</span><span class="sxs-lookup"><span data-stu-id="4fb70-125">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>

    <span data-ttu-id="4fb70-126">La commande définit le nombre maximal d’appels simultanés pour le nouveau groupe de SLA sur 3, et pour les appels au-delà de celui pour écouter un signal occupé :</span><span class="sxs-lookup"><span data-stu-id="4fb70-126">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    <span data-ttu-id="4fb70-127">Vous pouvez utiliser SET-CsSlaConfiguration pour créer un nouveau groupe de SLA ou en modifier un existant.</span><span class="sxs-lookup"><span data-stu-id="4fb70-127">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4fb70-128">Notez que ce que vous spécifiez pour doit être un compte d’utilisateur activé pour `-Identity` voix entreprise existant valide.</span><span class="sxs-lookup"><span data-stu-id="4fb70-128">Note that what you specify for  `-Identity` must be a valid existing Enterprise Voice-enabled user account.</span></span>

2. <span data-ttu-id="4fb70-129">Ajoutez des délégués au groupe à l’aide de la cmdlet [Add-applet cssladelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="4fb70-129">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    <span data-ttu-id="4fb70-130">L’exemple suivant ajoute un utilisateur au groupe SLA.</span><span class="sxs-lookup"><span data-stu-id="4fb70-130">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="4fb70-131">Chaque utilisateur ajouté au groupe doit être un utilisateur compatible voix entreprise valide :</span><span class="sxs-lookup"><span data-stu-id="4fb70-131">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    <span data-ttu-id="4fb70-132">Répétez l’applet de commande pour chaque utilisateur que vous souhaitez ajouter au groupe.</span><span class="sxs-lookup"><span data-stu-id="4fb70-132">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="4fb70-133">Les utilisateurs ne peuvent appartenir qu’à un seul groupe SLA.</span><span class="sxs-lookup"><span data-stu-id="4fb70-133">Users can only belong to a single SLA group.</span></span>

### <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="4fb70-134">Configurer l’option de disponibilité du groupe SLA</span><span class="sxs-lookup"><span data-stu-id="4fb70-134">Configure the SLA group Busy Option</span></span>

- <span data-ttu-id="4fb70-135">Configurez l’option de disponibilité du groupe SLA à l’aide de la cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="4fb70-135">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="4fb70-136">L’exemple suivant définit les appels qui dépassent le nombre maximal d’appels simultanés à transmettre au numéro de téléphone 202-555-1234.</span><span class="sxs-lookup"><span data-stu-id="4fb70-136">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="4fb70-137">La cible peut être un utilisateur de votre organisation au lieu d’un numéro de téléphone ; dans ce cas, la syntaxe de la personne qui reçoit les appels transférés est la même que lorsque vous spécifiez un délégué `sip:<NameofDelegate@domain>`:.</span><span class="sxs-lookup"><span data-stu-id="4fb70-137">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate:  `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="4fb70-138">L’autre paramètre possible pour `BusyOption` est `Voicemail`le suivant :</span><span class="sxs-lookup"><span data-stu-id="4fb70-138">The other possible parameter for  `BusyOption` is `Voicemail`:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="4fb70-139">Configurer l’option d’appel manqué du groupe SLA</span><span class="sxs-lookup"><span data-stu-id="4fb70-139">Configure the SLA group Missed Call Option</span></span>

1. <span data-ttu-id="4fb70-140">Configurez l’option d’appel manqué du groupe SLA à l’aide de la cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="4fb70-140">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. <span data-ttu-id="4fb70-141">L’exemple suivant spécifie que les appels manqués doivent être transférés à l' `sla_forward_number`utilisateur nommé.</span><span class="sxs-lookup"><span data-stu-id="4fb70-141">The following example specifies that missed calls are to be forwarded to the user named  `sla_forward_number`.</span></span> <span data-ttu-id="4fb70-142">Les options valides pour `-MissedCallOption` le paramètre `Forward`sont `BusySignal`, ou `Disconnect`.</span><span class="sxs-lookup"><span data-stu-id="4fb70-142">The valid options for the  `-MissedCallOption` parameter are `Forward`,  `BusySignal`, or  `Disconnect`.</span></span> <span data-ttu-id="4fb70-143">Si vous le `Forward`souhaitez, vous devez également inclure `-MissedCallForwardTarget` le paramètre, avec un utilisateur ou un numéro de téléphone comme cible :</span><span class="sxs-lookup"><span data-stu-id="4fb70-143">If you choose  `Forward`, you must also include the  `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="4fb70-144">Supprimer un délégué d’un groupe</span><span class="sxs-lookup"><span data-stu-id="4fb70-144">Remove a delegate from a group</span></span>

- <span data-ttu-id="4fb70-145">Supprimer un délégué d’un groupe à l’aide de l’applet de commande [Remove-applet cssladelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="4fb70-145">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    <span data-ttu-id="4fb70-146">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4fb70-146">For example:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a><span data-ttu-id="4fb70-147">Supprimer un groupe SLA</span><span class="sxs-lookup"><span data-stu-id="4fb70-147">Delete an SLA group</span></span>

- <span data-ttu-id="4fb70-148">Supprimez un groupe de SLA à l’aide de l’applet de commande [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="4fb70-148">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    <span data-ttu-id="4fb70-149">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4fb70-149">For example:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


