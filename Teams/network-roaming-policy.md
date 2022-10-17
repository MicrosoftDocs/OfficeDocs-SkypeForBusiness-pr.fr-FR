---
title: Stratégie d’itinérance réseau
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
search.appverid: MET150
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
description: Découvrez comment gérer les paramètres pour la stratégie Teams d’itinérance réseau.
ms.openlocfilehash: f8b1d78754c5f608aa76d9261b2164abc4de9194
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2022
ms.locfileid: "68585062"
---
# <a name="manage-video-and-media-settings-with-the-network-roaming-policy"></a>Gérer les paramètres vidéo et multimédia avec la stratégie d’itinérance réseau

Outre la gestion des paramètres vidéo et multimédia avec des stratégies de réunion, vous pouvez désormais contrôler dynamiquement l’utilisation des attributs suivants utilisés par le client Microsoft Teams à l’aide de TeamsNetworkRoamingPolicy : 

- Video IP
- Vitesse de transmission du média (Ko)

Cette stratégie vous permet d’affecter des paramètres à des sites réseau. Le client Teams choisit dynamiquement les paramètres en fonction du site réseau auquel il se connecte. Lorsque le client Teams se connecte à partir d’un site réseau avec une stratégie d’itinérance attribuée, cette stratégie est utilisée. Si aucune stratégie n’est affectée, les valeurs définies dans la stratégie de réunion sont utilisées. Pour plus d’informations sur les paramètres audio et vidéo de stratégie de réunion, voir [Paramètres de stratégie de réunion pour l’audio et la vidéo](meeting-policies-audio-and-video.md).

## <a name="configure-the-teamsnetworkroamingpolicy"></a>Configurer TeamsNetworkRoamingPolicy

Pour configurer TeamsNetworkRoamingPolicy, utilisez les applets de commande PowerShell suivantes :

- [Get-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/get-csteamsnetworkroamingpolicy)
- [New-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/new-csteamsnetworkroamingpolicy)
- [Set-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/set-csteamsnetworkroamingpolicy)
- [Remove-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/remove-csteamsnetworkroamingpolicy)

TeamsNetworkRoamingPolicy contient les paramètres suivants :

- AllowIPVideo : ce paramètre contrôle si la vidéo peut être activée dans les réunions hébergées par un utilisateur et dans les appels individuels et de groupe démarrés par un utilisateur.

- Ce paramètre détermine la vitesse de transmission moyenne totale du média pour les transmissions de partage d’applications audio et vidéo dans les appels et les réunions pour l’utilisateur.

Après avoir configuré la stratégie, affectez-la à un ou plusieurs sites réseau à l’aide de l’applet de commande [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) comme il suit :

```PowerShell
 Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy LowBandwidthSite
 ``` 
 
 Pour supprimer une stratégie d’un site réseau, utilisez l’applet de commande suivante :
 
 ```PowerShell
 Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy $null
 ```

To enable the network roaming policy for users who are not enterprise voice enabled, you must also enable the AllowNetworkConfigurationSettingsLookup setting in TeamsMeetingPolicy. This setting is off by default.

Pour plus d’informations sur la création de sites réseau, consultez [Paramètres réseau pour les fonctionnalités vocales cloud](cloud-voice-network-settings.md). 

## <a name="examples"></a>Exemples

```PowerShell
New-CsTeamsNetworkRoamingPolicy -Identity LowBandwidthSite -AllowIPVideo $false -MediaBitRateKb 1000
```

```PowerShell
Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy LowBandwidthSite
```

## <a name="supported-clients"></a>Clients pris en charge

- Windows 
- Bureau MacOS

## <a name="known-issues"></a>Problèmes connus

Lorsque vous spécifiez New- et Get-CsTeamsNetworkRoamingPolicy dans Teams Online PowerShell v 2.0.0, des données supplémentaires s’affichent.


## <a name="related-topics"></a>Voir aussi

- [Get-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/get-csteamsnetworkroamingpolicy)
- [New-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/new-csteamsnetworkroamingpolicy)
- [Set-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/set-csteamsnetworkroamingpolicy)
- [Remove-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/remove-csteamsnetworkroamingpolicy)
- [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite)
