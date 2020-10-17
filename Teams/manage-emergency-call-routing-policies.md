---
title: Gérer les stratégies de routage d’appel d’urgence
author: lanachin
ms.author: v-lanac
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
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser et gérer les stratégies d’acheminement des appels d’urgence dans Microsoft teams pour configurer des numéros d’urgence et définir le mode de routage des appels d’urgence.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 2ec28dfa2e3e3c685ea70d882c4dd6d4d342ec7f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532751"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a>Gérer les stratégies d’acheminement des appels d’urgence dans Microsoft teams

Si vous avez déployé le [routage direct du système téléphonique](direct-routing-landing-page.md) au sein de votre organisation, vous pouvez utiliser les stratégies d’acheminement des appels d’urgence de Microsoft teams pour configurer les numéros d’urgence et spécifier le mode de routage des appels d’urgence. Une stratégie d’acheminement des appels d’urgence détermine si les services d’urgence améliorés sont activés pour les utilisateurs auxquels la stratégie est affectée, les numéros utilisés pour appeler les services d’urgence (par exemple, 911 aux États-Unis) et comment les appels vers les services d’urgence sont routés.

Vous gérez les stratégies d’acheminement des appels **Voice**d’urgence en accédant à  >  **stratégies d’urgence** vocale dans le centre d’administration Microsoft teams ou à l’aide de Windows PowerShell. Elles peuvent être attribuées à des utilisateurs et des [sites réseau](cloud-voice-network-settings.md).

Pour les utilisateurs, vous pouvez utiliser la stratégie globale par défaut de l’organisation ou créer et attribuer des stratégies personnalisées. Les utilisateurs bénéficieront automatiquement de la stratégie globale, sauf si vous créez et attribuez une stratégie personnalisée. Gardez à l’esprit que vous pouvez modifier les paramètres de la stratégie globale, mais que vous ne pouvez pas les renommer ou les supprimer. Pour les sites réseau, vous créez et attribuez des stratégies personnalisées.

Si vous avez affecté une stratégie d’acheminement des appels d’urgence à un site réseau et à un utilisateur et que, si cet utilisateur se trouve sur ce site réseau, la stratégie attribuée au site réseau remplace celle qui est affectée à l’utilisateur.

## <a name="create-a-custom-emergency-call-routing-policy"></a>Créer une stratégie d’acheminement des appels d’urgence personnalisée

### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams, accédez à  >  **stratégies d’urgence**vocale, puis cliquez sur l’onglet stratégies de routage des **appels** .
2. Cliquez sur **Ajouter**.
3. Entrez un nom pour votre stratégie, ainsi qu’une description.
4. Pour activer les appels d’urgence dynamiques, activez les **appels d’urgence dynamiques**. Lorsque les appels d’urgence dynamiques sont activés, teams récupère les informations de stratégie et d’emplacement du service et inclut ces informations dans le cadre de l’appel d’urgence.
5. Définissez un ou plusieurs numéros d’urgence. Pour ce faire, sous **numéros d’urgence**, cliquez sur **Ajouter**, puis procédez comme suit :
    1. **Chaîne de numérotation d’urgence**: entrez la chaîne de numérotation d’urgence. Cette chaîne de numérotation indique qu’un appel est un appel d’urgence.
        > [!NOTE]
        > Pour le routage direct, nous faisons en sorte que les clients teams envoient les appels d’urgence en utilisant le signe « + » en face de la chaîne de numérotation d’urgence. Tant que la transition ne s’est pas terminée, le modèle d’itinéraire vocal correspondant à une chaîne de numérotation d’urgence doit garantir la prise de correspondances pour les chaînes qui contiennent et ne possèdent pas de « + », comme 911 et + 911. Par exemple, ^ \\ + ? 911 ou. *.
    2. **Masque de numérotation d’urgence**: pour chaque numéro d’urgence, vous pouvez spécifier zéro ou plusieurs masques de numérotation d’urgence. Un masque de numérotation correspond au numéro que vous souhaitez traduire dans la valeur de la chaîne de numérotation d’urgence. Cela permet d’appeler d’autres numéros d’urgence et de toujours avoir accès aux services d’urgence. <br>Par exemple, vous ajoutez 112 comme masque de numérotation d’urgence, qui est le numéro de service d’urgence pour la plupart des services d’Europe et 911 comme chaîne de numérotation d’urgence. Un utilisateur de teams d’Europe qui ne sait pas que 911 correspond au numéro d’urgence aux États-Unis et lorsqu’il appelle 112, l’appel est effectué à 911. Pour définir plusieurs masques de numérotation, séparez chaque valeur par un point-virgule. Par exemple, 112 ; 212.
    3. **Enregistrement d’utilisation RTC**: sélectionnez l’enregistrement d’utilisation du réseau téléphonique public commuté (RTC). L’enregistrement d’utilisation RTC détermine quel itinéraire est utilisé pour acheminer les appels d’urgence de la part des utilisateurs autorisés à les utiliser. L’itinéraire associé à cette utilisation doit pointer vers une ligne SIP (Session Initiation Protocol) dédiée aux appels d’urgence ou à une passerelle ELIN (Emergency Identification Number) qui route les appels d’urgence vers le point de réponse de sécurité publique le plus proche (PSAPI).

    > [!NOTE]
    > Les chaînes de numérotation et les masques de numérotation doivent être uniques au sein d’une stratégie. Cela signifie que pour une stratégie, vous pouvez définir plusieurs numéros d’urgence et définir plusieurs masques de numérotation pour une chaîne de numérotation, mais chaque chaîne de numérotation et chaque masque de numérotation doivent être utilisés une seule fois.

6. Cliquez sur **Enregistrer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).

## <a name="edit-an-emergency-call-routing-policy"></a>Modifier une stratégie d’acheminement des appels d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft Teams

Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams, accédez à  >  **stratégies d’urgence**vocale, puis cliquez sur l’onglet stratégies de routage des **appels** .
2. Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie, puis cliquez sur **modifier**.
3. Apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>Attribuer une stratégie d’acheminement d’appel d’urgence personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Voir aussi [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>Affecter une stratégie d’acheminement d’appel d’urgence personnalisée à un site réseau

Utilisez l’applet de connexion [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) pour attribuer une stratégie d’acheminement des appels d’urgence à un site réseau.

Cet exemple montre comment assigner une stratégie appelée politique de routage des appels d’urgence 1 au site site1.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>Voir aussi

[Gérer les stratégies d’appel d’urgence dans teams](manage-emergency-calling-policies.md)

[Présentation de Teams PowerShell](teams-powershell-overview.md)

[Attribuer des stratégies à vos utilisateurs dans teams](assign-policies.md)
