---
title: 'Lync Server 2013 : déploiement de l’apparence des lignes partagées'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Shared Line Appearance
ms:assetid: 6666dfef-9ecf-4834-af6a-2d5da227dfa3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712152(v=OCS.15)
ms:contentKeyID: 72522137
ms.date: 06/13/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1523a48b5d9056b1cca532a7edb1c826af841b8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="92b60-102">Déployer une apparence de ligne partagée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92b60-102">Deploy Shared Line Appearance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92b60-103">_**Dernière modification de la rubrique :** 2016-06-13_</span><span class="sxs-lookup"><span data-stu-id="92b60-103">_**Topic Last Modified:** 2016-06-13_</span></span>

<span data-ttu-id="92b60-104">Consultez cette rubrique pour découvrir comment déployer l’apparence de ligne partagée (SLA) dans Lync Server 2013, mise à jour cumulative avril 2016.</span><span class="sxs-lookup"><span data-stu-id="92b60-104">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="92b60-105">Le contrat SLA est une fonctionnalité permettant de gérer plusieurs appels sur un numéro spécifique appelé « numéro partagé ».</span><span class="sxs-lookup"><span data-stu-id="92b60-105">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="92b60-106">Pour plus d’informations sur cette fonctionnalité, reportez-vous à la rubrique [plan for Shared Line Appearance in Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="92b60-106">For more information about this feature, see [Plan for Shared Line Appearance in Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).</span></span>

<span data-ttu-id="92b60-107">L’apparence de ligne partagée (SLA) est une nouvelle fonctionnalité de Lync Server 2013, mise à jour cumulative avril 2016.</span><span class="sxs-lookup"><span data-stu-id="92b60-107">Shared Line Appearance (SLA) is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="92b60-108">Pour activer cette fonctionnalité, vous devez d’abord déployer cette mise à jour cumulative.</span><span class="sxs-lookup"><span data-stu-id="92b60-108">To enable this feature, you must have first deployed this cumulative update.</span></span>

<div>

## <a name="install-shared-line-appearance"></a><span data-ttu-id="92b60-109">Installation de l’apparence des lignes partagées</span><span class="sxs-lookup"><span data-stu-id="92b60-109">Install Shared Line Appearance</span></span>

1.  <span data-ttu-id="92b60-110">Une fois que Lync Server 2013, mise à jour cumulative avril 2016 est déployé, l’application SLA n’est pas activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="92b60-110">After Lync Server 2013, Cumulative Update April 2016 is deployed, the SLA application is not enabled by default.</span></span> <span data-ttu-id="92b60-111">Pour activer l’application, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="92b60-111">To enable the application, follow the steps below:</span></span>
    
    1.  <span data-ttu-id="92b60-112">Inscrivez le contrat SLA en tant qu’application serveur en exécutant la commande suivante pour chaque pool :</span><span class="sxs-lookup"><span data-stu-id="92b60-112">Register SLA as a server application by running the following command for each pool:</span></span>
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        <span data-ttu-id="92b60-113">où% FQDN% est le nom de domaine complet du pool.</span><span class="sxs-lookup"><span data-stu-id="92b60-113">where %FQDN% is the fully qualified domain name of the pool.</span></span>
    
    2.  <span data-ttu-id="92b60-114">Exécutez la commande suivante pour mettre à jour les rôles RBAC pour les cmdlets SLA :</span><span class="sxs-lookup"><span data-stu-id="92b60-114">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>
        ```powershell
        Update-CsAdminRole 
        ```
    3.  <span data-ttu-id="92b60-115">Redémarrez tous les serveurs frontaux (RTCSRV service) dans tous les pools où le contrat SLA a été installé et activé :</span><span class="sxs-lookup"><span data-stu-id="92b60-115">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="92b60-116">Créer un groupe de SLA et y ajouter des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="92b60-116">Create an SLA group and add users to it</span></span>

1.  <span data-ttu-id="92b60-117">Créez le groupe SLA à l’aide de l’applet de commande [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :</span><span class="sxs-lookup"><span data-stu-id="92b60-117">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="92b60-118">La cmdlet Set-CsSlaConfiguration marque le compte voix entreprise SLAGroup1 comme entité SLA et le nombre d’SLAGroup1 devient le numéro du groupe SLA.</span><span class="sxs-lookup"><span data-stu-id="92b60-118">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="92b60-119">Tous les appels vers SLAGroup1 sonneront dans l’ensemble du groupe SLA.</span><span class="sxs-lookup"><span data-stu-id="92b60-119">All calls to SLAGroup1 will ring the entire SLA group.</span></span>
    
    <span data-ttu-id="92b60-120">L’exemple suivant crée un groupe de SLA pour un utilisateur voix entreprise existant, SLAGroup1, et utilise le numéro attribué à SLAGroup1 comme numéro de la forme de service SLA.</span><span class="sxs-lookup"><span data-stu-id="92b60-120">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>
    
    <span data-ttu-id="92b60-121">La commande définit le nombre maximal d’appels simultanés pour le nouveau groupe de SLA sur 3, et pour les appels au-delà de celui pour écouter un signal occupé :</span><span class="sxs-lookup"><span data-stu-id="92b60-121">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    <span data-ttu-id="92b60-122">Vous pouvez utiliser SET-CsSlaConfiguration pour créer un nouveau groupe de SLA ou en modifier un existant.</span><span class="sxs-lookup"><span data-stu-id="92b60-122">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="92b60-123">Notez que ce que vous spécifiez pour doit être un compte d’utilisateur activé pour <CODE>-Identity</CODE> voix entreprise existant valide.</span><span class="sxs-lookup"><span data-stu-id="92b60-123">Note that what you specify for <CODE>-Identity</CODE> must be a valid existing Enterprise Voice-enabled user account.</span></span>

    
    </div>

2.  <span data-ttu-id="92b60-124">Ajoutez des délégués au groupe à l’aide de la cmdlet [Add-applet cssladelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) :</span><span class="sxs-lookup"><span data-stu-id="92b60-124">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) cmdlet:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="92b60-125">L’exemple suivant ajoute un utilisateur au groupe SLA.</span><span class="sxs-lookup"><span data-stu-id="92b60-125">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="92b60-126">Chaque utilisateur ajouté au groupe doit être un utilisateur compatible voix entreprise valide :</span><span class="sxs-lookup"><span data-stu-id="92b60-126">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    <span data-ttu-id="92b60-127">Répétez l’applet de commande pour chaque utilisateur que vous souhaitez ajouter au groupe.</span><span class="sxs-lookup"><span data-stu-id="92b60-127">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="92b60-128">Les utilisateurs ne peuvent appartenir qu’à un seul groupe SLA.</span><span class="sxs-lookup"><span data-stu-id="92b60-128">Users can only belong to a single SLA group.</span></span>

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="92b60-129">Configurer l’option de disponibilité du groupe SLA</span><span class="sxs-lookup"><span data-stu-id="92b60-129">Configure the SLA group Busy Option</span></span>

1.  <span data-ttu-id="92b60-130">Configurez l’option de disponibilité du groupe SLA à l’aide de la cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :</span><span class="sxs-lookup"><span data-stu-id="92b60-130">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="92b60-131">L’exemple suivant définit les appels qui dépassent le nombre maximal d’appels simultanés à transmettre au numéro de téléphone 202-555-1234.</span><span class="sxs-lookup"><span data-stu-id="92b60-131">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="92b60-132">La cible peut être un utilisateur de votre organisation au lieu d’un numéro de téléphone ; dans ce cas, la syntaxe de la personne qui reçoit les appels transférés est la même que lorsque vous spécifiez un délégué `sip:<NameofDelegate@domain>`:.</span><span class="sxs-lookup"><span data-stu-id="92b60-132">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate: `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="92b60-133">L’autre paramètre possible pour `BusyOption` est `Voicemail`le suivant :</span><span class="sxs-lookup"><span data-stu-id="92b60-133">The other possible parameter for `BusyOption` is `Voicemail`:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="92b60-134">Configurer l’option d’appel manqué du groupe SLA</span><span class="sxs-lookup"><span data-stu-id="92b60-134">Configure the SLA group Missed Call Option</span></span>

1.  <span data-ttu-id="92b60-135">Configurez l’option d’appel manqué du groupe SLA à l’aide de la cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :</span><span class="sxs-lookup"><span data-stu-id="92b60-135">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    <span data-ttu-id="92b60-136">L’exemple suivant spécifie que les appels manqués doivent être transférés à l' `sla_forward_number`utilisateur nommé.</span><span class="sxs-lookup"><span data-stu-id="92b60-136">The following example specifies that missed calls are to be forwarded to the user named `sla_forward_number`.</span></span> <span data-ttu-id="92b60-137">Les options valides pour `-MissedCallOption` le paramètre `Forward`sont `BusySignal`, ou `Disconnect`.</span><span class="sxs-lookup"><span data-stu-id="92b60-137">The valid options for the `-MissedCallOption` parameter are `Forward`, `BusySignal`, or `Disconnect`.</span></span> <span data-ttu-id="92b60-138">Si vous le `Forward`souhaitez, vous devez également inclure `-MissedCallForwardTarget` le paramètre, avec un utilisateur ou un numéro de téléphone comme cible :</span><span class="sxs-lookup"><span data-stu-id="92b60-138">If you choose `Forward`, you must also include the `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="92b60-139">Supprimer un délégué d’un groupe</span><span class="sxs-lookup"><span data-stu-id="92b60-139">Remove a delegate from a group</span></span>

1.  <span data-ttu-id="92b60-140">Supprimer un délégué d’un groupe à l’aide de l’applet de commande [Remove-applet cssladelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) :</span><span class="sxs-lookup"><span data-stu-id="92b60-140">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) cmdlet:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="92b60-141">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="92b60-141">For example:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate3@contoso.com
    ```
</div>

<div>

## <a name="delete-an-sla-group"></a><span data-ttu-id="92b60-142">Supprimer un groupe SLA</span><span class="sxs-lookup"><span data-stu-id="92b60-142">Delete an SLA group</span></span>

1.  <span data-ttu-id="92b60-143">Supprimez un groupe de SLA à l’aide de l’applet de commande [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="92b60-143">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>
    
    ```powershell
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    <span data-ttu-id="92b60-144">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="92b60-144">For example:</span></span>
    ```powershell
    Remove-CsSlaConfiguration -Identity SLAGroup1 
    ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

