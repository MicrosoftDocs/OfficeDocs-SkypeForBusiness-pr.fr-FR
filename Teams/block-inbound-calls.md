---
title: Bloquer les appels entrants dans Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
ms.custom: ''
description: Découvrez comment utiliser PowerShell pour gérer le blocage des appels entrants.
ms.openlocfilehash: 01d1fb08d0b0cca4bc0a35ca77109e976d63a1f0
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614427"
---
# <a name="block-inbound-calls"></a>Bloquer les appels entrants

Les forfaits d’appels Microsoft, le routage direct et l’opérateur Connect prennent tous en charge le blocage des appels entrants à partir du réseau téléphonique commuté (RTC). Cette fonctionnalité permet à un administrateur de définir une liste de modèles de nombres et d’exceptions au niveau global du locataire afin que l’ID d’appelant de chaque appel RTC entrant au locataire puisse être vérifié par rapport à la liste pour une correspondance. Si une correspondance est établie, un appel entrant est rejeté.

Cette fonctionnalité de blocage des appels entrants fonctionne uniquement sur les appels entrants qui proviennent du rtc et fonctionne uniquement au niveau global du locataire. Les utilisateurs Teams individuels ne peuvent pas manipuler cette liste. Le client Teams permet aux utilisateurs individuels de bloquer les appels RTC. Pour plus d’informations sur la façon dont vos utilisateurs finaux peuvent implémenter le blocage des appels, consultez [Gérer les paramètres d’appel dans Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).

> [!NOTE]
> Les appelants bloqués peuvent rencontrer des comportements légèrement différents lorsqu’ils ont été bloqués. Le comportement est basé sur la façon dont le transporteur de l’appelant bloqué gère la notification indiquant que l’appel n’est pas autorisé à se terminer correctement. Il peut s’agir, par exemple, d’un message indiquant que l’appel ne peut pas être effectué en tant que numérotation, ou simplement de la suppression de l’appel.

Notez qu’il n’est actuellement pas possible de gérer le blocage des appels à l’aide du Centre d’administration Teams.

## <a name="manage-call-blocking-by-using-powershell"></a>Gérer le blocage des appels à l’aide de PowerShell

Pour gérer le blocage des appels, vous devez définir un ou plusieurs modèles de nombres pour bloquer les appels, définir des exceptions aux modèles de nombres et activer la fonctionnalité de blocage des appels.

Les modèles de blocs de nombres sont définis comme des modèles d’expression régulière. L’ordre des expressions n’est pas important : le premier modèle mis en correspondance dans la liste entraîne le blocage de l’appel. Un nouveau nombre ou modèle ajouté ou supprimé dans la liste des appelants bloqués peut prendre jusqu’à 24 heures pour que le modèle devienne actif.

### <a name="activate-the-call-blocking-feature"></a>Activer la fonctionnalité de blocage des appels

Pour afficher et activer la fonctionnalité de blocage des appels, utilisez les applets de commande du module PowerShell **Teams Get-** et **Set-CsTenantBlockingCallingNumbers** Teams.

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) retourne les modèles de nombre de blocs entrants et les paramètres des modèles de nombres exemptés entrants pour la liste des nombres bloqués globaux. Cette applet de commande retourne également si le blocage a été activé (True ou False). 

- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) vous permet de spécifier si les appels bloqués du locataire global sont activés ou désactivés au niveau du locataire.

### <a name="manage-block-number-patterns"></a>Gérer les modèles de nombre de blocs

Vous gérez les modèles de nombres à l’aide des applets de commande PowerShell **De nouvelles**, **Get**, **Set****, Test** et **Remove-CsInboundBlockedNumberPattern Teams**. 

- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) retourne une liste de tous les modèles de nombres bloqués ajoutés à la liste des locataires, notamment Nom, Description, Activé (True/False) et Modèle.

- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) ajoute un modèle de nombre bloqué à la liste des locataires.

- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) supprime un modèle de nombre bloqué de la liste des locataires.

- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifie un ou plusieurs paramètres d’un modèle de nombre bloqué dans la liste des locataires.

- [Test-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) teste si les appels à partir d’un numéro de téléphone donné seront bloqués.


### <a name="examples"></a>Exemples

#### <a name="block-a-number"></a>Bloquer un nombre

Dans l’exemple suivant, l’administrateur client souhaite bloquer tous les appels provenant de la plage de numéros 1 (312) 555-0000 à 1 (312) 555-9999. Le modèle de nombre est créé afin que les deux nombres de la plage avec + préfixé et les nombres de la plage sans + préfixé soient mis en correspondance. Vous n’avez pas besoin d’inclure les symboles et () dans les numéros de téléphone, car le système supprime ces symboles avant la correspondance.  Pour activer le modèle de nombre, **définissez** le paramètre Activé sur True. Pour désactiver ce modèle de nombre spécifique, définissez le paramètre sur False.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

Dans l’exemple suivant, l’administrateur client souhaite bloquer tous les appels provenant du numéro 1 (412) 555-1234. Pour activer le modèle de nombre, le paramètre **Activé** est défini sur True.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

La création d’un modèle ajoute le modèle comme activé par défaut. La description est un champ facultatif pour fournir plus d’informations.

Nous vous recommandons de fournir un nom explicite pour comprendre facilement pourquoi le modèle a été ajouté. Pour bloquer les numéros de courrier indésirable, envisagez de nommer la règle de la même manière que le modèle de nombre mis en correspondance, puis ajoutez des informations supplémentaires dans la description selon les besoins.

