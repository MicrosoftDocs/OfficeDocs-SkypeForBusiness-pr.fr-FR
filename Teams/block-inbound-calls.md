---
title: Bloquer les appels entrants dans Microsoft teams
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 3bb1222f0662228e5c0de7b2253cbac162571b1e
ms.sourcegitcommit: a36514c7c8ea47bde4edb09c11ff99061b1f74c0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094680"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="011ab-102">Bloquer les appels entrants</span><span class="sxs-lookup"><span data-stu-id="011ab-102">Block inbound calls</span></span>

<span data-ttu-id="011ab-103">Le système téléphonique et les offres d’appels prennent en charge le blocage des appels entrants du réseau téléphonique public commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="011ab-103">Phone System Direct Routing and Calling Plans support blocking inbound calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="011ab-104">Cette fonctionnalité permet de définir une liste globale de clients de modèles de nombre de manière à ce que l’ID d’appelant de chaque appel RTC entrant au client puisse être vérifié par rapport à la liste de correspondance.</span><span class="sxs-lookup"><span data-stu-id="011ab-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="011ab-105">Si une correspondance est établie, un appel entrant est rejeté.</span><span class="sxs-lookup"><span data-stu-id="011ab-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="011ab-106">Cette fonctionnalité de blocage des appels entrants ne fonctionne que sur les appels entrants provenant du RTC et ne fonctionne que sur une base globale du client.</span><span class="sxs-lookup"><span data-stu-id="011ab-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="011ab-107">Cette fonction n’est pas disponible par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="011ab-107">It's not available on a per-user basis.</span></span>  

>[!NOTE]
> <span data-ttu-id="011ab-108">Les appelants bloqués peuvent avoir un comportement légèrement différent lorsqu’ils sont bloqués.</span><span class="sxs-lookup"><span data-stu-id="011ab-108">Blocked callers may experience slightly different behaviors when they've been blocked.</span></span> <span data-ttu-id="011ab-109">Ce comportement dépend de la façon dont le transporteur de l’appelant bloqué gère la notification d’échec de l’appel.</span><span class="sxs-lookup"><span data-stu-id="011ab-109">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="011ab-110">Par exemple, vous pouvez inclure un message de transporteur indiquant que l’appel ne peut pas être effectué comme composé, ou simplement en déposant un appel.</span><span class="sxs-lookup"><span data-stu-id="011ab-110">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="011ab-111">Appels et contrôles d’administration de blocage</span><span class="sxs-lookup"><span data-stu-id="011ab-111">Call blocking admin controls and information</span></span>

<span data-ttu-id="011ab-112">Les contrôles d’administration pour bloquer les numéros sont fournis uniquement via PowerShell.</span><span class="sxs-lookup"><span data-stu-id="011ab-112">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="011ab-113">Les modèles de blocs de nombres sont définis en tant que modèles d’expressions normales.</span><span class="sxs-lookup"><span data-stu-id="011ab-113">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="011ab-114">L’ordre des expressions n’est pas important : le premier modèle correspondant dans la liste entraîne le blocage de l’appel.</span><span class="sxs-lookup"><span data-stu-id="011ab-114">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="011ab-115">Un nouveau numéro ou modèle ajouté ou supprimé dans la liste des appelants bloqués peut prendre jusqu’à 24 heures avant que le modèle soit actif.</span><span class="sxs-lookup"><span data-stu-id="011ab-115">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="011ab-116">Commandes PowerShell de blocage des appels</span><span class="sxs-lookup"><span data-stu-id="011ab-116">Call blocking PowerShell commands</span></span>

<span data-ttu-id="011ab-117">Vous pouvez gérer les modèles de nombre à l’aide des **nouvelles**cmdlets **Get**, **Set**et **Remove**  - **CsInboundBlockedNumberPattern** .</span><span class="sxs-lookup"><span data-stu-id="011ab-117">You manage number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsInboundBlockedNumberPattern** cmdlets.</span></span> <span data-ttu-id="011ab-118">Vous pouvez gérer un modèle donné à l’aide de ces applets de option, y compris la possibilité de basculer entre les activations d’un modèle donné.</span><span class="sxs-lookup"><span data-stu-id="011ab-118">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>

