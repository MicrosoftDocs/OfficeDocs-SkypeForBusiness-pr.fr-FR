---
title: Applets de commande dans Skype entreprise Online qui utilisent uniquement l’étendue globale
description: Applets de commande dans Skype entreprise Online qui utilisent uniquement l’étendue globale.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: a2f59806128ceea825a4cdd966e85852b98079b0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545600"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a><span data-ttu-id="9dcd6-103">Applets de commande dans Skype entreprise Online qui utilisent uniquement l’étendue globale</span><span class="sxs-lookup"><span data-stu-id="9dcd6-103">Cmdlets in Skype for Business Online that use only the global scope</span></span>

 


<span data-ttu-id="9dcd6-104">Un certain nombre de paramètres Skype entreprise Online sont disponibles uniquement au niveau *Global*.</span><span class="sxs-lookup"><span data-stu-id="9dcd6-104">A number of Skype for Business Online settings are available only at the *global scope*.</span></span> <span data-ttu-id="9dcd6-105">Cela signifie qu’il existe une seule collection de paramètres qui s’applique à tous les utilisateurs qui sont affectés à ce client.</span><span class="sxs-lookup"><span data-stu-id="9dcd6-105">This means that there is a single collection of settings that applies to all the users who are assigned to that tenant.</span></span> <span data-ttu-id="9dcd6-106">(Chaque client possède sa propre collection de paramètres globaux uniques.) Lorsque vous utilisez des applets de commande limitées à l’étendue globale, le paramètre Identity est facultatif.</span><span class="sxs-lookup"><span data-stu-id="9dcd6-106">(Each tenant has its own unique collection of global settings.) When you are using cmdlets that are limited to the global scope, the Identity parameter is optional.</span></span> <span data-ttu-id="9dcd6-107">Par exemple, pour récupérer les paramètres de configuration de réunion, vous pouvez utiliser la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="9dcd6-107">For example, to retrieve meeting configuration settings, you can use this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="9dcd6-108">Vous pouvez également omettre le paramètre Identity et utiliser cette commande plus simple :</span><span class="sxs-lookup"><span data-stu-id="9dcd6-108">Alternatively, you can omit the Identity parameter and use this simpler command instead:</span></span>

    Get-CsMeetingConfiguration

<span data-ttu-id="9dcd6-109">Étant donné qu’il n’existe qu’une seule collection globale de paramètres de configuration de réunion, les deux commandes renvoient exactement les mêmes informations.</span><span class="sxs-lookup"><span data-stu-id="9dcd6-109">Because there is only one global collection of meeting configuration settings, the two commands return the exact same information.</span></span> <span data-ttu-id="9dcd6-110">Le paramètre Identity peut également être omis lors de l’utilisation de l’une des cmdlets **Set-CS** .</span><span class="sxs-lookup"><span data-stu-id="9dcd6-110">The Identity parameter can also be omitted when using one of the **Set-Cs** cmdlets.</span></span> <span data-ttu-id="9dcd6-111">Ces deux commandes sont identiques :</span><span class="sxs-lookup"><span data-stu-id="9dcd6-111">These two commands are identical:</span></span>

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

<span data-ttu-id="9dcd6-112">Les deux commandes sont identiques car, par défaut, Windows PowerShell modifie la collection globale si vous n’incluez pas le paramètre Identity.</span><span class="sxs-lookup"><span data-stu-id="9dcd6-112">The two commands are identical because, by default, Windows PowerShell will modify the global collection if you do not include the Identity parameter.</span></span>

