---
title: Exemple de script PowerShell - Créer & attribuer une stratégie de messagerie
author: serdars
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: Utilisez ce script PowerShell pour créer une stratégie de messagerie dans Teams et l’affecter aux utilisateurs de votre organisation.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 09254f9ed85f69551ee825dbeb8ae063a010f780
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823705"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>Exemple de script PowerShell : créer et attribuer une stratégie de messagerie

Utilisez ce script PowerShell pour créer une stratégie de messagerie dans Microsoft Teams et l’affecter aux utilisateurs. 

Pour plus d’informations sur l’utilisation de ce script PowerShell, consultez [Démarrage rapide - Teams pour l'éducation](../teams-quick-start-edu.yml).

Ce script utilise l’applet de commande [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) qui se trouve dans le module PowerShell Skype Entreprise Online. Consultez [Teams vue d’ensemble de PowerShell](../teams-powershell-overview.md) pour en savoir plus sur la gestion des Teams à l’aide de PowerShell.


## <a name="before-you-start"></a>Avant de commencer

Téléchargez et installez le [module PowerShell Skype Entreprise Online](https://www.microsoft.com/download/details.aspx?id=54616), puis redémarrez votre ordinateur si vous y êtes invité.

Pour en savoir plus, consultez [Gérer Skype Entreprise Online avec Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

## <a name="sample-script"></a>Exemple de script

```powershell
<#
.SYNOPSIS
This script creates a messaging policy in Teams and assigns it to users.
.DESCRIPTION
Use this script to create a messaging policy and assign it to users in your organization.
#>

$dataSetFilePath = "<csv file with user ids for newly provisioned students> "
 $dataSet = Import-Csv "$($dataSetFilePath)" -Header UserId –delimiter ","
 foreach($line in $dataSet)
 {
    $userId = $line.UserId
    Write-Host $userId
    Grant-CsTeamsMessagingPolicy -PolicyName "<<PolicyName for a policy created with Chat Off>>" -Identity $userId

 }
```

> [!NOTE]
> Vous pouvez également affecter une stratégie de messagerie directement aux utilisateurs à grande échelle par le biais d’une attribution de stratégie de lot ou d’un groupe dont les utilisateurs sont membres. Pour plus d’informations, consultez [Affecter des stratégies à de grands ensembles d’utilisateurs dans votre établissement scolaire](../batch-group-policy-assignment-edu.md) et [Attribuer des stratégies à vos utilisateurs dans Teams](../policy-assignment-overview.md).