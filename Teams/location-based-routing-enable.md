---
title: Activer le routage géodépendant pour le routage direct
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Découvrez comment activer le routage basé sur un emplacement pour le routage Direct.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 809e48e4a770906b93642356cc5f37fd03c411c4
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460331"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Activer le routage géodépendant pour le routage direct

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

Avant de suivre les étapes décrites dans cet article, assurez-vous que vous avez lu [Plan Location-Based de routage pour le routage Direct](location-based-routing-plan.md) et effectué les étapes dans [configurer les paramètres réseau pour le routage basé sur l’emplacement](location-based-routing-configure-network-settings.md).

Cet article décrit comment activer le routage basé sur un emplacement pour le routage Direct. Une fois que vous déployez l’acheminement d’un système téléphonique Direct et configurer des sous-réseaux, les sites et régions de réseau, vous êtes prêt à activer le routage basé sur l’emplacement. Pour effectuer les étapes décrites dans cet article, vous aurez besoin de se familiariser avec les applets de commande PowerShell. Pour plus d’informations, voir [Vue d’ensemble de PowerShell équipes](teams-powershell-overview.md).

 Vous devez activer la fonction de routage pour les éléments suivants :
- Utilisateurs
- Sites réseau
- Configurations de passerelle
- Stratégies d’appel

## <a name="enable-location-based-routing-for-users"></a>Activer le routage emplacement pour les utilisateurs

1. Utiliser le ``Set-CsOnlinePstnUsages`` applet de commande pour définir les utilisations RTC. Pour plusieurs utilisations, séparez chaque d’utilisation par une virgule.

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    Par exemple :
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. Utiliser le ``New-CsOnlineVoiceRoutingPolicy`` applet de commande pour créer une stratégie de routage voix pour associer l’utilisateur avec les utilisations PSTN appropriées.

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    Lorsque vous attribuez des utilisations PSTN à une stratégie de routage des communications vocales, assurez-vous que vous effectuez l’une des options suivantes :
    - Utiliser des utilisations PSTN associées aux itinéraires vocaux qui utilisent une passerelle PSTN locale vers le site
    - Utilisez les utilisations PSTN associées aux itinéraires vocaux qui utilisent une passerelle PSTN située dans une zone où des restrictions de routage basé sur l’emplacement ne sont pas nécessaires.

    Dans cet exemple, nous créer deux nouvelles stratégies routage des communications vocales et leur attribuer des utilisations PSTN. 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    Le tableau suivant présente les stratégies de routage voix définies dans cet exemple. 
    
    ||1 stratégie de routage voix|Stratégie de routage 2 voix|
    |---------|---------|---------|
    |ID de stratégie vocale en ligne   |Stratégie de routage Delhi vocale en ligne   |Stratégie de routage Hyderabad vocale en ligne    |
    |Utilisations PSTN en ligne  |Appel longue Distance  |Longue Distance internes, locales  |

    Pour plus d’informations, voir [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).
3. Utiliser le ``Grant-CsOnlineVoiceRoutingPolicy`` applet de commande pour associer en ligne vocale des stratégies de routage pour les utilisateurs qui ont besoin d’appliquer des restrictions de routage.
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a>Activer le routage emplacement pour les sites réseau
1.  Utiliser le ``Set-CsTenantNetworkSite`` applet de commande pour activer le routage basé sur l’emplacement et associer les stratégies de routage pour vos sites réseau qui doivent appliquer des restrictions de routage vocale.
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    Dans cet exemple, nous activer en fonction de routage pour le site Delhi et le site d’Hyderabad. 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    Le tableau suivant indique les sites activés pour le routage de fonction dans cet exemple.

    ||Site 1 (Delhi)  |Site 2 (Hyderabad)  |
    |---------|---------|---------|
|Nom du site    |Site 1 (Delhi)    |Site 2 (Hyderabad)   
    |EnableLocationBasedRouting    |True    |True    |
    |Sous-réseaux     |Sous-réseau 1 (Delhi)     |Sous-réseau 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-gateways"></a>Activer le routage emplacement pour les passerelles