- <span data-ttu-id="011ab-119">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) renvoie la liste de tous les modèles de numéros bloqués ajoutés à la liste des clients, y compris le nom, la description, l’activation (vrai/faux) et le modèle pour chacun d’eux.</span><span class="sxs-lookup"><span data-stu-id="011ab-119">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="011ab-120">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) ajoute un modèle de numéro bloqué à la liste des clients.</span><span class="sxs-lookup"><span data-stu-id="011ab-120">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="011ab-121">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) supprime un modèle de numéro bloqué de la liste des clients.</span><span class="sxs-lookup"><span data-stu-id="011ab-121">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="011ab-122">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifie un ou plusieurs paramètres d’un modèle de numéro bloqué dans la liste des clients.</span><span class="sxs-lookup"><span data-stu-id="011ab-122">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="011ab-123">L’affichage et l’activation de la fonctionnalité de blocage des appels complet est géré via les applets de CsTenantBlockingCallingNumbers **Get**et **Set**  - **CsTenantBlockingCallingNumbers** .</span><span class="sxs-lookup"><span data-stu-id="011ab-123">Viewing and activating the entire call blocking feature is managed through the **Get**, **Set** -**CsTenantBlockingCallingNumbers** cmdlets.</span></span>

- <span data-ttu-id="011ab-124">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) renvoie les paramètres de la liste globale des numéros bloqués, y compris activé (vrai/faux).</span><span class="sxs-lookup"><span data-stu-id="011ab-124">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="011ab-125">Il existe une seule stratégie de client globale qui ne peut pas être modifiée manuellement en dehors de l’activation ou de la désactivation de la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="011ab-125">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="011ab-126">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) autorise la modification de l’activation et de la désactivation des appels du client global au niveau du client.</span><span class="sxs-lookup"><span data-stu-id="011ab-126">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="011ab-127">Exemples</span><span class="sxs-lookup"><span data-stu-id="011ab-127">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="011ab-128">Bloquer un numéro</span><span class="sxs-lookup"><span data-stu-id="011ab-128">Block a number</span></span>

<span data-ttu-id="011ab-129">Dans cet exemple, les paramètres **Enabled** et **Description** sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="011ab-129">In this example, the **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="011ab-130">La création d’un nouveau modèle ajoute le modèle tel qu’il est activé par défaut.</span><span class="sxs-lookup"><span data-stu-id="011ab-130">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="011ab-131">La description est un champ facultatif pour fournir des informations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="011ab-131">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="011ab-132">Nous vous recommandons de fournir un nom significatif pour comprendre facilement la raison pour laquelle le modèle a été ajouté.</span><span class="sxs-lookup"><span data-stu-id="011ab-132">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="011ab-133">Dans le cas d’un simple blocage des numéros de courrier indésirable, attribuez-lui le même nom que le modèle de nombre que vous avez mis en correspondance et ajoutez des informations supplémentaires dans la description, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="011ab-133">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="011ab-134">Les modèles sont associés à l’aide d’expressions régulières (Regex).</span><span class="sxs-lookup"><span data-stu-id="011ab-134">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="011ab-135">Autorisez le temps de réplication avant de tester et de valider.</span><span class="sxs-lookup"><span data-stu-id="011ab-135">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="011ab-136">Autoriser un numéro</span><span class="sxs-lookup"><span data-stu-id="011ab-136">Allow a number</span></span>

<span data-ttu-id="011ab-137">Dans cet exemple, le paramètre **Identity** est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="011ab-137">In this example, the **Identity** parameter is required.</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="011ab-138">Si l’identité n’est pas connue, utilisez l’applet de passe **Get-CsInboundBlockedNumberPattern** pour trouver le modèle approprié et noter l’identité.</span><span class="sxs-lookup"><span data-stu-id="011ab-138">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="011ab-139">Ensuite, exécutez l’applet de **CsTenantBlockedNumberPattern de suppression** et transmettez la valeur d’identité appropriée.</span><span class="sxs-lookup"><span data-stu-id="011ab-139">Then, run the **Remove-CsTenantBlockedNumberPattern** cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="011ab-140">Autorisez le temps de réplication avant de tester et de valider.</span><span class="sxs-lookup"><span data-stu-id="011ab-140">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="011ab-141">Afficher tous les modèles de nombre</span><span class="sxs-lookup"><span data-stu-id="011ab-141">View all number patterns</span></span>

