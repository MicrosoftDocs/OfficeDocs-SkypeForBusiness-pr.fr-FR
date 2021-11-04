---
title: Bloquer les appels entrants dans Skype Entreprise Online
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Skype for Business
ms.localizationpriority: medium
ms.custom: Learn how to use PowerShell to manage inbound call blocking in Skype for Business Online.
ms.openlocfilehash: 6fa72103448d20d9c659eff32735fa5d14389509
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751393"
---
# <a name="block-inbound-calls"></a>Bloquer les appels entrants

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype Entreprise Les forfaits d’appels en ligne prend désormais en charge le blocage des appels entrants en provenance du réseau téléphonique commuté (PSTN). Cette fonctionnalité permet de définir une liste globale de modèles de numéro afin que l’ID d’appelant de chaque appel RSTN entrant vers le client puisse être vérifié par rapport à la liste pour une correspondance. En cas de correspondance, un appel entrant est rejeté.

Cette fonctionnalité de blocage des appels entrants fonctionne uniquement sur les appels entrants provenant du réseau PSTN et fonctionne uniquement sur une base globale du client. Elle n’est pas disponible par utilisateur.  

Cette fonctionnalité n’est pas encore disponible pour le routage direct.

>[!NOTE]
> Les appelants bloqués peuvent avoir des comportements légèrement différents lorsqu’ils ont été bloqués. Le comportement est basé sur la façon dont l’opérateur de l’appelant bloqué gère la notification que l’appel n’est pas autorisé à se terminer correctement. Il peut s’agir, par exemple, d’un message de l’opérateur indiquant que l’appel ne peut pas être effectué comme un appel composé, ou un simple abandon de l’appel.

## <a name="call-blocking-admin-controls-and-information"></a>Appel bloquant les contrôles d’administration et les informations

Les contrôles d’administration pour le blocage des numéros sont fournis à l’aide de PowerShell uniquement. Les modèles de blocs de nombres sont définis en tant que modèles d’expression régulière. L’ordre des expressions n’est pasimportant : le premier modèle de la liste a pour résultat le blocage de l’appel. L’activité d’un nouveau numéro ou modèle ajouté ou supprimé dans la liste des appelants bloqués peut prendre jusqu’à 24 heures.

## <a name="call-blocking-powershell-commands"></a>Appel bloquant les commandes PowerShell

Les modèles de nombres sont ```CsInboundBlockedNumberPattern``` gérés par le biais des ```New``` ```Get``` ```Set``` commandes, et ```Remove``` . Vous pouvez gérer un modèle donné à l’aide de ces cmdlets, y compris la possibilité d’activer un modèle donné.
- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) renvoie la liste de tous les modèles de numéro bloqués ajoutés à la liste des locataires, y compris Nom, Description, Activé (Vrai/Faux) et Modèle pour chacun d’eux.
- [New-CsInboundBlockedNumberPattern ajoute](/powershell/module/skype/new-csinboundblockednumberpattern) un modèle de numéro bloqué à la liste des locataires.
- [Remove-CsInboundBlockedNumberPattern supprime](/powershell/module/skype/remove-csinboundblockednumberpattern) un modèle de numéro bloqué de la liste des locataires.
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifie un ou plusieurs paramètres d’un modèle de nombre bloqué dans la liste des locataires.

L’affichage et l’activation de l’ensemble de la fonctionnalité de blocage d’appel sont ```CsTenantBlockingCallingNumbers``` gérés par le biais des commandes ```Get``` et ```Set``` .

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) renvoie les paramètres de la liste des nombres bloqués globaux, y compris Activé (True/False). Il existe une seule stratégie de client globale qui ne peut pas être modifiée manuellement si ce n’est pour activer ou désactiver la fonctionnalité.
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) permet d’autoriser ou non la modification des appels bloqués du client global au niveau du client.

### <a name="examples"></a>Exemples

#### <a name="block-a-number"></a>Bloquer un numéro

Dans cet exemple, les ```-Enabled``` ```-Description``` paramètres et les paramètres sont facultatifs :

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

La création d’un modèle ajoute le modèle comme étant activé par défaut. La description est un champ facultatif pour fournir des informations supplémentaires.

