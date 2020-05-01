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
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 748167dc8e03b53fc07611df0ff464d984fb5678
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/30/2020
ms.locfileid: "43951059"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>Exemple de script PowerShell : créer et attribuer une stratégie de messagerie

Utilisez ce script PowerShell pour créer une stratégie de messagerie dans Microsoft teams et l’affecter à des utilisateurs. 

Pour plus d’informations sur l’utilisation de ce script PowerShell, reportez-vous à la rubrique [démarrage rapide-teams pour l’éducation](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).

Ce script utilise l’applet de connexion [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) dans le module PowerShell de Skype entreprise online. Pour en savoir plus sur la gestion d’équipes à l’aide de PowerShell, voir [vue d’ensemble de PowerShell teams](../teams-powershell-overview.md) .


## <a name="before-you-start"></a>Avant de commencer

Téléchargez et installez le [module PowerShell de Skype entreprise Online](https://www.microsoft.com/download/details.aspx?id=39366), puis redémarrez l’ordinateur si vous y êtes invité.

Pour plus d’informations, reportez-vous à la rubrique [gestion de Skype entreprise Online avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).


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
> Vous pouvez également utiliser une affectation de stratégie de batch pour attribuer une stratégie de messagerie à des groupes de personnes importants. Pour plus d’informations [, voir attribuer des stratégies à de grands ensembles d’utilisateurs dans votre établissement scolaire](../batch-policy-assignment-edu.md) et [affecter des stratégies à vos utilisateurs dans teams](../assign-policies.md).
