---
title: Bloquer les appels entrants dans Microsoft Teams
ms.author: v-cichur
author: cichur
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.custom: Learn how to use PowerShell to manage inbound call blocking.
ms.openlocfilehash: ca2f8de5962572a08ab2a0ae7127446d14334c83
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799904"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="64cee-102">Bloquer les appels entrants</span><span class="sxs-lookup"><span data-stu-id="64cee-102">Block inbound calls</span></span>

<span data-ttu-id="64cee-103">Les plans de routage et d’appel directs du système téléphonique (PHONE System Direct Routing and Calling) prisent en charge le blocage des appels entrants à partir du réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="64cee-103">Phone System Direct Routing and Calling Plans support blocking inbound calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="64cee-104">Cette fonctionnalité permet de définir une liste globale de modèles de numéro afin que l’ID d’appelant de chaque appel PSTN entrant vers le client puisse être vérifié par rapport à la liste pour une correspondance.</span><span class="sxs-lookup"><span data-stu-id="64cee-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="64cee-105">En cas de correspondance, un appel entrant est rejeté.</span><span class="sxs-lookup"><span data-stu-id="64cee-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="64cee-106">Cette fonctionnalité de blocage des appels entrants fonctionne uniquement sur les appels entrants provenant du réseau PSTN et fonctionne uniquement au niveau global du client.</span><span class="sxs-lookup"><span data-stu-id="64cee-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="64cee-107">Elle n’est pas disponible par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="64cee-107">It's not available on a per-user basis.</span></span>  

>[!NOTE]
> <span data-ttu-id="64cee-108">Les appelants bloqués peuvent avoir des comportements légèrement différents lorsqu’ils sont bloqués.</span><span class="sxs-lookup"><span data-stu-id="64cee-108">Blocked callers may experience slightly different behaviors when they've been blocked.</span></span> <span data-ttu-id="64cee-109">Le comportement est basé sur la façon dont l’opérateur de l’appelant bloqué gère la notification de non-réussite de l’appel.</span><span class="sxs-lookup"><span data-stu-id="64cee-109">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="64cee-110">Il peut s’agir, par exemple, d’un message de l’opérateur indiquant que l’appel ne peut pas être effectué comme un appel composé, ou un simple abandon de l’appel.</span><span class="sxs-lookup"><span data-stu-id="64cee-110">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="64cee-111">Appel bloquant les contrôles d’administration et les informations</span><span class="sxs-lookup"><span data-stu-id="64cee-111">Call blocking admin controls and information</span></span>

<span data-ttu-id="64cee-112">Les contrôles d’administration pour le blocage des numéros sont fournis à l’aide de PowerShell uniquement.</span><span class="sxs-lookup"><span data-stu-id="64cee-112">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="64cee-113">Les modèles de blocs de nombres sont définis en tant que modèles d’expression régulière.</span><span class="sxs-lookup"><span data-stu-id="64cee-113">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="64cee-114">L’ordre des expressions n’est pasimportant : le premier modèle de la liste a pour résultat le blocage de l’appel.</span><span class="sxs-lookup"><span data-stu-id="64cee-114">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="64cee-115">L’activité d’un nouveau numéro ou modèle ajouté ou supprimé dans la liste des appelants bloqués peut prendre jusqu’à 24 heures.</span><span class="sxs-lookup"><span data-stu-id="64cee-115">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="64cee-116">Appel bloquant les commandes PowerShell</span><span class="sxs-lookup"><span data-stu-id="64cee-116">Call blocking PowerShell commands</span></span>

<span data-ttu-id="64cee-117">Vous gérez les modèles de nombres à l’aide des cmdlets **New,** **Get,** **Set,** **Remove**  - **CsInboundBlockedNumberPattern.**</span><span class="sxs-lookup"><span data-stu-id="64cee-117">You manage number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsInboundBlockedNumberPattern** cmdlets.</span></span> <span data-ttu-id="64cee-118">Vous pouvez gérer un modèle donné à l’aide de ces cmdlets, y compris la possibilité d’activer un modèle donné.</span><span class="sxs-lookup"><span data-stu-id="64cee-118">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>

