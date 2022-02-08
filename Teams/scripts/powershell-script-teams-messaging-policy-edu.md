---
title: Exemple de script PowerShell - Créer & stratégie de messagerie
author: serdars
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: Utilisez ce script PowerShell pour créer une stratégie de messagerie dans Teams et l’affecter à des utilisateurs de votre organisation.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c6c1faaff2ce252b1363fab149c7d168c5e042e5
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390836"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>Exemple de script PowerShell : créer et attribuer une stratégie de messagerie

Utilisez ce script PowerShell pour créer une stratégie de messagerie dans Microsoft Teams et l’affecter à des utilisateurs. 

Pour plus d’informations sur l’utilisation de ce script PowerShell, voir [Démarrage rapide - Teams pour l'éducation](../teams-quick-start-edu.yml).

Ce script utilise l’cmdlet [Grant-CsTeamsMesspolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) qui se trouve dans le module Skype Entreprise Online PowerShell. Consultez [Teams vue d’ensemble de PowerShell](../teams-powershell-overview.md) pour en savoir plus sur la gestion Teams’aide de PowerShell.


## <a name="before-you-start"></a>Avant de commencer

Téléchargez et installez [le module Skype Entreprise PowerShell online](https://www.microsoft.com/download/details.aspx?id=39366), puis redémarrez votre ordinateur si vous y êtes invité.

Pour en savoir plus, [voir Gérer Skype Entreprise Online avec Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

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
> Vous pouvez également affecter une stratégie de messagerie directement aux utilisateurs à l’échelle via une affectation de stratégie de lot ou à un groupe dont les utilisateurs sont membres. Pour plus d’informations, voir [Attribuer](../batch-group-policy-assignment-edu.md) des stratégies à un grand nombre d’utilisateurs dans votre établissement scolaire et Affecter des stratégies à vos utilisateurs [dans Teams](../policy-assignment-overview.md).