---
title: Activer le routage géodépendant pour le routage direct
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Découvrez comment activer le routage Location-Based pour le routage direct, notamment pour les utilisateurs, les sites réseau, les configurations de passerelle et les stratégies d’appel.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aadf5f4e4dff855d80c275be3d2027e767a732ad
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562193"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Activer le routage géodépendant pour le routage direct

Cet article explique comment activer Location-Based routage pour le routage direct. Avant de suivre les étapes décrites dans cet article, vérifiez que vous avez lu [Plan Location-Based Routage pour le routage direct](location-based-routing-plan.md) et que vous avez effectué les [étapes de configuration des paramètres réseau pour Location-Based routage](location-based-routing-configure-network-settings.md).

 Après avoir déployé le routage direct et configuré des régions réseau, des sites et des sous-réseaux, vous êtes prêt à activer Location-Based routage. Pour suivre les étapes décrites dans cet article, vous devez connaître les applets de commande PowerShell. Pour en savoir plus, consultez [la vue d’ensemble de Teams PowerShell](teams-powershell-overview.md)

 Vous devez activer Location-Based routage pour les éléments suivants :

- Utilisateurs
- Sites réseau
- Configurations de passerelle
- Stratégies d’appel

Vous pouvez utiliser le [Centre d’administration Teams](#using-the-microsoft-teams-admin-center) ou [PowerShell](#using-powershell) pour activer Location-Based routage.

## <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

### <a name="enable-location-based-routing-for-users"></a>Activer le routage Location-Based pour les utilisateurs

1. Créez une stratégie de routage vocal et attribuez des utilisations RTC à la stratégie. Lorsque vous attribuez des utilisations RTC à une stratégie, veillez à effectuer l’une des opérations suivantes :

    - Utilisez les utilisations RTC associées aux itinéraires vocaux qui utilisent une passerelle RTC locale vers le site.

    - Utilisez les utilisations RTC associées aux itinéraires vocaux qui utilisent une passerelle RTC située dans une région où Location-Based restrictions de routage ne sont pas nécessaires.

2. Affectez la stratégie de routage vocal aux utilisateurs qui nécessitent l’application de restrictions de routage.

Pour en savoir plus sur la création de stratégies de routage vocal et leur affectation aux utilisateurs, consultez [Gérer les stratégies de routage vocal dans Microsoft Teams](manage-voice-routing-policies.md).

### <a name="enable-location-based-routing-for-network-sites"></a>Activer le routage Location-Based pour les sites réseau

Activez Location-Based routage pour vos sites qui doivent appliquer des restrictions de routage. Pour ce faire, dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à la **topologie réseau** **Emplacements** > , sélectionnez un site réseau, cliquez sur **Modifier**, puis activez le **routage basé sur l’emplacement**.  

Pour plus d’informations, consultez [Gérer la topologie de votre réseau](manage-your-network-topology.md).

### <a name="enable-location-based-routing-for-gateways"></a>Activer le routage Location-Based pour les passerelles

Activez Location-Based le routage vers les passerelles qui routent les appels vers des passerelles RTC qui routent les appels vers le rtc, et associez le site réseau où se trouve la passerelle. 

1. Dans le volet de navigation de gauche, accédez à **Voice** > **Direct Routing**, puis cliquez sur l’onglet **SBC** .

2. Sélectionnez le SBC, puis cliquez sur **Modifier**. 

3. Sous **Routage basé sur l’emplacement et optimisation du média**, **activez Activer le routage basé sur l’emplacement**.

4. Spécifiez l’ID de site de passerelle, puis définissez le mode de contournement.

5. Cliquez sur **Enregistrer**.

### <a name="enable-location-based-routing-for-calling-policies"></a>Activer le routage Location-Based pour les stratégies d’appel

Pour appliquer Location-Based routage pour des utilisateurs spécifiques, configurez la stratégie d’appel de l’utilisateur pour empêcher le contournement des péages RTC. Pour ce faire, **activez le paramètre Empêcher le contournement des péages** dans la stratégie d’appel.

Pour en savoir plus, consultez [Stratégies d’appel dans Teams](teams-calling-policy.md).

## <a name="using-powershell"></a>Utiliser PowerShell

### <a name="enable-location-based-routing-for-users"></a>Activer le routage Location-Based pour les utilisateurs

1. Pour définir des utilisations RTC, utilisez l’applet de commande [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) . Pour plusieurs utilisations, séparez chaque utilisation par une virgule.

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```

    Par exemple :

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```

2. Pour créer une stratégie de routage vocal afin d’associer l’utilisateur à l’utilisation PSTN appropriée, utilisez l’applet de commande [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) .

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    Lorsque vous attribuez des utilisations RTC à une stratégie de routage vocal, veillez à effectuer l’une des opérations suivantes :

    - Utilisez les utilisations RTC associées aux itinéraires vocaux qui utilisent une passerelle RTC locale vers le site.

    - Utilisez les utilisations RTC associées aux itinéraires vocaux qui utilisent une passerelle RTC située dans une région où Location-Based restrictions de routage ne sont pas nécessaires.

    L’exemple suivant crée deux nouvelles stratégies de routage vocal et leur attribue des utilisations RTC. 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ``` 

    Le tableau suivant présente les stratégies de routage vocal définies dans cet exemple. 
    
    |&nbsp;|Stratégie de routage vocal 1|Stratégie de routage vocal 2|
    |---------|---------|---------|
    |ID de stratégie de voix en ligne   |Politique de routage des communications vocales en ligne à Delhi   |Politique de routage des communications vocales en ligne à Hyderabad    |
    |Utilisations PSTN en ligne  |Interurbains  |Longue distance, locale, interne  |

3. Pour associer des stratégies de routage vocal en ligne aux utilisateurs qui nécessitent l’application de restrictions de routage, utilisez l’applet de commande [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) .

    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```

### <a name="enable-location-based-routing-for-network-sites"></a>Activer le routage Location-Based pour les sites réseau

1. Pour activer Location-Based routage et associer des stratégies de routage vocal à vos sites réseau qui doivent appliquer des restrictions de routage, utilisez l’applet [de commande Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) .

    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    Cet exemple montre comment activer Location-Based routage pour le site de Delhi et le site Hyderabad. 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    Le tableau suivant montre les sites activés pour le routage Location-Based dans cet exemple.

    |&nbsp;|Site 1 (Delhi)  |Site 2 (Hyderabad)  |
    |---------|---------|---------|
    |Nom du site    |Site 1 (Delhi)    |Site 2 (Hyderabad)|
    |EnableLocationBasedRouting    |Vrai    |Vrai    |
    |Sous-réseaux     |Sous-réseau 1 (Delhi)     |Sous-réseau 2 (Hyderabad)     |


### <a name="enable-location-based-routing-for-gateways"></a>Activer le routage Location-Based pour les passerelles

1. Pour créer une configuration de passerelle pour chaque passerelle ou site réseau, utilisez l’applet de commande [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) . 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```

    Si plusieurs passerelles sont associées à un système (par exemple, passerelle ou PBX), modifiez chaque passerelle pour activer Location-Based restrictions de routage. 

    L’exemple suivant crée une configuration de passerelle pour chaque passerelle. 

    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    Pour plus d’informations, consultez [Configurer le routage direct](direct-routing-configure.md).
    
2. Pour activer Location-Based routage pour vos passerelles qui doivent appliquer des restrictions de routage, utilisez [l’applet de commande Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) . 

    Activez Location-Based le routage vers les passerelles qui routent les appels vers des passerelles RTC qui routent les appels vers le rtc, et associez le site réseau où se trouve la passerelle.

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

   L’exemple suivant active le routage Location-Based pour chaque passerelle associée aux passerelles RTC dans les sites Delhi et Hyderabad. 

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```

    N’activez pas le routage Location-Based pour les passerelles qui n’acheminent pas les appels vers le rtc. Toutefois, vous devez toujours associer la passerelle au site réseau où se trouve le système. Cela est dû au fait que Location-Based restrictions de routage doivent être appliquées pour les appels RTC qui atteignent des points de terminaison connectés via cette passerelle. Dans cet exemple, Location-Based routage n’est pas activé pour chaque passerelle associée aux systèmes PBX des sites Delhi et Hyderabad.

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>Activer le routage Location-Based pour les stratégies d’appel

Pour appliquer Location-Based routage pour des utilisateurs spécifiques, configurez la stratégie de voix des utilisateurs pour empêcher le contournement des péages PTSN. 

Pour activer Location-Based routage en empêchant le contournement payant RTC, utilisez l’applet de commande [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) .


```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```

Dans cet exemple, nous empêchent le contournement payant RTC des stratégies d’appel d’Utilisateur1. 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>Sujets associés

- [Paramètres réseau pour les fonctionnalités de voix cloud dans Teams](cloud-voice-network-settings.md)