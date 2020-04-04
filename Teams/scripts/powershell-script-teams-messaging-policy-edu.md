---
title: Exemple de script PowerShell-créer & affecter une stratégie de messagerie
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: Utilisez ce script PowerShell pour créer une stratégie de messagerie dans teams et l’attribuer aux utilisateurs de votre organisation.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ffd564d421c07503fe5e19ace8f24a0379418b74
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140977"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>Exemple de script PowerShell : créer et attribuer une stratégie de messagerie

Utilisez ce script PowerShell pour créer une stratégie de messagerie dans Microsoft teams et l’affecter à des utilisateurs. 

Pour plus d’informations sur l’utilisation de ce script PowerShell, reportez-vous à la rubrique [démarrage rapide-teams pour l’éducation](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).

Si vous débutez avec PowerShell et avez besoin d’aide pour démarrer, reportez-vous à la rubrique [Présentation d’Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).


## <a name="before-you-start"></a>Avant de commencer
Téléchargez et installez le [module Skype entreprise Online Connector](https://www.microsoft.com/download/details.aspx?id=39366), puis redémarrez l’ordinateur si vous y êtes invité.

Pour en savoir plus, voir [gérer Skype entreprise Online avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell) .


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


