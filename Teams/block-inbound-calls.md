---
title: Bloquer les appels entrants dans Microsoft Teams
ms.author: v-mahoffman
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
ms.localizationpriority: medium
ms.custom: Learn how to use PowerShell to manage inbound call blocking.
ms.openlocfilehash: 4e7e6d40173bb5917a6cf540481257b21253eeaa
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766222"
---
# <a name="block-inbound-calls"></a>Bloquer les appels entrants

Les plans d’appel Microsoft, le routage direct et l’opérateur Connecter prise en charge du blocage des appels entrants à partir du réseau téléphonique public commuté (PSTN). Cette fonctionnalité permet à un administrateur de définir une liste de modèles de numéro au niveau global du client de telle sorte que l’ID d’appelant de chaque appel PSTN entrant vers le client puisse être vérifié dans la liste pour une correspondance. En cas de correspondance, un appel entrant est rejeté.

Cette fonctionnalité de blocage des appels entrants fonctionne uniquement sur les appels entrants provenant du réseau PSTN et fonctionne uniquement au niveau global du client. Les utilisateurs Teams ne peuvent pas manipuler cette liste. Le Teams client autorise les utilisateurs individuels à bloquer les appels PSTN. Pour plus d’informations sur la façon dont vos utilisateurs finaux peuvent implémenter le blocage des appels, voir Gérer les [paramètres d’appel dans Teams.](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)

>[!NOTE]
> Les appelants bloqués peuvent avoir des comportements légèrement différents lorsqu’ils sont bloqués. Le comportement est basé sur la façon dont l’opérateur de l’appelant bloqué gère la notification que l’appel n’est pas autorisé à se terminer correctement. Il peut s’agir, par exemple, d’un message de l’opérateur indiquant que l’appel ne peut pas être effectué comme un appel composé, ou un simple abandon de l’appel.

## <a name="call-blocking-admin-controls-and-information"></a>Appel bloquant les contrôles d’administration et les informations

Les contrôles d’administration pour le blocage des numéros sont fournis à l’aide de PowerShell uniquement. Les modèles de blocs de nombres sont définis en tant que modèles d’expression régulière. L’ordre des expressions n’est pasimportant : le premier modèle de la liste a pour résultat le blocage de l’appel. L’activité d’un nouveau numéro ou modèle ajouté ou supprimé dans la liste des appelants bloqués peut prendre jusqu’à 24 heures.

## <a name="call-blocking-powershell-commands"></a>Appel bloquant les commandes PowerShell

Vous gérez les modèles de numéro à l’aide des cmdlets **New-,** **Get-,** **Set-** et **Remove-CsInboundBlockedNumberPattern.** Vous pouvez gérer un modèle donné à l’aide de ces cmdlets, y compris la possibilité d’activer un modèle donné.

- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) renvoie la liste de tous les modèles de numéro bloqués ajoutés à la liste des locataires, y compris Nom, Description, Activé (Vrai/Faux) et Modèle pour chacun d’eux.
- [New-CsInboundBlockedNumberPattern ajoute](/powershell/module/skype/new-csinboundblockednumberpattern) un modèle de numéro bloqué à la liste des locataires.
- [Remove-CsInboundBlockedNumberPattern supprime](/powershell/module/skype/remove-csinboundblockednumberpattern) un modèle de numéro bloqué de la liste des locataires.
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifie un ou plusieurs paramètres d’un modèle de nombre bloqué dans la liste des locataires.

L’affichage et l’activation de l’ensemble de la fonctionnalité de blocage d’appels sont gérés par le biais des cmdlets **Get-and-Set-CsTenantBlockingCallingNumbers.** 

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) renvoie les modèles de numéro de bloc entrant et les paramètres de modèles de nombres exemptés entrants pour la liste de nombres bloqués globaux. Cette cmdlet renvoie également si le blocage a été activé (True ou False). Il existe une seule stratégie de client globale qui ne peut pas être modifiée manuellement si ce n’est pour activer ou désactiver la fonctionnalité.
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) permet d’autoriser ou non la modification des appels bloqués du client global au niveau du client.

### <a name="examples"></a>Exemples

#### <a name="block-a-number"></a>Bloquer un numéro

Dans l’exemple suivant, l’administrateur client souhaite bloquer tous les appels provenant de la plage de numéro 1 (312) 555-0000 à 1 (312) 555-9999. Le modèle de nombre est créé de sorte que les deux nombres de la plage avec + préfixe et les nombres de la plage sans préfixe + soient mis en correspondance. Vous n’avez pas besoin d’inclure les symboles – et () dans les numéros de téléphone, car le système les bande avant la correspondance.  Pour activer le modèle de nombre, le **paramètre** Activé a la valeur True. Pour désactiver ce modèle de nombre spécifique, définissez le paramètre sur False.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

Dans l’exemple suivant, l’administrateur client souhaite bloquer tous les appels provenant du numéro 1 (412) 555-1234. Pour activer le modèle de nombre, le **paramètre** Activé a la valeur True.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

La création d’un modèle ajoute le modèle comme étant activé par défaut. La description est un champ facultatif pour fournir des informations supplémentaires.

Nous vous recommandons de fournir un nom significatif pour comprendre facilement pourquoi le modèle a été ajouté. Si vous bloquez simplement les numéros de courrier indésirable, vous pouvez nommer la règle de la même façon que le modèle de nombres qui correspond et ajouter des informations supplémentaires dans la description si nécessaire.