<span data-ttu-id="9dcd6-113">Les applets de commande suivantes fonctionnent uniquement au niveau de l’étendue globale :</span><span class="sxs-lookup"><span data-stu-id="9dcd6-113">The following cmdlets operate only at the global scope:</span></span>

  - <span data-ttu-id="9dcd6-114">[Get-CsImFilterConfiguration](https://technet.microsoft.com/library/gg398980\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9dcd6-114">[Get-CsImFilterConfiguration](https://technet.microsoft.com/library/gg398980\(v=ocs.15\))</span></span>

  - <span data-ttu-id="9dcd6-115">[Get-CsMeetingConfiguration](https://technet.microsoft.com/library/gg425875\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9dcd6-115">[Get-CsMeetingConfiguration](https://technet.microsoft.com/library/gg425875\(v=ocs.15\))</span></span>

  - <span data-ttu-id="9dcd6-116">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg413002\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9dcd6-116">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg413002\(v=ocs.15\))</span></span>

  - <span data-ttu-id="9dcd6-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9dcd6-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="9dcd6-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9dcd6-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="9dcd6-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9dcd6-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span></span>

  - <span data-ttu-id="9dcd6-120">[Get-CsTenantPublicProvider](https://technet.microsoft.com/library/jj994016\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9dcd6-120">[Get-CsTenantPublicProvider](https://technet.microsoft.com/library/jj994016\(v=ocs.15\))</span></span>

  - <span data-ttu-id="9dcd6-121">[Remove-CsVoicePolicy](https://technet.microsoft.com/library/gg398309\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9dcd6-121">[Remove-CsVoicePolicy](https://technet.microsoft.com/library/gg398309\(v=ocs.15\))</span></span>

  - <span data-ttu-id="9dcd6-122">[Set-CsMeetingConfiguration](https://technet.microsoft.com/library/gg398648\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9dcd6-122">[Set-CsMeetingConfiguration](https://technet.microsoft.com/library/gg398648\(v=ocs.15\))</span></span>

  - <span data-ttu-id="9dcd6-123">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg398484\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9dcd6-123">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg398484\(v=ocs.15\))</span></span>

<span data-ttu-id="9dcd6-124">Notez que l’applet de commande **Remove-CsVoicePolicy** est une anomalie.</span><span class="sxs-lookup"><span data-stu-id="9dcd6-124">Note that the **Remove-CsVoicePolicy** cmdlet is something of an anomaly.</span></span> <span data-ttu-id="9dcd6-125">Tout d’abord, cette applet de commande vous oblige à inclure le paramètre Identity :</span><span class="sxs-lookup"><span data-stu-id="9dcd6-125">First, this cmdlet does require you to include the Identity parameter:</span></span>

    Remove-CsVoicePolicy -Identity "global"

<span data-ttu-id="9dcd6-126">Deuxièmement, l’applet de commande **Remove-CsVoicePolicy** ne supprime pas réellement la stratégie de voix globale ; Skype entreprise Online ne vous permet pas de supprimer des stratégies globales ou des paramètres de configuration.</span><span class="sxs-lookup"><span data-stu-id="9dcd6-126">Second, the **Remove-CsVoicePolicy** cmdlet does not actually delete the global voice policy; Skype for Business Online does not allow you to delete global policies or configuration settings.</span></span> <span data-ttu-id="9dcd6-127">La cmdlet permet de rétablir les valeurs par défaut de toutes les propriétés de la stratégie de voix globale.</span><span class="sxs-lookup"><span data-stu-id="9dcd6-127">What the cmdlet does do is enable you to reset all the properties in the global voice policy to their default values.</span></span> <span data-ttu-id="9dcd6-128">Par exemple, par défaut, la propriété AllowCallForwarding est définie sur false.</span><span class="sxs-lookup"><span data-stu-id="9dcd6-128">For example, by default, the AllowCallForwarding property is set to False.</span></span> <span data-ttu-id="9dcd6-129">Toutefois, AllowCallForwarding peut avoir été modifié, avec la valeur true.</span><span class="sxs-lookup"><span data-stu-id="9dcd6-129">However, AllowCallForwarding may have been modified, with the value now set to True.</span></span> <span data-ttu-id="9dcd6-130">Lorsque vous exécutez la cmdlet **Remove-CsVoicePolicy** , la propriété AllowCallForwarding reprend sa valeur par défaut : false.</span><span class="sxs-lookup"><span data-stu-id="9dcd6-130">When you run the **Remove-CsVoicePolicy** cmdlet, the AllowCallForwarding property will revert to its default value: False.</span></span> <span data-ttu-id="9dcd6-131">Le tableau suivant résume ce scénario :</span><span class="sxs-lookup"><span data-stu-id="9dcd6-131">The following table summarizes this scenario:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9dcd6-132">Valeur AllowCallForwarding</span><span class="sxs-lookup"><span data-stu-id="9dcd6-132">AllowCallForwarding Value</span></span></th>
<th><span data-ttu-id="9dcd6-133">Scénario</span><span class="sxs-lookup"><span data-stu-id="9dcd6-133">Scenario</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9dcd6-134">False</span><span class="sxs-lookup"><span data-stu-id="9dcd6-134">False</span></span></p></td>
<td><p><span data-ttu-id="9dcd6-135">Valeur par défaut</span><span class="sxs-lookup"><span data-stu-id="9dcd6-135">Default value</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9dcd6-136">Vrai</span><span class="sxs-lookup"><span data-stu-id="9dcd6-136">True</span></span></p></td>
<td><p><span data-ttu-id="9dcd6-137">Après la modification de la stratégie globale</span><span class="sxs-lookup"><span data-stu-id="9dcd6-137">After the global policy has been modified</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9dcd6-138">False</span><span class="sxs-lookup"><span data-stu-id="9dcd6-138">False</span></span></p></td>
<td><p><span data-ttu-id="9dcd6-139">Après l’exécution de la cmdlet <strong>Remove-CsVoicePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="9dcd6-139">After <strong>Remove-CsVoicePolicy</strong> cmdlet has been run</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a><span data-ttu-id="9dcd6-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9dcd6-140">See Also</span></span>


[<span data-ttu-id="9dcd6-141">Identités, étendues et locataires dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="9dcd6-141">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="9dcd6-142">[Applets de commande Skype entreprise Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9dcd6-142">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