Nous vous recommandons de fournir un nom significatif pour comprendre facilement pourquoi le modèle a été ajouté. Si vous bloquez simplement les numéros de courrier indésirable, vous pouvez nommer la règle de la même façon que le modèle de nombres qui correspond et ajouter des informations supplémentaires dans la description si nécessaire.

Les modèles sont assortis à l’aide d’expressions régulières (Regex). Autorisez le temps de réplication avant de tester et de valider.

#### <a name="allow-a-number"></a>Autoriser un numéro

Dans cet exemple, le ```-Identity``` paramètre est obligatoire :

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
Si l’identité n’est pas connue, utilisez l’cmdlet pour identifier le modèle approprié ```Get-CsInboundBlockedNumberPattern``` et noter l’identité. Ensuite, exécutez la ```Remove-CsTenantBlockedNumberPattern``` cmdlet et transmettre la valeur d’identité appropriée.

Autorisez le temps de réplication avant de tester et de valider.

#### <a name="view-all-number-patterns"></a>Afficher tous les modèles de nombres

L’exécution de cette cmdlet renvoie la liste de tous les numéros bloqués entrés pour un client :

```powershell
Get-CsInboundBlockedNumberPattern
```

Utilisez les capacités intégrées de filtrage PowerShell pour filtrer les valeurs renvoyées comme requis.

## <a name="add-number-exceptions"></a>Ajouter des exceptions de nombre

Vous pouvez ajouter des exceptions aux modèles de nombres bloqués via les ```CsTenantBlockNumberExceptionPattern``` ```New``` ```Get``` commandes, ```Set``` et ```Remove``` .

- [New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) ajoute un modèle d’exception de nombre à la liste des locataires. 
- [Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) renvoie la liste de tous les modèles d’exceptions de nombres ajoutés à la liste des locataires.
- [Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifie un ou plusieurs paramètres en un ou plusieurs paramètres d’exception dans la liste des locataires.
- [Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) supprime un modèle d’exception de nombre de la liste des locataires.

### <a name="examples"></a>Exemples

#### <a name="add-a-number-exception"></a>Ajouter une exception

Dans cet exemple, un nouveau modèle d’exception de nombre est créé et l’ajoutera par défaut comme étant activé. Les ```-Enabled``` ```-Description``` paramètres et les paramètres sont facultatifs.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>Afficher toutes les exceptions de nombre

Dans cet exemple, le paramètre -Identity est facultatif. Si le paramètre n’est pas spécifié, cette cmdlet renvoie la liste de tous les ```-Identity``` modèles d’exceptions de nombre entrés pour un client.
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Modifier une exception de nombre

Dans cet exemple, le paramètre -Identity est obligatoire. ```Set-CsTenantBlockedNumberExceptionPattern```L’cmdlet vous permet de modifier un ou plusieurs paramètres pour une identité de modèle de nombre donnée.
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>Supprimer une exception

Dans cet exemple, le ```-Identity``` paramètre est obligatoire. Cette cmdlet supprime le modèle de numéro donné de la liste des locataires.  Si l’identité n’est pas connue, utilisez l’cmdlet pour identifier le modèle approprié ```Get-CsInboundBlockedNumberPattern``` et noter l’identité. Ensuite, exécutez la ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet et transmettre la valeur d’identité appropriée.Autorisez le temps de réplication avant de tester et de valider.  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Vérifier si un nombre est bloqué

Utilisez ```Test-CsInboundBlockedNumberPattern``` l’cmdlet pour vérifier si un numéro est bloqué dans le client.
 
Dans cet exemple, les paramètres et les ```-Phonenumber``` ```-Tenant``` paramètres sont obligatoires. Le paramètre doit être une chaîne numérique sans caractères supplémentaires tels que ```-PhoneNumber``` + ou -. Dans le TRPS, ```-Tenant parameter``` l’option est facultative. Le paramètre qui en résulte renvoie la valeur True si le nombre est bloqué dans le client et ```isNumberBlocked``` False s’il n’est pas bloqué.

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

## <a name="related-topics"></a>Sujets associés

- [Configurer votre ordinateur afin qu’il gère Skype Entreprise Online à l’aide d’Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
