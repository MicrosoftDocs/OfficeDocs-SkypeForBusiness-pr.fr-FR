---
title: Applets de commande dans Skype entreprise Online qui utilisent une identité d’utilisateur et l’étendue de la balise
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity and the tag scope
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56558838
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5319d527c859d239cd58eb5561d82a0b47a322e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001439"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a>Applets de commande dans Skype entreprise Online qui utilisent une identité d’utilisateur et l’étendue de la balise

 


Les applets **de commande Grant-CS** (utilisées pour affecter des stratégies aux utilisateurs) nécessitent deux identificateurs : une identité d’utilisateur (le paramètre Identity) et l’identité d’une stratégie par utilisateur (le paramètre PolicyName). Par exemple, pour affecter la stratégie de voix, RedmondVoicePolicy, à l’utilisateur Ken Myer, utilisez la commande suivante :

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Il y a deux éléments à garder à l’esprit lors de l’affectation de stratégies aux utilisateurs. Tout d’abord, seules les stratégies par utilisateur peuvent être affectées. Vous ne pouvez pas attribuer la stratégie globale à un utilisateur. Par exemple, la commande suivante échoue :

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

Cette commande échoue, car il n’est pas nécessaire d’attribuer la stratégie globale. Si vous souhaitez gérer un utilisateur à l’aide de la stratégie globale, assurez-vous que vous n’affectez pas cette stratégie par utilisateur. Si aucune stratégie par utilisateur n’a été affectée à un utilisateur, l’utilisateur est automatiquement géré à l’aide de la stratégie globale.


> [!NOTE]  
> Que se passe-t-il si l’utilisateur a été précédemment affecté à une stratégie par utilisateur et que vous souhaitez annuler l’affectation de cette stratégie et faire en sorte que l’utilisateur soit géré par la stratégie globale à la place ? Dans ce cas, vous utiliserez d’abord la syntaxe suivante, qui annule l’affectation d’une stratégie par utilisateur en accordant à cet utilisateur une stratégie NULL :<BR>Grant-CsVoicePolicy – Identity "Ken Myer" – PolicyName $Null



Deuxièmement, gardez à l’esprit que les stratégies par utilisateur sont créées au niveau de l’étendue de la balise. Toutefois, vous pouvez omettre le **préfixe** de balise lors de la spécification d’un nom de stratégie. Ces deux commandes sont identiques :

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Si vous souhaitez renvoyer les identités de toutes vos stratégies par utilisateur (ou au moins, toutes les stratégies par utilisateur de type spécifié, telles que les stratégies de voix), utilisez une commande semblable à celle-ci :

    Get-CsVoicePolicy -Filter "tag:*"

Les applets de commande suivantes utilisent à la fois l’identité d’un utilisateur et l’étendue de la balise :

  - [Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))

  - [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))

  - [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))

  - [Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))

  - [Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))

  - [Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))

## <a name="see-also"></a>Voir aussi


[Identités, étendues et locataires dans Skype entreprise Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Applets de commande Skype entreprise Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

