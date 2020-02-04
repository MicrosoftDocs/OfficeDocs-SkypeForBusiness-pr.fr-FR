---
title: Identités, étendues et clients dans Skype entreprise Online
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b08c459f64a4655ebb4dc670255645f985452aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a><span data-ttu-id="94804-102">Identités, étendues et clients dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="94804-102">Identities, scopes, and tenants in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94804-103">_**Dernière modification de la rubrique :** 2015-03-09_</span><span class="sxs-lookup"><span data-stu-id="94804-103">_**Topic Last Modified:** 2015-03-09_</span></span>

<span data-ttu-id="94804-104">La plupart des cmdlets Windows PowerShell utilisées pour gérer Skype entreprise Online nécessitent que vous soyez extrêmement précis de l’élément que vous tentez de gérer.</span><span class="sxs-lookup"><span data-stu-id="94804-104">Many of the Windows PowerShell cmdlets used to manage Skype for Business Online require you to be very specific about the item that you are trying to manage.</span></span> <span data-ttu-id="94804-105">Par exemple, lorsque vous exécutez l’applet [de cmdlet Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) , vous devez indiquer l’utilisateur que vous voulez gérer.</span><span class="sxs-lookup"><span data-stu-id="94804-105">For example, when you run the [Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) cmdlet, you must indicate which user you are trying to manage.</span></span> <span data-ttu-id="94804-106">C’est un bon sentiment.</span><span class="sxs-lookup"><span data-stu-id="94804-106">This makes sense.</span></span> <span data-ttu-id="94804-107">À moins que vous ne soyez spécifiquement en informant sur le compte d’utilisateur à gérer, l’applet **de passe Set-CsUserAcp** n’a aucune idée des informations de l’utilisateur à modifier.</span><span class="sxs-lookup"><span data-stu-id="94804-107">Unless you specifically tell the cmdlet which user account to manage, the **Set-CsUserAcp** cmdlet has no idea which user’s audio conferencing information should be modified.</span></span> <span data-ttu-id="94804-108">Pour cette raison, chaque fois que vous exécutez l’applet **de connexion Set-CsUserAcp** , vous devez inclure le paramètre Identity, suivi de l’identité du compte d’utilisateur à modifier :</span><span class="sxs-lookup"><span data-stu-id="94804-108">For this reason, each time you run the **Set-CsUserAcp** cmdlet, you’ll need to include the Identity parameter, followed by the Identity of the user account to be modified:</span></span>

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

<span data-ttu-id="94804-109">Si le terme *identité* correspond toujours à l’identité d’un compte d’utilisateur, il n’y a pas de raison de confusion.</span><span class="sxs-lookup"><span data-stu-id="94804-109">If the term *Identity* always referred to the Identity of a user account, there would be little cause for confusion.</span></span> <span data-ttu-id="94804-110">Lorsque vous travaillez avec des personnes (utilisateurs, contacts, etc.), les identités font référence aux utilisateurs individuels eux-mêmes.</span><span class="sxs-lookup"><span data-stu-id="94804-110">When you are dealing with people (users, contacts, and so on), Identities refer to the individual users themselves.</span></span> <span data-ttu-id="94804-111">Toutefois, les éléments autres que les comptes d’utilisateurs sont également dotés d’identités.</span><span class="sxs-lookup"><span data-stu-id="94804-111">However, items other than user accounts also have Identities.</span></span> <span data-ttu-id="94804-112">Lorsque vous travaillez avec des composants du service Skype entreprise Online (politiques, paramètres de configuration, etc.), le terme identité désigne un aspect légèrement différent.</span><span class="sxs-lookup"><span data-stu-id="94804-112">When you are dealing with components of the Skype for Business Online service—policies, configuration settings, and so on—the term Identity means something slightly different.</span></span> <span data-ttu-id="94804-113">Par exemple, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="94804-113">For example, consider this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="94804-114">Dans ce cas, l’identité « global » fait référence à l’étendue des paramètres de configuration de la réunion.</span><span class="sxs-lookup"><span data-stu-id="94804-114">In this case, the Identity "global" refers to the scope of the meeting configuration settings.</span></span> <span data-ttu-id="94804-115">*Scope* est un terme utilisé dans Skype entreprise Online (et dans Lync Server) pour désigner les sphères de gestion.</span><span class="sxs-lookup"><span data-stu-id="94804-115">*Scope* is a term used in Skype for Business Online (and in Lync Server) to designate spheres of management.</span></span> <span data-ttu-id="94804-116">Par défaut, les stratégies et les paramètres disposent toujours d’une étendue globale.</span><span class="sxs-lookup"><span data-stu-id="94804-116">By default, policies and settings always have a global scope.</span></span> <span data-ttu-id="94804-117">Lorsque vous configurez votre compte Skype entreprise Online pour la première fois, vous disposez par défaut d’une collection de stratégies globales et de paramètres : les paramètres de configuration de réunion globale, une stratégie d’accès externe globale, un plan de numérotation global, etc.</span><span class="sxs-lookup"><span data-stu-id="94804-117">When you first set up your Skype for Business Online account you'll have, by default, a collection of global policies and settings—global meeting configuration settings, a global external access policy, a global dial plan, and so on.</span></span>

