---
title: Bloquer les appels entrants dans Skype Entreprise Online
ms.author: v-cichur
author: cichur
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Skype for Business
localization_priority: Normal
ms.custom: Learn how to use PowerShell to manage inbound call blocking in Skype for Business Online.
ms.openlocfilehash: 7848aff5f5b4dbb56be713b9241f2ace1ee6e6b3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102070"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="598c2-102">Bloquer les appels entrants</span><span class="sxs-lookup"><span data-stu-id="598c2-102">Block inbound calls</span></span>

<span data-ttu-id="598c2-103">Les forfaits d’appels Skype Entreprise Online prend désormais en charge le blocage des appels entrants à partir du réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="598c2-103">Skype for Business Online Calling Plans now supports blocking of inbound calls from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="598c2-104">Cette fonctionnalité permet de définir une liste globale de modèles de numéro afin que l’ID d’appelant de chaque appel PSTN entrant vers le client puisse être vérifié par rapport à la liste pour une correspondance.</span><span class="sxs-lookup"><span data-stu-id="598c2-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="598c2-105">En cas de correspondance, un appel entrant est rejeté.</span><span class="sxs-lookup"><span data-stu-id="598c2-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="598c2-106">Cette fonctionnalité de blocage des appels entrants fonctionne uniquement sur les appels entrants provenant du réseau PSTN et fonctionne uniquement sur une base globale du client.</span><span class="sxs-lookup"><span data-stu-id="598c2-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="598c2-107">Elle n’est pas disponible par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="598c2-107">It's not available on a per-user basis.</span></span>  

<span data-ttu-id="598c2-108">Cette fonctionnalité n’est pas encore disponible pour le routage direct.</span><span class="sxs-lookup"><span data-stu-id="598c2-108">This feature isn't yet available for Direct Routing.</span></span>

>[!NOTE]
> <span data-ttu-id="598c2-109">Les appelants bloqués peuvent avoir des comportements légèrement différents lorsqu’ils ont été bloqués.</span><span class="sxs-lookup"><span data-stu-id="598c2-109">Blocked callers may experience slightly different behaviors when they have been blocked.</span></span> <span data-ttu-id="598c2-110">Le comportement est basé sur la façon dont l’opérateur de l’appelant bloqué gère la notification que l’appel n’est pas autorisé à se terminer correctement.</span><span class="sxs-lookup"><span data-stu-id="598c2-110">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="598c2-111">Il peut s’agir, par exemple, d’un message de l’opérateur indiquant que l’appel ne peut pas être effectué comme un appel composé, ou un simple abandon de l’appel.</span><span class="sxs-lookup"><span data-stu-id="598c2-111">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="598c2-112">Appel bloquant les contrôles d’administration et les informations</span><span class="sxs-lookup"><span data-stu-id="598c2-112">Call blocking admin controls and information</span></span>

<span data-ttu-id="598c2-113">Les contrôles d’administration pour le blocage des numéros sont fournis à l’aide de PowerShell uniquement.</span><span class="sxs-lookup"><span data-stu-id="598c2-113">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="598c2-114">Les modèles de blocs de nombres sont définis en tant que modèles d’expression régulière.</span><span class="sxs-lookup"><span data-stu-id="598c2-114">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="598c2-115">L’ordre des expressions n’est pasimportant : le premier modèle de la liste a pour résultat le blocage de l’appel.</span><span class="sxs-lookup"><span data-stu-id="598c2-115">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="598c2-116">L’activité d’un nouveau numéro ou modèle ajouté ou supprimé dans la liste des appelants bloqués peut prendre jusqu’à 24 heures.</span><span class="sxs-lookup"><span data-stu-id="598c2-116">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="598c2-117">Appel bloquant les commandes PowerShell</span><span class="sxs-lookup"><span data-stu-id="598c2-117">Call blocking PowerShell commands</span></span>

