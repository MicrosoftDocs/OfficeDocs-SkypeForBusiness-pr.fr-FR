---
title: Bloquer les appels entrants dans Skype entreprise Online
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: b238d69087c5b29e6d9abc898e91c44fd8053411
ms.sourcegitcommit: bb88ac0c9489bb47957e5ef1074b5df3126b6fdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266063"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="d35d5-102">Bloquer les appels entrants</span><span class="sxs-lookup"><span data-stu-id="d35d5-102">Block inbound calls</span></span>

<span data-ttu-id="d35d5-103">Les abonnements Skype entreprise Online prennent désormais en charge le blocage d’appels entrants du réseau téléphonique public commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="d35d5-103">Skype for Business Online Calling Plans now supports blocking of inbound calls from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="d35d5-104">Cette fonctionnalité permet de définir une liste globale de clients de modèles de nombre de manière à ce que l’ID d’appelant de chaque appel RTC entrant au client puisse être vérifié par rapport à la liste de correspondance.</span><span class="sxs-lookup"><span data-stu-id="d35d5-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="d35d5-105">Si une correspondance est établie, un appel entrant est rejeté.</span><span class="sxs-lookup"><span data-stu-id="d35d5-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="d35d5-106">Cette fonctionnalité de blocage des appels entrants ne fonctionne que sur les appels entrants provenant du RTC et ne fonctionne que sur une base globale du client.</span><span class="sxs-lookup"><span data-stu-id="d35d5-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="d35d5-107">Cette fonction n’est pas disponible par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d35d5-107">It's not available on a per-user basis.</span></span>  

<span data-ttu-id="d35d5-108">Cette fonctionnalité n’est pas encore disponible pour le routage direct.</span><span class="sxs-lookup"><span data-stu-id="d35d5-108">This feature isn't yet available for Direct Routing.</span></span>

>[!NOTE]
> <span data-ttu-id="d35d5-109">Les appelants bloqués peuvent avoir un comportement légèrement différent lorsqu’ils sont bloqués.</span><span class="sxs-lookup"><span data-stu-id="d35d5-109">Blocked callers may experience slightly different behaviors when they have been blocked.</span></span> <span data-ttu-id="d35d5-110">Ce comportement dépend de la façon dont le transporteur de l’appelant bloqué gère la notification d’échec de l’appel.</span><span class="sxs-lookup"><span data-stu-id="d35d5-110">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="d35d5-111">Par exemple, vous pouvez inclure un message de transporteur indiquant que l’appel ne peut pas être effectué comme composé, ou simplement en déposant un appel.</span><span class="sxs-lookup"><span data-stu-id="d35d5-111">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="d35d5-112">Appels et contrôles d’administration de blocage</span><span class="sxs-lookup"><span data-stu-id="d35d5-112">Call blocking admin controls and information</span></span>

<span data-ttu-id="d35d5-113">Les contrôles d’administration pour bloquer les numéros sont fournis uniquement via PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d35d5-113">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="d35d5-114">Les modèles de blocs de nombres sont définis en tant que modèles d’expressions normales.</span><span class="sxs-lookup"><span data-stu-id="d35d5-114">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="d35d5-115">L’ordre des expressions n’est pas important : le premier modèle correspondant dans la liste entraîne le blocage de l’appel.</span><span class="sxs-lookup"><span data-stu-id="d35d5-115">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="d35d5-116">Un nouveau numéro ou modèle ajouté ou supprimé dans la liste des appelants bloqués peut prendre jusqu’à 24 heures avant que le modèle soit actif.</span><span class="sxs-lookup"><span data-stu-id="d35d5-116">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="d35d5-117">Commandes PowerShell de blocage des appels</span><span class="sxs-lookup"><span data-stu-id="d35d5-117">Call blocking PowerShell commands</span></span>

