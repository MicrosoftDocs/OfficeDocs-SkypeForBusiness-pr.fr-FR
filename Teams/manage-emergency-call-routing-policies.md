---
title: Gérer les stratégies de routage vocal d’urgence pour le routage direct
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
description: Découvrez comment utiliser et gérer les stratégies de routage vocal d’urgence Microsoft Teams configurer des numéros d’urgence et spécifier la manière dont les appels d’urgence sont acheminés.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: f7a62338cc8fe3fbdc73e88cfca5dd9e525ff150
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605200"
---
# <a name="manage-emergency-voice-routing-policies-for-direct-routing"></a>Gérer les stratégies de routage vocal d’urgence pour le routage direct

Si vous avez [](direct-routing-landing-page.md) déployé le routage direct dans votre organisation, vous pouvez utiliser les stratégies de routage vocal d’urgence dans Microsoft Teams pour configurer les numéros d’urgence et spécifier le routage des appels d’urgence. Une stratégie de routage vocal d’urgence détermine si les services d’urgence améliorés sont activés pour les utilisateurs à qui la stratégie est affectée, les numéros utilisés pour appeler les services d’urgence (par exemple, le 112 en France) et la manière dont les appels vers les services d’urgence sont acheminés. 

> [!Note]
> **Notez que ces stratégies de routage vocal s’appliquent uniquement au routage direct, elles ne s’appliquent pas aux plans d’appels ou aux opérateurs Connecter.**

Pour gérer les stratégies de routage voix d’urgence, vous devez vous rendre sur Voice Emergency center Microsoft Teams centre d’administration ou à l’aide  >   de Windows PowerShell. Les stratégies peuvent être affectées à des utilisateurs et [à des sites réseau.](cloud-voice-network-settings.md)

Pour les utilisateurs, vous pouvez utiliser la stratégie globale (à l’échelle de l’organisation par défaut) ou créer et attribuer des stratégies personnalisées. Les utilisateurs obtiennent automatiquement la stratégie globale, sauf si vous créez et attribuez une stratégie personnalisée. N’oubliez pas que vous pouvez modifier les paramètres de la stratégie globale, mais que vous ne pouvez pas le renommer ou le supprimer. Pour les sites réseau, vous créez et attribuez des stratégies personnalisées.

Si vous avez affecté une stratégie de routage voix d’urgence à un site réseau et à un utilisateur, et si cet utilisateur se trouve sur ce site réseau, la stratégie attribuée au site réseau remplace la stratégie qui lui est affectée.

## <a name="create-a-custom-emergency-voice-routing-policy"></a>Créer une stratégie personnalisée de routage vocal d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le panneau de navigation de gauche Microsoft Teams d’administration, allez dans Stratégies d’urgence vocale, puis cliquez sur l’onglet Stratégies  >   **de routage des** appels.
2. Cliquez sur **Ajouter**.
3. Entrez un nom pour votre stratégie, ainsi qu’une description.
4. Pour activer les appels d’urgence dynamiques, activez **l’appel d’urgence dynamique.** Lorsque les appels d’urgence dynamiques sont activés, Teams récupère les informations de stratégie et d’emplacement du service et les inclut dans le cadre de l’appel d’urgence.
5. Définissez un ou plusieurs numéros d’urgence. Pour ce faire, sous **Numéros d’urgence,** cliquez **sur** Ajouter, puis :
    1. **Chaîne de numérotation d’urgence**: Entrer la chaîne de numérotation d’urgence. Cette chaîne de numérotation indique qu’un appel est un appel d’urgence.
        > [!NOTE]
        > **Pour le routage direct, Teams clients n’envoient plus d’appels d’urgence avec un « + » devant la chaîne de numérotation d’urgence. Assurez-vous que le modèle de l’itinéraire vocal pour correspondre à une chaîne de numérotation d’urgence reflète ce changement.**
    2. **Masque de numérotation** d’urgence : pour chaque numéro d’urgence, vous pouvez spécifier un ou plusieurs masques de numérotation d’urgence. Un masque de numérotation est le numéro que vous voulez traduire en valeur de la chaîne de numérotation d’urgence. Cela permet d’appeler d’autres numéros d’urgence tout en permettant d’appeler les services d’urgence. <br>Par exemple, vous ajoutez le chiffre 112 comme masque de numérotation d’urgence, qui est le numéro de service d’urgence pour la plupart de l’Europe, et le 911 comme chaîne de numérotation d’urgence. Un utilisateur Teams d’Europe en visite peut ne pas savoir que le 911 est le numéro d’urgence aux États-Unis et, quand il compose le 112, composez le 111. Pour définir plusieurs masques de numérotation, séparez les valeurs par un point-virgule. Par exemple, 112;212.
    3. **Enregistrement d’utilisation PSTN**: sélectionnez l’enregistrement d’utilisation de réseau téléphonique commuté (PSTN). L’enregistrement d’utilisation PSTN permet de déterminer l’itinéraire utilisé pour router les appels d’urgence des utilisateurs autorisés à les utiliser. L’itinéraire associé à cette utilisation doit pointer vers une ligne SIP (Session Initiation Protocol) dédiée à des appels d’urgence ou à une passerelle ELIN (Emergency Location Identification Number) qui route les appels d’urgence vers le point de réponse de sécurité publique (PUBLIC Safety Answering Point) le plus proche.

    > [!NOTE]
    > Les chaînes de numérotation et masques de numérotation doivent être uniques dans une stratégie. Cela signifie que pour une stratégie, vous pouvez définir plusieurs numéros d’urgence et définir plusieurs masques de numérotation pour une chaîne de numérotation, mais chaque chaîne de numérotation et masque de numérotation ne doivent être utilisés qu’une seule fois.

6. Cliquez sur **Enregistrer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [New-CsTeamsEmergencyCallRoutingPolicy.](/powershell/module/skype/new-csteamsemergencycallroutingpolicy)

## <a name="edit-an-emergency-voice-routing-policy"></a>Modifier une stratégie de routage vocal d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez.

1. Dans le panneau de navigation de gauche Microsoft Teams d’administration, allez dans Stratégies d’urgence vocale, puis cliquez sur l’onglet Stratégies  >   **de routage des** appels.
2. Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis cliquez sur **Modifier**.
3. A apporter les modifications de votre souhaitez, puis cliquez sur **Enregistrer.**

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [Set-CsTeamsEmergencyCallRoutingPolicy.](/powershell/module/skype/set-csteamsemergencycallroutingpolicy)

## <a name="assign-a-custom-emergency-voice-routing-policy-to-users"></a>Affecter une stratégie personnalisée de routage vocal d’urgence aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Voir également [Grant-CsTeamsEmergencyCallRoutingPolicy.](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)

## <a name="assign-a-custom-emergency-voice-routing-policy-to-a-network-site"></a>Affecter une stratégie personnalisée de routage vocal d’urgence à un site réseau

Utilisez la cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) pour affecter une stratégie de routage des appels d’urgence à un site réseau.

Cet exemple montre comment affecter une stratégie appelée Stratégie de routage des appels d’urgence 1 sur le site Site1.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>Sujets associés

[Gérer les stratégies d’appel d’urgence Teams](manage-emergency-calling-policies.md)

[Présentation de Teams PowerShell](teams-powershell-overview.md)

[Attribuer des stratégies à vos utilisateurs](policy-assignment-overview.md)