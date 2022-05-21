---
title: Gérer les stratégies de routage des appels d’urgence pour le routage direct
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment utiliser et gérer les stratégies de routage des appels d’urgence dans Microsoft Teams pour configurer des numéros d’urgence et spécifier comment les appels d’urgence sont acheminés.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 33a0493d038586aa51daf29e320e9ffa9c6c7b5b
ms.sourcegitcommit: 4435ac0efcb95e4e5e1f21289e46761e79482ab5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2022
ms.locfileid: "65624118"
---
# <a name="manage-emergency-call-routing-policies-for-direct-routing"></a>Gérer les stratégies de routage des appels d’urgence pour le routage direct

Si vous avez déployé le [routage direct](direct-routing-landing-page.md) dans votre organisation, vous pouvez utiliser des stratégies de routage des appels d’urgence dans Microsoft Teams pour configurer des numéros d’urgence et spécifier le routage des appels d’urgence. Une stratégie de routage des appels d’urgence détermine si les services d’urgence améliorés sont activés pour les utilisateurs auxquels la stratégie est attribuée, les numéros utilisés pour appeler les services d’urgence (par exemple, 911 dans le États-Unis) et la façon dont les appels aux services d’urgence sont acheminés. 

> [!Note]
> **Notez que ces stratégies de routage des appels s’appliquent uniquement au routage direct . Elles ne s’appliquent pas aux forfaits d’appels ou aux Operator Connect.**

Vous gérez les stratégies de routage des appels d’urgence en accédant aux **stratégies VoiceEmergency**  >  dans le centre d’administration Microsoft Teams ou en utilisant Windows PowerShell. Les stratégies peuvent être affectées aux utilisateurs et aux [sites réseau](cloud-voice-network-settings.md).

Pour les utilisateurs, vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) ou créer et affecter des stratégies personnalisées. Les utilisateurs obtiennent automatiquement la stratégie globale, sauf si vous créez et affectez une stratégie personnalisée. N’oubliez pas que vous pouvez modifier les paramètres de la stratégie globale, mais que vous ne pouvez pas les renommer ou les supprimer. Pour les sites réseau, vous créez et attribuez des stratégies personnalisées.

Si vous avez affecté une stratégie de routage des appels d’urgence à un site réseau et à un utilisateur et si cet utilisateur se trouve sur ce site réseau, la stratégie affectée au site réseau remplace la stratégie affectée à l’utilisateur.

## <a name="create-a-custom-emergency-call-routing-policy"></a>Créer une stratégie de routage des appels d’urgence personnalisée

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez aux **stratégies VoiceEmergency** > , puis cliquez sur l’onglet **Stratégies de routage** des appels.
2. Cliquez sur **Ajouter**.
3. Entrez un nom pour votre stratégie, ainsi qu’une description.
4. Pour activer les appels d’urgence dynamiques, activez **l’appel d’urgence dynamique**. Lorsque l’appel d’urgence dynamique est activé, Teams récupère les informations de stratégie et d’emplacement du service et inclut ces informations dans le cadre de l’appel d’urgence.
5. Définissez un ou plusieurs numéros d’urgence. Pour ce faire, sous **Numéros d’urgence**, cliquez sur **Ajouter**, puis procédez comme suit :
    1. **Chaîne de numérotation d’urgence** : entrez la chaîne de numérotation d’urgence. Cette chaîne de numérotation indique qu’un appel est un appel d’urgence et que le modèle d’itinéraire doit correspondre exactement à cette chaîne de numérotation. 
        > [!NOTE]
        > **Pour le routage direct, Teams clients n’envoient plus d’appels d’urgence avec un « + » devant la chaîne de numérotation d’urgence. Assurez-vous que le modèle de routage vocal correspondant à une chaîne de numérotation d’urgence reflète cette modification.**
    2. **Masque de numérotation d’urgence** : pour chaque numéro d’urgence, vous pouvez spécifier zéro ou plusieurs masques de numérotation d’urgence. Un masque de numérotation est le numéro que vous souhaitez traduire en valeur de la chaîne de numérotation d’urgence. Cela permet de composer d’autres numéros d’urgence et d’avoir toujours l’appel aux services d’urgence. <br>Par exemple, vous ajoutez le 112 comme masque de numérotation d’urgence, qui est le numéro de service d’urgence pour la majeure partie de l’Europe, et le 911 comme chaîne de numérotation d’urgence. Un utilisateur Teams d’Europe qui visite peut ne pas savoir que le 911 est le numéro d’urgence dans le États-Unis, et lorsqu’il compose le 112, l’appel est effectué au 911. Pour définir plusieurs masques de numérotation, séparez chaque valeur par un point-virgule. Par exemple, 112;212.
    3. **Enregistrement d’utilisation RTC** : sélectionnez l’enregistrement d’utilisation du réseau téléphonique commuté (RTC). L’enregistrement d’utilisation RTC est utilisé pour déterminer l’itinéraire utilisé pour acheminer les appels d’urgence des utilisateurs autorisés à les utiliser. L’itinéraire associé à cette utilisation doit pointer vers une jonction SIP (Session Initiation Protocol) dédiée aux appels d’urgence ou vers une passerelle ELIN (Emergency Location Identification Number) qui route les appels d’urgence vers le point de réponse de sécurité publique (PSAP) le plus proche.

    > [!NOTE]
    > Les chaînes de numérotation et les masques de numérotation doivent être uniques dans une stratégie. Cela signifie que pour une stratégie, vous pouvez définir plusieurs numéros d’urgence et définir plusieurs masques de numérotation pour une chaîne de numérotation, mais chaque chaîne de numérotation et chaque masque de numérotation ne doivent être utilisés qu’une seule fois.

6. Cliquez sur **Enregistrer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [New-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/new-csteamsemergencycallroutingpolicy).

## <a name="edit-an-emergency-call-routing-policy"></a>Modifier une stratégie de routage des appels d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

Vous pouvez modifier la stratégie globale ou les stratégies personnalisées que vous créez.

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez aux **stratégies VoiceEmergency** > , puis cliquez sur l’onglet **Stratégies de routage** des appels.
2. Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis cliquez sur **Modifier**.
3. Apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [Set-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/set-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>Affecter une stratégie de routage des appels d’urgence personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Voir aussi [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>Affecter une stratégie de routage d’appel d’urgence personnalisée à un site réseau

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

Vous pouvez affecter la stratégie globale ou les stratégies personnalisées que vous créez.

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez à la **topologie** **LocationsNetwork** > , puis cliquez sur l’onglet **Sites réseau**.
2. Sélectionnez le site en cliquant à gauche du nom, puis cliquez sur **Modifier**.
3. Sous Stratégie **de routage des appels d’urgence**, sélectionnez la stratégie, puis cliquez sur **Enregistrer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Utilisez l’applet [de commande Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) pour affecter une stratégie de routage des appels d’urgence à un site réseau.

Cet exemple montre comment affecter une stratégie appelée stratégie de routage des appels d’urgence 1 au site Site1.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>Voir aussi

[Gérer les stratégies d’appel d’urgence dans Teams](manage-emergency-calling-policies.md)

[Présentation de Teams PowerShell](teams-powershell-overview.md)

[Attribuer des stratégies à vos utilisateurs](policy-assignment-overview.md)
