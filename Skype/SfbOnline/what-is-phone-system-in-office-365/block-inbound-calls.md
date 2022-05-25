---
title: Bloquer les appels entrants dans Skype Entreprise Online
ms.author: serdars
author: SerdarSoysal
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
description: Les administrateurs peuvent apprendre à bloquer les appels entrants dans Skype Entreprise Online.
ms.openlocfilehash: 40b43f669ededf7ac334c25c79b5af09140c075d
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671650"
---
# <a name="block-inbound-calls"></a>Bloquer les appels entrants

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype Entreprise les forfaits d’appels en ligne prennent désormais en charge le blocage des appels entrants à partir du réseau téléphonique commuté (RTC). Cette fonctionnalité permet de définir une liste globale de modèles de nombres de locataires afin que l’ID d’appelant de chaque appel RTC entrant au locataire puisse être vérifié par rapport à la liste pour une correspondance. Si une correspondance est établie, un appel entrant est rejeté.

Cette fonctionnalité de blocage des appels entrants fonctionne uniquement sur les appels entrants qui proviennent du RTC et fonctionne uniquement sur une base globale du locataire. Il n’est pas disponible par utilisateur.

Cette fonctionnalité n’est pas encore disponible pour le routage direct.

>[!NOTE]
> Les appelants bloqués peuvent rencontrer des comportements légèrement différents lorsqu’ils ont été bloqués. Le comportement est basé sur la façon dont le transporteur de l’appelant bloqué gère la notification indiquant que l’appel n’est pas autorisé à se terminer correctement. Il peut s’agir, par exemple, d’un message indiquant que l’appel ne peut pas être effectué en tant que numérotation, ou simplement de la suppression de l’appel.

## <a name="call-blocking-admin-controls-and-information"></a>Informations et contrôles d’administration bloquants des appels

Administration contrôles pour les nombres bloquants sont fournis à l’aide de PowerShell uniquement. Les modèles de blocs de nombres sont définis comme des modèles d’expression régulière. L’ordre des expressions n’est pas important : le premier modèle mis en correspondance dans la liste entraîne le blocage de l’appel. Un nouveau nombre ou modèle ajouté ou supprimé dans la liste des appelants bloqués peut prendre jusqu’à 24 heures pour que le modèle devienne actif.

## <a name="call-blocking-powershell-commands"></a>Commandes PowerShell bloquantes d’appel

Les modèles de nombres sont gérés par le ```CsInboundBlockedNumberPattern``` biais des ```New```commandes , ```Get```, ```Set```et ```Remove```. Vous pouvez gérer un modèle donné à l’aide de ces applets de commande, notamment la possibilité de basculer l’activation d’un modèle donné.
- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) retourne une liste de tous les modèles de nombres bloqués ajoutés à la liste des locataires, notamment Nom, Description, Activé (True/False) et Modèle pour chacun d’eux.
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) ajoute un modèle de nombre bloqué à la liste des locataires.
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) supprime un modèle de nombre bloqué de la liste des locataires.
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifie un ou plusieurs paramètres d’un modèle de nombre bloqué dans la liste des locataires.

L’affichage et l’activation de l’ensemble de la fonctionnalité de blocage des appels sont gérés via les ```CsTenantBlockingCallingNumbers``` commandes ```Get``` et ```Set```.

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) retourne les paramètres de la liste des nombres bloqués globaux, y compris Activé (True/False). Il existe une stratégie de locataire global unique qui ne peut pas être modifiée manuellement, sauf pour activer ou désactiver la fonctionnalité.
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) permet d’activer et de désactiver les appels bloqués du locataire global au niveau du locataire.

### <a name="examples"></a>Exemples

#### <a name="block-a-number"></a>Bloquer un nombre

Dans cet exemple, les paramètres et ```-Description``` les ```-Enabled``` paramètres sont facultatifs :

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

La création d’un modèle ajoute le modèle comme activé par défaut. La description est un champ facultatif pour fournir plus d’informations.

Nous vous recommandons de fournir un nom explicite pour comprendre facilement pourquoi le modèle a été ajouté. Dans le cas d’un simple blocage des numéros de courrier indésirable, envisagez de nommer la règle de la même manière que le modèle de nombre mis en correspondance et ajoutez des informations supplémentaires dans la description selon les besoins.

Les modèles sont mis en correspondance à l’aide d’expressions régulières (Expressions régulières).
Accordez du temps pour la réplication avant de tester et de valider.