<span data-ttu-id="94804-118">Ces stratégies et paramètres globaux ont été introduits dans Microsoft Lync Server 2010 pour garantir la gestion de tous les utilisateurs et de tous les composants, d’une certaine façon.</span><span class="sxs-lookup"><span data-stu-id="94804-118">These global policies and settings were introduced in Microsoft Lync Server 2010 to help ensure that all users and all components would always, in some way, be managed.</span></span> <span data-ttu-id="94804-119">Ce n’est pas nécessairement vrai dans Microsoft Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="94804-119">This was not necessarily true in Microsoft Office Communicator 2007 R2.</span></span> <span data-ttu-id="94804-120">En fonction de la manière dont vous avez accédé au système, vous risquez de vous trouver dans un état essentiellement non géré (en général, la stratégie de groupe n’ayant pas pu être appliquée à votre compte d’utilisateur).</span><span class="sxs-lookup"><span data-stu-id="94804-120">Depending on how you accessed the system, you could potentially end up in a largely unmanaged state (typically, because Group Policy could not be applied to your user account).</span></span> <span data-ttu-id="94804-121">En revanche, dans Lync Server et dans Skype entreprise Online, rien n’est jamais laissé non plus.</span><span class="sxs-lookup"><span data-stu-id="94804-121">In contrast, in Lync Server and in Skype for Business Online, nothing is ever left unmanaged.</span></span> <span data-ttu-id="94804-122">En effet, les stratégies globales et les paramètres sont toujours appliqués en tout lieu.</span><span class="sxs-lookup"><span data-stu-id="94804-122">This is because, in lieu of anything else, global policies and settings will always be enforced.</span></span>

