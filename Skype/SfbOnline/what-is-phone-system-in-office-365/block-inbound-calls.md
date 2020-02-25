---
title: Bloquer les appels entrants dans Skype entreprise Online
ms.author: v-lanac
author: lanachin
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Skype for Business
localization_priority: Normal
ms.custom: Learn how to use PowerShell to manage inbound call blocking in Skype for Business Online.
ms.openlocfilehash: b238d69087c5b29e6d9abc898e91c44fd8053411
ms.sourcegitcommit: bb88ac0c9489bb47957e5ef1074b5df3126b6fdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266063"
---
# <a name="block-inbound-calls"></a>Bloquer les appels entrants

Les abonnements Skype entreprise Online prennent désormais en charge le blocage d’appels entrants du réseau téléphonique public commuté (RTC). Cette fonctionnalité permet de définir une liste globale de clients de modèles de nombre de manière à ce que l’ID d’appelant de chaque appel RTC entrant au client puisse être vérifié par rapport à la liste de correspondance. Si une correspondance est établie, un appel entrant est rejeté.

Cette fonctionnalité de blocage des appels entrants ne fonctionne que sur les appels entrants provenant du RTC et ne fonctionne que sur une base globale du client. Cette fonction n’est pas disponible par utilisateur.  

Cette fonctionnalité n’est pas encore disponible pour le routage direct.

>[!NOTE]
> Les appelants bloqués peuvent avoir un comportement légèrement différent lorsqu’ils sont bloqués. Ce comportement dépend de la façon dont le transporteur de l’appelant bloqué gère la notification d’échec de l’appel. Par exemple, vous pouvez inclure un message de transporteur indiquant que l’appel ne peut pas être effectué comme composé, ou simplement en déposant un appel.

## <a name="call-blocking-admin-controls-and-information"></a>Appels et contrôles d’administration de blocage

Les contrôles d’administration pour bloquer les numéros sont fournis uniquement via PowerShell. Les modèles de blocs de nombres sont définis en tant que modèles d’expressions normales. L’ordre des expressions n’est pas important : le premier modèle correspondant dans la liste entraîne le blocage de l’appel. Un nouveau numéro ou modèle ajouté ou supprimé dans la liste des appelants bloqués peut prendre jusqu’à 24 heures avant que le modèle soit actif.

## <a name="call-blocking-powershell-commands"></a>Commandes PowerShell de blocage des appels