#### <a name="allow-a-number"></a>Autoriser un nombre

Dans cet exemple, le ```-Identity``` paramètre est requis :

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```

Si l’identité n’est pas connue, utilisez l’applet ```Get-CsInboundBlockedNumberPattern``` de commande pour d’abord localiser le modèle approprié et noter l’identité. Ensuite, exécutez l’applet ```Remove-CsTenantBlockedNumberPattern``` de commande et transmettez la valeur d’identité appropriée.

Accordez du temps pour la réplication avant de tester et de valider.

#### <a name="view-all-number-patterns"></a>Afficher tous les modèles de nombres

L’exécution de cette applet de commande retourne une liste de tous les numéros bloqués entrés pour un locataire :

```powershell
Get-CsInboundBlockedNumberPattern
```

Utilisez des capacités de filtrage PowerShell intégrées pour analyser les valeurs retournées en fonction des besoins.

## <a name="add-number-exceptions"></a>Ajouter des exceptions de nombre

Vous pouvez ajouter des exceptions aux modèles de nombres bloqués via les ```CsTenantBlockNumberExceptionPattern``` commandes, ```New```, ```Get```, ```Set```et ```Remove```.

- [New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) ajoute un modèle d’exception numérique à la liste des locataires.
- [Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) retourne une liste de tous les modèles d’exception numérique ajoutés à la liste des locataires.
- [Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifie un ou plusieurs paramètres en modèle d’exception numérique dans la liste des locataires.
- [Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) supprime un modèle d’exception numérique de la liste des locataires.

### <a name="examples"></a>Exemples

#### <a name="add-a-number-exception"></a>Ajouter une exception de nombre

Dans cet exemple, un nouveau modèle d’exception de nombre est créé et ajoute par défaut le modèle comme activé. Les paramètres et ```-Description``` les ```-Enabled``` paramètres sont facultatifs.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"
```

#### <a name="view-all-number-exceptions"></a>Afficher toutes les exceptions de nombre

Dans cet exemple, le paramètre -Identity est facultatif. Si le ```-Identity``` paramètre n’est pas spécifié, cette applet de commande retourne une liste de tous les modèles d’exception numérique entrés pour un locataire.

```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Modifier une exception de nombre

Dans cet exemple, le paramètre -Identity est obligatoire. L’applet ```Set-CsTenantBlockedNumberExceptionPattern``` de commande vous permet de modifier un ou plusieurs paramètres pour une identité de modèle de nombre donnée.

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string>
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$"
```

#### <a name="remove-a-number-exception"></a>Supprimer une exception de nombre

Dans cet exemple, le ```-Identity``` paramètre est requis. Cette applet de commande supprime le modèle de nombre donné de la liste des locataires.  Si l’identité n’est pas connue, utilisez l’applet ```Get-CsInboundBlockedNumberPattern``` de commande pour d’abord localiser le modèle approprié et noter l’identité. Ensuite, exécutez l’applet ```Remove-CsTenantBlockedNumberExceptionPattern``` de commande et transmettez la valeur d’identité appropriée. Accordez du temps pour la réplication avant de tester et de valider.

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Tester si un nombre est bloqué

Utilisez l’applet ```Test-CsInboundBlockedNumberPattern``` de commande pour vérifier si un nombre est bloqué dans le locataire.

Dans cet exemple, les paramètres et ```-Tenant``` les ```-Phonenumber``` paramètres sont requis. Le ```-PhoneNumber``` paramètre doit être une chaîne numérique sans caractères supplémentaires tels que + ou -. Dans TRPS, l’option ```-Tenant parameter``` est facultative. Le paramètre résultant ```isNumberBlocked``` retourne la valeur True si le nombre est bloqué dans le locataire et False s’il n’est pas bloqué.

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

## <a name="a-note-about-regex"></a>Remarque sur Regex

Comme indiqué précédemment, la correspondance de modèle pour les appelants bloquants est effectuée à l’aide de Regex. Plusieurs outils sont disponibles en ligne pour vous aider à valider une correspondance de modèle Regex. Si vous n’êtes pas familiarisé avec les modèles Regex, nous vous recommandons de prendre le temps de vous familiariser avec les principes de base. Pour vous assurer que vous obtenez les résultats attendus, utilisez un outil pour valider les correspondances de modèle avant d’ajouter de nouvelles correspondances de nombre bloqué à votre locataire.

## <a name="related-topics"></a>Voir aussi

- [Configurer votre ordinateur pour gérer Skype Entreprise Online à l’aide de Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