<span data-ttu-id="d35d5-118">Les modèles de nombre sont gérés ```CsInboundBlockedNumberPattern``` par ```New```le ```Get```biais ```Set```des commandes ```Remove```,, et.</span><span class="sxs-lookup"><span data-stu-id="d35d5-118">Number patterns are managed through the ```CsInboundBlockedNumberPattern``` commands ```New```, ```Get```, ```Set```, and ```Remove```.</span></span> <span data-ttu-id="d35d5-119">Vous pouvez gérer un modèle donné à l’aide de ces applets de option, y compris la possibilité de basculer entre les activations d’un modèle donné.</span><span class="sxs-lookup"><span data-stu-id="d35d5-119">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>
- <span data-ttu-id="d35d5-120">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) renvoie la liste de tous les modèles de numéros bloqués ajoutés à la liste des clients, y compris le nom, la description, l’activation (vrai/faux) et le modèle pour chacun d’eux.</span><span class="sxs-lookup"><span data-stu-id="d35d5-120">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="d35d5-121">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) ajoute un modèle de numéro bloqué à la liste des clients.</span><span class="sxs-lookup"><span data-stu-id="d35d5-121">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="d35d5-122">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) supprime un modèle de numéro bloqué de la liste des clients.</span><span class="sxs-lookup"><span data-stu-id="d35d5-122">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="d35d5-123">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifie un ou plusieurs paramètres d’un modèle de numéro bloqué dans la liste des clients.</span><span class="sxs-lookup"><span data-stu-id="d35d5-123">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="d35d5-124">L’affichage et l’activation de la fonctionnalité de blocage des appels complet ```CsTenantBlockingCallingNumbers``` est ```Get``` géré ```Set```via les commandes et.</span><span class="sxs-lookup"><span data-stu-id="d35d5-124">Viewing and activating the entire call blocking feature is managed through the ```CsTenantBlockingCallingNumbers``` commands ```Get``` and ```Set```.</span></span>

- <span data-ttu-id="d35d5-125">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) renvoie les paramètres de la liste globale des numéros bloqués, y compris activé (vrai/faux).</span><span class="sxs-lookup"><span data-stu-id="d35d5-125">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="d35d5-126">Il existe une seule stratégie de client globale qui ne peut pas être modifiée manuellement en dehors de l’activation ou de la désactivation de la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="d35d5-126">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="d35d5-127">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) autorise la modification de l’activation et de la désactivation des appels du client global au niveau du client.</span><span class="sxs-lookup"><span data-stu-id="d35d5-127">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="d35d5-128">Exemples</span><span class="sxs-lookup"><span data-stu-id="d35d5-128">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="d35d5-129">Bloquer un numéro</span><span class="sxs-lookup"><span data-stu-id="d35d5-129">Block a number</span></span>

<span data-ttu-id="d35d5-130">Dans cet exemple, les ```-Enabled``` paramètres ```-Description``` et sont facultatifs :</span><span class="sxs-lookup"><span data-stu-id="d35d5-130">In this example, the ```-Enabled``` and ```-Description``` parameters are optional:</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="d35d5-131">La création d’un nouveau modèle ajoute le modèle tel qu’il est activé par défaut.</span><span class="sxs-lookup"><span data-stu-id="d35d5-131">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="d35d5-132">La description est un champ facultatif pour fournir des informations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="d35d5-132">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="d35d5-133">Nous vous recommandons de fournir un nom significatif pour comprendre facilement la raison pour laquelle le modèle a été ajouté.</span><span class="sxs-lookup"><span data-stu-id="d35d5-133">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="d35d5-134">Dans le cas d’un simple blocage des numéros de courrier indésirable, attribuez-lui le même nom que le modèle de nombre que vous avez mis en correspondance et ajoutez des informations supplémentaires dans la description, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="d35d5-134">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="d35d5-135">Les modèles sont associés à l’aide d’expressions régulières (Regex).</span><span class="sxs-lookup"><span data-stu-id="d35d5-135">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="d35d5-136">Autorisez le temps de réplication avant de tester et de valider.</span><span class="sxs-lookup"><span data-stu-id="d35d5-136">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="d35d5-137">Autoriser un numéro</span><span class="sxs-lookup"><span data-stu-id="d35d5-137">Allow a number</span></span>

<span data-ttu-id="d35d5-138">Dans cet exemple, le ```-Identity``` paramètre est requis :</span><span class="sxs-lookup"><span data-stu-id="d35d5-138">In this example, the ```-Identity``` parameter is required:</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="d35d5-139">Si l’identité n’est pas connue, ```Get-CsInboundBlockedNumberPattern``` utilisez la cmdlet pour rechercher d’abord le modèle approprié et notez l’identité.</span><span class="sxs-lookup"><span data-stu-id="d35d5-139">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="d35d5-140">Ensuite, exécutez l' ```Remove-CsTenantBlockedNumberPattern``` applet de cmdlet et transmettez la valeur d’identité appropriée.</span><span class="sxs-lookup"><span data-stu-id="d35d5-140">Then, run the ```Remove-CsTenantBlockedNumberPattern``` cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="d35d5-141">Autorisez le temps de réplication avant de tester et de valider.</span><span class="sxs-lookup"><span data-stu-id="d35d5-141">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="d35d5-142">Afficher tous les modèles de nombre</span><span class="sxs-lookup"><span data-stu-id="d35d5-142">View all number patterns</span></span>

