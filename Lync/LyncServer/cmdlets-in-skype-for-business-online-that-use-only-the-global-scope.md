---
title: Applets de commande dans Skype entreprise Online qui utilisent uniquement l’étendue globale
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
ms.openlocfilehash: b97f3c8d9ca7dda0b96db211192350184cbf27b1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755096"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a>Applets de commande dans Skype entreprise Online qui utilisent uniquement l’étendue globale

 


Un certain nombre de paramètres Skype entreprise Online sont disponibles uniquement au niveau *Global*. Cela signifie qu’il existe une seule collection de paramètres qui s’applique à tous les utilisateurs qui sont affectés à ce client. (Chaque client possède sa propre collection de paramètres globaux uniques.) Lorsque vous utilisez des applets de commande limitées à l’étendue globale, le paramètre Identity est facultatif. Par exemple, pour récupérer les paramètres de configuration de réunion, vous pouvez utiliser la commande suivante :

    Get-CsMeetingConfiguration -Identity "global"

Vous pouvez également omettre le paramètre Identity et utiliser cette commande plus simple :

    Get-CsMeetingConfiguration

Étant donné qu’il n’existe qu’une seule collection globale de paramètres de configuration de réunion, les deux commandes renvoient exactement les mêmes informations. Le paramètre Identity peut également être omis lors de l’utilisation de l’une des cmdlets **Set-CS** . Ces deux commandes sont identiques :

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

Les deux commandes sont identiques car, par défaut, Windows PowerShell modifie la collection globale si vous n’incluez pas le paramètre Identity.

Les applets de commande suivantes fonctionnent uniquement au niveau de l’étendue globale :

  - [Get-CsImFilterConfiguration](https://technet.microsoft.com/library/gg398980\(v=ocs.15\))

  - [Get-CsMeetingConfiguration](https://technet.microsoft.com/library/gg425875\(v=ocs.15\))

  - [Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg413002\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))

  - [Get-CsTenantPublicProvider](https://technet.microsoft.com/library/jj994016\(v=ocs.15\))

  - [Remove-CsVoicePolicy](https://technet.microsoft.com/library/gg398309\(v=ocs.15\))

  - [Set-CsMeetingConfiguration](https://technet.microsoft.com/library/gg398648\(v=ocs.15\))

  - [Set-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg398484\(v=ocs.15\))

Notez que l’applet de commande **Remove-CsVoicePolicy** est une anomalie. Tout d’abord, cette applet de commande vous oblige à inclure le paramètre Identity :

    Remove-CsVoicePolicy -Identity "global"

Deuxièmement, l’applet de commande **Remove-CsVoicePolicy** ne supprime pas réellement la stratégie de voix globale ; Skype entreprise Online ne vous permet pas de supprimer des stratégies globales ou des paramètres de configuration. La cmdlet permet de rétablir les valeurs par défaut de toutes les propriétés de la stratégie de voix globale. Par exemple, par défaut, la propriété AllowCallForwarding est définie sur false. Toutefois, AllowCallForwarding peut avoir été modifié, avec la valeur true. Lorsque vous exécutez la cmdlet **Remove-CsVoicePolicy** , la propriété AllowCallForwarding reprend sa valeur par défaut : false. Le tableau suivant résume ce scénario :


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
<td><p>Faux</p></td>
<td><p>Valeur par défaut</p></td>
</tr>
<tr class="even">
<td><p>Vrai</p></td>
<td><p>Après la modification de la stratégie globale</p></td>
</tr>
<tr class="odd">
<td><p>Faux</p></td>
<td><p>Après l’exécution de la cmdlet <strong>Remove-CsVoicePolicy</strong></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a>Voir aussi


[Identités, étendues et locataires dans Skype entreprise Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Applets de commande Skype entreprise Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

