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
description: Découvrez les problèmes qui surentent les caractères spéciaux dans les noms des stratégies et ce que vous pouvez faire pour le résoudre.
ms.openlocfilehash: 15df8b64f423d1ee20df6e230e4a9cdbebcb56db
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116982"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Quelles sont les restrictions d’un caractère spécial dans les stratégies Teams ?

Vous ne pouvez pas créer ou modifier des stratégies (pour la messagerie, les **réunions, etc.)** qui ont un caractère spécial dans le nom du Microsoft Teams d’administration. 

Si un nom de stratégie contient des caractères spéciaux, la gestion de ces stratégies dans le Microsoft Teams d’administration s’est limité. **C’est pourquoi nous recommandons vivement que les noms de stratégie n’incluent pas de caractères spéciaux.** 

Les noms de stratégie qui ont été créés à l’aide de PowerShell pour les réunions et la messagerie dans Teams peuvent avoir des caractères spéciaux tels que @,#,$. Toutefois, si vous souhaitez apporter des modifications à la stratégie dans le Microsoft Teams d’administration, vous ne pourrez pas. 

Si vous avez une stratégie avec des caractères spéciaux, vous devrez soit la modifier à l’aide d’Windows PowerShell (indéfiniment), soit créer une stratégie dans le Centre d’administration Microsoft Teams avec les mêmes paramètres que l’ancienne stratégie et l’affecter au même groupe d’utilisateurs.

## <a name="to-remove-special-characters"></a>Pour supprimer les caractères spéciaux

**Étape 1 : établir une connexion à distance avec PowerShell.**
> [!NOTE]
> Skype Entreprise Online Connector fait actuellement partie de la dernière version Teams module PowerShell.
>
> Si vous utilisez la dernière version [Teams public PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n’avez pas besoin d’installer Skype Entreprise Online Connector.

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


**Étape 2 : obtenez les paramètres de l’ancienne stratégie et capturez le résultat.**

> [!NOTE]
> Cet exemple s’agit [d’une stratégie de](/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) messagerie.  Les étapes seraient les mêmes pour d’autres types de stratégie, mais vous devez utiliser l’cmdlet correcte. 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**Étape 3 : créer une stratégie.**

Vous pouvez créer la nouvelle stratégie avec le même paramètre à l’aide du centre d’administration Microsoft Teams de l’utilisateur ou de PowerShell.

L’exécution de cette stratégie crée une stratégie pour vous, mais vous devrez ajouter les paramètres corrects en voyant [Set-CsTeamsMess premierPolicy,](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) puis en l’exécutant :

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Étape 4 : affecter la stratégie.**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Pour plus d’informations sur cette cmdlet, voir [Grant-CsTeamsMess paysPolicy.](/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps)

**Étape 5 : supprimer l’ancienne stratégie.**

L’ancienne stratégie avec les caractères spéciaux est alors supprimé.
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
Pour plus d’informations sur cette cmdlet, voir [Remove-CsTeamsMesspolicy.](/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps)

Si cette commande réussit, vous avez terminé. Si la commande ci-dessus renvoie une erreur, l’ancienne stratégie étant affectée aux utilisateurs, vous devez exécuter cette stratégie pour supprimer tous les utilisateurs affectés de la stratégie :

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Pourquoi devez-vous utiliser Office 365 PowerShell ?](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez les paramètres de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > Le module Windows PowerShell de Skype Entreprise Online vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online et Microsoft Teams. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé à partir du Centre de téléchargement Microsoft sur Windows PowerShell Module pour [Skype Entreprise Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
