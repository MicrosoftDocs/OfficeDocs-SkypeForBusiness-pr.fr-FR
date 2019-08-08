---
title: Activer le routage géodépendant pour le routage direct
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Apprenez à activer le routage en fonction de l’emplacement pour le routage direct.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 160a4646ba212c9e654ec06fca2fdd107b2671c7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245127"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Activer le routage géodépendant pour le routage direct

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

Avant de suivre les étapes décrites dans cet article, assurez-vous d’avoir lu le [routage de l’emplacement de votre plan pour le routage direct](location-based-routing-plan.md) et effectué les étapes décrites dans [configurer les paramètres réseau pour le routage via emplacement](location-based-routing-configure-network-settings.md).

Cet article explique comment activer le routage sur la base de l’emplacement pour le routage direct. Après le déploiement du routage direct du système téléphonique et la configuration des zones, des sites et des sous-réseaux, vous pouvez activer le routage par emplacement. Pour suivre les étapes décrites dans cet article, vous devez être familiarisé avec les applets de méthode PowerShell. Pour en savoir plus, voir [vue d’ensemble de PowerShell teams](teams-powershell-overview.md).

 Vous devez activer le routage par emplacement pour les éléments suivants:
- Utilisateurs
- Sites réseau
- Configurations des passerelles
- Politiques d’appel

## <a name="enable-location-based-routing-for-users"></a>Activer le routage basé sur l’emplacement pour les utilisateurs

1. Utilisez l’applet de commande [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) pour définir les utilisations PSTN. Pour les utilisations multiples, séparez chaque utilisation par une virgule.

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    Par exemple :
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. Utilisez l’applet de commande [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) pour créer une stratégie de routage vocal et associer l’utilisateur aux utilisations RTC appropriées.

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    Lorsque vous attribuez des utilisations RTC à une stratégie de routage vocale, effectuez l’une des opérations suivantes:
    - Utiliser les utilisations RTC associées aux itinéraires vocaux qui utilisent une passerelle PSTN locale au site
    - Utilisez les utilisations RTC associées aux itinéraires vocaux qui utilisent une passerelle RTC située dans une région où les restrictions de routage basées sur les emplacements ne sont pas nécessaires.

    Dans cet exemple, nous créons deux nouvelles stratégies de routage vocal et affectons des utilisations PSTN. 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    Le tableau suivant répertorie les stratégies de routage vocal définies dans cet exemple. 
    
    ||Politique de routage de la voix 1|Politique de routage de la voix 2|
    |---------|---------|---------|
    |ID de la stratégie vocale en ligne   |Politique de routage vocal de Delhi en ligne   |Politique de routage de la voix en ligne Hyderabad    |
    |Utilisations RTC en ligne  |Longue distance  |Longue distance, local, interne  |

3. Utilisez l’applet de contrôle [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) pour associer des stratégies de routage vocal en ligne aux utilisateurs qui ont besoin de restrictions de routage.
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a>Activer le routage par emplacement pour les sites réseau
1.  Utilisez l’applet de connexion [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) pour activer le routage par emplacement et associer des stratégies de routage de messagerie à vos sites réseau qui doivent appliquer des restrictions de routage.
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    Dans cet exemple, nous activons le routage en fonction de l’emplacement pour le site de Delhi et le site Hyderabad. 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    Le tableau suivant indique les sites activés pour le routage par emplacement dans cet exemple.

    ||Site 1 (Delhi)  |Site 2 (Hyderabad)  |
    |---------|---------|---------|
|Nom du site    |Site 1 (Delhi)    |Site 2 (Hyderabad)   
    |EnableLocationBasedRouting    |True    |True    |
    |Sous-réseaux     |Sous-réseau 1 (Delhi)     |Sous-réseau 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-gateways"></a>Activer le routage basé sur l’emplacement pour les passerelles
