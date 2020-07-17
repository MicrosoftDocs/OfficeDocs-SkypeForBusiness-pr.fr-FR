---
title: Identités, étendues et locataires dans Skype entreprise Online
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3e5217c4214e6e86ca4c1dff62410c247cf7f8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a><span data-ttu-id="4ba84-102">Identités, étendues et locataires dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4ba84-102">Identities, scopes, and tenants in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ba84-103">_**Dernière modification de la rubrique :** 2015-03-09_</span><span class="sxs-lookup"><span data-stu-id="4ba84-103">_**Topic Last Modified:** 2015-03-09_</span></span>

<span data-ttu-id="4ba84-104">La plupart des applets de commande Windows PowerShell utilisées pour gérer Skype entreprise Online nécessitent un très grand nombre de détails sur l’élément que vous tentez de gérer.</span><span class="sxs-lookup"><span data-stu-id="4ba84-104">Many of the Windows PowerShell cmdlets used to manage Skype for Business Online require you to be very specific about the item that you are trying to manage.</span></span> <span data-ttu-id="4ba84-105">Par exemple, lorsque vous exécutez la cmdlet [Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) , vous devez indiquer l’utilisateur que vous tentez de gérer.</span><span class="sxs-lookup"><span data-stu-id="4ba84-105">For example, when you run the [Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) cmdlet, you must indicate which user you are trying to manage.</span></span> <span data-ttu-id="4ba84-106">Cela est logique.</span><span class="sxs-lookup"><span data-stu-id="4ba84-106">This makes sense.</span></span> <span data-ttu-id="4ba84-107">Sauf si vous indiquez spécifiquement à l’applet de commande le compte d’utilisateur à gérer, l’applet de commande **Set-CsUserAcp** n’a aucune idée des informations de conférence audio de l’utilisateur à modifier.</span><span class="sxs-lookup"><span data-stu-id="4ba84-107">Unless you specifically tell the cmdlet which user account to manage, the **Set-CsUserAcp** cmdlet has no idea which user’s audio conferencing information should be modified.</span></span> <span data-ttu-id="4ba84-108">Pour cette raison, chaque fois que vous exécutez la cmdlet **Set-CsUserAcp** , vous devez inclure le paramètre Identity, suivi de l’identité du compte d’utilisateur à modifier :</span><span class="sxs-lookup"><span data-stu-id="4ba84-108">For this reason, each time you run the **Set-CsUserAcp** cmdlet, you’ll need to include the Identity parameter, followed by the Identity of the user account to be modified:</span></span>

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

<span data-ttu-id="4ba84-109">Si le terme *Identity* fait toujours référence à l’identité d’un compte d’utilisateur, il n’y aurait pas de risque de confusion.</span><span class="sxs-lookup"><span data-stu-id="4ba84-109">If the term *Identity* always referred to the Identity of a user account, there would be little cause for confusion.</span></span> <span data-ttu-id="4ba84-110">Lorsque vous traitez avec des personnes (utilisateurs, contacts, etc.), les identités font référence aux utilisateurs individuels eux-mêmes.</span><span class="sxs-lookup"><span data-stu-id="4ba84-110">When you are dealing with people (users, contacts, and so on), Identities refer to the individual users themselves.</span></span> <span data-ttu-id="4ba84-111">Toutefois, les éléments autres que les comptes d’utilisateur ont également des identités.</span><span class="sxs-lookup"><span data-stu-id="4ba84-111">However, items other than user accounts also have Identities.</span></span> <span data-ttu-id="4ba84-112">Lorsque vous gérez des composants du service Skype entreprise Online (stratégies, paramètres de configuration, etc.), le terme Identity signifie quelque peu légèrement différent.</span><span class="sxs-lookup"><span data-stu-id="4ba84-112">When you are dealing with components of the Skype for Business Online service—policies, configuration settings, and so on—the term Identity means something slightly different.</span></span> <span data-ttu-id="4ba84-113">Par exemple, considérez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4ba84-113">For example, consider this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="4ba84-114">Dans ce cas, l’identité « globale » fait référence à l’étendue des paramètres de configuration de réunion.</span><span class="sxs-lookup"><span data-stu-id="4ba84-114">In this case, the Identity "global" refers to the scope of the meeting configuration settings.</span></span> <span data-ttu-id="4ba84-115">*Scope* est un terme utilisé dans Skype entreprise Online (et dans Lync Server) pour désigner les sphères de gestion.</span><span class="sxs-lookup"><span data-stu-id="4ba84-115">*Scope* is a term used in Skype for Business Online (and in Lync Server) to designate spheres of management.</span></span> <span data-ttu-id="4ba84-116">Par défaut, les stratégies et les paramètres ont toujours une portée globale.</span><span class="sxs-lookup"><span data-stu-id="4ba84-116">By default, policies and settings always have a global scope.</span></span> <span data-ttu-id="4ba84-117">Lorsque vous configurez pour la première fois votre compte Skype entreprise Online, vous disposez, par défaut, d’une collection de stratégies et de paramètres globaux (paramètres de configuration de réunion globale), d’une stratégie d’accès externe globale, d’un plan de numérotation global, etc.</span><span class="sxs-lookup"><span data-stu-id="4ba84-117">When you first set up your Skype for Business Online account you'll have, by default, a collection of global policies and settings—global meeting configuration settings, a global external access policy, a global dial plan, and so on.</span></span>

