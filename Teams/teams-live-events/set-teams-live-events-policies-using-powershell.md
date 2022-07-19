---
title: Utiliser PowerShell pour définir des stratégies d’événements en direct
author: mkbond007
ms.author: mabond
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
description: Exemples d’utilisation de PowerShell pour définir des stratégies dans Teams afin de contrôler qui peut contenir des événements en direct dans votre organisation et les fonctionnalités disponibles dans les événements.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e0d46c0675bd8b810f8dbce8585661184fbef74f
ms.sourcegitcommit: 791d0a341ff873145fa893ece05055729b0b8d50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/18/2022
ms.locfileid: "66838839"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>Utiliser PowerShell pour définir les stratégies d’événements en direct dans Microsoft Teams

Vous pouvez utiliser les applets de commande Windows PowerShell suivantes pour définir et affecter des paramètres de stratégie pour les événements en direct dans Teams : 
- [Get-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

Voici quelques exemples.

> [!NOTE]
> Avant de pouvoir exécuter ces applets de commande, vous devez être connecté à Skype Entreprise Online PowerShell. Pour plus d’informations, consultez [Gérer Skype Entreprise Online avec Microsoft 365 ou Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

## <a name="allow-users-to-schedule-live-events"></a>Autoriser les utilisateurs à planifier des événements en direct 

> [!NOTE]
> Ces exemples concernent les événements produits dans Teams. Pour les événements générés avec une application ou un appareil externe, vous devez effectuer des étapes supplémentaires. Pour plus d’informations, consultez [Autoriser les utilisateurs à planifier des événements qui ont été produits avec une application ou un appareil externe](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).

**Autoriser un utilisateur à planifier des événements en direct**

Si la stratégie globale est affectée à l’utilisateur, exécutez et vérifiez que le paramètre *AllowBroadcastScheduling* a la valeur *True* :
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Ensuite, affectez l’utilisateur à la stratégie globale, exécutez :
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Scénarios utilisateur
**Vous souhaitez que tous les utilisateurs de votre organisation puissent planifier des événements en direct**

Si la stratégie globale est affectée aux utilisateurs, exécutez et vérifiez que *AllowBroadcastScheduling* *est défini sur *True* :
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Si une stratégie autre que la stratégie globale est affectée aux utilisateurs, exécutez et vérifiez que *-AllowBroadcastScheduling* a la valeur *True* :
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**Vous souhaitez que la planification des événements en direct soit désactivée au sein de votre organisation**

Désactivez la planification des événements en direct, exécutez :
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Affectez tous les utilisateurs de votre organisation à la stratégie globale, exécutez :
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Vous souhaitez qu’un grand nombre d’utilisateurs puissent planifier des événements en direct et empêcher un ensemble d’utilisateurs de les planifier**

Exécutez et vérifiez que *AllowBroadcastScheduling* a la valeur *True* :
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
Ensuite, affectez un utilisateur ou des utilisateurs à la stratégie globale, exécutez :
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
**Vous souhaitez désactiver la planification d’événements en direct pour un grand nombre d’utilisateurs et autoriser un ensemble d’utilisateurs à les planifier**

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
## <a name="set-who-can-join-live-events"></a>Définir les personnes pouvant participer à des événements en direct
 
Définissez la stratégie globale pour permettre aux utilisateurs de créer des événements auxquels tout le monde, y compris les utilisateurs anonymes, peut participer, s’exécute :
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

Définissez la stratégie globale pour activer les sous-titres et légendes en direct (transcription) pour les participants à l’événement :
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>Sujets associés
- [Configurer les événements en direct Teams](set-up-for-teams-live-events.md)
- [Présentation de Teams PowerShell](../teams-powershell-overview.md)