- <span data-ttu-id="64cee-119">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) renvoie la liste de tous les modèles de numéro bloqués ajoutés à la liste des locataires, y compris Nom, Description, Activé (Vrai/Faux) et Modèle pour chacun d’eux.</span><span class="sxs-lookup"><span data-stu-id="64cee-119">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="64cee-120">[New-CsInboundBlockedNumberPattern ajoute](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) un modèle de numéro bloqué à la liste des locataires.</span><span class="sxs-lookup"><span data-stu-id="64cee-120">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="64cee-121">[Remove-CsInboundBlockedNumberPattern supprime](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) un modèle de numéro bloqué de la liste des locataires.</span><span class="sxs-lookup"><span data-stu-id="64cee-121">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="64cee-122">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifie un ou plusieurs paramètres d’un modèle de nombre bloqué dans la liste des locataires.</span><span class="sxs-lookup"><span data-stu-id="64cee-122">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="64cee-123">L’affichage et l’activation de l’ensemble de la fonctionnalité de blocage des appels sont gérés via les cmdlets **Get,** **Set**  - **CsTenantBlockingCallingNumbers.**</span><span class="sxs-lookup"><span data-stu-id="64cee-123">Viewing and activating the entire call blocking feature is managed through the **Get**, **Set** -**CsTenantBlockingCallingNumbers** cmdlets.</span></span>

- <span data-ttu-id="64cee-124">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) renvoie les paramètres de la liste des nombres bloqués globaux, y compris Activé (True/False).</span><span class="sxs-lookup"><span data-stu-id="64cee-124">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="64cee-125">Il existe une seule stratégie de client globale qui ne peut pas être modifiée manuellement si ce n’est pour activer ou désactiver la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="64cee-125">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="64cee-126">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) permet d’autoriser ou non la modification des appels bloqués du client global au niveau du client.</span><span class="sxs-lookup"><span data-stu-id="64cee-126">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="64cee-127">Exemples</span><span class="sxs-lookup"><span data-stu-id="64cee-127">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="64cee-128">Bloquer un numéro</span><span class="sxs-lookup"><span data-stu-id="64cee-128">Block a number</span></span>

<span data-ttu-id="64cee-129">Dans cet exemple, les paramètres **Activé** et **Description** sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="64cee-129">In this example, the **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="64cee-130">La création d’un modèle ajoute le modèle comme étant activé par défaut.</span><span class="sxs-lookup"><span data-stu-id="64cee-130">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="64cee-131">La description est un champ facultatif pour fournir des informations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="64cee-131">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="64cee-132">Nous vous recommandons de fournir un nom significatif pour comprendre facilement pourquoi le modèle a été ajouté.</span><span class="sxs-lookup"><span data-stu-id="64cee-132">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="64cee-133">Si vous bloquez simplement les numéros de courrier indésirable, vous pouvez nommer la règle de la même façon que le modèle de nombres qui correspond et ajouter des informations supplémentaires dans la description si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="64cee-133">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="64cee-134">Les modèles sont assortis à l’aide d’expressions régulières (Regex).</span><span class="sxs-lookup"><span data-stu-id="64cee-134">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="64cee-135">Autorisez le temps de réplication avant de tester et de valider.</span><span class="sxs-lookup"><span data-stu-id="64cee-135">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="64cee-136">Autoriser un numéro</span><span class="sxs-lookup"><span data-stu-id="64cee-136">Allow a number</span></span>

<span data-ttu-id="64cee-137">Dans cet exemple, le **paramètre Identité** est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="64cee-137">In this example, the **Identity** parameter is required.</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="64cee-138">Si l’identité n’est pas connue, utilisez l’cmdlet **Get-CsInboundBlockedNumberPattern** pour identifier le modèle approprié et noter l’identité.</span><span class="sxs-lookup"><span data-stu-id="64cee-138">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="64cee-139">Ensuite, exécutez la cmdlet **Remove-CsTenantBlockedNumberPattern** et transmettre la valeur d’identité appropriée.</span><span class="sxs-lookup"><span data-stu-id="64cee-139">Then, run the **Remove-CsTenantBlockedNumberPattern** cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="64cee-140">Autorisez le temps de réplication avant de tester et de valider.</span><span class="sxs-lookup"><span data-stu-id="64cee-140">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="64cee-141">Afficher tous les modèles de nombres</span><span class="sxs-lookup"><span data-stu-id="64cee-141">View all number patterns</span></span>

