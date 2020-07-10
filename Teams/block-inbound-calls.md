---
title: Bloquer les appels entrants dans Microsoft teams
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 3bb1222f0662228e5c0de7b2253cbac162571b1e
ms.sourcegitcommit: a36514c7c8ea47bde4edb09c11ff99061b1f74c0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094680"
---
# <a name="block-inbound-calls"></a>Bloquer les appels entrants

Le système téléphonique et les offres d’appels prennent en charge le blocage des appels entrants du réseau téléphonique public commuté (RTC). Cette fonctionnalité permet de définir une liste globale de clients de modèles de nombre de manière à ce que l’ID d’appelant de chaque appel RTC entrant au client puisse être vérifié par rapport à la liste de correspondance. Si une correspondance est établie, un appel entrant est rejeté.

Cette fonctionnalité de blocage des appels entrants ne fonctionne que sur les appels entrants provenant du RTC et ne fonctionne que sur une base globale du client. Cette fonction n’est pas disponible par utilisateur.  

>[!NOTE]
> Les appelants bloqués peuvent avoir un comportement légèrement différent lorsqu’ils sont bloqués. Ce comportement dépend de la façon dont le transporteur de l’appelant bloqué gère la notification d’échec de l’appel. Par exemple, vous pouvez inclure un message de transporteur indiquant que l’appel ne peut pas être effectué comme composé, ou simplement en déposant un appel.

## <a name="call-blocking-admin-controls-and-information"></a>Appels et contrôles d’administration de blocage

Les contrôles d’administration pour bloquer les numéros sont fournis uniquement via PowerShell. Les modèles de blocs de nombres sont définis en tant que modèles d’expressions normales. L’ordre des expressions n’est pas important : le premier modèle correspondant dans la liste entraîne le blocage de l’appel. Un nouveau numéro ou modèle ajouté ou supprimé dans la liste des appelants bloqués peut prendre jusqu’à 24 heures avant que le modèle soit actif.

## <a name="call-blocking-powershell-commands"></a>Commandes PowerShell de blocage des appels

Vous pouvez gérer les modèles de nombre à l’aide des **nouvelles**cmdlets **Get**, **Set**et **Remove**  - **CsInboundBlockedNumberPattern** . Vous pouvez gérer un modèle donné à l’aide de ces applets de option, y compris la possibilité de basculer entre les activations d’un modèle donné.