Les modèles de nombre sont gérés ```CsInboundBlockedNumberPattern``` par ```New```le ```Get```biais ```Set```des commandes ```Remove```,, et. Vous pouvez gérer un modèle donné à l’aide de ces applets de option, y compris la possibilité de basculer entre les activations d’un modèle donné.
- [Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) renvoie la liste de tous les modèles de numéros bloqués ajoutés à la liste des clients, y compris le nom, la description, l’activation (vrai/faux) et le modèle pour chacun d’eux.
- [New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) ajoute un modèle de numéro bloqué à la liste des clients.
- [Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) supprime un modèle de numéro bloqué de la liste des clients.
- [Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifie un ou plusieurs paramètres d’un modèle de numéro bloqué dans la liste des clients.

L’affichage et l’activation de la fonctionnalité de blocage des appels complet ```CsTenantBlockingCallingNumbers``` est ```Get``` géré ```Set```via les commandes et.

- [Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) renvoie les paramètres de la liste globale des numéros bloqués, y compris activé (vrai/faux). Il existe une seule stratégie de client globale qui ne peut pas être modifiée manuellement en dehors de l’activation ou de la désactivation de la fonctionnalité.
- [Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) autorise la modification de l’activation et de la désactivation des appels du client global au niveau du client.

### <a name="examples"></a>Exemples

#### <a name="block-a-number"></a>Bloquer un numéro

Dans cet exemple, les ```-Enabled``` paramètres ```-Description``` et sont facultatifs :

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

La création d’un nouveau modèle ajoute le modèle tel qu’il est activé par défaut. La description est un champ facultatif pour fournir des informations supplémentaires.

Nous vous recommandons de fournir un nom significatif pour comprendre facilement la raison pour laquelle le modèle a été ajouté. Dans le cas d’un simple blocage des numéros de courrier indésirable, attribuez-lui le même nom que le modèle de nombre que vous avez mis en correspondance et ajoutez des informations supplémentaires dans la description, le cas échéant.

Les modèles sont associés à l’aide d’expressions régulières (Regex). Autorisez le temps de réplication avant de tester et de valider.

#### <a name="allow-a-number"></a>Autoriser un numéro

Dans cet exemple, le ```-Identity``` paramètre est requis :

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
Si l’identité n’est pas connue, ```Get-CsInboundBlockedNumberPattern``` utilisez la cmdlet pour rechercher d’abord le modèle approprié et notez l’identité. Ensuite, exécutez l' ```Remove-CsTenantBlockedNumberPattern``` applet de cmdlet et transmettez la valeur d’identité appropriée.

Autorisez le temps de réplication avant de tester et de valider.

#### <a name="view-all-number-patterns"></a>Afficher tous les modèles de nombre

L’exécution de cette cmdlet renvoie la liste de tous les numéros bloqués entrés pour un client :

```powershell
Get-CsInboundBlockedNumberPattern
```

Utilisez des capacités de filtrage PowerShell intégrées pour analyser les valeurs renvoyées selon les besoins.

## <a name="add-number-exceptions"></a>Ajouter des exceptions de nombre

Vous pouvez ajouter des exceptions aux modèles de nombre bloqués par ```New```le ```Get```biais ```Set```des ```CsTenantBlockNumberExceptionPattern``` commandes ```Remove```,,, et.

- [New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) ajoute un modèle d’exception numérique à la liste de clients. 
- [Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) renvoie la liste de tous les modèles d’exception de nombre ajoutés à la liste des clients.
- [Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifie un ou plusieurs paramètres en un modèle d’exception numérique dans la liste des clients.
- [Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) supprime un modèle d’exception numérique de la liste des clients.

### <a name="examples"></a>Exemples

#### <a name="add-a-number-exception"></a>Ajouter une exception de nombre

Dans cet exemple, un nouveau modèle d’exception de nombre est créé et il ajoute par défaut le modèle est activé. Les ```-Enabled``` paramètres ```-Description``` et sont facultatifs.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>Afficher toutes les exceptions d’une numérotation

Dans cet exemple, le paramètre-Identity est facultatif. Si le ```-Identity``` paramètre n’est pas spécifié, cette applet de cmdlet renvoie une liste de tous les modèles d’exception de nombre entrés pour un client.
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Modifier une exception de nombre

Dans cet exemple, le paramètre-Identity est obligatoire. L' ```Set-CsTenantBlockedNumberExceptionPattern``` applet de passe vous permet de modifier un ou plusieurs paramètres pour une identité de modèle de nombre donnée.
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>Supprimer un numéro d’exception

Dans cet exemple, le ```-Identity``` paramètre est obligatoire. Cette applet de passe supprime le modèle de nombre indiqué de la liste des clients.  Si l’identité n’est pas connue, ```Get-CsInboundBlockedNumberPattern``` utilisez la cmdlet pour rechercher d’abord le modèle approprié et notez l’identité. Ensuite, exécutez l' ```Remove-CsTenantBlockedNumberExceptionPattern``` applet de cmdlet et transmettez la valeur d’identité appropriée.Autorisez le temps de réplication avant de tester et de valider.  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Tester la présence d’un numéro bloqué

Utilisez l' ```Test-CsInboundBlockedNumberPattern``` applet de contrôle pour vérifier si un numéro est bloqué dans le client.
 
Dans cet exemple, les ```-Phonenumber``` paramètres ```-Tenant``` et sont obligatoires. Le ```-PhoneNumber``` paramètre doit être une chaîne numérique sans caractère supplémentaire, comme + ou-. Dans TRPS, ```-Tenant parameter``` est facultatif. Le paramètre ```isNumberBlocked``` obtenu renvoie la valeur vrai si le nombre est bloqué dans le client et faux s’il n’est pas bloqué.

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|httpResponseCode  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | Vrai        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|httpResponseCode  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | False        |         |

## <a name="a-note-about-regex"></a>Note concernant Regex

Comme indiqué plus haut, le modèle correspondant au blocage des appelants est réalisé à l’aide de Regex. Plusieurs outils sont disponibles en ligne pour vous aider à valider une correspondance de modèle Regex. Si vous n’êtes pas familiarisé avec les modèles Regex, nous vous conseillons de prendre le temps de vous familiariser avec les concepts de base. Pour vous assurer que vous obtenez les résultats attendus, utilisez un outil permettant de valider les correspondances de modèles avant d’ajouter le nouveau numéro bloqué à votre client. 

## <a name="related-topics"></a>Rubriques connexes

- [Configurer votre ordinateur pour gérer Skype entreprise Online à l’aide de Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