<span data-ttu-id="64cee-142">L’exécution de cette cmdlet renvoie la liste de tous les numéros bloqués entrés pour un client :</span><span class="sxs-lookup"><span data-stu-id="64cee-142">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="64cee-143">Utilisez les capacités intégrées de filtrage PowerShell pour filtrer les valeurs renvoyées comme requis.</span><span class="sxs-lookup"><span data-stu-id="64cee-143">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="64cee-144">Ajouter des exceptions de nombre</span><span class="sxs-lookup"><span data-stu-id="64cee-144">Add number exceptions</span></span>

<span data-ttu-id="64cee-145">Vous pouvez ajouter des exceptions aux modèles de nombres bloqués à l’aide des cmdlets **New,** **Get,** **Set,** **Remove**  - **CsTenantBlockNumberExceptionPattern.**</span><span class="sxs-lookup"><span data-stu-id="64cee-145">You can add exceptions to blocked number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsTenantBlockNumberExceptionPattern** cmdlets.</span></span>

- <span data-ttu-id="64cee-146">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) ajoute un modèle d’exception de nombre à la liste des locataires.</span><span class="sxs-lookup"><span data-stu-id="64cee-146">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="64cee-147">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) renvoie la liste de tous les modèles d’exceptions de nombres ajoutés à la liste des locataires.</span><span class="sxs-lookup"><span data-stu-id="64cee-147">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="64cee-148">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifie un ou plusieurs paramètres en un ou plusieurs paramètres d’exception dans la liste des locataires.</span><span class="sxs-lookup"><span data-stu-id="64cee-148">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="64cee-149">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) supprime un modèle d’exception de nombre de la liste des locataires.</span><span class="sxs-lookup"><span data-stu-id="64cee-149">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="64cee-150">Exemples</span><span class="sxs-lookup"><span data-stu-id="64cee-150">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="64cee-151">Ajouter une exception</span><span class="sxs-lookup"><span data-stu-id="64cee-151">Add a number exception</span></span>

<span data-ttu-id="64cee-152">Dans cet exemple, un nouveau modèle d’exception de nombre est créé et l’ajoutera par défaut comme étant activé.</span><span class="sxs-lookup"><span data-stu-id="64cee-152">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="64cee-153">Les **paramètres Activé** **et Description** sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="64cee-153">The **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="64cee-154">Afficher toutes les exceptions de nombre</span><span class="sxs-lookup"><span data-stu-id="64cee-154">View all number exceptions</span></span>

<span data-ttu-id="64cee-155">Dans cet exemple, le **paramètre Identité** est facultatif.</span><span class="sxs-lookup"><span data-stu-id="64cee-155">In this example, the **Identity** parameter is optional.</span></span> <span data-ttu-id="64cee-156">Si le **paramètre Identité** n’est pas spécifié, cette cmdlet renvoie la liste de tous les modèles d’exceptions de nombre entrés pour un client.</span><span class="sxs-lookup"><span data-stu-id="64cee-156">If the **Identity** parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="64cee-157">Modifier une exception de nombre</span><span class="sxs-lookup"><span data-stu-id="64cee-157">Modify a number exception</span></span>

<span data-ttu-id="64cee-158">Dans cet exemple, le **paramètre Identité** est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="64cee-158">In this example, the **Identity** parameter is mandatory.</span></span> <span data-ttu-id="64cee-159">L’cmdlet **Set-CsTenantBlockedNumberExceptionPattern** vous permet de modifier un ou plusieurs paramètres pour une identité de modèle de nombre donnée.</span><span class="sxs-lookup"><span data-stu-id="64cee-159">The **Set-CsTenantBlockedNumberExceptionPattern** cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="64cee-160">Supprimer une exception</span><span class="sxs-lookup"><span data-stu-id="64cee-160">Remove a number exception</span></span>