<span data-ttu-id="d35d5-143">L’exécution de cette cmdlet renvoie la liste de tous les numéros bloqués entrés pour un client :</span><span class="sxs-lookup"><span data-stu-id="d35d5-143">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="d35d5-144">Utilisez des capacités de filtrage PowerShell intégrées pour analyser les valeurs renvoyées selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="d35d5-144">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="d35d5-145">Ajouter des exceptions de nombre</span><span class="sxs-lookup"><span data-stu-id="d35d5-145">Add number exceptions</span></span>

<span data-ttu-id="d35d5-146">Vous pouvez ajouter des exceptions aux modèles de nombre bloqués par ```New```le ```Get```biais ```Set```des ```CsTenantBlockNumberExceptionPattern``` commandes ```Remove```,,, et.</span><span class="sxs-lookup"><span data-stu-id="d35d5-146">You can add exceptions to blocked number patterns through the ```CsTenantBlockNumberExceptionPattern``` commands, ```New```, ```Get```, ```Set```, and ```Remove```.</span></span>

- <span data-ttu-id="d35d5-147">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) ajoute un modèle d’exception numérique à la liste de clients.</span><span class="sxs-lookup"><span data-stu-id="d35d5-147">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="d35d5-148">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) renvoie la liste de tous les modèles d’exception de nombre ajoutés à la liste des clients.</span><span class="sxs-lookup"><span data-stu-id="d35d5-148">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="d35d5-149">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifie un ou plusieurs paramètres en un modèle d’exception numérique dans la liste des clients.</span><span class="sxs-lookup"><span data-stu-id="d35d5-149">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="d35d5-150">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) supprime un modèle d’exception numérique de la liste des clients.</span><span class="sxs-lookup"><span data-stu-id="d35d5-150">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="d35d5-151">Exemples</span><span class="sxs-lookup"><span data-stu-id="d35d5-151">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="d35d5-152">Ajouter une exception de nombre</span><span class="sxs-lookup"><span data-stu-id="d35d5-152">Add a number exception</span></span>

<span data-ttu-id="d35d5-153">Dans cet exemple, un nouveau modèle d’exception de nombre est créé et il ajoute par défaut le modèle est activé.</span><span class="sxs-lookup"><span data-stu-id="d35d5-153">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="d35d5-154">Les ```-Enabled``` paramètres ```-Description``` et sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="d35d5-154">The ```-Enabled``` and ```-Description``` parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="d35d5-155">Afficher toutes les exceptions d’une numérotation</span><span class="sxs-lookup"><span data-stu-id="d35d5-155">View all number exceptions</span></span>

<span data-ttu-id="d35d5-156">Dans cet exemple, le paramètre-Identity est facultatif.</span><span class="sxs-lookup"><span data-stu-id="d35d5-156">In this example, the -Identity parameter is optional.</span></span> <span data-ttu-id="d35d5-157">Si le ```-Identity``` paramètre n’est pas spécifié, cette applet de cmdlet renvoie une liste de tous les modèles d’exception de nombre entrés pour un client.</span><span class="sxs-lookup"><span data-stu-id="d35d5-157">If the ```-Identity``` parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="d35d5-158">Modifier une exception de nombre</span><span class="sxs-lookup"><span data-stu-id="d35d5-158">Modify a number exception</span></span>

<span data-ttu-id="d35d5-159">Dans cet exemple, le paramètre-Identity est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="d35d5-159">In this example, the -Identity parameter is mandatory.</span></span> <span data-ttu-id="d35d5-160">L' ```Set-CsTenantBlockedNumberExceptionPattern``` applet de passe vous permet de modifier un ou plusieurs paramètres pour une identité de modèle de nombre donnée.</span><span class="sxs-lookup"><span data-stu-id="d35d5-160">The ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="d35d5-161">Supprimer un numéro d’exception</span><span class="sxs-lookup"><span data-stu-id="d35d5-161">Remove a number exception</span></span>