<span data-ttu-id="011ab-142">L’exécution de cette cmdlet renvoie la liste de tous les numéros bloqués entrés pour un client :</span><span class="sxs-lookup"><span data-stu-id="011ab-142">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="011ab-143">Utilisez des capacités de filtrage PowerShell intégrées pour analyser les valeurs renvoyées selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="011ab-143">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="011ab-144">Ajouter des exceptions de nombre</span><span class="sxs-lookup"><span data-stu-id="011ab-144">Add number exceptions</span></span>

<span data-ttu-id="011ab-145">Vous pouvez ajouter des exceptions aux modèles de nombre bloqués à l’aide des applets de **nouvelle**applet de CsTenantBlockNumberExceptionPattern, **Get**, **Set**et **Remove**  - **CsTenantBlockNumberExceptionPattern** .</span><span class="sxs-lookup"><span data-stu-id="011ab-145">You can add exceptions to blocked number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsTenantBlockNumberExceptionPattern** cmdlets.</span></span>

- <span data-ttu-id="011ab-146">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) ajoute un modèle d’exception numérique à la liste de clients.</span><span class="sxs-lookup"><span data-stu-id="011ab-146">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="011ab-147">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) renvoie la liste de tous les modèles d’exception de nombre ajoutés à la liste des clients.</span><span class="sxs-lookup"><span data-stu-id="011ab-147">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="011ab-148">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifie un ou plusieurs paramètres en un modèle d’exception numérique dans la liste des clients.</span><span class="sxs-lookup"><span data-stu-id="011ab-148">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="011ab-149">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) supprime un modèle d’exception numérique de la liste des clients.</span><span class="sxs-lookup"><span data-stu-id="011ab-149">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="011ab-150">Exemples</span><span class="sxs-lookup"><span data-stu-id="011ab-150">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="011ab-151">Ajouter une exception de nombre</span><span class="sxs-lookup"><span data-stu-id="011ab-151">Add a number exception</span></span>

<span data-ttu-id="011ab-152">Dans cet exemple, un nouveau modèle d’exception de nombre est créé et il ajoute par défaut le modèle est activé.</span><span class="sxs-lookup"><span data-stu-id="011ab-152">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="011ab-153">Les paramètres **Enabled** et **Description** sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="011ab-153">The **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="011ab-154">Afficher toutes les exceptions d’une numérotation</span><span class="sxs-lookup"><span data-stu-id="011ab-154">View all number exceptions</span></span>

<span data-ttu-id="011ab-155">Dans cet exemple, le paramètre **Identity** est facultatif.</span><span class="sxs-lookup"><span data-stu-id="011ab-155">In this example, the **Identity** parameter is optional.</span></span> <span data-ttu-id="011ab-156">Si le paramètre **Identity** n’est pas spécifié, cette applet de cmdlet renvoie une liste de modèles d’exception de nombre entrés pour un client.</span><span class="sxs-lookup"><span data-stu-id="011ab-156">If the **Identity** parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="011ab-157">Modifier une exception de nombre</span><span class="sxs-lookup"><span data-stu-id="011ab-157">Modify a number exception</span></span>

<span data-ttu-id="011ab-158">Dans cet exemple, le paramètre **Identity** est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="011ab-158">In this example, the **Identity** parameter is mandatory.</span></span> <span data-ttu-id="011ab-159">L’applet **de passe Set-CsTenantBlockedNumberExceptionPattern** vous permet de modifier un ou plusieurs paramètres pour une identité de modèle de nombre donnée.</span><span class="sxs-lookup"><span data-stu-id="011ab-159">The **Set-CsTenantBlockedNumberExceptionPattern** cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="011ab-160">Supprimer un numéro d’exception</span><span class="sxs-lookup"><span data-stu-id="011ab-160">Remove a number exception</span></span>