- [Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) renvoie la liste de tous les modèles de numéros bloqués ajoutés à la liste des clients, y compris le nom, la description, l’activation (vrai/faux) et le modèle pour chacun d’eux.
- [New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) ajoute un modèle de numéro bloqué à la liste des clients.
- [Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) supprime un modèle de numéro bloqué de la liste des clients.
- [Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifie un ou plusieurs paramètres d’un modèle de numéro bloqué dans la liste des clients.

L’affichage et l’activation de la fonctionnalité de blocage des appels complet est géré via les applets de CsTenantBlockingCallingNumbers **Get**et **Set**  - **CsTenantBlockingCallingNumbers** .

- [Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) renvoie les paramètres de la liste globale des numéros bloqués, y compris activé (vrai/faux). Il existe une seule stratégie de client globale qui ne peut pas être modifiée manuellement en dehors de l’activation ou de la désactivation de la fonctionnalité.
- [Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) autorise la modification de l’activation et de la désactivation des appels du client global au niveau du client.

### <a name="examples"></a>Exemples

#### <a name="block-a-number"></a>Bloquer un numéro

Dans cet exemple, les paramètres **Enabled** et **Description** sont facultatifs.

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

La création d’un nouveau modèle ajoute le modèle tel qu’il est activé par défaut. La description est un champ facultatif pour fournir des informations supplémentaires.

Nous vous recommandons de fournir un nom significatif pour comprendre facilement la raison pour laquelle le modèle a été ajouté. Dans le cas d’un simple blocage des numéros de courrier indésirable, attribuez-lui le même nom que le modèle de nombre que vous avez mis en correspondance et ajoutez des informations supplémentaires dans la description, le cas échéant.

Les modèles sont associés à l’aide d’expressions régulières (Regex). Autorisez le temps de réplication avant de tester et de valider.

#### <a name="allow-a-number"></a>Autoriser un numéro

Dans cet exemple, le paramètre **Identity** est obligatoire.

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
Si l’identité n’est pas connue, utilisez l’applet de passe **Get-CsInboundBlockedNumberPattern** pour trouver le modèle approprié et noter l’identité. Ensuite, exécutez l’applet de **CsTenantBlockedNumberPattern de suppression** et transmettez la valeur d’identité appropriée.

Autorisez le temps de réplication avant de tester et de valider.

#### <a name="view-all-number-patterns"></a>Afficher tous les modèles de nombre

L’exécution de cette cmdlet renvoie la liste de tous les numéros bloqués entrés pour un client :

```powershell
Get-CsInboundBlockedNumberPattern
```

Utilisez des capacités de filtrage PowerShell intégrées pour analyser les valeurs renvoyées selon les besoins.

## <a name="add-number-exceptions"></a>Ajouter des exceptions de nombre

Vous pouvez ajouter des exceptions aux modèles de nombre bloqués à l’aide des applets de **nouvelle**applet de CsTenantBlockNumberExceptionPattern, **Get**, **Set**et **Remove**  - **CsTenantBlockNumberExceptionPattern** .

- [New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) ajoute un modèle d’exception numérique à la liste de clients. 
- [Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) renvoie la liste de tous les modèles d’exception de nombre ajoutés à la liste des clients.
- [Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifie un ou plusieurs paramètres en un modèle d’exception numérique dans la liste des clients.
- [Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) supprime un modèle d’exception numérique de la liste des clients.

### <a name="examples"></a>Exemples

#### <a name="add-a-number-exception"></a>Ajouter une exception de nombre

Dans cet exemple, un nouveau modèle d’exception de nombre est créé et il ajoute par défaut le modèle est activé. Les paramètres **Enabled** et **Description** sont facultatifs.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>Afficher toutes les exceptions d’une numérotation

Dans cet exemple, le paramètre **Identity** est facultatif. Si le paramètre **Identity** n’est pas spécifié, cette applet de cmdlet renvoie une liste de modèles d’exception de nombre entrés pour un client.
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Modifier une exception de nombre

Dans cet exemple, le paramètre **Identity** est obligatoire. L’applet **de passe Set-CsTenantBlockedNumberExceptionPattern** vous permet de modifier un ou plusieurs paramètres pour une identité de modèle de nombre donnée.
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>Supprimer un numéro d’exception

Dans cet exemple, le paramètre **Identity** est obligatoire. Cette applet de passe supprime le modèle de nombre indiqué de la liste des clients.  Si l’identité n’est pas connue, utilisez l’applet de passe **Get-CsInboundBlockedNumberPattern** pour trouver le modèle approprié et noter l’identité. Ensuite, exécutez l’applet de **CsTenantBlockedNumberExceptionPattern de suppression** et transmettez la valeur d’identité appropriée.Autorisez le temps de réplication avant de tester et de valider.  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Tester la présence d’un numéro bloqué

Utilisez l’applet de **contrôle test-CsInboundBlockedNumberPattern** pour vérifier si un numéro est bloqué dans le client.
 
Dans cet exemple, les paramètres **PhoneNumber** et **locataire** sont obligatoires. Le paramètre **PhoneNumber** doit être une chaîne numérique sans caractère supplémentaire, comme + ou-. Dans TRPS, le **paramètre locataire** est facultatif. Le paramètre **isNumberBlocked** obtenu renvoie la valeur true si le nombre est bloqué dans le locataire et false dans le cas contraire.

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
