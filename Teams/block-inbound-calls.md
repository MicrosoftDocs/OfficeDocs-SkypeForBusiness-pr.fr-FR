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
ms.openlocfilehash: ca2f8de5962572a08ab2a0ae7127446d14334c83
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799904"
---
# <a name="block-inbound-calls"></a>Bloquer les appels entrants

Les plans de routage et d’appel directs du système téléphonique (PHONE System Direct Routing and Calling) prisent en charge le blocage des appels entrants à partir du réseau téléphonique commuté (PSTN). Cette fonctionnalité permet de définir une liste globale de modèles de numéro afin que l’ID d’appelant de chaque appel PSTN entrant vers le client puisse être vérifié par rapport à la liste pour une correspondance. En cas de correspondance, un appel entrant est rejeté.

Cette fonctionnalité de blocage des appels entrants fonctionne uniquement sur les appels entrants provenant du réseau PSTN et fonctionne uniquement sur une base globale du client. Elle n’est pas disponible par utilisateur.  

>[!NOTE]
> Les appelants bloqués peuvent avoir des comportements légèrement différents lorsqu’ils sont bloqués. Le comportement est basé sur la façon dont l’opérateur de l’appelant bloqué gère la notification de non-réussite de l’appel. Il peut s’agir, par exemple, d’un message de l’opérateur indiquant que l’appel ne peut pas être effectué comme un appel composé, ou un simple abandon de l’appel.

## <a name="call-blocking-admin-controls-and-information"></a>Appel bloquant les contrôles d’administration et les informations

Les contrôles d’administration pour le blocage des numéros sont fournis à l’aide de PowerShell uniquement. Les modèles de blocs de nombres sont définis en tant que modèles d’expression régulière. L’ordre des expressions n’est pasimportant : le premier modèle de la liste a pour résultat le blocage de l’appel. L’activité d’un nouveau numéro ou modèle ajouté ou supprimé dans la liste des appelants bloqués peut prendre jusqu’à 24 heures.

## <a name="call-blocking-powershell-commands"></a>Appel bloquant les commandes PowerShell

Vous gérez les modèles de nombres à l’aide des cmdlets **New,** **Get,** **Set,** **Remove**  - **CsInboundBlockedNumberPattern.** Vous pouvez gérer un modèle donné à l’aide de ces cmdlets, y compris la possibilité d’activer un modèle donné.