<span data-ttu-id="4ba84-118">Ces stratégies et paramètres globaux ont été introduits dans Microsoft Lync Server 2010 pour garantir que tous les utilisateurs et tous les composants devaient toujours être gérés.</span><span class="sxs-lookup"><span data-stu-id="4ba84-118">These global policies and settings were introduced in Microsoft Lync Server 2010 to help ensure that all users and all components would always, in some way, be managed.</span></span> <span data-ttu-id="4ba84-119">Cela n’était pas nécessairement vrai dans Microsoft Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="4ba84-119">This was not necessarily true in Microsoft Office Communicator 2007 R2.</span></span> <span data-ttu-id="4ba84-120">En fonction de la manière dont vous avez accédé au système, vous risquez de vous trouver dans un État largement non géré (en général, parce que la stratégie de groupe n’a pas pu être appliquée à votre compte d’utilisateur).</span><span class="sxs-lookup"><span data-stu-id="4ba84-120">Depending on how you accessed the system, you could potentially end up in a largely unmanaged state (typically, because Group Policy could not be applied to your user account).</span></span> <span data-ttu-id="4ba84-121">En revanche, dans Lync Server et dans Skype entreprise Online, rien n’est jamais laissé non géré.</span><span class="sxs-lookup"><span data-stu-id="4ba84-121">In contrast, in Lync Server and in Skype for Business Online, nothing is ever left unmanaged.</span></span> <span data-ttu-id="4ba84-122">En effet, à la place du reste, les stratégies globales et les paramètres seront toujours appliqués.</span><span class="sxs-lookup"><span data-stu-id="4ba84-122">This is because, in lieu of anything else, global policies and settings will always be enforced.</span></span>

<span data-ttu-id="4ba84-123">Qu’est-ce que nous voulons dire par « à la place de quelque chose » ?</span><span class="sxs-lookup"><span data-stu-id="4ba84-123">What do we mean by "in lieu of anything else"?</span></span> <span data-ttu-id="4ba84-124">En ce qui concerne Skype entreprise Online, il est possible de créer des stratégies au niveau de l' *étendue de la balise*ou d’une sphère de gestion.</span><span class="sxs-lookup"><span data-stu-id="4ba84-124">Well, in the case of Skype for Business Online, it’s possible to create policies at the *tag scope*, or sphere of management.</span></span> <span data-ttu-id="4ba84-125">Les stratégies créées au niveau de l’étendue de la balise (également appelée *étendue par utilisateur*) ont priorité sur les stratégies créées au niveau global.</span><span class="sxs-lookup"><span data-stu-id="4ba84-125">Policies created at the tag scope (also known as *the per-user scope*) take priority over policies created at the global scope.</span></span> <span data-ttu-id="4ba84-126">En d’autres termes, une stratégie par utilisateur est toujours prioritaire sur une stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="4ba84-126">In other words, a per-user policy will always take precedence over a global policy.</span></span> <span data-ttu-id="4ba84-127">Par exemple, vous avez peut-être deux stratégies d’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="4ba84-127">For example, you might have two external user access policies.</span></span> <span data-ttu-id="4ba84-128">La stratégie globale interdit aux utilisateurs de communiquer avec des personnes disposant de comptes sur des fournisseurs de messagerie instantanée (IM) publics, tels que Windows Live.</span><span class="sxs-lookup"><span data-stu-id="4ba84-128">The global policy prohibits users from communicating with people who have accounts on public instant messaging (IM) providers, such as Windows Live.</span></span> <span data-ttu-id="4ba84-129">La stratégie par utilisateur, AllowPublicIMCommunication, permet de communiquer avec des fournisseurs de messagerie instantanée publics.</span><span class="sxs-lookup"><span data-stu-id="4ba84-129">The per-user policy, AllowPublicIMCommunication, allows communication with public IM providers.</span></span>

