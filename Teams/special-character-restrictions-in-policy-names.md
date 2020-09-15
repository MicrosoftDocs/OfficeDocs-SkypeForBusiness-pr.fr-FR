---
title: Restrictions de caractère spécial dans les stratégies Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: Découvrez les problèmes liés aux caractères spéciaux dans les noms de stratégies et ce que vous pouvez faire pour résoudre ce problème.
ms.openlocfilehash: 899cffa45bc5ec7a36339e89e3cb97e35e6e4507
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814713"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Quelles sont les restrictions d’un caractère spécial dans les stratégies Teams ?

**Vous ne pouvez pas créer ou modifier des stratégies (pour la messagerie, les réunions, etc.) dont le nom contient un caractère spécial dans le centre d’administration Microsoft teams**. 

Si le nom d’une stratégie contient des caractères spéciaux, vous ne serez plus limité à la gestion de ces stratégies dans le centre d’administration Microsoft Teams. Par **exemple, nous vous recommandons vivement de ne pas inclure de caractères spéciaux dans les noms de stratégie**. 

Les noms de stratégie qui ont été créés à l’aide de PowerShell pour les réunions et la messagerie dans teams peuvent avoir des caractères spéciaux tels que @, #, $. Toutefois, si vous souhaitez apporter des modifications à la stratégie dans le centre d’administration Microsoft Teams, vous ne serez pas en mesure de le faire. 

Si vous disposez d’une stratégie contenant des caractères spéciaux, vous devez modifier la stratégie à l’aide de Windows PowerShell (Forever) ou créer une nouvelle stratégie dans le centre d’administration Microsoft teams avec les mêmes paramètres que l’ancienne stratégie et l’affecter au même groupe d’utilisateurs.

## <a name="to-remove-special-characters"></a>Pour supprimer des caractères spéciaux

**Étape 1 : créer une connexion à distance avec PowerShell.**
> [!NOTE]
> Le connecteur Skype entreprise Online fait actuellement partie du dernier module PowerShell Teams.
>
> Si vous utilisez la dernière [version publique de teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), vous n’avez pas besoin d’installer le connecteur Skype entreprise online.

```PowerShell
 Import-Module -Name MicrosoftTeams
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


**Étape 2 : obtenir les paramètres de l’ancienne stratégie et capturer la sortie.**

> [!NOTE]
> Cet exemple s’utilise pour une stratégie de [messagerie](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) .  Les étapes sont identiques pour les autres types de stratégies, mais vous devez utiliser l’applet de cmdlet correcte. 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**Étape 3 : créer une nouvelle stratégie.**

Vous pouvez créer une nouvelle stratégie avec le même paramètre à l’aide du centre d’administration Microsoft teams ou de PowerShell.

L’exécution de cette opération entraîne la création d’une stratégie pour vous, mais vous devrez ajouter les paramètres appropriés en vérifiant [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) , puis en exécutant celle-ci :

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Étape 4 : affecter la stratégie.**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Pour plus d’informations sur cette cmdlet, voir [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) .

**Étape 5 : supprimer l’ancienne stratégie.**

Cette opération a pour effet de supprimer l’ancienne stratégie qui contient les caractères spéciaux.
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
Pour plus d’informations sur cette cmdlet, voir [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) .

Si cette commande aboutit, vous avez terminé. Si la commande ci-dessus renvoie une erreur, c’est parce que l’ancienne stratégie est affectée aux utilisateurs et que vous devez les exécuter pour supprimer tous les utilisateurs assignés de la stratégie :

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Windows PowerShell vous permet de gérer Microsoft 365 ou Office 365 à l’aide d’un point d’administration unique qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Pourquoi avez-vous besoin d’utiliser Office 365 PowerShell ?](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité qui consiste à utiliser le centre d’administration Microsoft 365, par exemple, lorsque vous modifiez les paramètres de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype entreprise Online vous permet de créer une session Windows PowerShell distante qui se connecte à Skype entreprise Online et Microsoft Teams. Ce module, qui est pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé à partir du centre de téléchargement Microsoft dans le [module Windows PowerShell pour Skype entreprise online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  