<span data-ttu-id="598c2-118">Les modèles de nombres sont ```CsInboundBlockedNumberPattern``` gérés par le biais ```New``` des ```Get``` ```Set``` commandes, et ```Remove``` .</span><span class="sxs-lookup"><span data-stu-id="598c2-118">Number patterns are managed through the ```CsInboundBlockedNumberPattern``` commands ```New```, ```Get```, ```Set```, and ```Remove```.</span></span> <span data-ttu-id="598c2-119">Vous pouvez gérer un modèle donné à l’aide de ces cmdlets, y compris la possibilité d’activer un modèle donné.</span><span class="sxs-lookup"><span data-stu-id="598c2-119">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>
- <span data-ttu-id="598c2-120">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) renvoie la liste de tous les modèles de numéro bloqués ajoutés à la liste des locataires, y compris Nom, Description, Activé (Vrai/Faux) et Modèle pour chacun d’eux.</span><span class="sxs-lookup"><span data-stu-id="598c2-120">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="598c2-121">[New-CsInboundBlockedNumberPattern ajoute](/powershell/module/skype/new-csinboundblockednumberpattern) un modèle de numéro bloqué à la liste des locataires.</span><span class="sxs-lookup"><span data-stu-id="598c2-121">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="598c2-122">[Remove-CsInboundBlockedNumberPattern supprime](/powershell/module/skype/remove-csinboundblockednumberpattern) un modèle de numéro bloqué de la liste des locataires.</span><span class="sxs-lookup"><span data-stu-id="598c2-122">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="598c2-123">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifie un ou plusieurs paramètres d’un modèle de nombre bloqué dans la liste des locataires.</span><span class="sxs-lookup"><span data-stu-id="598c2-123">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="598c2-124">L’affichage et l’activation de l’ensemble de la fonctionnalité de blocage d’appel sont ```CsTenantBlockingCallingNumbers``` gérés par le biais des commandes ```Get``` et ```Set``` .</span><span class="sxs-lookup"><span data-stu-id="598c2-124">Viewing and activating the entire call blocking feature is managed through the ```CsTenantBlockingCallingNumbers``` commands ```Get``` and ```Set```.</span></span>

- <span data-ttu-id="598c2-125">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) renvoie les paramètres de la liste des nombres bloqués globaux, y compris Activé (True/False).</span><span class="sxs-lookup"><span data-stu-id="598c2-125">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="598c2-126">Il existe une seule stratégie de client globale qui ne peut pas être modifiée manuellement si ce n’est pour activer ou désactiver la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="598c2-126">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="598c2-127">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) permet d’autoriser ou non la modification des appels bloqués du client global au niveau du client.</span><span class="sxs-lookup"><span data-stu-id="598c2-127">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="598c2-128">Exemples</span><span class="sxs-lookup"><span data-stu-id="598c2-128">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="598c2-129">Bloquer un numéro</span><span class="sxs-lookup"><span data-stu-id="598c2-129">Block a number</span></span>

<span data-ttu-id="598c2-130">Dans cet exemple, les ```-Enabled``` ```-Description``` paramètres et les paramètres sont facultatifs :</span><span class="sxs-lookup"><span data-stu-id="598c2-130">In this example, the ```-Enabled``` and ```-Description``` parameters are optional:</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="598c2-131">La création d’un modèle ajoute le modèle comme étant activé par défaut.</span><span class="sxs-lookup"><span data-stu-id="598c2-131">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="598c2-132">La description est un champ facultatif pour fournir des informations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="598c2-132">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="598c2-133">Nous vous recommandons de fournir un nom significatif pour comprendre facilement pourquoi le modèle a été ajouté.</span><span class="sxs-lookup"><span data-stu-id="598c2-133">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="598c2-134">Si vous bloquez simplement les numéros de courrier indésirable, envisagez d’nommer la règle de la même façon que le modèle de nombre qui correspond et d’ajouter des informations supplémentaires dans la description si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="598c2-134">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="598c2-135">Les modèles sont assortis à l’aide d’expressions régulières (Regex).</span><span class="sxs-lookup"><span data-stu-id="598c2-135">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="598c2-136">Autorisez le temps de réplication avant de tester et de valider.</span><span class="sxs-lookup"><span data-stu-id="598c2-136">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="598c2-137">Autoriser un numéro</span><span class="sxs-lookup"><span data-stu-id="598c2-137">Allow a number</span></span>

<span data-ttu-id="598c2-138">Dans cet exemple, le ```-Identity``` paramètre est obligatoire :</span><span class="sxs-lookup"><span data-stu-id="598c2-138">In this example, the ```-Identity``` parameter is required:</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="598c2-139">Si l’identité n’est pas connue, utilisez l’cmdlet pour identifier le modèle approprié ```Get-CsInboundBlockedNumberPattern``` et noter l’identité.</span><span class="sxs-lookup"><span data-stu-id="598c2-139">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="598c2-140">Ensuite, exécutez la ```Remove-CsTenantBlockedNumberPattern``` cmdlet et transmettre la valeur d’identité appropriée.</span><span class="sxs-lookup"><span data-stu-id="598c2-140">Then, run the ```Remove-CsTenantBlockedNumberPattern``` cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="598c2-141">Autorisez le temps de réplication avant de tester et de valider.</span><span class="sxs-lookup"><span data-stu-id="598c2-141">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="598c2-142">Afficher tous les modèles de nombres</span><span class="sxs-lookup"><span data-stu-id="598c2-142">View all number patterns</span></span>