<span data-ttu-id="94804-123">Qu’est-ce que nous voulons dire par « au lieu de tout autre » ?</span><span class="sxs-lookup"><span data-stu-id="94804-123">What do we mean by "in lieu of anything else"?</span></span> <span data-ttu-id="94804-124">Dans le cas de Skype entreprise Online, il est possible de créer des politiques au niveau de l' *étendue des balises*ou de la sphère de gestion.</span><span class="sxs-lookup"><span data-stu-id="94804-124">Well, in the case of Skype for Business Online, it’s possible to create policies at the *tag scope*, or sphere of management.</span></span> <span data-ttu-id="94804-125">Les stratégies créées à l’étendue des balises (également connues sous le nom d' *étendue par utilisateur*) sont prioritaires sur les stratégies créées au niveau de l’étendue globale.</span><span class="sxs-lookup"><span data-stu-id="94804-125">Policies created at the tag scope (also known as *the per-user scope*) take priority over policies created at the global scope.</span></span> <span data-ttu-id="94804-126">En d’autres termes, une stratégie par utilisateur sera toujours prioritaire sur une stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="94804-126">In other words, a per-user policy will always take precedence over a global policy.</span></span> <span data-ttu-id="94804-127">Par exemple, vous pouvez avoir deux stratégies d’accès utilisateur externes.</span><span class="sxs-lookup"><span data-stu-id="94804-127">For example, you might have two external user access policies.</span></span> <span data-ttu-id="94804-128">La stratégie globale interdit aux utilisateurs de communiquer avec des personnes disposant de comptes sur des fournisseurs de messagerie instantanée (IM) publics tels que Windows Live.</span><span class="sxs-lookup"><span data-stu-id="94804-128">The global policy prohibits users from communicating with people who have accounts on public instant messaging (IM) providers, such as Windows Live.</span></span> <span data-ttu-id="94804-129">La stratégie par utilisateur, AllowPublicIMCommunication, permet de communiquer avec les fournisseurs de messagerie instantanée publics.</span><span class="sxs-lookup"><span data-stu-id="94804-129">The per-user policy, AllowPublicIMCommunication, allows communication with public IM providers.</span></span>

<span data-ttu-id="94804-130">Vous pouvez également avoir deux utilisateurs : Ken Myer et Pilar Arès.</span><span class="sxs-lookup"><span data-stu-id="94804-130">You might also have two users: Ken Myer and Pilar Ackerman.</span></span> <span data-ttu-id="94804-131">Ken Myer a été affecté de la stratégie par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="94804-131">Ken Myer has been assigned the per-user policy.</span></span> <span data-ttu-id="94804-132">Pilar Arès n’a pas été affecté d’une stratégie par utilisateur ; c’est-à-dire qu’elle est gérée par la stratégie d’accès externe globale.</span><span class="sxs-lookup"><span data-stu-id="94804-132">Pilar Ackerman has not been assigned a per-user policy; that is, she is managed by the global external access policy.</span></span> <span data-ttu-id="94804-133">Le tableau suivant indique quels utilisateurs (le cas échéant) peuvent communiquer avec les fournisseurs de messagerie instantanée publics :</span><span class="sxs-lookup"><span data-stu-id="94804-133">The following table shows which user (if any) can communicate with public IM providers:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="94804-134">Paramètres de stratégie</span><span class="sxs-lookup"><span data-stu-id="94804-134">Policy Settings</span></span></th>
<th><span data-ttu-id="94804-135">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="94804-135">Ken Myer</span></span></th>
<th><span data-ttu-id="94804-136">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="94804-136">Pilar Ackerman</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="94804-137">Paramètre de stratégie globale pour les fournisseurs de messagerie instantanée publics</span><span class="sxs-lookup"><span data-stu-id="94804-137">Global policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="94804-138">Non</span><span class="sxs-lookup"><span data-stu-id="94804-138">No</span></span></p></td>
<td><p><span data-ttu-id="94804-139">Non</span><span class="sxs-lookup"><span data-stu-id="94804-139">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94804-140">Paramètre de stratégie par utilisateur pour les fournisseurs de messagerie instantanée publics</span><span class="sxs-lookup"><span data-stu-id="94804-140">Per-user policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="94804-141">Oui</span><span class="sxs-lookup"><span data-stu-id="94804-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="94804-142">Non</span><span class="sxs-lookup"><span data-stu-id="94804-142">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94804-143">L’utilisateur peut communiquer avec les fournisseurs de messagerie instantanée publics</span><span class="sxs-lookup"><span data-stu-id="94804-143">User can communicate with public IM providers</span></span></p></td>
<td><p><span data-ttu-id="94804-144">Oui</span><span class="sxs-lookup"><span data-stu-id="94804-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="94804-145">Non</span><span class="sxs-lookup"><span data-stu-id="94804-145">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="94804-146">Comme vous pouvez le constater, Ken Myer est autorisé à communiquer avec les fournisseurs de messagerie instantanée publics.</span><span class="sxs-lookup"><span data-stu-id="94804-146">As you can see, Ken Myer is allowed to communicate with public IM providers.</span></span> <span data-ttu-id="94804-147">En effet, les paramètres de la stratégie par utilisateur qui lui sont attribués remplacent ceux de la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="94804-147">This is because the settings in the per-user policy assigned to him override the settings in the global policy.</span></span> <span data-ttu-id="94804-148">Pilar Arès ne peut pas communiquer avec les fournisseurs de messagerie instantanée publics.</span><span class="sxs-lookup"><span data-stu-id="94804-148">Pilar Ackerman cannot communicate with public IM providers.</span></span> <span data-ttu-id="94804-149">C’est parce qu’elle est gérée par la stratégie globale et que la stratégie globale interdit ces communications.</span><span class="sxs-lookup"><span data-stu-id="94804-149">This is because she is managed by the global policy, and the global policy prohibits such communications.</span></span>