Les modèles sont mis en correspondance à l’aide d’expressions régulières (Expressions régulières). Pour plus d’informations, consultez [Utilisation de Regex](#using-regex).

Accordez du temps pour la réplication avant de tester et de valider.

#### <a name="allow-a-number"></a>Autoriser un nombre

Vous pouvez autoriser l’appel d’un nombre en supprimant le modèle de nombre bloqué. Dans l’exemple suivant, l’administrateur client souhaite autoriser 1 (412) 555-1234 à effectuer de nouveau des appels.

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```

Si l’identité n’est pas connue, utilisez l’applet de commande **Get-CsInboundBlockedNumberPattern** pour d’abord localiser le modèle approprié et noter l’identité. Ensuite, exécutez l’applet **de commande Remove-CsInboundBlockedNumberPattern** et transmettez la valeur d’identité appropriée.

Accordez du temps pour la réplication avant de tester et de valider.

#### <a name="view-all-number-patterns"></a>Afficher tous les modèles de nombres

L’applet de commande suivante retourne une liste de tous les nombres bloqués entrés pour un locataire :

```powershell
Get-CsInboundBlockedNumberPattern
```

Utilisez des capacités de filtrage PowerShell intégrées pour analyser les valeurs retournées en fonction des besoins.

#### <a name="test-whether-a-number-is-blocked"></a>Tester si un nombre est bloqué

Pour vérifier si un nombre est bloqué dans le locataire, utilisez l’applet de commande **Test-CsInboundBlockedNumberPattern** .

Le paramètre **PhoneNumber** est obligatoire et doit être une chaîne numérique sans caractères supplémentaires, tels que +, ou (). Le paramètre **IsNumberBlocked** qui en résulte retourne la valeur True si le nombre est bloqué dans le locataire ; le paramètre retourne False s’il n’est pas bloqué.

Dans les exemples suivants, vous pouvez voir que le numéro de téléphone 1 (312) 555-8884 est bloqué, car il se trouve dans la plage bloquée ci-dessus. Le numéro de téléphone 1 (312) 555-8883 est autorisé en fonction de l’exemption créée ci-dessous.

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

### <a name="manage-number-exceptions"></a>Gérer les exceptions de nombre

Vous pouvez ajouter des exceptions aux modèles de nombre bloqué à l’aide des applets de commande **New-**, **Get**, **Set et** **Remove-CsInboundExemptNumberPattern** .

- [New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) ajoute un modèle d’exception numérique à la liste des locataires.

- [Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) retourne une liste de tous les modèles d’exception numérique ajoutés à la liste des locataires.

- [Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) modifie un ou plusieurs paramètres en modèle d’exception numérique dans la liste des locataires.

- [Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) supprime un modèle d’exception numérique de la liste des locataires.

### <a name="examples"></a>Exemples

#### <a name="add-a-number-exception"></a>Ajouter une exception de nombre

Dans l’exemple suivant, l’administrateur client souhaite autoriser les numéros de téléphone 1 (312) 555-8882 et 1 (312) 555-8883 à passer des appels au locataire, même si ces deux numéros de téléphone se trouvent dans la plage qui a été bloquée dans l’exemple ci-dessus. Pour ce faire, un nouveau modèle d’exception de nombre est créé comme suit :

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

Pour activer le modèle de nombre, le paramètre **Activé** est défini sur True. Pour désactiver ce modèle de nombre spécifique, définissez le paramètre sur False.

#### <a name="view-all-number-exceptions"></a>Afficher toutes les exceptions de nombre

Dans cet exemple, le paramètre **Identity** est facultatif. Si le paramètre **Identity** n’est pas spécifié, cette applet de commande retourne une liste de tous les modèles d’exception numérique entrés pour un locataire.

```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Get-CsInboundExemptNumberPattern
```

#### <a name="modify-a-number-exception"></a>Modifier une exception de nombre

L’applet **de commande Set-CsInboundExemptNumberPattern** vous permet de modifier un ou plusieurs paramètres pour une identité de modèle de nombre donné. Dans cet exemple, le paramètre **Identity** est requis.

```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string>
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a>Supprimer une exception de nombre

L’applet **de commande Remove-CsInboundExemptNumberPattern** supprime le modèle de nombre donné de la liste des locataires. Dans cet exemple, le paramètre **Identity** est requis.

Si l’identité n’est pas connue, utilisez l’applet de commande **Get-CsInboundExemptNumberPattern** pour d’abord localiser le modèle approprié et noter l’identité. Ensuite, exécutez l’applet **de commande Remove-CsInboundExemptNumberPattern** et transmettez la valeur d’identité appropriée. Accordez du temps pour la réplication avant de tester et de valider.

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="using-regex"></a>Utilisation de Regex

La correspondance de modèle pour les appelants bloquants est effectuée à l’aide de Regex. Plusieurs outils sont disponibles en ligne pour vous aider à valider une correspondance de modèle Regex. Si vous n’êtes pas familiarisé avec les modèles Regex, nous vous recommandons de prendre le temps de vous familiariser avec les principes de base. Pour vous assurer que vous obtenez les résultats attendus, utilisez un outil pour valider les correspondances de modèle avant d’ajouter de nouvelles correspondances de nombre bloqué à votre locataire.
