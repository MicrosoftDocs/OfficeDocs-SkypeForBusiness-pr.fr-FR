---
title: Cmdlets dans Skype entreprise Online utilisant uniquement l’étendue globale
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use only the global scope
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56558800
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 210e9116152ebe071ec81d2e0d48ff31b7c20a60
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233105"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a><span data-ttu-id="e85f2-102">Cmdlets dans Skype entreprise Online utilisant uniquement l’étendue globale</span><span class="sxs-lookup"><span data-stu-id="e85f2-102">Cmdlets in Skype for Business Online that use only the global scope</span></span>

 


<span data-ttu-id="e85f2-103">Un certain nombre de paramètres Skype entreprise Online ne sont disponibles qu’à l' *étendue globale*.</span><span class="sxs-lookup"><span data-stu-id="e85f2-103">A number of Skype for Business Online settings are available only at the *global scope*.</span></span> <span data-ttu-id="e85f2-104">Cela signifie qu’il existe une collection unique de paramètres qui s’applique à tous les utilisateurs qui sont affectés à ce client.</span><span class="sxs-lookup"><span data-stu-id="e85f2-104">This means that there is a single collection of settings that applies to all the users who are assigned to that tenant.</span></span> <span data-ttu-id="e85f2-105">(Chaque client dispose de sa propre collection unique de paramètres globaux.) Lorsque vous utilisez des applets de applet qui sont limitées à l’étendue globale, le paramètre Identity est facultatif.</span><span class="sxs-lookup"><span data-stu-id="e85f2-105">(Each tenant has its own unique collection of global settings.) When you are using cmdlets that are limited to the global scope, the Identity parameter is optional.</span></span> <span data-ttu-id="e85f2-106">Par exemple, pour récupérer les paramètres de configuration de la réunion, vous pouvez utiliser la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="e85f2-106">For example, to retrieve meeting configuration settings, you can use this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="e85f2-107">Par ailleurs, vous pouvez omettre le paramètre Identity et utiliser cette commande plus simple:</span><span class="sxs-lookup"><span data-stu-id="e85f2-107">Alternatively, you can omit the Identity parameter and use this simpler command instead:</span></span>

    Get-CsMeetingConfiguration

<span data-ttu-id="e85f2-108">Étant donné qu’il n’existe qu’une seule collection globale de paramètres de configuration de réunion, les deux commandes renvoient exactement les mêmes informations.</span><span class="sxs-lookup"><span data-stu-id="e85f2-108">Because there is only one global collection of meeting configuration settings, the two commands return the exact same information.</span></span> <span data-ttu-id="e85f2-109">Le paramètre Identity peut également être omis lors de l’utilisation d’une cmdlet **Set-CS** .</span><span class="sxs-lookup"><span data-stu-id="e85f2-109">The Identity parameter can also be omitted when using one of the **Set-Cs** cmdlets.</span></span> <span data-ttu-id="e85f2-110">Ces deux commandes sont identiques:</span><span class="sxs-lookup"><span data-stu-id="e85f2-110">These two commands are identical:</span></span>

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

<span data-ttu-id="e85f2-111">Les deux commandes sont identiques, car, par défaut, Windows PowerShell modifie la collection globale si vous n’incluez pas le paramètre Identity.</span><span class="sxs-lookup"><span data-stu-id="e85f2-111">The two commands are identical because, by default, Windows PowerShell will modify the global collection if you do not include the Identity parameter.</span></span>

<span data-ttu-id="e85f2-112">Les applets de commande suivantes fonctionnent uniquement au niveau de l’étendue globale:</span><span class="sxs-lookup"><span data-stu-id="e85f2-112">The following cmdlets operate only at the global scope:</span></span>

  - <span data-ttu-id="e85f2-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e85f2-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e85f2-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e85f2-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e85f2-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e85f2-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e85f2-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e85f2-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e85f2-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e85f2-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e85f2-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e85f2-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e85f2-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e85f2-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e85f2-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e85f2-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e85f2-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e85f2-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e85f2-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e85f2-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))</span></span>