<span data-ttu-id="94804-150">Des stratégies par utilisateur doivent être créées pour vous par le biais du support technique d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="94804-150">Per-user policies must be created for you by Office 365 Support.</span></span> <span data-ttu-id="94804-151">Une fois les stratégies créées, vous pouvez les affecter aux utilisateurs à l’aide de l’applet de passe **Grant-CS** appropriée (par exemple, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)).</span><span class="sxs-lookup"><span data-stu-id="94804-151">After the policies are created, you can then assign them to users by using the appropriate **Grant-Cs** cmdlet (for example, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)).</span></span> <span data-ttu-id="94804-152">Les stratégies par utilisateur sont faciles à identifier, car l’identité de la stratégie commence toujours par le **préfixe**de la balise.</span><span class="sxs-lookup"><span data-stu-id="94804-152">Per-user policies are easy to identify because the policy Identity always begins with the tag **prefix**.</span></span> <span data-ttu-id="94804-153">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="94804-153">For example:</span></span>

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> <span data-ttu-id="94804-154">Le <STRONG>préfixe</STRONG> de l’indicateur passe aux jours de développement premiers de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="94804-154">The tag <STRONG>prefix</STRONG> dates back to the early development days of Lync Server 2010.</span></span> <span data-ttu-id="94804-155">Dans ces jours, les politiques par utilisateur étaient appelées <EM>stratégies d’étiquette</EM> et identifiées par le <STRONG>préfixe</STRONG>de balise.</span><span class="sxs-lookup"><span data-stu-id="94804-155">In those days, per-user policies were referred to as <EM>tag policies</EM> and were identified by the tag <STRONG>prefix</STRONG>.</span></span> <span data-ttu-id="94804-156">Ces stratégies sont désormais plus précises que celles définies <EM>par l’utilisateur</EM>, et l’étendue de la balise est désignée de façon plus précise comme <EM>une étendue par utilisateur</EM>.</span><span class="sxs-lookup"><span data-stu-id="94804-156">These policies are now more accurately referred to as <EM>per-user policies</EM>, and the tag scope is more accurately referred to as the <EM>per-user scope</EM>.</span></span> <span data-ttu-id="94804-157">Toutefois, pour des raisons techniques, le <STRONG>préfixe</STRONG> d’indicateur n’a jamais changé.</span><span class="sxs-lookup"><span data-stu-id="94804-157">However, for technical reasons, the tag <STRONG>prefix</STRONG> was never changed.</span></span>



</div>

<span data-ttu-id="94804-158">Un autre terme clé utilisé lors de l’utilisation de Skype entreprise Online et de Windows PowerShell est le *client*.</span><span class="sxs-lookup"><span data-stu-id="94804-158">Another key term used when working with Skype for Business Online and Windows PowerShell is *tenant*.</span></span> <span data-ttu-id="94804-159">Lorsque vous configurez un compte Skype entreprise Online, votre nouveau déploiement dispose d’un numéro d’ID de client, qui est un identificateur global unique (GUID), semblable à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="94804-159">When you set up a Skype for Business Online account, your new deployment is assigned a tenant ID number, which is a globally unique identifier (GUID) similar to this:</span></span>

    bf19b7db-6960-41e5-a139-2aa373474354