<span data-ttu-id="4ba84-130">Vous pouvez également avoir deux utilisateurs : Ken Myer et Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="4ba84-130">You might also have two users: Ken Myer and Pilar Ackerman.</span></span> <span data-ttu-id="4ba84-131">La stratégie par utilisateur a été affectée à Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="4ba84-131">Ken Myer has been assigned the per-user policy.</span></span> <span data-ttu-id="4ba84-132">Pilar Ackerman n’a pas été affecté à une stratégie par utilisateur ; en d’autres conditions, elle est gérée par la stratégie d’accès externe globale.</span><span class="sxs-lookup"><span data-stu-id="4ba84-132">Pilar Ackerman has not been assigned a per-user policy; that is, she is managed by the global external access policy.</span></span> <span data-ttu-id="4ba84-133">Le tableau suivant indique l’utilisateur (le cas échéant) qui peut communiquer avec des fournisseurs de messagerie instantanée publics :</span><span class="sxs-lookup"><span data-stu-id="4ba84-133">The following table shows which user (if any) can communicate with public IM providers:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4ba84-134">Paramètres de stratégie</span><span class="sxs-lookup"><span data-stu-id="4ba84-134">Policy Settings</span></span></th>
<th><span data-ttu-id="4ba84-135">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="4ba84-135">Ken Myer</span></span></th>
<th><span data-ttu-id="4ba84-136">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="4ba84-136">Pilar Ackerman</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ba84-137">Paramètre de stratégie globale pour les fournisseurs de messagerie instantanée publics</span><span class="sxs-lookup"><span data-stu-id="4ba84-137">Global policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="4ba84-138">Non</span><span class="sxs-lookup"><span data-stu-id="4ba84-138">No</span></span></p></td>
<td><p><span data-ttu-id="4ba84-139">Non</span><span class="sxs-lookup"><span data-stu-id="4ba84-139">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ba84-140">Paramètre de stratégie par utilisateur pour les fournisseurs de messagerie instantanée publics</span><span class="sxs-lookup"><span data-stu-id="4ba84-140">Per-user policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="4ba84-141">Oui</span><span class="sxs-lookup"><span data-stu-id="4ba84-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="4ba84-142">Non</span><span class="sxs-lookup"><span data-stu-id="4ba84-142">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ba84-143">Un utilisateur peut communiquer avec des fournisseurs de messagerie instantanée publics</span><span class="sxs-lookup"><span data-stu-id="4ba84-143">User can communicate with public IM providers</span></span></p></td>
<td><p><span data-ttu-id="4ba84-144">Oui</span><span class="sxs-lookup"><span data-stu-id="4ba84-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="4ba84-145">Non</span><span class="sxs-lookup"><span data-stu-id="4ba84-145">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4ba84-146">Comme vous pouvez le constater, Ken Myer est autorisé à communiquer avec des fournisseurs de messagerie instantanée publics.</span><span class="sxs-lookup"><span data-stu-id="4ba84-146">As you can see, Ken Myer is allowed to communicate with public IM providers.</span></span> <span data-ttu-id="4ba84-147">Cela est dû au fait que les paramètres de la stratégie par utilisateur qui lui sont attribués remplacent les paramètres dans la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="4ba84-147">This is because the settings in the per-user policy assigned to him override the settings in the global policy.</span></span> <span data-ttu-id="4ba84-148">Pilar Ackerman ne peut pas communiquer avec des fournisseurs de messagerie instantanée publics.</span><span class="sxs-lookup"><span data-stu-id="4ba84-148">Pilar Ackerman cannot communicate with public IM providers.</span></span> <span data-ttu-id="4ba84-149">Cela est dû au fait qu’elle est gérée par la stratégie globale et que la stratégie globale interdit ces communications.</span><span class="sxs-lookup"><span data-stu-id="4ba84-149">This is because she is managed by the global policy, and the global policy prohibits such communications.</span></span>

