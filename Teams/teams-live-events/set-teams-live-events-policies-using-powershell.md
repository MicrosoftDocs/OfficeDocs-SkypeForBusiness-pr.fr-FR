---
title: Utiliser PowerShell pour définir les stratégies d’événements en direct dans Microsoft Teams
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Exemples d’utilisation de PowerShell pour définir des stratégies dans teams pour contrôler les utilisateurs qui peuvent contenir des événements en direct au sein de votre organisation et les fonctionnalités qui sont disponibles dans les événements qu’ils créent
appliesto:
- Microsoft Teams
ms.openlocfilehash: d9f96adcf4aa40b93b89b99013b9bc5ca466c25b
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570167"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>Utiliser PowerShell pour définir les stratégies d’événements en direct dans Microsoft Teams

Vous pouvez utiliser les applets de commande Windows PowerShell suivantes pour définir et affecter des paramètres de stratégie pour les événements en direct dans teams : 
- [Get-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Nouveau-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

Voici quelques exemples.

## <a name="allow-users-to-schedule-live-events"></a>Permettre aux utilisateurs de planifier des événements en direct 

> [!NOTE]
> Ces exemples concernent les événements produits dans Teams. Pour les événements produits avec une application ou un appareil externe, vous devez effectuer des étapes supplémentaires. Pour plus d’informations, reportez-vous à la rubrique [permettre aux utilisateurs de planifier des événements qui ont été produits avec un appareil ou une application externe](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).

**Permettre à un utilisateur de planifier des événements en direct**

Si la stratégie globale est affectée à l’utilisateur, exécutez et vérifiez que le paramètre *AllowBroadcastScheduling* est défini sur *true*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Affectez ensuite à l’utilisateur la politique globale, exécutez :
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Scénarios utilisateur
**Vous souhaitez que tous les utilisateurs de votre organisation puissent planifier des événements en direct**

Si les utilisateurs disposent de la stratégie globale, exécutez et vérifiez que *AllowBroadcastScheduling* * est défini sur *true*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Si les utilisateurs se voient attribuer une stratégie autre que la stratégie globale, exécutez et vérifiez que *-AllowBroadcastScheduling* est défini sur *true*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**Vous voulez que le calendrier des événements dynamiques soit désactivé au sein de votre organisation**

Désactiver la planification des événements en direct, exécutez :
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Attribuer à tous les utilisateurs de votre organisation la stratégie globale, exécuter :
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Vous voulez qu’un grand nombre d’utilisateurs puisse planifier des événements en direct et empêcher un ensemble d’utilisateurs de les planifier**

Exécutez et vérifiez que *AllowBroadcastScheduling* est défini sur *true*:
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
Puis affectez un ou des utilisateurs à la stratégie globale, exécutez :
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Créer une nouvelle stratégie qui n’autorise pas la planification d’événements en direct, exécutez :
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
Désactiver la planification des événements en direct, exécutez :
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
Assigner des utilisateurs à cette stratégie, exécutez :
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**Vous voulez désactiver la planification d’événements en direct pour un grand nombre d’utilisateurs et permettre à un utilisateur de les planifier**

Désactiver la planification des événements en direct, exécutez :
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Ensuite, attribuez ces utilisateurs à la stratégie globale, exécutez :
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Créer une stratégie pour autoriser la planification d’événements en direct, exécutez :
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Activez la planification des événements en direct, exécutez :
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
Assigner des utilisateurs à cette stratégie, exécutez :
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>Définir qui peut participer à des événements en direct
 
Définissez la stratégie globale pour autoriser les utilisateurs à créer des événements que tout le monde, y compris les utilisateurs anonymes, peuvent participer :
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>Définir l’option d’enregistrement pour les événements en direct
> [!NOTE]
> Ce paramètre s’applique uniquement aux événements produits dans Teams.

Définissez la stratégie globale pour désactiver l’enregistrement des événements en direct :
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a>Définir des légendes et des sous-titres en direct dans les événements en direct
> [!NOTE]
> Ce paramètre s’applique uniquement aux événements produits dans Teams. 

Définissez la stratégie globale pour activer les légendes dynamiques et les sous-titres (transcription) pour les participants au service :
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>Voir aussi
- [Configurer les événements en direct Teams](set-up-for-teams-live-events.md)