<span data-ttu-id="64cee-161">Dans cet exemple, le **paramètre Identité** est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="64cee-161">In this example, the **Identity** parameter is required.</span></span> <span data-ttu-id="64cee-162">Cette cmdlet supprime le modèle de numéro donné de la liste des locataires.</span><span class="sxs-lookup"><span data-stu-id="64cee-162">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="64cee-163">Si l’identité n’est pas connue, utilisez l’cmdlet **Get-CsInboundBlockedNumberPattern** pour identifier le modèle approprié et noter l’identité.</span><span class="sxs-lookup"><span data-stu-id="64cee-163">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="64cee-164">Ensuite, exécutez la cmdlet **Remove-CsTenantBlockedNumberExceptionPattern** et transmettre la valeur d’identité appropriée.</span><span class="sxs-lookup"><span data-stu-id="64cee-164">Then, run the **Remove-CsTenantBlockedNumberExceptionPattern** cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="64cee-165">Autorisez le temps de réplication avant de tester et de valider.</span><span class="sxs-lookup"><span data-stu-id="64cee-165"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="64cee-166">Vérifier si un nombre est bloqué</span><span class="sxs-lookup"><span data-stu-id="64cee-166">Test whether a number is blocked</span></span>

<span data-ttu-id="64cee-167">Utilisez **l’cmdlet Test-CsInboundBlockedNumberPattern** pour vérifier si un nombre est bloqué dans le client.</span><span class="sxs-lookup"><span data-stu-id="64cee-167">Use the **Test-CsInboundBlockedNumberPattern** cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="64cee-168">Dans cet exemple, les **paramètres PhoneNumber** **et Tenant** sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="64cee-168">In this example, the **PhoneNumber** and **Tenant** parameters are required.</span></span> <span data-ttu-id="64cee-169">Le **paramètre PhoneNumber** doit être une chaîne numérique sans caractères supplémentaires tels que + ou -.</span><span class="sxs-lookup"><span data-stu-id="64cee-169">The **PhoneNumber** parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="64cee-170">Dans le TRPS, le **paramètre client** est facultatif.</span><span class="sxs-lookup"><span data-stu-id="64cee-170">In TRPS, the **Tenant parameter** is optional.</span></span> <span data-ttu-id="64cee-171">Le paramètre **isNumberBlocked** qui en résulte renvoie la valeur True si le nombre est bloqué dans le client et False s’il n’est pas bloqué.</span><span class="sxs-lookup"><span data-stu-id="64cee-171">The resulting **isNumberBlocked** parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="64cee-172">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="64cee-172">httpResponseCode</span></span>  |<span data-ttu-id="64cee-173">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="64cee-173">isNumberBlocked</span></span>   |<span data-ttu-id="64cee-174">errorMessage</span><span class="sxs-lookup"><span data-stu-id="64cee-174">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="64cee-175">200</span><span class="sxs-lookup"><span data-stu-id="64cee-175">200</span></span>    | <span data-ttu-id="64cee-176">Vrai</span><span class="sxs-lookup"><span data-stu-id="64cee-176">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="64cee-177">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="64cee-177">httpResponseCode</span></span>  |<span data-ttu-id="64cee-178">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="64cee-178">isNumberBlocked</span></span>   |<span data-ttu-id="64cee-179">errorMessage</span><span class="sxs-lookup"><span data-stu-id="64cee-179">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="64cee-180">200</span><span class="sxs-lookup"><span data-stu-id="64cee-180">200</span></span>    | <span data-ttu-id="64cee-181">False</span><span class="sxs-lookup"><span data-stu-id="64cee-181">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="64cee-182">Note sur Regex</span><span class="sxs-lookup"><span data-stu-id="64cee-182">A note about Regex</span></span>

<span data-ttu-id="64cee-183">Comme indiqué précédemment, la correspondance au modèle de blocage des appelants est effectuée à l’aide de Regex.</span><span class="sxs-lookup"><span data-stu-id="64cee-183">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="64cee-184">Plusieurs outils sont disponibles en ligne pour vous aider à valider une correspondance au modèle Regex.</span><span class="sxs-lookup"><span data-stu-id="64cee-184">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="64cee-185">Si vous n’êtes pas familiarisé avec les modèles Regex, nous vous recommandons de prendre le temps de vous familiariser avec les bases.</span><span class="sxs-lookup"><span data-stu-id="64cee-185">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="64cee-186">Pour vous assurer d’obtenir les résultats attendus, utilisez un outil pour valider les correspondances de modèle avant d’ajouter de nouveaux nombres bloqués à votre client.</span><span class="sxs-lookup"><span data-stu-id="64cee-186">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span>
