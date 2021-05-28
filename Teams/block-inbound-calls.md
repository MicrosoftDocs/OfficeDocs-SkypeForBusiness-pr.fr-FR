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
ms.openlocfilehash: e584e9f0c16ef77424121c37ce87c6d63afb4b92
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689762"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="38016-102">Bloquer les appels entrants</span><span class="sxs-lookup"><span data-stu-id="38016-102">Block inbound calls</span></span>

<span data-ttu-id="38016-103">Les plans d’appel Microsoft, le routage direct et l’opérateur Connecter prise en charge du blocage des appels entrants à partir du réseau téléphonique public commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="38016-103">Microsoft Calling Plans, Direct Routing, and Operator Connect all support blocking inbound calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="38016-104">Cette fonctionnalité permet à un administrateur de définir une liste de modèles de numéro au niveau global du client de telle sorte que l’ID d’appelant de chaque appel PSTN entrant vers le client puisse être vérifié dans la liste pour une correspondance.</span><span class="sxs-lookup"><span data-stu-id="38016-104">This feature allows an administrator to define a  list of number patterns at the tenant global level so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="38016-105">En cas de correspondance, un appel entrant est rejeté.</span><span class="sxs-lookup"><span data-stu-id="38016-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="38016-106">Cette fonctionnalité de blocage des appels entrants fonctionne uniquement sur les appels entrants provenant du réseau PSTN et fonctionne uniquement au niveau global du client.</span><span class="sxs-lookup"><span data-stu-id="38016-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant global level.</span></span> <span data-ttu-id="38016-107">Les utilisateurs Teams ne peuvent pas manipuler cette liste.</span><span class="sxs-lookup"><span data-stu-id="38016-107">Individual Teams users can’t manipulate this list.</span></span> <span data-ttu-id="38016-108">Le Teams client autorise les utilisateurs individuels à bloquer les appels PSTN.</span><span class="sxs-lookup"><span data-stu-id="38016-108">The Teams client does allow individual users to block PSTN calls.</span></span> <span data-ttu-id="38016-109">Pour plus d’informations sur la façon dont vos utilisateurs finaux peuvent implémenter le blocage des appels, voir Gérer les [paramètres d’appel dans Teams.](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span><span class="sxs-lookup"><span data-stu-id="38016-109">For information about how your end users can implement call blocking, see [Manage call settings in Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span>

>[!NOTE]
> <span data-ttu-id="38016-110">Les appelants bloqués peuvent avoir des comportements légèrement différents lorsqu’ils sont bloqués.</span><span class="sxs-lookup"><span data-stu-id="38016-110">Blocked callers may experience slightly different behaviors when they've been blocked.</span></span> <span data-ttu-id="38016-111">Le comportement est basé sur la façon dont l’opérateur de l’appelant bloqué gère la notification que l’appel n’est pas autorisé à se terminer correctement.</span><span class="sxs-lookup"><span data-stu-id="38016-111">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="38016-112">Il peut s’agir, par exemple, d’un message de l’opérateur indiquant que l’appel ne peut pas être effectué comme un appel composé, ou un simple abandon de l’appel.</span><span class="sxs-lookup"><span data-stu-id="38016-112">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="38016-113">Appel bloquant les contrôles d’administration et les informations</span><span class="sxs-lookup"><span data-stu-id="38016-113">Call blocking admin controls and information</span></span>

<span data-ttu-id="38016-114">Les contrôles d’administration pour le blocage des numéros sont fournis à l’aide de PowerShell uniquement.</span><span class="sxs-lookup"><span data-stu-id="38016-114">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="38016-115">Les modèles de blocs de nombres sont définis en tant que modèles d’expression régulière.</span><span class="sxs-lookup"><span data-stu-id="38016-115">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="38016-116">L’ordre des expressions n’est pasimportant : le premier modèle de la liste a pour résultat le blocage de l’appel.</span><span class="sxs-lookup"><span data-stu-id="38016-116">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="38016-117">L’activité d’un nouveau numéro ou modèle ajouté ou supprimé dans la liste des appelants bloqués peut prendre jusqu’à 24 heures.</span><span class="sxs-lookup"><span data-stu-id="38016-117">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="38016-118">Appel bloquant les commandes PowerShell</span><span class="sxs-lookup"><span data-stu-id="38016-118">Call blocking PowerShell commands</span></span>

<span data-ttu-id="38016-119">Vous gérez les modèles de numéro à l’aide des cmdlets **New-,** **Get-,** **Set-** et **Remove-CsInboundBlockedNumberPattern.**</span><span class="sxs-lookup"><span data-stu-id="38016-119">You manage number patterns by using the **New-**, **Get-**, **Set-**, and **Remove-CsInboundBlockedNumberPattern** cmdlets.</span></span> <span data-ttu-id="38016-120">Vous pouvez gérer un modèle donné à l’aide de ces cmdlets, y compris la possibilité d’activer un modèle donné.</span><span class="sxs-lookup"><span data-stu-id="38016-120">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>

- <span data-ttu-id="38016-121">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) renvoie la liste de tous les modèles de numéro bloqués ajoutés à la liste des locataires, y compris Nom, Description, Activé (Vrai/Faux) et Modèle pour chacun d’eux.</span><span class="sxs-lookup"><span data-stu-id="38016-121">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="38016-122">[New-CsInboundBlockedNumberPattern ajoute](/powershell/module/skype/new-csinboundblockednumberpattern) un modèle de numéro bloqué à la liste des locataires.</span><span class="sxs-lookup"><span data-stu-id="38016-122">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="38016-123">[Remove-CsInboundBlockedNumberPattern supprime](/powershell/module/skype/remove-csinboundblockednumberpattern) un modèle de numéro bloqué de la liste des locataires.</span><span class="sxs-lookup"><span data-stu-id="38016-123">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="38016-124">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifie un ou plusieurs paramètres d’un modèle de nombre bloqué dans la liste des locataires.</span><span class="sxs-lookup"><span data-stu-id="38016-124">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="38016-125">L’affichage et l’activation de l’ensemble de la fonctionnalité de blocage d’appels sont gérés par le biais des cmdlets **Get-and-Set-CsTenantBlockingCallingNumbers.** </span><span class="sxs-lookup"><span data-stu-id="38016-125">Viewing and activating the entire call blocking feature is managed through the **Get-** and **Set-CsTenantBlockingCallingNumbers** cmdlets.</span></span>

- <span data-ttu-id="38016-126">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) renvoie les modèles de numéro de bloc entrant et les paramètres de modèles de nombres exemptés entrants pour la liste de nombres bloqués globaux.</span><span class="sxs-lookup"><span data-stu-id="38016-126">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the inbound block number patterns and the inbound exempt number patterns parameters for the global blocked number list.</span></span> <span data-ttu-id="38016-127">Cette cmdlet renvoie également si le blocage a été activé (True ou False).</span><span class="sxs-lookup"><span data-stu-id="38016-127">This cmdlet also returns whether blocking has been Enabled (True or False).</span></span> <span data-ttu-id="38016-128">Il existe une seule stratégie de client globale qui ne peut pas être modifiée manuellement si ce n’est pour activer ou désactiver la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="38016-128">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="38016-129">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) permet d’autoriser ou non la modification des appels bloqués du client global au niveau du client.</span><span class="sxs-lookup"><span data-stu-id="38016-129">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="38016-130">Exemples</span><span class="sxs-lookup"><span data-stu-id="38016-130">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="38016-131">Bloquer un numéro</span><span class="sxs-lookup"><span data-stu-id="38016-131">Block a number</span></span>

