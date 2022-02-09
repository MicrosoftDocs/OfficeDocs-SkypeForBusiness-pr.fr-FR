---
title: Activer le routage géodépendant pour le routage direct
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Découvrez comment activer Location-Based routage direct, notamment l’activer pour les utilisateurs, les sites réseau, les configurations de passerelle et les stratégies d’appel.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a53ab4ad866f3d9ad6acb1258247da59b15a27d9
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399488"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Activer le routage géodépendant pour le routage direct

Avant de suivre les étapes de cet article, assurez-vous que vous avez lu l’article [Plan Location-Based Routage](location-based-routing-plan.md) de routage direct et que vous avez suivi les étapes de configuration des paramètres réseau pour le [Location-Based routage](location-based-routing-configure-network-settings.md).

Cet article décrit comment activer Location-Based routage pour le routage direct. Une fois que vous Système téléphonique un routage direct et que vous avez installé les régions, sites et sous-réseaux réseau, vous êtes prêt à activer Location-Based routage. Pour suivre les étapes de cet article, vous devez être familiarisé avec les cmdlets PowerShell. Pour en savoir plus, voir [Teams vue d’ensemble de PowerShell](teams-powershell-overview.md).

 Vous devez activer Location-Based routage pour les suivantes :
- Utilisateurs
- Sites réseau
- Configurations de la passerelle
- Stratégies d’appel

Vous pouvez utiliser le [Centre Microsoft Teams’administration](#using-the-microsoft-teams-admin-center) de l’utilisateur ou [PowerShell](#using-powershell) pour activer Location-Based routage.

## <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

### <a name="enable-location-based-routing-for-users"></a>Activer Location-Based routage pour les utilisateurs

1. Créez une stratégie de routage vocal et attribuez des utilisations PSTN à la stratégie. Lorsque vous attribuez des utilisations PSTN à une stratégie, assurez-vous d’effectuer l’une des tâches suivantes :

    - Utilisez les utilisations PSTN associées aux itinéraires vocaux qui utilisent une passerelle PSTN locale vers le site.
    - Utilisez les utilisations PSTN associées aux itinéraires vocaux qui utilisent une passerelle PSTN située dans une région où Location-Based restrictions de routage ne sont pas nécessaires.
2. Affectez la stratégie de routage voix aux utilisateurs qui ont besoin d’appliquer des restrictions de routage.

Pour en savoir plus sur la création de stratégies de routage voix et leur attribution aux utilisateurs, voir Gérer les stratégies de [routage vocal dans Microsoft Teams](manage-voice-routing-policies.md).

### <a name="enable-location-based-routing-for-network-sites"></a>Activer Location-Based routage pour les sites réseau

Activez Location-Based routage pour vos sites qui ont besoin d’appliquer des restrictions de routage. Pour ce faire, dans le menu de navigation gauche du Centre d’administration Microsoft Teams, sélectionnez la topologie **LocationsNetwork** > , sélectionnez un site réseau, cliquez sur Modifier, puis activer le **routage** basé sur l’emplacement.  

Pour plus d’informations, [voir Gérer votre topologie de réseau](manage-your-network-topology.md).

### <a name="enable-location-based-routing-for-gateways"></a>Activer Location-Based routage pour les passerelles

Activez Location-Based routage vers des passerelles qui routent des appels vers des passerelles PSTN qui routent des appels vers le réseau PSTN et associez le site réseau où se trouve la passerelle. 

1. Dans le groupe de navigation de gauche, allez sur **Routage VoiceDirect** > , puis cliquez sur l’onglet **SBCs**.
2. Sélectionnez le SBC, puis cliquez sur **Modifier**. 
3. Sous **Routage et optimisation** des médias basés sur l’emplacement, **activez Activer le routage basé sur l’emplacement**.
4. Spécifiez l’ID de site de la passerelle, puis définissez le mode de dérivation.
5. Cliquez sur **Enregistrer**.

### <a name="enable-location-based-routing-for-calling-policies"></a>Activer Location-Based routage des appels

Pour appliquer Location-Based routage pour des utilisateurs spécifiques, définissez la stratégie d’appel de l’utilisateur afin d’empêcher la dérivation PSTN toll. Pour ce faire, vous pouvez activer **le paramètre Prévenir** le contournement toll dans la stratégie d’appel.

Pour en savoir plus, [consultez les stratégies d’appel dans Teams](teams-calling-policy.md).

## <a name="using-powershell"></a>Utiliser PowerShell

### <a name="enable-location-based-routing-for-users"></a>Activer Location-Based routage pour les utilisateurs

1. Utilisez [l’cmdlet Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) pour définir les utilisations PSTN. Pour plusieurs utilisations, séparez chaque utilisation par une virgule.

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    Par exemple :
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. Utilisez [l’cmdlet New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) pour créer une stratégie de routage voix afin d’associer l’utilisateur aux utilisations PSTN appropriées.

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    Lorsque vous affectez des utilisations PSTN à une stratégie de routage vocale, assurez-vous d’effectuer l’une des tâches suivantes :
    - Utiliser les utilisations PSTN associées aux itinéraires vocaux qui utilisent une passerelle RSTN locale vers le site
    - Utilisez les utilisations PSTN associées aux itinéraires vocaux qui utilisent une passerelle PSTN située dans une région où Location-Based restrictions de routage ne sont pas nécessaires.

    Dans cet exemple, nous créons deux stratégies de routage voix et leur affectons des utilisations PSTN. 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    Le tableau suivant indique les stratégies de routage voix définies dans cet exemple. 
    
    |&nbsp;|Stratégie de routage voix 1|Stratégie de routage voix 2|
    |---------|---------|---------|
    |ID de stratégie vocale en ligne   |Politique de routage vocal en ligne d’Online   |Politique de routage vocal en ligne du Service vos achats en ligne    |
    |Utilisations PSTN en ligne  |Longue distance  |Longue distance, local, interne  |

3. Utilisez l’cmdlet [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) pour associer des stratégies de routage voix en ligne aux utilisateurs qui demandent l’application de restrictions de routage.
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a>Activer Location-Based routage pour les sites réseau

1.  Utilisez l’cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) pour activer le routage Location-Based et associer des stratégies de routage voix à vos sites réseau qui doivent appliquer des restrictions de routage.
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    Dans cet exemple, nous avons activé Location-Based routage pour le site Densoin et le site Densoin. 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    Le tableau suivant indique les sites activés pour le Location-Based routage dans cet exemple.

    |&nbsp;|Site 1 (Syz)  |Site 2 (Sod)  |
    |---------|---------|---------|
    |Nom du site    |Site 1 (Syz)    |Site 2 (Sod)|
    |EnableLocationBasedRouting    |Vrai    |Vrai    |
    |Sous-réseaux     |Sous-réseau 1 (Syz)     |Sous-réseau 2 (Syz)     |

