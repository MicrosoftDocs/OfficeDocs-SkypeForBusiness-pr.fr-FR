---
title: Cmdlets dans Skype entreprise Online utilisant uniquement l’étendue globale
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use only the global scope
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56558800
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5610649295fdf4089372d9c59e4ccb51228c1fc2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728104"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a><span data-ttu-id="6b0ea-102">Cmdlets dans Skype entreprise Online utilisant uniquement l’étendue globale</span><span class="sxs-lookup"><span data-stu-id="6b0ea-102">Cmdlets in Skype for Business Online that use only the global scope</span></span>

 


<span data-ttu-id="6b0ea-103">Un certain nombre de paramètres Skype entreprise Online ne sont disponibles qu’à l' *étendue globale*.</span><span class="sxs-lookup"><span data-stu-id="6b0ea-103">A number of Skype for Business Online settings are available only at the *global scope*.</span></span> <span data-ttu-id="6b0ea-104">Cela signifie qu’il existe une collection unique de paramètres qui s’applique à tous les utilisateurs qui sont affectés à ce client.</span><span class="sxs-lookup"><span data-stu-id="6b0ea-104">This means that there is a single collection of settings that applies to all the users who are assigned to that tenant.</span></span> <span data-ttu-id="6b0ea-105">(Chaque client dispose de sa propre collection unique de paramètres globaux.) Lorsque vous utilisez des applets de applet qui sont limitées à l’étendue globale, le paramètre Identity est facultatif.</span><span class="sxs-lookup"><span data-stu-id="6b0ea-105">(Each tenant has its own unique collection of global settings.) When you are using cmdlets that are limited to the global scope, the Identity parameter is optional.</span></span> <span data-ttu-id="6b0ea-106">Par exemple, pour récupérer les paramètres de configuration de la réunion, vous pouvez utiliser la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6b0ea-106">For example, to retrieve meeting configuration settings, you can use this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="6b0ea-107">Par ailleurs, vous pouvez omettre le paramètre Identity et utiliser cette commande plus simple :</span><span class="sxs-lookup"><span data-stu-id="6b0ea-107">Alternatively, you can omit the Identity parameter and use this simpler command instead:</span></span>

    Get-CsMeetingConfiguration

<span data-ttu-id="6b0ea-108">Étant donné qu’il n’existe qu’une seule collection globale de paramètres de configuration de réunion, les deux commandes renvoient exactement les mêmes informations.</span><span class="sxs-lookup"><span data-stu-id="6b0ea-108">Because there is only one global collection of meeting configuration settings, the two commands return the exact same information.</span></span> <span data-ttu-id="6b0ea-109">Le paramètre Identity peut également être omis lors de l’utilisation d’une cmdlet **Set-CS** .</span><span class="sxs-lookup"><span data-stu-id="6b0ea-109">The Identity parameter can also be omitted when using one of the **Set-Cs** cmdlets.</span></span> <span data-ttu-id="6b0ea-110">Ces deux commandes sont identiques :</span><span class="sxs-lookup"><span data-stu-id="6b0ea-110">These two commands are identical:</span></span>

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

<span data-ttu-id="6b0ea-111">Les deux commandes sont identiques, car, par défaut, Windows PowerShell modifie la collection globale si vous n’incluez pas le paramètre Identity.</span><span class="sxs-lookup"><span data-stu-id="6b0ea-111">The two commands are identical because, by default, Windows PowerShell will modify the global collection if you do not include the Identity parameter.</span></span>

<span data-ttu-id="6b0ea-112">Les applets de commande suivantes fonctionnent uniquement au niveau de l’étendue globale :</span><span class="sxs-lookup"><span data-stu-id="6b0ea-112">The following cmdlets operate only at the global scope:</span></span>

  - <span data-ttu-id="6b0ea-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6b0ea-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))</span></span>

  - <span data-ttu-id="6b0ea-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6b0ea-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))</span></span>

  - <span data-ttu-id="6b0ea-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6b0ea-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))</span></span>

  - <span data-ttu-id="6b0ea-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6b0ea-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="6b0ea-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6b0ea-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="6b0ea-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6b0ea-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span></span>

  - <span data-ttu-id="6b0ea-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6b0ea-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))</span></span>

  - <span data-ttu-id="6b0ea-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6b0ea-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))</span></span>

  - <span data-ttu-id="6b0ea-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6b0ea-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))</span></span>

  - <span data-ttu-id="6b0ea-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6b0ea-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))</span></span>