<span data-ttu-id="38016-132">Dans l’exemple suivant, l’administrateur client souhaite bloquer tous les appels provenant de la plage de numéro 1 (312) 555-0000 à 1 (312) 555-9999.</span><span class="sxs-lookup"><span data-stu-id="38016-132">In the following example, the tenant administrator wants to block all calls coming from the number range 1 (312) 555-0000 to 1 (312) 555-9999.</span></span> <span data-ttu-id="38016-133">Le modèle de nombre est créé de sorte que les deux nombres de la plage avec + préfixe et les nombres de la plage sans préfixe + soient mis en correspondance.</span><span class="sxs-lookup"><span data-stu-id="38016-133">The number pattern is created so that both numbers in range with + prefixed and numbers in the range without + prefixed are matched.</span></span> <span data-ttu-id="38016-134">Vous n’avez pas besoin d’inclure les symboles – et () dans les numéros de téléphone, car le système les bande avant la correspondance.</span><span class="sxs-lookup"><span data-stu-id="38016-134">You don’t need to include the symbols – and () in the phone numbers because the system strips these symbols before matching.</span></span>  <span data-ttu-id="38016-135">Pour activer le modèle de nombre, le **paramètre** Activé a la valeur True.</span><span class="sxs-lookup"><span data-stu-id="38016-135">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span> <span data-ttu-id="38016-136">Pour désactiver ce modèle de nombre spécifique, définissez le paramètre sur False.</span><span class="sxs-lookup"><span data-stu-id="38016-136">To disable this specific number pattern, set the parameter to False.</span></span>

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