<span data-ttu-id="4ba84-150">Les stratégies par utilisateur doivent être créées pour vous par le support Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4ba84-150">Per-user policies must be created for you by Microsoft Support.</span></span> <span data-ttu-id="4ba84-151">Une fois les stratégies créées, vous pouvez les affecter à des utilisateurs à l’aide de la cmdlet **Grant-CS** appropriée (par exemple, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)).</span><span class="sxs-lookup"><span data-stu-id="4ba84-151">After the policies are created, you can then assign them to users by using the appropriate **Grant-Cs** cmdlet (for example, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)).</span></span> <span data-ttu-id="4ba84-152">Les stratégies par utilisateur sont faciles à identifier car l’identité de la stratégie commence toujours par le **préfixe**de balise.</span><span class="sxs-lookup"><span data-stu-id="4ba84-152">Per-user policies are easy to identify because the policy Identity always begins with the tag **prefix**.</span></span> <span data-ttu-id="4ba84-153">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4ba84-153">For example:</span></span>

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> <span data-ttu-id="4ba84-154">Les dates de <STRONG>préfixe</STRONG> de balise aux premiers jours de développement de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4ba84-154">The tag <STRONG>prefix</STRONG> dates back to the early development days of Lync Server 2010.</span></span> <span data-ttu-id="4ba84-155">Pendant ces jours, les stratégies par utilisateur étaient appelées <EM>stratégies de balise</EM> et étaient identifiées par le <STRONG>préfixe</STRONG>de balise.</span><span class="sxs-lookup"><span data-stu-id="4ba84-155">In those days, per-user policies were referred to as <EM>tag policies</EM> and were identified by the tag <STRONG>prefix</STRONG>.</span></span> <span data-ttu-id="4ba84-156">Ces stratégies sont désormais plus précisément désignées comme des <EM>stratégies par utilisateur</EM>, et l’étendue de la balise est plus précisément désignée <EM>par l’étendue par utilisateur</EM>.</span><span class="sxs-lookup"><span data-stu-id="4ba84-156">These policies are now more accurately referred to as <EM>per-user policies</EM>, and the tag scope is more accurately referred to as the <EM>per-user scope</EM>.</span></span> <span data-ttu-id="4ba84-157">Toutefois, pour des raisons techniques, le <STRONG>préfixe</STRONG> de balise n’a jamais été modifié.</span><span class="sxs-lookup"><span data-stu-id="4ba84-157">However, for technical reasons, the tag <STRONG>prefix</STRONG> was never changed.</span></span>



</div>

<span data-ttu-id="4ba84-158">Un autre terme clé utilisé avec Skype entreprise Online et Windows PowerShell est *client*.</span><span class="sxs-lookup"><span data-stu-id="4ba84-158">Another key term used when working with Skype for Business Online and Windows PowerShell is *tenant*.</span></span> <span data-ttu-id="4ba84-159">Lorsque vous configurez un compte Skype entreprise Online, votre nouveau déploiement se voit attribuer un numéro d’ID de client, qui est un identificateur global unique (GUID) de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="4ba84-159">When you set up a Skype for Business Online account, your new deployment is assigned a tenant ID number, which is a globally unique identifier (GUID) similar to this:</span></span>

    bf19b7db-6960-41e5-a139-2aa373474354

