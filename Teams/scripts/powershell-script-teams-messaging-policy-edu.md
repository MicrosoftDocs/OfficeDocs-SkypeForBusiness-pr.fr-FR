---
title: 'Exemple de script PowerShell : créer et attribuer une stratégie de messagerie'
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: Utilisez ce script PowerShell pour créer une stratégie de messagerie dans teams et l’attribuer aux utilisateurs de votre organisation.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1fd414c960406418e9189a68e219b6a08bb7a939
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243097"
---
<a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>Exemple de script PowerShell : créer et attribuer une stratégie de messagerie
-------------------------------------------------------------------------

Utilisez ce script PowerShell pour créer une stratégie de messagerie dans Microsoft teams et l’affecter à des utilisateurs. 

Pour plus d’informations sur l’utilisation de ce script PowerShell, reportez-vous à la rubrique [démarrage rapide-teams pour l’éducation](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).

Si vous débutez avec PowerShell et avez besoin d’aide pour démarrer, reportez-vous à la rubrique [Présentation d’Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).


## <a name="sample-script"></a>Exemple de script

````powershell
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
````