1. Utiliser le ``New-CsOnlinePstnGateway`` applet de commande pour créer une configuration de passerelle pour chaque site de la passerelle ou le réseau. 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    Si plusieurs passerelles sont associés à un système (par exemple, la passerelle ou le PBX), modifiez chaque passerelle pour activer les restrictions de routage basé sur l’emplacement. 

    Dans cet exemple, nous créons une configuration de la passerelle pour chaque passerelle. 
    ```
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    Pour plus d’informations, voir [Configurer le routage Direct](direct-routing-configure.md).
    
2. Utiliser le ``Set-CSOnlinePSTNGateway`` applet de commande pour activer le routage emplacement pour vos passerelles qui doivent appliquer des restrictions de routage. 

    Activer le routage emplacement aux passerelles qui routent les appels vers les passerelles PSTN qui acheminer les appels vers la passerelle PSTN, puis associez le site réseau où se trouve la passerelle.

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    Dans cet exemple, nous activer en fonction de routage pour chaque passerelle qui est associé à des passerelles PSTN dans les sites Delhi et Hyderabad. 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    N’activez pas basée sur l’emplacement de routage pour les passerelles qui ne routent les appels RTC. Toutefois, vous devez associer la passerelle au site réseau où se trouve le système. Il s’agit, car les restrictions de routage basé sur l’emplacement doivent être appliqués pour les appels PSTN atteindre les points de terminaison connectés via cette passerelle. Dans cet exemple, en fonction de routage n’est pas activé pour chaque passerelle est associée à des systèmes PBX dans les sites Delhi et Hyderabad.

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    Points de terminaison connectés aux systèmes qui ne routent les appels RTC (par exemple, un PBX) auront des restrictions similaires comme points de terminaison d’utilisateurs équipes activés pour le routage basé sur l’emplacement. Cela signifie que ces utilisateurs peuvent passer et recevoir des appels vers et depuis les utilisateurs équipes quel que soit emplacement son. Ils peuvent également émettre et recevoir des appels vers et depuis d’autres systèmes qui ne routent les appels vers le réseau téléphonique commuté (par exemple, un point de terminaison connecté à un système PBX différents) quel que soit le site réseau auquel le système est associé. Tous les appels entrants, les appels sortants, les transferts d’appel et le transfert d’appel qui impliquent des points de terminaison RTC seront soumis aux applications de routage basé sur l’emplacement. Ces appels doivent utiliser uniquement les passerelles PSTN qui sont définis en tant que local à ces systèmes. 

    Le tableau suivant présente la configuration de la passerelle de quatre passerelles dans deux sites différents réseau : deux connectés à des passerelles PSTN et deux connectés à des systèmes PBX. 

    ||GatewaySiteLbrEnabled   |NetworkSiteID  |
    |---------|---------|---------|
    |DEL PstnGateway:Gateway 1-EG    |    True     |   Site 1 (Delhi)      |
    |PstnGateway:Gateway 2 HYD-EG     |   True      |      Site 2 (Hyderabad)   |
    |DEL PstnGateway:Gateway 3-PBX    |    False     |     Site 1 (Delhi)    |
    |HYD PstnGateway:Gateway 4-PBX    |    False     |    Site 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-calling-policies"></a>Activer le routage basé sur l’emplacement pour l’appel de stratégies

Pour appliquer un emplacement de routage pour des utilisateurs spécifiques, configurer la stratégie de voix des utilisateurs afin d’empêcher le numéro payant PTSN contournement de média. 

Utiliser le ``Grant-CsTeamsCallingPolicy`` applet de commande pour activer le routage basé sur l’emplacement en empêchant payant PSTN de contournement.

```
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
Dans cet exemple, nous empêcher PSTN payant contournement de média à l’utilisateur1 stratégies de l’appel. 

```
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a>Rubriques connexes
- [Planifier le routage géodépendant pour le routage direct](location-based-routing-plan.md)
- [Configurer les paramètres de réseau pour le routage géodépendant](location-based-routing-configure-network-settings.md)
- [Terminologie du routage géodépendant](location-based-routing-terminology.md)