Les modèles sont assortis à l’aide d’expressions régulières (Regex). Pour plus d’informations, voir [Utiliser Regex.](#using-regex)

Autorisez le temps de réplication avant de tester et de valider. 

#### <a name="allow-a-number"></a>Autoriser un numéro

Vous pouvez autoriser un numéro à appeler en supprimant le modèle de numéro bloqué. Dans l’exemple suivant, l’administrateur client souhaite autoriser le 1 (412) 555-1234 à effectuer de nouveaux appels.

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```
 
Si l’identité n’est pas connue, utilisez l’cmdlet **Get-CsInboundBlockedNumberPattern** pour identifier le modèle approprié et noter l’identité. Ensuite, exécutez la **cmdlet Remove-CsInboundBlockedNumberPattern** et transmettre la valeur d’identité appropriée.

Autorisez le temps de réplication avant de tester et de valider.

#### <a name="view-all-number-patterns"></a>Afficher tous les modèles de nombres

L’exécution de cette cmdlet renvoie la liste de tous les numéros bloqués entrés pour un client :

```powershell
Get-CsInboundBlockedNumberPattern
```

Utilisez les capacités intégrées de filtrage PowerShell pour filtrer les valeurs renvoyées comme requis.

## <a name="add-number-exceptions"></a>Ajouter des exceptions de nombre

Vous pouvez ajouter des exceptions aux modèles de nombres bloqués à l’aide des cmdlets **New-,** **Get-,** **Set-** et **Remove-CsInboundExemptNumberPattern.**

- [New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) ajoute un modèle d’exception de nombre à la liste des locataires. 
- [Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) renvoie la liste de tous les modèles d’exceptions de nombres ajoutés à la liste des locataires.
- [Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) modifie un ou plusieurs paramètres en un modèle d’exception de nombre dans la liste des locataires.
- [Remove-CsInboundExemptNumberPattern supprime](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) un modèle d’exception de nombre de la liste des locataires.

### <a name="examples"></a>Exemples

#### <a name="add-a-number-exception"></a>Ajouter une exception

Dans l’exemple suivant, l’administrateur client souhaite autoriser les numéros de téléphone 1 (312) 555-8882 et 1 (312) 555-8883 pour appeler le client, même si ces deux numéros de téléphone se trouveraient dans la plage bloquée dans l’exemple ci-dessus. Pour ce faire, un nouveau modèle d’exception de nombre est créé comme suit :

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

Pour activer le modèle de nombre, le **paramètre** Activé a la valeur True. Pour désactiver ce modèle de nombre spécifique, définissez le paramètre sur False.


#### <a name="view-all-number-exceptions"></a>Afficher toutes les exceptions de nombre

Dans cet exemple, le **paramètre Identité** est facultatif. Si le **paramètre Identité** n’est pas spécifié, cette cmdlet renvoie la liste de tous les modèles d’exceptions de nombre entrés pour un client.
 
```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```
 
```powershell
Get-CsInboundExemptNumberPattern 
```

#### <a name="modify-a-number-exception"></a>Modifier une exception de nombre

L’cmdlet **Set-CsInboundExemptNumberPattern** vous permet de modifier un ou plusieurs paramètres pour une identité de modèle de nombre donnée. Dans cet exemple, le **paramètre Identité** est obligatoire.
 
```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a>Supprimer une exception

L’cmdlet **Remove-CsInboundExemptNumberPattern** supprime le modèle de nombre donné de la liste de locataires. Dans cet exemple, le **paramètre Identité** est obligatoire. 

Si l’identité n’est pas connue, utilisez l’cmdlet **Get-CsInboundExemptNumberPattern** pour rechercher le modèle approprié et noter l’identité. Ensuite, exécutez la cmdlet **Remove-CsInboundExemptNumberPattern** et transmettre la valeur d’identité appropriée.Autorisez le temps de réplication avant de tester et de valider.  

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="test-whether-a-number-is-blocked"></a>Vérifier si un nombre est bloqué

Utilisez **l’cmdlet Test-CsInboundBlockedNumberPattern** pour vérifier si un nombre est bloqué dans le client.
 
Le **paramètre PhoneNumber** est obligatoire et doit être une chaîne numérique sans caractères supplémentaires, tels que +, - ou (). Le paramètre **IsNumberBlocked** qui en résulte renvoie la valeur True si le nombre est bloqué dans le client . Le paramètre renvoie False s’il n’est pas bloqué.

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

### <a name="examples"></a>Exemples

Dans ces exemples, vous pouvez voir que le numéro de téléphone 1 (312) 555-8884 est bloqué car il devrait être dans la plage bloquée ci-dessus, alors que le numéro de téléphone 1 (312) 555-8883 est autorisé à appeler comme il devrait l’être en fonction de l’exonération créée ci-dessus.

```PowerShell
Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558884

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : True
errorMessage    :

Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558883

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : False
errorMessage    :
```

## <a name="using-regex"></a>Utilisation de Regex

La correspondance au modèle de blocage des appelants est effectuée à l’aide de Regex. Plusieurs outils sont disponibles en ligne pour vous aider à valider une correspondance au modèle Regex. Si vous n’êtes pas familiarisé avec les modèles Regex, nous vous recommandons de prendre le temps de vous familiariser avec les bases. Pour vous assurer d’obtenir les résultats attendus, utilisez un outil pour valider les correspondances de modèle avant d’ajouter de nouveaux nombres bloqués à votre client.