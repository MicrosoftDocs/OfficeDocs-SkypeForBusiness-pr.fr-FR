---
title: Déploiement du mode partage de lignes dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: Pour découvrir comment déployer le mode partage de lignes dans Skype Entreprise Server 2015, mise à jour cumulative de novembre 2015, reportez-vous à cette rubrique. Le mode partage de lignes est une fonctionnalité permettant de gérer plusieurs appels sur un numéro spécifique appelé « numéro partagé ».
ms.openlocfilehash: e8325cd7bbd6c1777143ac83ad88aae07a3a48a0
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568337"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="19515-104">Déploiement du mode partage de lignes dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="19515-104">Deploy Shared Line Appearance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="19515-p102">Pour découvrir comment déployer le mode partage de lignes dans Skype Entreprise Server 2015, mise à jour cumulative de novembre 2015, reportez-vous à cette rubrique. Le mode partage de lignes est une fonctionnalité permettant de gérer plusieurs appels sur un numéro spécifique appelé « numéro partagé ».</span><span class="sxs-lookup"><span data-stu-id="19515-p102">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update. SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span> 
  
<span data-ttu-id="19515-107">Pour plus d’informations sur cette fonctionnalité, voir [planifier l’apparence de la ligne Shared dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="19515-107">For more information about this feature, see [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span></span>
  
<span data-ttu-id="19515-108">Apparence de ligne partagé (SLA) est une nouvelle fonctionnalité dans Skype pour Business Server, novembre 2015 mise à jour Cumulative.</span><span class="sxs-lookup"><span data-stu-id="19515-108">Shared Line Appearance (SLA) is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> <span data-ttu-id="19515-109">Pour activer cette fonctionnalité, vous devez d’abord avoir déployé cette mise à jour cumulative.</span><span class="sxs-lookup"><span data-stu-id="19515-109">To enable this feature, you must have first deployed this cumulative update.</span></span>
  
### <a name="install-shared-line-appearance"></a><span data-ttu-id="19515-110">Installation du mode partage de lignes</span><span class="sxs-lookup"><span data-stu-id="19515-110">Install Shared Line Appearance</span></span>

1. <span data-ttu-id="19515-111">Une fois Skype pour Business Server, novembre 2015 mise à jour Cumulative est déployé, exécutez la `SkypeServerUpdateInstaller.exe` correctif sur chaque serveur frontal du pool.</span><span class="sxs-lookup"><span data-stu-id="19515-111">After Skype for Business Server, November 2015 Cumulative Update is deployed, run the  `SkypeServerUpdateInstaller.exe` patch on each Front End Server in the pool.</span></span>
    
2. <span data-ttu-id="19515-p104">Le programme d’installation déploiera la version la plus récente de l’application Mode partage de lignes, mais l’application n’est pas activée par défaut. Elle est activée en suivant la procédure décrite ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="19515-p104">The installer will deploy the latest version of the SLA application, however, the application is not enabled by default. It is enabled by following the steps outlined below:</span></span>
    
    <span data-ttu-id="19515-114">a.</span><span class="sxs-lookup"><span data-stu-id="19515-114">a.</span></span> <span data-ttu-id="19515-115">Enregistrez le mode partage de lignes comme application serveur en exécutant la commande ci-dessous pour chaque pool :</span><span class="sxs-lookup"><span data-stu-id="19515-115">Register SLA as a server application by running the following command for each pool:</span></span>
    
   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled                 $true -Priority (Get-CsServerApplication -Identity              'Service:Registrar:%FQDN%/UserServices').Priority 
   ```

   <span data-ttu-id="19515-116">où %FQDN% est le nom de domaine complet du pool.</span><span class="sxs-lookup"><span data-stu-id="19515-116">where %FQDN% is the fully qualified domain name of the pool.</span></span> 
    
    <span data-ttu-id="19515-117">b.</span><span class="sxs-lookup"><span data-stu-id="19515-117">b.</span></span> <span data-ttu-id="19515-118">Exécutez la commande ci-dessous pour mettre à jour les rôles RBAC pour les applets de commande du mode partage de lignes :</span><span class="sxs-lookup"><span data-stu-id="19515-118">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span> 
    
   ```
   Update-CsAdminRole 
   ```

    <span data-ttu-id="19515-119">c.</span><span class="sxs-lookup"><span data-stu-id="19515-119">c.</span></span> <span data-ttu-id="19515-120">Redémarrez tous les serveurs frontaux (service RTCSERV) dans tous les pools où le mode partage de lignes a été installé et activé :</span><span class="sxs-lookup"><span data-stu-id="19515-120">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>
    
  ```
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV   
  ```

### <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="19515-121">Créez un groupe de mode partage de lignes et ajoutez-y des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="19515-121">Create an SLA group and add users to it</span></span>

1. <span data-ttu-id="19515-122">Créer le groupe SLA à l’aide de l’applet de commande [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="19515-122">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>
    
  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="19515-p108">L’applet de commande Set-CsSlaConfiguration marque le compte SLAGroup1 de Voix Entreprise en tant qu’entité de mode partage de lignes, et le numéro de SLAGroup1 devient le numéro du groupe de mode partage de lignes. Tous les appels vers SLAGroup1 sonneront chez l’ensemble du groupe de mode partage de lignes.</span><span class="sxs-lookup"><span data-stu-id="19515-p108">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group. All calls to SLAGroup1 will ring the entire SLA group.</span></span>
    
    <span data-ttu-id="19515-125">L’exemple ci-dessous crée un groupe de mode partage de lignes pour un utilisateur Voix Entreprise existant, SLAGroup1, et utilise le numéro attribué pour SLAGroup1 comme numéro de ligne principale du mode partage de lignes.</span><span class="sxs-lookup"><span data-stu-id="19515-125">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span> 
    
    <span data-ttu-id="19515-126">La commande définit le nombre maximal d’appels simultanés pour le nouveau groupe de mode partage de lignes sur 3. Les appels qui dépassent cette limitent entendront une tonalité Occupé :</span><span class="sxs-lookup"><span data-stu-id="19515-126">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>
    
  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
  ```

    <span data-ttu-id="19515-127">Vous pouvez utiliser Set-CsSlaConfiguration pour créer un groupe de mode partage de lignes ou modifier un groupe existant.</span><span class="sxs-lookup"><span data-stu-id="19515-127">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="19515-128">Notez que ce que vous spécifiez pour `-Identity` doit être un compte d’utilisateur activés pour Enterprise Voice existant valide.</span><span class="sxs-lookup"><span data-stu-id="19515-128">Note that what you specify for  `-Identity` must be a valid existing Enterprise Voice-enabled user account.</span></span>
  
2. <span data-ttu-id="19515-129">Ajoutez les délégués au groupe à l’aide de l’applet de commande [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="19515-129">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet:</span></span>
    
  ```
  Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
  ```

    <span data-ttu-id="19515-130">L’exemple ci-dessous permet d’ajouter un utilisateur au groupe de mode partage de lignes.</span><span class="sxs-lookup"><span data-stu-id="19515-130">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="19515-131">Chaque utilisateur ajouté au groupe doit être un utilisateur activé pour Enterprise Voice valid :</span><span class="sxs-lookup"><span data-stu-id="19515-131">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>
    
  ```
  Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
  ```

    <span data-ttu-id="19515-p110">Répétez l’applet de commande pour chaque utilisateur que vous voulez ajouter au groupe. Les utilisateurs peuvent seulement appartenir à un seul groupe de mode de partage de lignes.</span><span class="sxs-lookup"><span data-stu-id="19515-p110">Repeat the cmdlet for each user you want to add to the group. Users can only belong to a single SLA group.</span></span>
    
### <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="19515-134">Configuration de l’option Occupé du groupe de mode partage de lignes</span><span class="sxs-lookup"><span data-stu-id="19515-134">Configure the SLA group Busy Option</span></span>

- <span data-ttu-id="19515-135">Configurer le SLA de groupe Option occupé (e) à l’aide de l’applet de commande [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="19515-135">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>
    
  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="19515-136">L’exemple suivant définit les appels qui dépassent le nombre maximal d’appels simultanés d’être transférés vers la 202-555-1234 numéro téléphonique.</span><span class="sxs-lookup"><span data-stu-id="19515-136">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="19515-137">La cible peut être un utilisateur de votre organisation au lieu d’un numéro de téléphone ; Dans ce cas, la syntaxe de la personne qui doit recevoir le transfert des appels est la même que lorsque vous spécifiez un délégué : `sip:<NameofDelegate@domain>`.</span><span class="sxs-lookup"><span data-stu-id="19515-137">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate:  `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="19515-138">L’autre paramètre possible pour `BusyOption` est `Voicemail`:</span><span class="sxs-lookup"><span data-stu-id="19515-138">The other possible parameter for  `BusyOption` is `Voicemail`:</span></span>
    
  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234]
  ```

### <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="19515-139">Configuration de l’option Appel manqué du groupe de mode partage de lignes</span><span class="sxs-lookup"><span data-stu-id="19515-139">Configure the SLA group Missed Call Option</span></span>

1. <span data-ttu-id="19515-140">Configurer le groupe SLA Option d’appel manqué à l’aide de l’applet de commande [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="19515-140">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>
    
  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
  ```

2. <span data-ttu-id="19515-141">L’exemple suivant spécifie que les appels manqués doivent être transférés à l’utilisateur nommé `sla_forward_number`.</span><span class="sxs-lookup"><span data-stu-id="19515-141">The following example specifies that missed calls are to be forwarded to the user named  `sla_forward_number`.</span></span> <span data-ttu-id="19515-142">Les options valides pour le `-MissedCallOption` paramètre sont `Forward`, `BusySignal`, ou `Disconnect`.</span><span class="sxs-lookup"><span data-stu-id="19515-142">The valid options for the  `-MissedCallOption` parameter are `Forward`,  `BusySignal`, or  `Disconnect`.</span></span> <span data-ttu-id="19515-143">Si vous choisissez `Forward`, vous devez également inclure la `-MissedCallForwardTarget` paramètre, avec un utilisateur ou numéro de téléphone comme cible :</span><span class="sxs-lookup"><span data-stu-id="19515-143">If you choose  `Forward`, you must also include the  `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>
    
  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
  ```

### <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="19515-144">Suppression d’un délégué d’un groupe</span><span class="sxs-lookup"><span data-stu-id="19515-144">Remove a delegate from a group</span></span>

- <span data-ttu-id="19515-145">Supprimer un délégué d’un groupe à l’aide de l’applet de commande [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="19515-145">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet:</span></span>
    
  ```
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    <span data-ttu-id="19515-146">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="19515-146">For example:</span></span>
    
  ```
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a><span data-ttu-id="19515-147">Suppression d’un groupe de mode partage de lignes</span><span class="sxs-lookup"><span data-stu-id="19515-147">Delete an SLA group</span></span>

- <span data-ttu-id="19515-148">Supprimer un groupe de contrat à l’aide de l’applet de commande [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="19515-148">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>
    
  ```
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    <span data-ttu-id="19515-149">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="19515-149">For example:</span></span> 
    
  ```
  Remove-CsSlaConfiguration -Identity SLAGroup1 
  ```


