---
title: Gérer les stratégies d’appel d’urgence dans Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment utiliser et gérer des stratégies d’appel d’urgence dans Microsoft Teams pour définir ce qui se passe lorsqu’un utilisateur Teams de votre organisation effectue un appel d’urgence.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 1d2dc0e2213f6294e2c596722a4f5ab49bec8487
ms.sourcegitcommit: eb0e754d7e2877f686021d3ab75b6d8d44db3a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/06/2023
ms.locfileid: "69727746"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Gérer les stratégies d’appel d’urgence dans Microsoft Teams

Si votre organisation utilise les forfaits d’appels Microsoft, Operator Connect, Teams Phone Mobile ou le routage direct comme [option de connectivité RTC](pstn-connectivity.md), vous pouvez utiliser des stratégies d’appel d’urgence dans Microsoft Teams pour définir ce qui se passe lorsqu’un utilisateur Teams de votre organisation passe un appel d’urgence.

Vous pouvez définir les personnes à notifier et la façon dont elles le sont lorsqu’un utilisateur auquel la stratégie est affectée appelle des services d’urgence. Par exemple, vous pouvez configurer des paramètres de stratégie pour avertir automatiquement le service de sécurité de votre organisation et lui faire écouter les appels d’urgence.  

Vous gérez les stratégies d’appel d’urgence en accédant à **Stratégies d’urgence** **vocale** >  dans le Centre d’administration Microsoft Teams ou en utilisant Windows PowerShell. Les stratégies peuvent être attribuées aux utilisateurs et aux [sites réseau](cloud-voice-network-settings.md).

Pour les utilisateurs, vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) ou créer et attribuer des stratégies personnalisées. Les utilisateurs obtiennent automatiquement la stratégie globale, sauf si vous créez et affectez une stratégie personnalisée. Gardez à l’esprit que vous pouvez modifier les paramètres de la stratégie globale, mais vous ne pouvez pas la renommer ou la supprimer. Pour les sites réseau, vous créez et affectez des stratégies personnalisées.

Si vous avez affecté une stratégie d’appel d’urgence à un site réseau et à un utilisateur, et si cet utilisateur se trouve sur ce site réseau, la stratégie affectée au site réseau remplace la stratégie attribuée à l’utilisateur.

## <a name="create-a-custom-emergency-calling-policy"></a>Créer une stratégie d’appel d’urgence personnalisée

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Stratégies d’urgence** **vocale** > , puis cliquez sur l’onglet **Stratégies d’appel**.

2. Cliquez sur **Ajouter**.

3. Entrez un nom pour votre stratégie, ainsi qu’une description.

4. Définissez le **mode de recherche d’emplacement externe** sur activé pour permettre à vos utilisateurs finaux de configurer leur adresse d’urgence lorsqu’ils travaillent à partir d’un emplacement réseau en dehors du réseau d’entreprise.

5. Définissez la façon dont vous souhaitez informer les personnes de votre organisation, généralement le bureau de sécurité, lorsqu’un appel d’urgence est effectué. Pour ce faire, sous **Mode notification**, sélectionnez l’une des options suivantes :

    - **Envoyer une notification uniquement** : un message de conversation Teams est envoyé aux utilisateurs et aux groupes que vous spécifiez.
    - **Conférence dans mais muet** : un message de conversation Teams est envoyé aux utilisateurs et groupes que vous spécifiez et ils peuvent écouter (mais pas participer) à la conversation entre l’appelant et l’opérateur PSAP.
    - **Conférence dans et ne sont pas activés** : un message de conversation Teams est envoyé aux utilisateurs et aux groupes que vous spécifiez et ils peuvent réactiver pour écouter et participer à la conversation entre l’appelant et l’opérateur PSAP.

6.  Définissez **l’exclusion de responsabilité du service d’urgence** pour afficher une bannière pour rappeler à vos utilisateurs finaux de confirmer leur emplacement d’urgence.

7.  Si vous avez sélectionné l’une des conférences dans les modes de notification **désactivés** , dans la zone **Numéros à composer pour les notifications d’appels d’urgence** , vous pouvez entrer un numéro de téléphone RTC d’un utilisateur ou d’un groupe pour appeler et rejoindre l’appel d’urgence. Par exemple, entrez le numéro du bureau de sécurité de votre organisation, qui recevra un appel lorsqu’un appel d’urgence sera effectué et pourra ensuite écouter l’appel. Le téléphone RTC ne peut pas être désactivé, même si le mode est défini **sur Conférence en sourdine, mais qu’il est en mesure de le réactiver**.

8. Définissez les personnes que vous souhaitez notifier lorsqu’un appel d’urgence est effectué, par exemple le personnel de votre bureau de sécurité. Vous pouvez définir une liste d’utilisateurs, de groupes de distribution ou de groupes de sécurité. Un maximum de 50 utilisateurs peuvent être avertis.

9. Cliquez sur **Appliquer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Consultez [New-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/new-csteamsemergencycallingpolicy).

## <a name="edit-an-emergency-calling-policy"></a>Modifier une stratégie d’appel d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

Vous pouvez modifier la stratégie globale ou les stratégies personnalisées que vous créez.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Stratégies d’urgence** **vocale** > , puis cliquez sur l’onglet **Stratégies d’appel**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis cliquez sur **Modifier**.
3. Apportez les modifications souhaitées, puis cliquez sur **Appliquer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Consultez [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Affecter une stratégie d’appel d’urgence personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Voir aussi [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>Affecter une stratégie d’appel d’urgence personnalisée à un site réseau

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

Vous pouvez affecter la stratégie globale ou les stratégies personnalisées que vous créez.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Emplacements** >  Topologie **réseau**, puis cliquez sur l’onglet **Sites réseau**.
2. Sélectionnez le site en cliquant à gauche du nom, puis cliquez sur **Modifier**.
3. Sous **Stratégie d’appel d’urgence**, sélectionnez la stratégie, puis cliquez sur **Enregistrer**.

### <a name="using-powershell"></a>Utiliser PowerShell
Utilisez l’applet [de commande Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) pour affecter une stratégie d’appel d’urgence à un site réseau.

L’exemple suivant montre comment affecter une stratégie appelée Contoso Emergency Calling Policy 1 au site Site1.

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>Rubriques connexes

[Gérer les stratégies de routage des appels d’urgence dans Teams](manage-emergency-call-routing-policies.md)

[Présentation de Teams PowerShell](teams-powershell-overview.md)

[Attribuer des stratégies à vos utilisateurs](policy-assignment-overview.md)