<span data-ttu-id="6b0ea-123">Notez que l’applet de l’applet de **suppression-CsVoicePolicy** est une anomalie.</span><span class="sxs-lookup"><span data-stu-id="6b0ea-123">Note that the **Remove-CsVoicePolicy** cmdlet is something of an anomaly.</span></span> <span data-ttu-id="6b0ea-124">Tout d’abord, cette applet de recherche vous demande d’inclure le paramètre Identity :</span><span class="sxs-lookup"><span data-stu-id="6b0ea-124">First, this cmdlet does require you to include the Identity parameter:</span></span>

    Remove-CsVoicePolicy -Identity "global"

<span data-ttu-id="6b0ea-125">Deuxièmement, l’applet de l’applet de **suppression-CsVoicePolicy** n’entraîne pas la suppression effective de la stratégie vocale globale. Skype entreprise Online ne vous permet pas de supprimer les stratégies globales ou les paramètres de configuration.</span><span class="sxs-lookup"><span data-stu-id="6b0ea-125">Second, the **Remove-CsVoicePolicy** cmdlet does not actually delete the global voice policy; Skype for Business Online does not allow you to delete global policies or configuration settings.</span></span> <span data-ttu-id="6b0ea-126">Ce que fait l’applet de passe consiste à rétablir ses valeurs par défaut pour toutes les propriétés de la stratégie vocale globale.</span><span class="sxs-lookup"><span data-stu-id="6b0ea-126">What the cmdlet does do is enable you to reset all the properties in the global voice policy to their default values.</span></span> <span data-ttu-id="6b0ea-127">Par exemple, par défaut, la propriété AllowCallForwarding est définie sur false.</span><span class="sxs-lookup"><span data-stu-id="6b0ea-127">For example, by default, the AllowCallForwarding property is set to False.</span></span> <span data-ttu-id="6b0ea-128">Toutefois, AllowCallForwarding a pu être modifié, avec la valeur true.</span><span class="sxs-lookup"><span data-stu-id="6b0ea-128">However, AllowCallForwarding may have been modified, with the value now set to True.</span></span> <span data-ttu-id="6b0ea-129">Lorsque vous exécutez l’applet de cmdlet **Remove-CsVoicePolicy** , la propriété AllowCallForwarding revient à sa valeur par défaut : false.</span><span class="sxs-lookup"><span data-stu-id="6b0ea-129">When you run the **Remove-CsVoicePolicy** cmdlet, the AllowCallForwarding property will revert to its default value: False.</span></span> <span data-ttu-id="6b0ea-130">Le tableau suivant récapitule ce scénario :</span><span class="sxs-lookup"><span data-stu-id="6b0ea-130">The following table summarizes this scenario:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6b0ea-131">Valeur AllowCallForwarding</span><span class="sxs-lookup"><span data-stu-id="6b0ea-131">AllowCallForwarding Value</span></span></th>
<th><span data-ttu-id="6b0ea-132">Scénario</span><span class="sxs-lookup"><span data-stu-id="6b0ea-132">Scenario</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6b0ea-133">False</span><span class="sxs-lookup"><span data-stu-id="6b0ea-133">False</span></span></p></td>
<td><p><span data-ttu-id="6b0ea-134">Valeur par défaut</span><span class="sxs-lookup"><span data-stu-id="6b0ea-134">Default value</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b0ea-135">Vrai</span><span class="sxs-lookup"><span data-stu-id="6b0ea-135">True</span></span></p></td>
<td><p><span data-ttu-id="6b0ea-136">Après la modification de la stratégie globale</span><span class="sxs-lookup"><span data-stu-id="6b0ea-136">After the global policy has been modified</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b0ea-137">False</span><span class="sxs-lookup"><span data-stu-id="6b0ea-137">False</span></span></p></td>
<td><p><span data-ttu-id="6b0ea-138">Après l’exécution de la cmdlet <strong>Remove-CsVoicePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="6b0ea-138">After <strong>Remove-CsVoicePolicy</strong> cmdlet has been run</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a><span data-ttu-id="6b0ea-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6b0ea-139">See Also</span></span>


[<span data-ttu-id="6b0ea-140">Identités, étendues et clients dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="6b0ea-140">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="6b0ea-141">[Applets de commande de Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6b0ea-141">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