<span data-ttu-id="598c2-143">L’exécution de cette cmdlet renvoie la liste de tous les numéros bloqués entrés pour un client :</span><span class="sxs-lookup"><span data-stu-id="598c2-143">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="598c2-144">Utilisez les capacités intégrées de filtrage PowerShell pour filtrer les valeurs renvoyées comme requis.</span><span class="sxs-lookup"><span data-stu-id="598c2-144">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="598c2-145">Ajouter des exceptions de nombre</span><span class="sxs-lookup"><span data-stu-id="598c2-145">Add number exceptions</span></span>

<span data-ttu-id="598c2-146">Vous pouvez ajouter des exceptions aux modèles de nombres bloqués via les ```CsTenantBlockNumberExceptionPattern``` ```New``` ```Get``` commandes, ```Set``` et ```Remove``` .</span><span class="sxs-lookup"><span data-stu-id="598c2-146">You can add exceptions to blocked number patterns through the ```CsTenantBlockNumberExceptionPattern``` commands, ```New```, ```Get```, ```Set```, and ```Remove```.</span></span>

- <span data-ttu-id="598c2-147">[New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) ajoute un modèle d’exception de nombre à la liste des locataires.</span><span class="sxs-lookup"><span data-stu-id="598c2-147">[New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="598c2-148">[Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) renvoie la liste de tous les modèles d’exceptions de nombres ajoutés à la liste des locataires.</span><span class="sxs-lookup"><span data-stu-id="598c2-148">[Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="598c2-149">[Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifie un ou plusieurs paramètres en un ou plusieurs paramètres d’exception dans la liste des locataires.</span><span class="sxs-lookup"><span data-stu-id="598c2-149">[Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="598c2-150">[Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) supprime un modèle d’exception de nombre de la liste des locataires.</span><span class="sxs-lookup"><span data-stu-id="598c2-150">[Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="598c2-151">Exemples</span><span class="sxs-lookup"><span data-stu-id="598c2-151">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="598c2-152">Ajouter une exception</span><span class="sxs-lookup"><span data-stu-id="598c2-152">Add a number exception</span></span>

<span data-ttu-id="598c2-153">Dans cet exemple, un nouveau modèle d’exception de nombre est créé et l’ajoutera par défaut comme étant activé.</span><span class="sxs-lookup"><span data-stu-id="598c2-153">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="598c2-154">Les ```-Enabled``` ```-Description``` paramètres et les paramètres sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="598c2-154">The ```-Enabled``` and ```-Description``` parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="598c2-155">Afficher toutes les exceptions de nombre</span><span class="sxs-lookup"><span data-stu-id="598c2-155">View all number exceptions</span></span>

<span data-ttu-id="598c2-156">Dans cet exemple, le paramètre -Identity est facultatif.</span><span class="sxs-lookup"><span data-stu-id="598c2-156">In this example, the -Identity parameter is optional.</span></span> <span data-ttu-id="598c2-157">Si le paramètre n’est pas spécifié, cette cmdlet renvoie la liste de tous les ```-Identity``` modèles d’exceptions de nombre entrés pour un client.</span><span class="sxs-lookup"><span data-stu-id="598c2-157">If the ```-Identity``` parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="598c2-158">Modifier une exception de nombre</span><span class="sxs-lookup"><span data-stu-id="598c2-158">Modify a number exception</span></span>

<span data-ttu-id="598c2-159">Dans cet exemple, le paramètre -Identity est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="598c2-159">In this example, the -Identity parameter is mandatory.</span></span> <span data-ttu-id="598c2-160">```Set-CsTenantBlockedNumberExceptionPattern```L’cmdlet vous permet de modifier un ou plusieurs paramètres pour une identité de modèle de nombre donnée.</span><span class="sxs-lookup"><span data-stu-id="598c2-160">The ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="598c2-161">Supprimer une exception</span><span class="sxs-lookup"><span data-stu-id="598c2-161">Remove a number exception</span></span>

<span data-ttu-id="598c2-162">Dans cet exemple, le ```-Identity``` paramètre est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="598c2-162">In this example, the ```-Identity``` parameter is required.</span></span> <span data-ttu-id="598c2-163">Cette cmdlet supprime le modèle de numéro donné de la liste des locataires.</span><span class="sxs-lookup"><span data-stu-id="598c2-163">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="598c2-164">Si l’identité n’est pas connue, utilisez l’cmdlet pour identifier le modèle approprié ```Get-CsInboundBlockedNumberPattern``` et noter l’identité.</span><span class="sxs-lookup"><span data-stu-id="598c2-164">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="598c2-165">Ensuite, exécutez la ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet et transmettre la valeur d’identité appropriée.</span><span class="sxs-lookup"><span data-stu-id="598c2-165">Then, run the ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="598c2-166">Autorisez le temps de réplication avant de tester et de valider.</span><span class="sxs-lookup"><span data-stu-id="598c2-166"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="598c2-167">Vérifier si un nombre est bloqué</span><span class="sxs-lookup"><span data-stu-id="598c2-167">Test whether a number is blocked</span></span>

<span data-ttu-id="598c2-168">Utilisez ```Test-CsInboundBlockedNumberPattern``` l’cmdlet pour vérifier si un numéro est bloqué dans le client.</span><span class="sxs-lookup"><span data-stu-id="598c2-168">Use the ```Test-CsInboundBlockedNumberPattern``` cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="598c2-169">Dans cet exemple, les ```-Phonenumber``` ```-Tenant``` paramètres sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="598c2-169">In this example, the ```-Phonenumber``` and ```-Tenant``` parameters are required.</span></span> <span data-ttu-id="598c2-170">Le paramètre doit être une chaîne numérique sans caractères supplémentaires tels que ```-PhoneNumber``` + ou -.</span><span class="sxs-lookup"><span data-stu-id="598c2-170">The ```-PhoneNumber``` parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="598c2-171">Dans le TRPS, ```-Tenant parameter``` l’option est facultative.</span><span class="sxs-lookup"><span data-stu-id="598c2-171">In TRPS, the ```-Tenant parameter``` is optional.</span></span> <span data-ttu-id="598c2-172">Le paramètre qui en résulte renvoie la valeur True si le nombre est bloqué dans le client et ```isNumberBlocked``` False s’il n’est pas bloqué.</span><span class="sxs-lookup"><span data-stu-id="598c2-172">The resulting ```isNumberBlocked``` parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="598c2-173">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="598c2-173">httpResponseCode</span></span>  |<span data-ttu-id="598c2-174">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="598c2-174">isNumberBlocked</span></span>   |<span data-ttu-id="598c2-175">errorMessage</span><span class="sxs-lookup"><span data-stu-id="598c2-175">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="598c2-176">200</span><span class="sxs-lookup"><span data-stu-id="598c2-176">200</span></span>    | <span data-ttu-id="598c2-177">Vrai</span><span class="sxs-lookup"><span data-stu-id="598c2-177">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="598c2-178">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="598c2-178">httpResponseCode</span></span>  |<span data-ttu-id="598c2-179">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="598c2-179">isNumberBlocked</span></span>   |<span data-ttu-id="598c2-180">errorMessage</span><span class="sxs-lookup"><span data-stu-id="598c2-180">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="598c2-181">200</span><span class="sxs-lookup"><span data-stu-id="598c2-181">200</span></span>    | <span data-ttu-id="598c2-182">False</span><span class="sxs-lookup"><span data-stu-id="598c2-182">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="598c2-183">Note sur Regex</span><span class="sxs-lookup"><span data-stu-id="598c2-183">A note about Regex</span></span>

<span data-ttu-id="598c2-184">Comme indiqué précédemment, la correspondance au modèle de blocage des appelants est effectuée à l’aide de Regex.</span><span class="sxs-lookup"><span data-stu-id="598c2-184">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="598c2-185">Plusieurs outils sont disponibles en ligne pour vous aider à valider une correspondance de modèle Regex.</span><span class="sxs-lookup"><span data-stu-id="598c2-185">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="598c2-186">Si vous n’êtes pas familiarisé avec les modèles Regex, nous vous recommandons de prendre le temps de vous familiariser avec les bases.</span><span class="sxs-lookup"><span data-stu-id="598c2-186">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="598c2-187">Pour vous assurer d’obtenir les résultats attendus, utilisez un outil pour valider les correspondances de modèle avant d’ajouter de nouveaux nombres bloqués à votre client.</span><span class="sxs-lookup"><span data-stu-id="598c2-187">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="598c2-188">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="598c2-188">Related topics</span></span>

- [<span data-ttu-id="598c2-189">Configurer votre ordinateur pour gérer Skype Entreprise Online à l’aide d’Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="598c2-189">Set up your computer to manage Skype for Business Online by using Windows PowerShell</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)