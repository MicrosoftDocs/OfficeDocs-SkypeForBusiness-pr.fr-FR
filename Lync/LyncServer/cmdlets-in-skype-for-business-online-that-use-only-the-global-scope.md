---
title: Applets de commande utilisant la portée globale uniquement
TOCTitle: Applets de commande utilisant la portée globale uniquement
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56269563
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Applets de commande utilisant la portée globale uniquement

 

_**Dernière rubrique modifiée :** 2015-06-22_

Plusieurs paramètres Skype Entreprise Online sont disponibles au seul niveau de la *portée globale*. En d’autres termes, une seule collection de paramètres est appliquée à l’ensemble des utilisateurs affectés à ce client (chaque client a sa propre collection unique de paramètres globaux). Lorsque vous utilisez des applets de commande limitées à la portée globale, le paramètre Identity est facultatif. Par exemple, pour récupérer les paramètres de configuration d’une réunion, vous pouvez utiliser la commande suivante :

    Get-CsMeetingConfiguration -Identity "global"

Vous pouvez également omettre le paramètre Identity et utiliser cette commande plus simple à la place :

    Get-CsMeetingConfiguration

Comme il n’y a qu’une collection globale de paramètres de configuration de réunion, les deux commandes retournent précisément les mêmes informations. Le paramètre Identity peut également être omis lorsque l’une des applets de commande **Set-Cs** est utilisée. Ces deux commandes sont identiques :

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

Les deux commandes sont identiques, car Windows PowerShell modifie la collection globale par défaut si vous n’incluez pas le paramètre Identity.

Les applets de commande ne fonctionnent qu’au niveau de la portée globale :

  - [Get-CsImFilterConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsImFilterConfiguration)

  - [Get-CsMeetingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingConfiguration)

  - [Get-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPrivacyConfiguration)

  - [Get-CsTenantFederationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTenantFederationConfiguration)

  - [Get-CsTenantHybridConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenantHybridConfiguration)

  - [Get-CsTenantLicensingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenantLicensingConfiguration)

  - [Get-CsTenantPublicProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsTenantPublicProvider)

  - [Remove-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsVoicePolicy)

  - [Set-CsMeetingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMeetingConfiguration)

  - [Set-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPrivacyConfiguration)

Notez que l’applet de commande **Remove-CsVoicePolicy** constitue une sorte d’anomalie. Tout d’abord, cette applet de commande nécessite que vous incluiez le paramètre Identity :

    Remove-CsVoicePolicy -Identity "global"

Deuxièmement, l’applet de commande **Remove-CsVoicePolicy** ne supprime pas réellement la stratégie de voix globale : Skype Entreprise Online ne vous permet pas de supprimer les stratégies globales ou les paramètres de configuration. Elle vous permet seulement de rétablir les valeurs par défaut des propriétés de la stratégie de voix globale. Par exemple, la propriété AllowCallForwarding est définie sur False par défaut. Pour autant, il est possible que la propriété AllowCallForwarding ait été modifiée (la valeur étant définie sur True). Lorsque vous exécutez l’applet de commande **Remove-CsVoicePolicy**, la valeur par défaut (False) de la propriété AllowCallForwarding est rétablie. Le tableau suivant fournit un résumé de ce scénario :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Valeur de la propriété AllowCallForwarding</th>
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
<td><p>Après l’exécution de l’applet de commande <strong>Remove-CsVoicePolicy</strong></p></td>
</tr>
</tbody>
</table>


## Voir aussi

#### Concepts

[Identités, étendues et clients](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Applets de commande de Lync Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

