---
title: Gérer les stratégies d’appel d’urgence dans Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser et gérer les stratégies d’appel d’urgence dans Microsoft Teams pour définir ce qui se passe lorsqu’un utilisateur de Teams dans votre organisation effectue un appel d’urgence.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 34f6e901049dd080ee070e7858f24b70535ee189
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120565"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Gérer les stratégies d’appel d’urgence dans Microsoft Teams

Si votre organisation utilise des [plans](set-up-calling-plans.md) d’appels ou un routage direct de système téléphonique [déployé,](direct-routing-landing-page.md)vous pouvez utiliser les stratégies d’appel d’urgence dans Microsoft Teams pour définir ce qui se passe lorsqu’un utilisateur de Teams dans votre organisation effectue un appel d’urgence. Vous pouvez définir les personnes à informer et la manière dont ils sont avertis lorsqu’un utilisateur affecté à la stratégie appelle les services d’urgence. Par exemple, vous pouvez configurer les paramètres de stratégie pour avertir automatiquement le service de sécurité de votre organisation et lui faire écouter les appels d’urgence.  

Pour gérer les stratégies d’appel d’urgence, vous devez utiliser le Centre d’administration Microsoft Teams pour utiliser les stratégies d’urgence vocale ou l’aide  >   Windows PowerShell. Les stratégies peuvent être affectées à des utilisateurs et [à des sites réseau.](cloud-voice-network-settings.md)

Pour les utilisateurs, vous pouvez utiliser la stratégie globale (à l’échelle de l’organisation par défaut) ou créer et attribuer des stratégies personnalisées. Les utilisateurs obtiennent automatiquement la stratégie globale, sauf si vous créez et attribuez une stratégie personnalisée. N’oubliez pas que vous pouvez modifier les paramètres de la stratégie globale, mais que vous ne pouvez pas le renommer ou le supprimer. Pour les sites réseau, vous créez et attribuez des stratégies personnalisées.

Si vous avez affecté une stratégie d’appel d’urgence à un site réseau et à un utilisateur, et si cet utilisateur se trouve sur ce site réseau, la stratégie attribuée au site réseau remplace la stratégie qui lui est affectée.

## <a name="create-a-custom-emergency-calling-policy"></a>Créer une stratégie personnalisée d’appels d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le navigation gauche du Centre d’administration Microsoft Teams, allez sur Stratégies d’urgence vocale, puis cliquez sur   >   **l’onglet Stratégies d’appel.**
2. Cliquez sur **Ajouter**.
3. Entrez un nom pour votre stratégie, ainsi qu’une description.
4. Définissez la façon dont vous voulez avertir les personnes de votre organisation, généralement le service de sécurité, lorsqu’un appel d’urgence est effectué. Pour ce faire, sous **Mode de notification,** sélectionnez l’une des sélections suivantes :
    - **Envoyer une notification uniquement**: un message de conversation Teams est envoyé aux utilisateurs et groupes que vous spécifiez.
    - Conférence en mode muet impossible d’activer le son : un message de conversation Teams est envoyé aux utilisateurs et aux groupes que vous spécifiez et ils peuvent écouter (mais ne peuvent pas participer) à la conversation entre l’appelant et l’opérateurCONFÉRENCE.
    - Conférence en mode muet, mais possibilité d’activer le son : un message de conversation Teams est envoyé aux utilisateurs et aux groupes que vous spécifiez, et ils peuvent activer le son pour écouter l’appelant et participer à la conversation entre l’appelant et l’opérateur CENTRE.PUBLIC.
5.  Si vous avez sélectionné l’un des modes de **notification** muet, dans la zone Numéros pour appeler les **notifications** d’appel d’urgence, vous pouvez entrer le numéro de téléphone PSTN d’un utilisateur ou d’un groupe pour appeler et rejoindre l’appel d’urgence. Par exemple, entrez le numéro du service de sécurité de votre organisation, qui recevra un appel lorsqu’un appel d’urgence sera effectué et pourra ensuite écouter l’appel. Le téléphone PSTN ne peut pas être réactive même lorsque le mode est réglé sur Conférence en mode Muet, mais est en mesure **d’activer le son.**
6. Recherchez et sélectionnez un ou plusieurs utilisateurs ou groupes, tels que le service de sécurité de votre organisation, pour être informé lorsqu’un appel d’urgence est effectué.  La notification peut être envoyée à des adresses e-mail d’utilisateurs, de groupes de distribution et de groupes de sécurité. Un maximum de 50 utilisateurs peuvent en être informés.
7. Cliquez sur **Appliquer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [New-CsTeamsEmergencyCallingPolicy.](/powershell/module/skype/new-csteamsemergencycallingpolicy)

## <a name="edit-an-emergency-calling-policy"></a>Modifier une stratégie d’appel d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez.

1. Dans le navigation gauche du Centre d’administration Microsoft Teams, allez sur Stratégies d’urgence vocale, puis cliquez sur   >   **l’onglet Stratégies d’appel.**
2. Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis cliquez sur **Modifier**.
3. A apporter les modifications de votre souhaitez, puis cliquez sur **Appliquer.**

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [Set-CsTeamsEmergencyCallingPolicy.](/powershell/module/skype/set-csteamsemergencycallingpolicy)

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Affecter une stratégie d’appel d’urgence personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Voir aussi [Grant-CsTeamsEmergencyCallingPolicy.](/powershell/module/skype/grant-csteamsemergencycallingpolicy)

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>Affecter une stratégie personnalisée d’appel d’urgence à un site réseau

Utilisez la [cmdlet Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) pour affecter une stratégie d’appel d’urgence à un site réseau.

L’exemple suivant montre comment affecter une stratégie appelée Stratégie d’appel d’urgence de Contoso 1 au site Site1.

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>Rubriques connexes

[Gérer les stratégies de routage d’appel d’urgence dans Teams](manage-emergency-call-routing-policies.md)

[Présentation de Teams PowerShell](teams-powershell-overview.md)

[Attribuer des stratégies à vos utilisateurs](assign-policies.md)