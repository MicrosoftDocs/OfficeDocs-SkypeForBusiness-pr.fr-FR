---
title: Applets de commande qui utilisent une identité utilisateur et l’étendue de balise
TOCTitle: Applets de commande qui utilisent une identité utilisateur et l’étendue de balise
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56269573
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Applets de commande qui utilisent une identité utilisateur et l’étendue de balise

 

_**Dernière rubrique modifiée :** 2015-06-22_

Les applets de commande **Grant-Cs** (utilisées pour affecter des stratégies aux utilisateurs) nécessitent deux identifiants : une identité utilisateur (paramètre Identity) et l’identité d’une stratégie utilisateur (paramètre PolicyName). Par exemple, pour affecter la stratégie de voix RedmondVoicePolicy à l’utilisateur Ken Myer, vous devez utiliser la commande suivante :

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Deux éléments sont à prendre en compte quand vous affectez des stratégies à des utilisateurs. Premièrement, seules des stratégies utilisateur peuvent être affectées. Vous ne pouvez pas affecter la stratégie globale à un utilisateur. Par exemple, la commande suivante échouera :

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

Cette commande échoue, car il n’y a pas besoin d’affecter la stratégie globale. Si vous voulez gérer un utilisateur à l’aide de la stratégie globale, veillez à ne pas affecter une stratégie utilisateur à cet utilisateur. Si aucune stratégie utilisateur n’a été affectée à un utilisateur, l’utilisateur est géré automatiquement à l’aide de la stratégie globale.

> [!NOTE]  
> Que se passe-t-il si une stratégie utilisateur a déjà été affectée à l’utilisateur et que vous voulez annuler l’affectation de cette stratégie pour que l’utilisateur soit géré par la stratégie globale ? Dans ce cas, vous devez commencer par utiliser la syntaxe suivante qui permet d’annuler l’affectation d’une stratégie utilisateur via l’octroi d’une stratégie null à cet utilisateur :<br />
Grant-CsVoicePolicy –Identity &quot;Ken Myer&quot; –PolicyName $Null


Rappelez-vous ensuite que ces stratégies utilisateur sont créées au niveau de l’étendue de balise. Vous pouvez toutefois omettre le **préfixe** de la balise lorsque vous spécifiez le nom d’une stratégie. Ces deux commandes sont identiques :

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Si vous voulez retourner les identités pour toutes vos stratégies utilisateur (ou au moins toutes les stratégies utilisateur du type spécifié, telles que les stratégies de voix), utilisez une commande comme celle-ci :

    Get-CsVoicePolicy -Filter "tag:*"

Les applets de commande suivantes utilisent une identité utilisateur et l’étendue de balise :

  - [Grant-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsClientPolicy)

  - [Grant-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsConferencingPolicy)

  - [Grant-CsDialPlan](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsDialPlan)

  - [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)

  - [Grant-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsHostedVoicemailPolicy)

  - [Grant-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsVoicePolicy)

## Voir aussi

#### Concepts

[Identités, étendues et clients](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Applets de commande de Lync Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

