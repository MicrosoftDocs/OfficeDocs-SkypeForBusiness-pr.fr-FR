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
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: Découvrez les problèmes liés aux caractères spéciaux dans les noms des stratégies et ce que vous pouvez faire pour le résoudre.
ms.openlocfilehash: c304e292aa10508e7c8b02fe2825b83897f22e38
ms.sourcegitcommit: 1788f852508208a01f230f6f68a5a81ec8594c47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860077"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Quelles sont les restrictions d’un caractère spécial dans les stratégies Teams ?

**Vous ne pouvez pas créer ou modifier des stratégies (pour la messagerie, les réunions, etc.) qui ont un caractère spécial dans le nom du centre d’administration Microsoft Teams**. 

Si un nom de stratégie contient des caractères spéciaux, vous serez limité dans la gestion de ces stratégies dans le centre d’administration Microsoft Teams. **Par conséquent, nous recommandons vivement que les noms de stratégie n’incluent pas de caractères spéciaux**. 

Les noms de stratégie qui ont été créés à l’aide de PowerShell pour les réunions et la messagerie dans Teams peuvent avoir des caractères spéciaux tels que @,#,$. Toutefois, si vous souhaitez apporter des modifications à la stratégie dans le centre d’administration Microsoft Teams, vous ne pourrez pas le faire. 

Si vous avez une stratégie avec des caractères spéciaux, vous devez modifier la stratégie à l’aide de Windows PowerShell (pour toujours) ou créer une stratégie dans le centre d’administration Microsoft Teams avec les mêmes paramètres que l’ancienne stratégie et l’affecter au même groupe d’utilisateurs.

## <a name="to-remove-special-characters"></a>Pour supprimer des caractères spéciaux

**Étape 1 : établir une connexion à distance avec PowerShell.**
> [!NOTE]
> Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams.
>
> Si vous utilisez la dernière [version publique Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), vous n’avez pas besoin d’installer le connecteur Skype Entreprise Online.

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


**Étape 2 : obtenir les paramètres de l’ancienne stratégie et capturer la sortie.**

> [!NOTE]
> Cet exemple concerne une [stratégie de messagerie](/powershell/module/skype/get-csteamsmessagingpolicy) .  Les étapes sont les mêmes pour les autres types de stratégie, mais vous devez utiliser l’applet de commande appropriée. 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**Étape 3 : créer une stratégie.**

Vous pouvez créer la nouvelle stratégie avec le même paramètre à l’aide du centre d’administration Microsoft Teams ou de PowerShell.

L’exécution de cette opération crée une stratégie pour vous, mais vous devez ajouter les paramètres corrects en affichant [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy) , puis en l’exécutant :

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Étape 4 : affecter la stratégie.**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Pour plus d’informations sur cette applet de commande, consultez [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) .

**Étape 5 : supprimer l’ancienne stratégie.**

Cela supprime l’ancienne stratégie avec les caractères spéciaux.
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
Pour plus d’informations sur cette applet de commande, consultez [Remove-CsTeamsMessagingPolicy](/powershell/module/skype/remove-csteamsmessagingpolicy) .

Si cette commande réussit, vous avez terminé. Si la commande ci-dessus retourne une erreur, c’est parce que l’ancienne stratégie est affectée aux utilisateurs, vous devez donc exécuter pour supprimer tous les utilisateurs affectés de la stratégie :

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Pourquoi utiliser Office 365 PowerShell ?](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell présente de nombreux avantages en termes de vitesse, de simplicité et de productivité par rapport à l’utilisation de l’Centre d'administration Microsoft 365, par exemple lorsque vous modifiez les paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online vous permet de créer une session de Windows PowerShell distante qui se connecte à Skype Entreprise Online et Microsoft Teams. Ce module, qui est pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé à partir du Centre de téléchargement Microsoft dans [Windows PowerShell Module pour Skype Entreprise Online.](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)
