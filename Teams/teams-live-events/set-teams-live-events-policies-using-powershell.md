---
title: Utilisation de PowerShell pour définir des stratégies d’événements en direct dans Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
description: Exemples illustrant comment utiliser PowerShell pour définir des stratégies dans les équipes pour contrôler qui peut contenir des événements en direct dans votre organisation et les fonctionnalités qui sont disponibles dans les événements qu’ils créent
appliesto:
- Microsoft Teams
ms.openlocfilehash: f802c2b67c0a4cd4b0838dd9aeec9c4bbf884968
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26535912"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>Utilisation de PowerShell pour définir des stratégies d’événements en direct dans Microsoft Teams
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

Vous pouvez utiliser les applets de commande Windows PowerShell suivante pour configurer et affecter des paramètres de stratégie pour les événements en temps réel dans les équipes : 
- [Get-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Nouvelle CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

Voici quelques exemples.

## <a name="allow-users-to-schedule-live-events"></a>Permettre aux utilisateurs de planifier des événements en direct 

> [!NOTE]
> Ces exemples sont pour les événements de démarrage rapide. Pour les événements de codage externe, il existe des étapes supplémentaires que vous devez effectuer. Pour plus d’informations, voir [permettent aux utilisateurs de planifier des événements de codage externe](set-up-for-teams-live-events.md#enable-users-to-schedule-external-encoder-events).

**Autoriser un utilisateur à organiser des événements en direct**

Si l’utilisateur est affecté à la stratégie globale, exécuter et vérifiez que le paramètre *AllowBroadcastScheduling* est définie sur *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Affecter l’utilisateur à la stratégie globale, exécutez :
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Scénarios utilisateur
**Vous que tous les utilisateurs dans votre organisation pour pouvoir planifier des événements en direct**

Si les utilisateurs sont affectés à la stratégie globale, exécutez et vérifiez *AllowBroadcastScheduling* * est défini sur *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Si les utilisateurs sont affectés à une stratégie de la stratégie globale, exécuter et vérifiez que l’option *-AllowBroadcastScheduling* est définie sur *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**Vous souhaitez que les événements live désactivé au sein de votre organisation de la planification**

Désactiver la planification d’événements en direct, exécutez :
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Affecter tous les utilisateurs de votre organisation à la stratégie globale, exécutez :
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Vous souhaitez un grand nombre d’utilisateurs puissent planifier des événements en direct et empêcher un ensemble d’utilisateurs de leur planification**

Exécutez et vérifiez que *AllowBroadcastScheduling* est définie sur *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
Puis affecter un ou plusieurs utilisateurs à la stratégie globale, exécutez :
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Créer une nouvelle stratégie qui n’autorise pas la planification d’événements en direct, exécutez :
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingpolicy
```
Désactiver la planification d’événements en direct, exécutez :
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingpolicy -AllowBroadcastScheduling $false
```
Puis affecter des utilisateurs à cette stratégie, exécutez :
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingpolicy -Verbose
```
**Pour désactiver des événements live planification pour un grand nombre d’utilisateurs en autorisant un ensemble d’utilisateurs à l’échéancier**

Désactiver la planification d’événements en direct, exécutez :
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Puis affecter ces utilisateurs à la stratégie globale, exécutez :
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Créer une stratégie pour autoriser la planification d’événements en direct, exécutez :
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Activer la planification d’événements en direct, exécutez :
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
Puis affecter des utilisateurs à cette stratégie, exécutez :
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>Set qui peut participer à des événements en direct
 
Définir la stratégie globale pour permettre aux utilisateurs de créer des événements que tout le monde, y compris les utilisateurs anonymes, peut participer, exécutez :
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>Définissez l’option d’enregistrement des événements live
> [!NOTE]
> Ce paramètre s’applique uniquement aux événements de démarrage rapide.

Définir la stratégie globale pour désactiver l’enregistrement des événements live :
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-transcription-and-translation-in-live-events-coming-soon"></a>Définir la transcription et traduction dans les événements live (bientôt disponible)
> [!NOTE]
> Ce paramètre s’applique uniquement aux événements de démarrage rapide. 

Définir la stratégie globale pour activer transcription et traduction sur des participants d’événement :
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>Rubriques connexes
- [Configurer des équipes événements en direct](set-up-for-teams-live-events.md)