1. Utilisez l’applet de nouvelle applet de [CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) pour créer une configuration de passerelle pour chaque passerelle ou site réseau. 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    Si plusieurs passerelles sont associées à un système (par exemple, passerelle ou PBX), modifiez chaque passerelle pour activer les restrictions de routage basées sur l’emplacement. 

    Dans cet exemple, nous créons une configuration de passerelle pour chaque passerelle. 
    ```
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    Pour plus d’informations, consultez [configurer le routage direct](direct-routing-configure.md).
    
2. Utilisez l’applet de cmdlet [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) pour activer le routage de géolocalisation des passerelles qui doivent appliquer des restrictions de routage. 

    Activez le routage par emplacement vers des passerelles qui acheminent les appels vers les passerelles RTC qui routent les appels vers le RTC et associez le site réseau où se trouve la passerelle.

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    Dans cet exemple, nous activons le routage en fonction de l’emplacement pour chaque passerelle associée aux passerelles RTC dans les sites Delhi et Hyderabad. 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    N’activez pas le routage basé sur l’emplacement pour les passerelles qui ne routent pas les appels vers le RTC. Toutefois, vous devez toujours associer la passerelle au site réseau où se trouve le système. En effet, les restrictions de routage basées sur l’emplacement doivent être appliquées pour les appels RTC atteignant des points de terminaison qui sont connectés par le biais de cette passerelle. Dans cet exemple, le routage basé sur l’emplacement n’est pas activé pour chaque passerelle associée aux systèmes PBX dans les sites Delhi et Hyderabad.

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    Les points de terminaison connectés à des systèmes qui ne routent pas les appels vers le RTC (par exemple, un PBX) présentent des restrictions similaires pour le routage de l’emplacement. Cela signifie que ces utilisateurs peuvent passer et recevoir des appels vers et depuis les utilisateurs Teams, quel que soit l’emplacement de l’utilisateur. Ils peuvent également passer et recevoir des appels vers et à partir d’autres systèmes qui ne routent pas les appels vers le réseau PSTN (par exemple, un point de terminaison connecté à un autre système PBX), quel que soit le site du réseau auquel le système est associé. Tous les appels entrants, les appels sortants, les transferts d’appel et le transfert d’appel qui impliquent des points de terminaison RTC sont soumis à des conditions de routage basées sur l’emplacement. Ces appels doivent uniquement utiliser des passerelles RTC définies comme locales pour de tels systèmes. 

    Le tableau suivant montre la configuration de la passerelle de quatre passerelles sur deux sites réseau différents: deux connectés à des passerelles RTC et deux connectés aux systèmes PBX. 

    ||GatewaySiteLbrEnabled   |NetworkSiteID  |
    |---------|---------|---------|
    |PstnGateway: passerelle 1 DEL-GW    |    True     |   Site 1 (Delhi)      |
    |PstnGateway: passerelle 2 HYD-GW     |   True      |      Site 2 (Hyderabad)   |
    |PstnGateway: passerelle 3 DEL-PBX    |    False     |     Site 1 (Delhi)    |
    |PstnGateway: passerelle 4 HYD-PBX    |    False     |    Site 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-calling-policies"></a>Activer le routage par emplacement pour les stratégies d’appel

Pour appliquer le routage de géolocalisation pour des utilisateurs spécifiques, configurez la politique vocale des utilisateurs afin d’éviter le contournement des appels PTSN. 

Utilisez l’applet de passe [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) pour activer le routage géolocalisation en prévenant le contournement du numéro RTC.

```
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
Dans cet exemple, nous empêcherons le contournement du numéro de téléphone PSTN aux politiques d’appel de la fonction utilisateur1. 

```
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a>Voir aussi
- [Planifier le routage géodépendant pour le routage direct](location-based-routing-plan.md)
- [Configurer les paramètres de réseau pour le routage géodépendant](location-based-routing-configure-network-settings.md)
- [Terminologie du routage géodépendant](location-based-routing-terminology.md)