<span data-ttu-id="011ab-161">Dans cet exemple, le paramètre **Identity** est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="011ab-161">In this example, the **Identity** parameter is required.</span></span> <span data-ttu-id="011ab-162">Cette applet de passe supprime le modèle de nombre indiqué de la liste des clients.</span><span class="sxs-lookup"><span data-stu-id="011ab-162">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="011ab-163">Si l’identité n’est pas connue, utilisez l’applet de passe **Get-CsInboundBlockedNumberPattern** pour trouver le modèle approprié et noter l’identité.</span><span class="sxs-lookup"><span data-stu-id="011ab-163">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="011ab-164">Ensuite, exécutez l’applet de **CsTenantBlockedNumberExceptionPattern de suppression** et transmettez la valeur d’identité appropriée.</span><span class="sxs-lookup"><span data-stu-id="011ab-164">Then, run the **Remove-CsTenantBlockedNumberExceptionPattern** cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="011ab-165">Autorisez le temps de réplication avant de tester et de valider.</span><span class="sxs-lookup"><span data-stu-id="011ab-165"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="011ab-166">Tester la présence d’un numéro bloqué</span><span class="sxs-lookup"><span data-stu-id="011ab-166">Test whether a number is blocked</span></span>

<span data-ttu-id="011ab-167">Utilisez l’applet de **contrôle test-CsInboundBlockedNumberPattern** pour vérifier si un numéro est bloqué dans le client.</span><span class="sxs-lookup"><span data-stu-id="011ab-167">Use the **Test-CsInboundBlockedNumberPattern** cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="011ab-168">Dans cet exemple, les paramètres **PhoneNumber** et **locataire** sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="011ab-168">In this example, the **PhoneNumber** and **Tenant** parameters are required.</span></span> <span data-ttu-id="011ab-169">Le paramètre **PhoneNumber** doit être une chaîne numérique sans caractère supplémentaire, comme + ou-.</span><span class="sxs-lookup"><span data-stu-id="011ab-169">The **PhoneNumber** parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="011ab-170">Dans TRPS, le **paramètre locataire** est facultatif.</span><span class="sxs-lookup"><span data-stu-id="011ab-170">In TRPS, the **Tenant parameter** is optional.</span></span> <span data-ttu-id="011ab-171">Le paramètre **isNumberBlocked** obtenu renvoie la valeur true si le nombre est bloqué dans le locataire et false dans le cas contraire.</span><span class="sxs-lookup"><span data-stu-id="011ab-171">The resulting **isNumberBlocked** parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="011ab-172">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="011ab-172">httpResponseCode</span></span>  |<span data-ttu-id="011ab-173">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="011ab-173">isNumberBlocked</span></span>   |<span data-ttu-id="011ab-174">errorMessage</span><span class="sxs-lookup"><span data-stu-id="011ab-174">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="011ab-175">200</span><span class="sxs-lookup"><span data-stu-id="011ab-175">200</span></span>    | <span data-ttu-id="011ab-176">Vrai</span><span class="sxs-lookup"><span data-stu-id="011ab-176">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="011ab-177">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="011ab-177">httpResponseCode</span></span>  |<span data-ttu-id="011ab-178">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="011ab-178">isNumberBlocked</span></span>   |<span data-ttu-id="011ab-179">errorMessage</span><span class="sxs-lookup"><span data-stu-id="011ab-179">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="011ab-180">200</span><span class="sxs-lookup"><span data-stu-id="011ab-180">200</span></span>    | <span data-ttu-id="011ab-181">False</span><span class="sxs-lookup"><span data-stu-id="011ab-181">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="011ab-182">Note concernant Regex</span><span class="sxs-lookup"><span data-stu-id="011ab-182">A note about Regex</span></span>

<span data-ttu-id="011ab-183">Comme indiqué plus haut, le modèle correspondant au blocage des appelants est réalisé à l’aide de Regex.</span><span class="sxs-lookup"><span data-stu-id="011ab-183">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="011ab-184">Plusieurs outils sont disponibles en ligne pour vous aider à valider une correspondance de modèle Regex.</span><span class="sxs-lookup"><span data-stu-id="011ab-184">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="011ab-185">Si vous n’êtes pas familiarisé avec les modèles Regex, nous vous conseillons de prendre le temps de vous familiariser avec les concepts de base.</span><span class="sxs-lookup"><span data-stu-id="011ab-185">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="011ab-186">Pour vous assurer que vous obtenez les résultats attendus, utilisez un outil permettant de valider les correspondances de modèles avant d’ajouter le nouveau numéro bloqué à votre client.</span><span class="sxs-lookup"><span data-stu-id="011ab-186">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span>
