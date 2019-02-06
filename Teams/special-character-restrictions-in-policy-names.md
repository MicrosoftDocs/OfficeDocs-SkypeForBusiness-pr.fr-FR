---
title: Quelles sont les restrictions de caractère spécial dans les stratégies d’équipes ?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- msteams
- skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Teams_ITAdmin_Help
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.teamsadmincenter.policies.naming.error
description: Voir existe avec des caractères spéciaux dans les noms des stratégies et ce que vous pouvez faire pour résoudre des problèmes.
ms.openlocfilehash: ffb6082a613587b654f997bc2b2154bfeade15bf
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754735"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Quelles sont les restrictions de caractère spécial dans les stratégies d’équipes ?

**Vous ne pouvez pas créer ou des stratégies de modifier (pour la messagerie, réunions, etc.) qui ont un caractère spécial dans le nom de l’administrateur des équipes Microsoft Centre**. 

Si un nom de stratégie contient des caractères spéciaux, vous serez limité dans la gestion de ces stratégies dans le centre d’administration Microsoft Teams. **Par conséquent, il est fortement recommandé que les noms de stratégie ne pas inclure des caractères spéciaux**. 

Les noms de stratégie qui ont été créés à l’aide de PowerShell pour les réunions et messagerie dans les équipes peuvent avoir des caractères spéciaux tels que @, #, $. Toutefois, si vous souhaitez apporter des modifications à la stratégie dans le centre d’administration Microsoft Teams, vous ne pourrez. 

Si vous disposez d’une stratégie avec des caractères spéciaux, vous devrez soit modifier la stratégie à l’aide de Windows PowerShell (toujours) ou créer une nouvelle stratégie dans le centre d’administration Microsoft Teams avec les mêmes paramètres que l’ancienne stratégie et l’affecter au même groupe d’utilisateurs.

## <a name="to-remove-special-characters"></a>Pour supprimer les caractères spéciaux

**Étape 1 : établir une connexion à distance PowerShell.** 
 [Configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) si vous n’avez pas encore.
```
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


**Étape 2 : obtenir les paramètres de l’ancienne stratégie et capturer la sortie.**

> [!NOTE]
> Cet exemple est destiné à une stratégie de [messagerie](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) .  Les étapes serait identique pour d’autres types de stratégie, mais vous devez utiliser l’applet de commande correct. 

  ```
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**Étape 3 : créer une nouvelle stratégie.**

Vous pouvez créer la nouvelle stratégie avec le même paramètre à l’aide du centre d’administration de Microsoft Teams ou de PowerShell.

Exécuter cette crée une nouvelle stratégie pour vous, mais vous devez ajouter les paramètres corrects en consultant la rubrique [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) et puis de l’exécuter :

  ```
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Étape 4 : attribuer la stratégie.**
 ```
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Voir [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) pour plus d’informations sur cette applet de commande.

**Étape 5 - supprimer l’ancienne stratégie.**

Cette opération supprime l’ancienne stratégie avec des caractères spéciaux.
  ```
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
[Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) pour plus d’informations sur cette applet de commande, voir.

Si cette commande réussit, vous avez terminé. Si la commande ci-dessus retourne une erreur, il est car l’ancienne stratégie est affectée aux utilisateurs afin que vous devez exécuter pour supprimer tous les utilisateurs affectés de la stratégie :

```
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Pourquoi vous devez utiliser Office 365 PowerShell ?](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleures méthodes de gestion d’Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell présente de nombreux avantages dans vitesse, la simplicité et la productivité sur qu’à l’aide du centre d’administration Office 365, tels que lorsque vous modifiez les paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype pour Business Online permet de vous permet de créer une session Windows PowerShell à distance qui se connecte à Skype pour Business Online et Microsoft Teams. Ce module, qui est pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé depuis le Center Download Microsoft à [le Module Windows PowerShell pour Skype pour Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  