<span data-ttu-id="4ba84-160">Quelques-unes des applets de commande Skype entreprise Online vous obligent à entrer l’ID de client chaque fois que vous exécutez l’applet de commande.</span><span class="sxs-lookup"><span data-stu-id="4ba84-160">A few of the Skype for Business Online cmdlets require you to enter the tenant ID whenever you run the cmdlet.</span></span> <span data-ttu-id="4ba84-161">Vous devez entrer l’ID de client même si vous avez ouvert une session sur, et uniquement un seul client.</span><span class="sxs-lookup"><span data-stu-id="4ba84-161">You must enter the tenant ID even if you have logged on to, and only have, one tenant.</span></span> <span data-ttu-id="4ba84-162">Heureusement, il n’est pas nécessaire de mémoriser l’ID de client.</span><span class="sxs-lookup"><span data-stu-id="4ba84-162">Fortunately, you do not have to memorize the tenant ID.</span></span> <span data-ttu-id="4ba84-163">Vous pouvez récupérer votre ID de client à tout moment en exécutant la commande Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="4ba84-163">You can retrieve your tenant ID at any time by running the following Windows PowerShell command:</span></span>

    Get-CsTenant | Select-Object TenantId

<span data-ttu-id="4ba84-164">Bien entendu, connaître la différence entre l’étendue globale et l’étendue par utilisateur (ou l’étendue de la balise) n’est qu’une partie de la bataille.</span><span class="sxs-lookup"><span data-stu-id="4ba84-164">Of course, knowing things such as the difference between the global scope and the per-user scope (or the tag scope) is only half the battle.</span></span> <span data-ttu-id="4ba84-165">Il est également important de déterminer quand (ou même si) vous pouvez utiliser ces étendues.</span><span class="sxs-lookup"><span data-stu-id="4ba84-165">It’s also important to know when (or even if) you can use these scopes.</span></span> <span data-ttu-id="4ba84-166">Il en est de même pour les identités et le paramètre locataire.</span><span class="sxs-lookup"><span data-stu-id="4ba84-166">The same is true for Identities and the tenant parameter.</span></span> <span data-ttu-id="4ba84-167">Les rubriques suivantes décrivent comment les différentes applets de commande Skype entreprise Online utilisent des identités, des étendues et le paramètre client :</span><span class="sxs-lookup"><span data-stu-id="4ba84-167">The following topics describe how the different Skype for Business Online cmdlets use Identities, scopes, and the tenant parameter:</span></span>

  - [<span data-ttu-id="4ba84-168">Applets de commande dans Skype entreprise Online qui utilisent uniquement l’étendue globale</span><span class="sxs-lookup"><span data-stu-id="4ba84-168">Cmdlets in Skype for Business Online that use only the global scope</span></span>](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [<span data-ttu-id="4ba84-169">Applets de commande dans Skype entreprise Online qui utilisent l’étendue globale et l’étendue de la balise</span><span class="sxs-lookup"><span data-stu-id="4ba84-169">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [<span data-ttu-id="4ba84-170">Applets de commande dans Skype entreprise Online qui utilisent une identité d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="4ba84-170">Cmdlets in Skype for Business Online that use a user identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [<span data-ttu-id="4ba84-171">Applets de commande dans Skype entreprise Online qui utilisent une identité d’utilisateur et l’étendue de la balise</span><span class="sxs-lookup"><span data-stu-id="4ba84-171">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [<span data-ttu-id="4ba84-172">Applets de commande dans Skype entreprise Online qui utilisent le paramètre client</span><span class="sxs-lookup"><span data-stu-id="4ba84-172">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [<span data-ttu-id="4ba84-173">Applets de commande dans Skype entreprise Online qui utilisent l’identité d’un fournisseur de services de conférence</span><span class="sxs-lookup"><span data-stu-id="4ba84-173">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [<span data-ttu-id="4ba84-174">Applets de commande dans Skype entreprise Online qui n’utilisent pas d’étendue ni d’identité</span><span class="sxs-lookup"><span data-stu-id="4ba84-174">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