### <a name="enable-location-based-routing-for-gateways"></a>Activer Location-Based routage pour les passerelles

1. Utilisez la [cmdlet New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) pour créer une configuration de passerelle pour chaque passerelle ou site réseau. 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    Si plusieurs passerelles sont associées à un système (par exemple, passerelle ou PBX), modifiez chaque passerelle pour activer les Location-Based de routage. 

    Dans cet exemple, nous créons une configuration de passerelle pour chaque passerelle. 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    Pour plus d’informations, [voir Configurer le routage direct](direct-routing-configure.md).
    
2. Utilisez [l’cmdlet Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) pour activer Location-Based routage pour vos passerelles qui doivent appliquer des restrictions de routage. 

    Activez Location-Based routage vers des passerelles qui routent des appels vers des passerelles PSTN qui routent des appels vers le réseau PSTN et associez le site réseau où se trouve la passerelle.

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    Dans cet exemple, nous avons activé Location-Based routage des utilisateurs pour chaque passerelle associée aux passerelles RSTN dans les sites des centres d’information et des entreprises. 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    N’activez pas Location-Based routage pour les passerelles qui ne routent pas les appels vers le RSTN. Toutefois, vous devez toujours associer la passerelle au site réseau où se trouve le système. En effet, Location-Based restrictions de routage doivent être appliquées pour les appels RSTN qui atteignent des points de terminaison connectés via cette passerelle. Dans cet exemple, le Location-Based routage des données n’est pas activé pour chaque passerelle associée aux systèmes PBX dans les sites Vostâches et Vos centres d’information.

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>Activer Location-Based routage des appels

Pour appliquer Location-Based routage pour des utilisateurs spécifiques, définissez la stratégie vocale des utilisateurs afin d’empêcher la dérivation toll du PTSN. 

Utilisez [l’cmdlet Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) pour activer Location-Based routage en empêchant la dérivation PSTN toll.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
Dans cet exemple, nous empêchons la dérivation PSTN contre les stratégies d’appel de l’utilisateur 1. 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>Voir aussi

- [Paramètres réseau pour les fonctionnalités vocales cloud dans Teams](cloud-voice-network-settings.md)