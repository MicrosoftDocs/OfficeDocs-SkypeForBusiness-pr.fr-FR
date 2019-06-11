---
title: Cmdlets dans Skype entreprise Online utilisant uniquement l’étendue globale
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that use only the global scope
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56558800
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af9bb88fc4dbe3b7814d1f2f69d711527a769a3b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838099"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a>Cmdlets dans Skype entreprise Online utilisant uniquement l’étendue globale

 


Un certain nombre de paramètres Skype entreprise Online ne sont disponibles qu’à l' *étendue globale*. Cela signifie qu’il existe une collection unique de paramètres qui s’applique à tous les utilisateurs qui sont affectés à ce client. (Chaque client dispose de sa propre collection unique de paramètres globaux.) Lorsque vous utilisez des applets de applet qui sont limitées à l’étendue globale, le paramètre Identity est facultatif. Par exemple, pour récupérer les paramètres de configuration de la réunion, vous pouvez utiliser la commande suivante:

    Get-CsMeetingConfiguration -Identity "global"

Par ailleurs, vous pouvez omettre le paramètre Identity et utiliser cette commande plus simple:

    Get-CsMeetingConfiguration

Étant donné qu’il n’existe qu’une seule collection globale de paramètres de configuration de réunion, les deux commandes renvoient exactement les mêmes informations. Le paramètre Identity peut également être omis lors de l’utilisation d’une cmdlet **Set-CS** . Ces deux commandes sont identiques:

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

Les deux commandes sont identiques, car, par défaut, Windows PowerShell modifie la collection globale si vous n’incluez pas le paramètre Identity.

Les applets de commande suivantes fonctionnent uniquement au niveau de l’étendue globale:

  - [Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))

  - [Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))

  - [Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))

  - [Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))

  - [Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))

  - [Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))

  - [Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))

Notez que l’applet de l’applet de **suppression-CsVoicePolicy** est une anomalie. Tout d’abord, cette applet de recherche vous demande d’inclure le paramètre Identity:

    Remove-CsVoicePolicy -Identity "global"

Deuxièmement, l’applet de l’applet de **suppression-CsVoicePolicy** n’entraîne pas la suppression effective de la stratégie vocale globale. Skype entreprise Online ne vous permet pas de supprimer les stratégies globales ou les paramètres de configuration. Ce que fait l’applet de passe consiste à rétablir ses valeurs par défaut pour toutes les propriétés de la stratégie vocale globale. Par exemple, par défaut, la propriété AllowCallForwarding est définie sur false. Toutefois, AllowCallForwarding a pu être modifié, avec la valeur true. Lorsque vous exécutez l’applet de cmdlet **Remove-CsVoicePolicy** , la propriété AllowCallForwarding revient à sa valeur par défaut: false. Le tableau suivant récapitule ce scénario:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Valeur AllowCallForwarding</th>
<th>Scénario</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>False</p></td>
<td><p>Valeur par défaut</p></td>
</tr>
<tr class="even">
<td><p>True</p></td>
<td><p>Après la modification de la stratégie globale</p></td>
</tr>
<tr class="odd">
<td><p>False</p></td>
<td><p>Après l’exécution de la cmdlet <strong>Remove-CsVoicePolicy</strong></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a>Voir aussi


[Identités, étendues et clients dans Skype entreprise Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Applets de commande de Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