<span data-ttu-id="e85f2-123">Notez que l’applet de l’applet de **suppression-CsVoicePolicy** est une anomalie.</span><span class="sxs-lookup"><span data-stu-id="e85f2-123">Note that the **Remove-CsVoicePolicy** cmdlet is something of an anomaly.</span></span> <span data-ttu-id="e85f2-124">Tout d’abord, cette applet de recherche vous demande d’inclure le paramètre Identity:</span><span class="sxs-lookup"><span data-stu-id="e85f2-124">First, this cmdlet does require you to include the Identity parameter:</span></span>

    Remove-CsVoicePolicy -Identity "global"

<span data-ttu-id="e85f2-125">Deuxièmement, l’applet de l’applet de **suppression-CsVoicePolicy** n’entraîne pas la suppression effective de la stratégie vocale globale. Skype entreprise Online ne vous permet pas de supprimer les stratégies globales ou les paramètres de configuration.</span><span class="sxs-lookup"><span data-stu-id="e85f2-125">Second, the **Remove-CsVoicePolicy** cmdlet does not actually delete the global voice policy; Skype for Business Online does not allow you to delete global policies or configuration settings.</span></span> <span data-ttu-id="e85f2-126">Ce que fait l’applet de passe consiste à rétablir ses valeurs par défaut pour toutes les propriétés de la stratégie vocale globale.</span><span class="sxs-lookup"><span data-stu-id="e85f2-126">What the cmdlet does do is enable you to reset all the properties in the global voice policy to their default values.</span></span> <span data-ttu-id="e85f2-127">Par exemple, par défaut, la propriété AllowCallForwarding est définie sur false.</span><span class="sxs-lookup"><span data-stu-id="e85f2-127">For example, by default, the AllowCallForwarding property is set to False.</span></span> <span data-ttu-id="e85f2-128">Toutefois, AllowCallForwarding a pu être modifié, avec la valeur true.</span><span class="sxs-lookup"><span data-stu-id="e85f2-128">However, AllowCallForwarding may have been modified, with the value now set to True.</span></span> <span data-ttu-id="e85f2-129">Lorsque vous exécutez l’applet de cmdlet **Remove-CsVoicePolicy** , la propriété AllowCallForwarding revient à sa valeur par défaut: false.</span><span class="sxs-lookup"><span data-stu-id="e85f2-129">When you run the **Remove-CsVoicePolicy** cmdlet, the AllowCallForwarding property will revert to its default value: False.</span></span> <span data-ttu-id="e85f2-130">Le tableau suivant récapitule ce scénario:</span><span class="sxs-lookup"><span data-stu-id="e85f2-130">The following table summarizes this scenario:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e85f2-131">Valeur AllowCallForwarding</span><span class="sxs-lookup"><span data-stu-id="e85f2-131">AllowCallForwarding Value</span></span></th>
<th><span data-ttu-id="e85f2-132">Scénario</span><span class="sxs-lookup"><span data-stu-id="e85f2-132">Scenario</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e85f2-133">False</span><span class="sxs-lookup"><span data-stu-id="e85f2-133">False</span></span></p></td>
<td><p><span data-ttu-id="e85f2-134">Valeur par défaut</span><span class="sxs-lookup"><span data-stu-id="e85f2-134">Default value</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e85f2-135">True</span><span class="sxs-lookup"><span data-stu-id="e85f2-135">True</span></span></p></td>
<td><p><span data-ttu-id="e85f2-136">Après la modification de la stratégie globale</span><span class="sxs-lookup"><span data-stu-id="e85f2-136">After the global policy has been modified</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e85f2-137">False</span><span class="sxs-lookup"><span data-stu-id="e85f2-137">False</span></span></p></td>
<td><p><span data-ttu-id="e85f2-138">Après l’exécution de la cmdlet <strong>Remove-CsVoicePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="e85f2-138">After <strong>Remove-CsVoicePolicy</strong> cmdlet has been run</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a><span data-ttu-id="e85f2-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e85f2-139">See Also</span></span>


[<span data-ttu-id="e85f2-140">Identités, étendues et clients dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="e85f2-140">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="e85f2-141">[Applets de commande de Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e85f2-141">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