- [Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) renvoie la liste de tous les modèles de nombres bloqués ajoutés à la liste des locataires, y compris Nom, Description, Activé (Vrai/Faux) et Modèle pour chacun d’eux.
- [New-CsInboundBlockedNumberPattern ajoute](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) un modèle de numéro bloqué à la liste des locataires.
- [Remove-CsInboundBlockedNumberPattern supprime](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) un modèle de numéro bloqué de la liste des locataires.
- [Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifie un ou plusieurs paramètres d’un modèle de nombre bloqué dans la liste des locataires.

L’affichage et l’activation de l’ensemble de la fonctionnalité de blocage des appels sont gérés via les cmdlets **Get,** **Set**  - **CsTenantBlockingCallingNumbers.**

- [Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) renvoie les paramètres de la liste des nombres bloqués globaux, y compris Activé (True/False). Il existe une seule stratégie de client globale qui ne peut pas être modifiée manuellement si ce n’est pour activer ou désactiver la fonctionnalité.
- [Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) permet d’autoriser ou non la modification des appels bloqués du client global au niveau du client.

### <a name="examples"></a>Exemples

#### <a name="block-a-number"></a>Bloquer un numéro

Dans cet exemple, les paramètres **Activé** et **Description** sont facultatifs.

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

La création d’un modèle ajoute le modèle comme étant activé par défaut. La description est un champ facultatif pour fournir des informations supplémentaires.

Nous vous recommandons de fournir un nom significatif pour comprendre facilement pourquoi le modèle a été ajouté. Si vous bloquez simplement les numéros de courrier indésirable, envisagez d’nommer la règle de la même façon que le modèle de nombre qui correspond et d’ajouter des informations supplémentaires dans la description si nécessaire.

Les modèles sont assortis à l’aide d’expressions régulières (Regex). Autorisez le temps de réplication avant de tester et de valider.

#### <a name="allow-a-number"></a>Autoriser un numéro

Dans cet exemple, le **paramètre Identité** est obligatoire.

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
Si l’identité n’est pas connue, utilisez l’cmdlet **Get-CsInboundBlockedNumberPattern** pour identifier le modèle approprié et noter l’identité. Ensuite, exécutez la cmdlet **Remove-CsTenantBlockedNumberPattern** et transmettre la valeur d’identité appropriée.

Autorisez le temps de réplication avant de tester et de valider.

#### <a name="view-all-number-patterns"></a>Afficher tous les modèles de nombres

L’exécution de cette cmdlet renvoie la liste de tous les numéros bloqués entrés pour un client :

```powershell
Get-CsInboundBlockedNumberPattern
```

Utilisez les capacités intégrées de filtrage PowerShell pour filtrer les valeurs renvoyées comme requis.

## <a name="add-number-exceptions"></a>Ajouter des exceptions de nombre

Vous pouvez ajouter des exceptions aux modèles de nombres bloqués à l’aide des cmdlets **New,** **Get,** **Set,** **Remove**  - **CsTenantBlockNumberExceptionPattern.**

- [New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) ajoute un modèle d’exception de nombre à la liste des locataires. 
- [Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) renvoie la liste de tous les modèles d’exceptions de nombres ajoutés à la liste des locataires.
- [Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifie un ou plusieurs paramètres en un ou plusieurs paramètres d’exception dans la liste des locataires.
- [Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) supprime un modèle d’exception de nombre de la liste des locataires.

### <a name="examples"></a>Exemples

#### <a name="add-a-number-exception"></a>Ajouter une exception

Dans cet exemple, un nouveau modèle d’exception de nombre est créé et l’ajoutera par défaut comme étant activé. Les **paramètres Activé** **et Description** sont facultatifs.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>Afficher toutes les exceptions de nombre

Dans cet exemple, le **paramètre Identité** est facultatif. Si le **paramètre Identité** n’est pas spécifié, cette cmdlet renvoie la liste de tous les modèles d’exceptions de nombre entrés pour un client.
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Modifier une exception de nombre

Dans cet exemple, le **paramètre Identité** est obligatoire. L’cmdlet **Set-CsTenantBlockedNumberExceptionPattern** vous permet de modifier un ou plusieurs paramètres pour une identité de modèle de nombre donnée.
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>Supprimer une exception

Dans cet exemple, le **paramètre Identité** est obligatoire. Cette cmdlet supprime le modèle de numéro donné de la liste des locataires.  Si l’identité n’est pas connue, utilisez l’cmdlet **Get-CsInboundBlockedNumberPattern** pour identifier le modèle approprié et noter l’identité. Ensuite, exécutez la cmdlet **Remove-CsTenantBlockedNumberExceptionPattern** et transmettre la valeur d’identité appropriée.Autorisez le temps de réplication avant de tester et de valider.  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Vérifier si un nombre est bloqué

Utilisez **l’cmdlet Test-CsInboundBlockedNumberPattern** pour vérifier si un nombre est bloqué dans le client.
 
Dans cet exemple, les **paramètres PhoneNumber** et **Tenant** sont obligatoires. Le **paramètre PhoneNumber** doit être une chaîne numérique sans caractères supplémentaires tels que + ou -. Dans le TRPS, le **paramètre client** est facultatif. Le paramètre **isNumberBlocked** qui en résulte renvoie la valeur True si le nombre est bloqué dans le client et False s’il n’est pas bloqué.

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

## <a name="a-note-about-regex"></a>Note sur Regex

Comme indiqué précédemment, la correspondance au modèle de blocage des appelants est effectuée à l’aide de Regex. Plusieurs outils sont disponibles en ligne pour vous aider à valider une correspondance au modèle Regex. Si vous n’êtes pas familiarisé avec les modèles Regex, nous vous recommandons de prendre le temps de vous familiariser avec les bases. Pour vous assurer d’obtenir les résultats attendus, utilisez un outil pour valider les correspondances de modèle avant d’ajouter de nouveaux nombres bloqués à votre client.