<span data-ttu-id="94804-160">Quelques-unes des cmdlets de Skype entreprise Online vous demandent d’entrer l’ID de locataire chaque fois que vous exécutez l’applet de connexion.</span><span class="sxs-lookup"><span data-stu-id="94804-160">A few of the Skype for Business Online cmdlets require you to enter the tenant ID whenever you run the cmdlet.</span></span> <span data-ttu-id="94804-161">Vous devez entrer l’ID de locataire même si vous vous êtes connecté à un seul client.</span><span class="sxs-lookup"><span data-stu-id="94804-161">You must enter the tenant ID even if you have logged on to, and only have, one tenant.</span></span> <span data-ttu-id="94804-162">Heureusement, il n’est pas nécessaire de mémoriser l’ID de locataire.</span><span class="sxs-lookup"><span data-stu-id="94804-162">Fortunately, you do not have to memorize the tenant ID.</span></span> <span data-ttu-id="94804-163">Vous pouvez récupérer votre ID de locataire à tout moment en exécutant la commande Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="94804-163">You can retrieve your tenant ID at any time by running the following Windows PowerShell command:</span></span>

    Get-CsTenant | Select-Object TenantId

<span data-ttu-id="94804-164">Bien entendu, il n’y a pas de différence entre l’étendue globale et l’étendue par utilisateur (ou l’étendue de la balise).</span><span class="sxs-lookup"><span data-stu-id="94804-164">Of course, knowing things such as the difference between the global scope and the per-user scope (or the tag scope) is only half the battle.</span></span> <span data-ttu-id="94804-165">Il est également important de savoir quand (ou même si) vous pouvez utiliser ces étendues.</span><span class="sxs-lookup"><span data-stu-id="94804-165">It’s also important to know when (or even if) you can use these scopes.</span></span> <span data-ttu-id="94804-166">Il en va de même pour les identités et le paramètre locataire.</span><span class="sxs-lookup"><span data-stu-id="94804-166">The same is true for Identities and the tenant parameter.</span></span> <span data-ttu-id="94804-167">Les rubriques suivantes décrivent la façon dont les différentes applets de commande Skype entreprise Online utilisent les identités, les étendues et le paramètre locataire :</span><span class="sxs-lookup"><span data-stu-id="94804-167">The following topics describe how the different Skype for Business Online cmdlets use Identities, scopes, and the tenant parameter:</span></span>

  - [<span data-ttu-id="94804-168">Cmdlets dans Skype entreprise Online utilisant uniquement l’étendue globale</span><span class="sxs-lookup"><span data-stu-id="94804-168">Cmdlets in Skype for Business Online that use only the global scope</span></span>](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [<span data-ttu-id="94804-169">Cmdlets dans Skype entreprise Online utilisant l’étendue globale et l’étendue des indicateurs</span><span class="sxs-lookup"><span data-stu-id="94804-169">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [<span data-ttu-id="94804-170">Cmdlets dans Skype entreprise Online utilisant une identité d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="94804-170">Cmdlets in Skype for Business Online that use a user identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [<span data-ttu-id="94804-171">Cmdlets dans Skype entreprise Online utilisant une identité d’utilisateur et une étendue de balises</span><span class="sxs-lookup"><span data-stu-id="94804-171">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [<span data-ttu-id="94804-172">Cmdlets dans Skype entreprise Online utilisant le paramètre locataire</span><span class="sxs-lookup"><span data-stu-id="94804-172">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [<span data-ttu-id="94804-173">Cmdlets dans Skype entreprise Online utilisant l’identité d’un fournisseur de conférence</span><span class="sxs-lookup"><span data-stu-id="94804-173">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [<span data-ttu-id="94804-174">Cmdlets dans Skype entreprise Online qui n’utilisent pas d’étendue ou d’identité</span><span class="sxs-lookup"><span data-stu-id="94804-174">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