<span data-ttu-id="d35d5-162">Dans cet exemple, le ```-Identity``` paramètre est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="d35d5-162">In this example, the ```-Identity``` parameter is required.</span></span> <span data-ttu-id="d35d5-163">Cette applet de passe supprime le modèle de nombre indiqué de la liste des clients.</span><span class="sxs-lookup"><span data-stu-id="d35d5-163">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="d35d5-164">Si l’identité n’est pas connue, ```Get-CsInboundBlockedNumberPattern``` utilisez la cmdlet pour rechercher d’abord le modèle approprié et notez l’identité.</span><span class="sxs-lookup"><span data-stu-id="d35d5-164">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="d35d5-165">Ensuite, exécutez l' ```Remove-CsTenantBlockedNumberExceptionPattern``` applet de cmdlet et transmettez la valeur d’identité appropriée.</span><span class="sxs-lookup"><span data-stu-id="d35d5-165">Then, run the ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="d35d5-166">Autorisez le temps de réplication avant de tester et de valider.</span><span class="sxs-lookup"><span data-stu-id="d35d5-166"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="d35d5-167">Tester la présence d’un numéro bloqué</span><span class="sxs-lookup"><span data-stu-id="d35d5-167">Test whether a number is blocked</span></span>

<span data-ttu-id="d35d5-168">Utilisez l' ```Test-CsInboundBlockedNumberPattern``` applet de contrôle pour vérifier si un numéro est bloqué dans le client.</span><span class="sxs-lookup"><span data-stu-id="d35d5-168">Use the ```Test-CsInboundBlockedNumberPattern``` cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="d35d5-169">Dans cet exemple, les ```-Phonenumber``` paramètres ```-Tenant``` et sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="d35d5-169">In this example, the ```-Phonenumber``` and ```-Tenant``` parameters are required.</span></span> <span data-ttu-id="d35d5-170">Le ```-PhoneNumber``` paramètre doit être une chaîne numérique sans caractère supplémentaire, comme + ou-.</span><span class="sxs-lookup"><span data-stu-id="d35d5-170">The ```-PhoneNumber``` parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="d35d5-171">Dans TRPS, ```-Tenant parameter``` est facultatif.</span><span class="sxs-lookup"><span data-stu-id="d35d5-171">In TRPS, the ```-Tenant parameter``` is optional.</span></span> <span data-ttu-id="d35d5-172">Le paramètre ```isNumberBlocked``` obtenu renvoie la valeur vrai si le nombre est bloqué dans le client et faux s’il n’est pas bloqué.</span><span class="sxs-lookup"><span data-stu-id="d35d5-172">The resulting ```isNumberBlocked``` parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="d35d5-173">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="d35d5-173">httpResponseCode</span></span>  |<span data-ttu-id="d35d5-174">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="d35d5-174">isNumberBlocked</span></span>   |<span data-ttu-id="d35d5-175">errorMessage</span><span class="sxs-lookup"><span data-stu-id="d35d5-175">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d35d5-176">200</span><span class="sxs-lookup"><span data-stu-id="d35d5-176">200</span></span>    | <span data-ttu-id="d35d5-177">Vrai</span><span class="sxs-lookup"><span data-stu-id="d35d5-177">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="d35d5-178">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="d35d5-178">httpResponseCode</span></span>  |<span data-ttu-id="d35d5-179">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="d35d5-179">isNumberBlocked</span></span>   |<span data-ttu-id="d35d5-180">errorMessage</span><span class="sxs-lookup"><span data-stu-id="d35d5-180">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d35d5-181">200</span><span class="sxs-lookup"><span data-stu-id="d35d5-181">200</span></span>    | <span data-ttu-id="d35d5-182">False</span><span class="sxs-lookup"><span data-stu-id="d35d5-182">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="d35d5-183">Note concernant Regex</span><span class="sxs-lookup"><span data-stu-id="d35d5-183">A note about Regex</span></span>

<span data-ttu-id="d35d5-184">Comme indiqué plus haut, le modèle correspondant au blocage des appelants est réalisé à l’aide de Regex.</span><span class="sxs-lookup"><span data-stu-id="d35d5-184">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="d35d5-185">Plusieurs outils sont disponibles en ligne pour vous aider à valider une correspondance de modèle Regex.</span><span class="sxs-lookup"><span data-stu-id="d35d5-185">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="d35d5-186">Si vous n’êtes pas familiarisé avec les modèles Regex, nous vous conseillons de prendre le temps de vous familiariser avec les concepts de base.</span><span class="sxs-lookup"><span data-stu-id="d35d5-186">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="d35d5-187">Pour vous assurer que vous obtenez les résultats attendus, utilisez un outil permettant de valider les correspondances de modèles avant d’ajouter le nouveau numéro bloqué à votre client.</span><span class="sxs-lookup"><span data-stu-id="d35d5-187">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="d35d5-188">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="d35d5-188">Related topics</span></span>

- [<span data-ttu-id="d35d5-189">Configurer votre ordinateur pour gérer Skype entreprise Online à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d35d5-189">Set up your computer to manage Skype for Business Online by using Windows PowerShell</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
