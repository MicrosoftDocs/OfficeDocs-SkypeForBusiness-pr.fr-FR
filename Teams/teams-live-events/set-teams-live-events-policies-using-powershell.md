---
title: Utiliser PowerShell pour définir des stratégies d’événements en direct
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: Exemples d’utilisation de PowerShell pour définir des stratégies dans Teams afin de contrôler qui peut tenir des événements en direct dans votre organisation et les fonctionnalités disponibles dans les événements.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ef243860ea1450dcd5539d3d5b01025e7eac55cd
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767574"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>Utiliser PowerShell pour définir les stratégies d’événements en direct dans Microsoft Teams

Vous pouvez utiliser les applets de commande Windows PowerShell suivantes pour définir et affecter des paramètres de stratégie pour les événements en direct dans Teams :

- [Get-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/get-csteamsmeetingbroadcastpolicy)
- [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy)
- [New-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/new-csteamsmeetingbroadcastpolicy)
- [Grant-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy)
- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment)

Voici quelques exemples.

> [!NOTE]
> Avant de pouvoir exécuter ces applets de commande, vous devez être connecté à Skype Entreprise Online PowerShell. Pour plus d’informations, consultez [Gérer Skype Entreprise Online avec Microsoft 365 ou Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

## <a name="allow-users-to-schedule-live-events"></a>Autoriser les utilisateurs à planifier des événements en direct

> [!NOTE]
> Ces exemples concernent les événements générés dans Teams.

### <a name="allow-a-user-to-schedule-live-events"></a>Autoriser un utilisateur à planifier des événements en direct

Si la stratégie globale est affectée à l’utilisateur, exécutez et vérifiez que le paramètre *AllowBroadcastScheduling a la* valeur *True* :

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```

Ensuite, affectez l’utilisateur à la stratégie globale, exécutez :

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Scénarios utilisateur

#### <a name="you-want-all-users-in-your-organization-to-be-able-to-schedule-live-events"></a>Vous souhaitez que tous les utilisateurs de votre organisation puissent planifier des événements en direct

Si la stratégie globale est affectée aux utilisateurs, exécutez et vérifiez que *AllowBroadcastScheduling* est défini sur *True* :

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```

Si une stratégie autre que la stratégie globale est affectée aux utilisateurs, exécutez et vérifiez que *-AllowBroadcastScheduling a la* valeur *True* :

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

#### <a name="you-want-live-events-scheduling-to-be-disabled-across-your-organization"></a>Vous souhaitez désactiver la planification des événements en direct au sein de votre organisation

Désactivez la planification des événements en direct, exécutez :

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```

Affectez tous les utilisateurs de votre organisation à la stratégie globale, exécutez :

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

#### <a name="you-want-a-large-number-of-users-to-be-able-to-schedule-live-events-and-prevent-a-set-of-users-from-scheduling-them"></a>Vous souhaitez qu’un grand nombre d’utilisateurs puissent planifier des événements en direct et empêcher un ensemble d’utilisateurs de les planifier

Exécutez et vérifiez que *AllowBroadcastScheduling* est défini sur *True* :

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```

Ensuite, affectez un ou plusieurs utilisateurs à la stratégie globale, exécutez :

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Créez une stratégie qui n’autorise pas la planification d’événements en direct, exécutez :

```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```

Désactivez la planification des événements en direct, exécutez :

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```

Ensuite, affectez des utilisateurs à cette stratégie, exécutez :

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```

#### <a name="you-want-to-disable-live-event-scheduling-for-a-large-number-of-the-users-and-allow-a-set-of-users-to-schedule-them"></a>Vous souhaitez désactiver la planification des événements en direct pour un grand nombre d’utilisateurs et autoriser un ensemble d’utilisateurs à les planifier

Désactivez la planification des événements en direct, exécutez :

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```

Ensuite, affectez ces utilisateurs à la stratégie globale, exécutez :

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Créez une stratégie pour autoriser la planification des événements en direct, exécutez :

```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```

Activez la planification des événements en direct, exécutez :

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```

Ensuite, affectez des utilisateurs à cette stratégie, exécutez :

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```

## <a name="set-who-can-join-live-events"></a>Définir les personnes autorisées à participer à des événements en direct

Définissez la stratégie globale pour permettre aux utilisateurs de créer des événements auxquels tout le monde, y compris les utilisateurs anonymes, peut participer et exécuter :

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```

## <a name="set-the-recording-option-for-live-events"></a>Définir l’option d’enregistrement pour les événements en direct

> [!NOTE]
> Ce paramètre s’applique uniquement aux événements produits dans Teams.

Définissez la stratégie globale pour désactiver l’enregistrement des événements en direct :

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```

## <a name="set-live-captions-and-subtitles-in-live-events"></a>Définir des sous-titres et des sous-titres en direct dans des événements en direct

> [!NOTE]
> Ce paramètre s’applique uniquement aux événements produits dans Teams.

Définissez la stratégie globale pour activer les sous-titres en direct et les sous-titres (transcription) pour les participants à l’événement :

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>Rubriques connexes

- [Configurer les événements en direct Teams](set-up-for-teams-live-events.md)
- [Présentation de Teams PowerShell](../teams-powershell-overview.md)