<span data-ttu-id="38016-137">Dans l’exemple suivant, l’administrateur client souhaite bloquer tous les appels provenant du numéro 1 (412) 555-1234.</span><span class="sxs-lookup"><span data-stu-id="38016-137">In the next example, the tenant administrator wants to block all calls coming from the number 1 (412) 555-1234.</span></span> <span data-ttu-id="38016-138">Pour activer le modèle de nombre, le **paramètre** Activé a la valeur True.</span><span class="sxs-lookup"><span data-stu-id="38016-138">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span>

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

<span data-ttu-id="38016-139">La création d’un modèle ajoute le modèle comme étant activé par défaut.</span><span class="sxs-lookup"><span data-stu-id="38016-139">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="38016-140">La description est un champ facultatif pour fournir des informations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="38016-140">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="38016-141">Nous vous recommandons de fournir un nom significatif pour comprendre facilement pourquoi le modèle a été ajouté.</span><span class="sxs-lookup"><span data-stu-id="38016-141">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="38016-142">Si vous bloquez simplement les numéros de courrier indésirable, vous pouvez nommer la règle de la même façon que le modèle de nombres qui correspond et ajouter des informations supplémentaires dans la description si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="38016-142">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="38016-143">Les modèles sont assortis à l’aide d’expressions régulières (Regex).</span><span class="sxs-lookup"><span data-stu-id="38016-143">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="38016-144">Pour plus d’informations, voir [Utiliser Regex.](#using-regex)</span><span class="sxs-lookup"><span data-stu-id="38016-144">For more information, see [Using Regex](#using-regex).</span></span>

<span data-ttu-id="38016-145">Autorisez le temps de réplication avant de tester et de valider.</span><span class="sxs-lookup"><span data-stu-id="38016-145">Allow time for replication before you test and validate.</span></span> 

#### <a name="allow-a-number"></a><span data-ttu-id="38016-146">Autoriser un numéro</span><span class="sxs-lookup"><span data-stu-id="38016-146">Allow a number</span></span>

<span data-ttu-id="38016-147">Vous pouvez autoriser un numéro à appeler en supprimant le modèle de numéro bloqué.</span><span class="sxs-lookup"><span data-stu-id="38016-147">You can allow a number to call by removing the blocked number pattern.</span></span> <span data-ttu-id="38016-148">Dans l’exemple suivant, l’administrateur client souhaite autoriser le 1 (412) 555-1234 à effectuer de nouveaux appels.</span><span class="sxs-lookup"><span data-stu-id="38016-148">In the following example, the tenant administrator wants to allow 1 (412) 555-1234 to make calls again.</span></span>

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```
 
<span data-ttu-id="38016-149">Si l’identité n’est pas connue, utilisez l’cmdlet **Get-CsInboundBlockedNumberPattern** pour identifier le modèle approprié et noter l’identité.</span><span class="sxs-lookup"><span data-stu-id="38016-149">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="38016-150">Ensuite, exécutez la **cmdlet Remove-CsInboundBlockedNumberPattern** et transmettre la valeur d’identité appropriée.</span><span class="sxs-lookup"><span data-stu-id="38016-150">Then, run the **Remove-CsInboundBlockedNumberPattern** cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="38016-151">Autorisez le temps de réplication avant de tester et de valider.</span><span class="sxs-lookup"><span data-stu-id="38016-151">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="38016-152">Afficher tous les modèles de nombres</span><span class="sxs-lookup"><span data-stu-id="38016-152">View all number patterns</span></span>

<span data-ttu-id="38016-153">L’exécution de cette cmdlet renvoie la liste de tous les numéros bloqués entrés pour un client :</span><span class="sxs-lookup"><span data-stu-id="38016-153">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="38016-154">Utilisez les capacités intégrées de filtrage PowerShell pour filtrer les valeurs renvoyées comme requis.</span><span class="sxs-lookup"><span data-stu-id="38016-154">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="38016-155">Ajouter des exceptions de nombre</span><span class="sxs-lookup"><span data-stu-id="38016-155">Add number exceptions</span></span>

<span data-ttu-id="38016-156">Vous pouvez ajouter des exceptions aux modèles de nombres bloqués à l’aide des cmdlets **New-,** **Get-,** **Set-** et **Remove-CsInboundExemptNumberPattern.**</span><span class="sxs-lookup"><span data-stu-id="38016-156">You can add exceptions to blocked number patterns by using the **New-**, **Get-**, **Set-**, and **Remove-CsInboundExemptNumberPattern** cmdlets.</span></span>

- <span data-ttu-id="38016-157">[New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) ajoute un modèle d’exception de nombre à la liste des locataires.</span><span class="sxs-lookup"><span data-stu-id="38016-157">[New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="38016-158">[Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) renvoie la liste de tous les modèles d’exceptions de nombres ajoutés à la liste des locataires.</span><span class="sxs-lookup"><span data-stu-id="38016-158">[Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="38016-159">[Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) modifie un ou plusieurs paramètres en un modèle d’exception de nombre dans la liste des locataires.</span><span class="sxs-lookup"><span data-stu-id="38016-159">[Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="38016-160">[Remove-CsInboundExemptNumberPattern supprime](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) un modèle d’exception de nombre de la liste des locataires.</span><span class="sxs-lookup"><span data-stu-id="38016-160">[Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="38016-161">Exemples</span><span class="sxs-lookup"><span data-stu-id="38016-161">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="38016-162">Ajouter une exception</span><span class="sxs-lookup"><span data-stu-id="38016-162">Add a number exception</span></span>

<span data-ttu-id="38016-163">Dans l’exemple suivant, l’administrateur client souhaite autoriser les numéros de téléphone 1 (312) 555-8882 et 1 (312) 555-8883 pour appeler le client, même si ces deux numéros de téléphone se trouveraient dans la plage bloquée dans l’exemple ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="38016-163">In the following example, the tenant administrator wants to allow the phone numbers 1 (312) 555-8882 and 1 (312) 555-8883 to make calls to the tenant, even if these two phone numbers are in the range that has been blocked in the example above.</span></span> <span data-ttu-id="38016-164">Pour ce faire, un nouveau modèle d’exception de nombre est créé comme suit :</span><span class="sxs-lookup"><span data-stu-id="38016-164">To enable this, a new number exception pattern is created as follows:</span></span>

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

<span data-ttu-id="38016-165">Pour activer le modèle de nombre, le **paramètre** Activé a la valeur True.</span><span class="sxs-lookup"><span data-stu-id="38016-165">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span> <span data-ttu-id="38016-166">Pour désactiver ce modèle de nombre spécifique, définissez le paramètre sur False.</span><span class="sxs-lookup"><span data-stu-id="38016-166">To disable this specific number pattern, set the parameter to False.</span></span>


#### <a name="view-all-number-exceptions"></a><span data-ttu-id="38016-167">Afficher toutes les exceptions de nombre</span><span class="sxs-lookup"><span data-stu-id="38016-167">View all number exceptions</span></span>

<span data-ttu-id="38016-168">Dans cet exemple, le **paramètre Identité** est facultatif.</span><span class="sxs-lookup"><span data-stu-id="38016-168">In this example, the **Identity** parameter is optional.</span></span> <span data-ttu-id="38016-169">Si le **paramètre Identité** n’est pas spécifié, cette cmdlet renvoie la liste de tous les modèles d’exceptions de nombre entrés pour un client.</span><span class="sxs-lookup"><span data-stu-id="38016-169">If the **Identity** parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```
 
```powershell
Get-CsInboundExemptNumberPattern 
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="38016-170">Modifier une exception de nombre</span><span class="sxs-lookup"><span data-stu-id="38016-170">Modify a number exception</span></span>

<span data-ttu-id="38016-171">L’cmdlet **Set-CsInboundExemptNumberPattern** vous permet de modifier un ou plusieurs paramètres pour une identité de modèle de nombre donnée.</span><span class="sxs-lookup"><span data-stu-id="38016-171">The **Set-CsInboundExemptNumberPattern** cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span> <span data-ttu-id="38016-172">Dans cet exemple, le **paramètre Identité** est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="38016-172">In this example, the **Identity** parameter is required.</span></span>
 
```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="38016-173">Supprimer une exception</span><span class="sxs-lookup"><span data-stu-id="38016-173">Remove a number exception</span></span>

<span data-ttu-id="38016-174">L’cmdlet **Remove-CsInboundExemptNumberPattern** supprime le modèle de nombre donné de la liste de locataires.</span><span class="sxs-lookup"><span data-stu-id="38016-174">The **Remove-CsInboundExemptNumberPattern** cmdlet will remove the given number pattern from the tenant list.</span></span> <span data-ttu-id="38016-175">Dans cet exemple, le **paramètre Identité** est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="38016-175">In this example, the **Identity** parameter is required.</span></span> 

<span data-ttu-id="38016-176">Si l’identité n’est pas connue, utilisez l’cmdlet **Get-CsInboundExemptNumberPattern** pour rechercher le modèle approprié et noter l’identité.</span><span class="sxs-lookup"><span data-stu-id="38016-176">If the identity isn't known, use the **Get-CsInboundExemptNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="38016-177">Ensuite, exécutez la cmdlet **Remove-CsInboundExemptNumberPattern** et transmettre la valeur d’identité appropriée.</span><span class="sxs-lookup"><span data-stu-id="38016-177">Then, run the **Remove-CsInboundExemptNumberPattern** cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="38016-178">Autorisez le temps de réplication avant de tester et de valider.</span><span class="sxs-lookup"><span data-stu-id="38016-178"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="38016-179">Vérifier si un nombre est bloqué</span><span class="sxs-lookup"><span data-stu-id="38016-179">Test whether a number is blocked</span></span>

<span data-ttu-id="38016-180">Utilisez **l’cmdlet Test-CsInboundBlockedNumberPattern** pour vérifier si un nombre est bloqué dans le client.</span><span class="sxs-lookup"><span data-stu-id="38016-180">Use the **Test-CsInboundBlockedNumberPattern** cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="38016-181">Le **paramètre PhoneNumber** est obligatoire et doit être une chaîne numérique sans caractères supplémentaires, tels que +, - ou ().</span><span class="sxs-lookup"><span data-stu-id="38016-181">The **PhoneNumber** parameter is required, and should be a numeric string without any additional characters, such as +, - or ().</span></span> <span data-ttu-id="38016-182">Le paramètre **IsNumberBlocked** qui en résulte renvoie la valeur True si le nombre est bloqué dans le client . Le paramètre renvoie False s’il n’est pas bloqué.</span><span class="sxs-lookup"><span data-stu-id="38016-182">The resulting **IsNumberBlocked** parameter returns a value of True if the number is blocked in the tenant; the parameter returns False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

### <a name="examples"></a><span data-ttu-id="38016-183">Exemples</span><span class="sxs-lookup"><span data-stu-id="38016-183">Examples</span></span>

<span data-ttu-id="38016-184">Dans ces exemples, vous pouvez voir que le numéro de téléphone 1 (312) 555-8884 est bloqué car il devrait être dans la plage bloquée ci-dessus, alors que le numéro de téléphone 1 (312) 555-8883 est autorisé à appeler comme il devrait l’être en fonction de l’exonération créée ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="38016-184">In these examples you can see that the phone number 1 (312) 555-8884 is blocked as it should be due to it being in the blocked range above, while the phone number 1 (312) 555-8883 is allowed to call as it should be based on the exemption created above.</span></span>

```PowerShell
Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558884

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : True
errorMessage    :

Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558883

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : False
errorMessage    :
```

## <a name="using-regex"></a><span data-ttu-id="38016-185">Utilisation de Regex</span><span class="sxs-lookup"><span data-stu-id="38016-185">Using Regex</span></span>

<span data-ttu-id="38016-186">La correspondance au modèle de blocage des appelants est effectuée à l’aide de Regex.</span><span class="sxs-lookup"><span data-stu-id="38016-186">The pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="38016-187">Plusieurs outils sont disponibles en ligne pour vous aider à valider une correspondance au modèle Regex.</span><span class="sxs-lookup"><span data-stu-id="38016-187">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="38016-188">Si vous n’êtes pas familiarisé avec les modèles Regex, nous vous recommandons de prendre le temps de vous familiariser avec les bases.</span><span class="sxs-lookup"><span data-stu-id="38016-188">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="38016-189">Pour vous assurer d’obtenir les résultats attendus, utilisez un outil pour valider les correspondances de modèle avant d’ajouter de nouveaux nombres bloqués à votre client.</span><span class="sxs-lookup"><span data-stu-id="38016-189">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span>