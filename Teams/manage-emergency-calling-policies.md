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
ms.openlocfilehash: 66ff287911a22de8b65ed356cd07833a2bbbb0ca
ms.sourcegitcommit: 4435ac0efcb95e4e5e1f21289e46761e79482ab5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2022
ms.locfileid: "65624098"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Gérer les stratégies d’appel d’urgence dans Microsoft Teams

Si votre organisation utilise les plans d’appel Microsoft, Operator Connect ou le routage direct comme option de [connectivité RTC](pstn-connectivity.md), vous pouvez utiliser des stratégies d’appel d’urgence dans Microsoft Teams pour définir ce qui se passe lorsqu’un utilisateur Teams de votre organisation effectue un appel d’urgence.

Vous pouvez définir les personnes à notifier et la façon dont elles sont averties lorsqu’un utilisateur auquel la stratégie est affectée appelle des services d’urgence. Par exemple, vous pouvez configurer les paramètres de stratégie pour informer automatiquement le bureau de sécurité de votre organisation et lui demander d’écouter les appels d’urgence.  

Vous gérez les stratégies d’appel d’urgence en accédant aux **stratégies VoiceEmergency**  >  dans le centre d’administration Microsoft Teams ou en utilisant Windows PowerShell. Les stratégies peuvent être affectées aux utilisateurs et aux [sites réseau](cloud-voice-network-settings.md).

Pour les utilisateurs, vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) ou créer et affecter des stratégies personnalisées. Les utilisateurs obtiennent automatiquement la stratégie globale, sauf si vous créez et affectez une stratégie personnalisée. N’oubliez pas que vous pouvez modifier les paramètres de la stratégie globale, mais que vous ne pouvez pas les renommer ou les supprimer. Pour les sites réseau, vous créez et attribuez des stratégies personnalisées.

Si vous avez affecté une stratégie d’appel d’urgence à un site réseau et à un utilisateur et si cet utilisateur se trouve sur ce site réseau, la stratégie affectée au site réseau remplace la stratégie affectée à l’utilisateur.

## <a name="create-a-custom-emergency-calling-policy"></a>Créer une stratégie d’appel d’urgence personnalisée

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez aux **stratégies VoiceEmergency** > , puis cliquez sur l’onglet **Stratégies d’appel**.
2. Cliquez sur **Ajouter**.
3. Entrez un nom pour votre stratégie, ainsi qu’une description.
4. Définissez le **mode recherche d’emplacement externe** sur activé pour permettre à vos utilisateurs finaux de configurer leur adresse d’urgence lorsqu’ils travaillent à partir d’un emplacement réseau en dehors du réseau d’entreprise.
5. Définissez la façon dont vous souhaitez informer les personnes de votre organisation, généralement le bureau de sécurité, lorsqu’un appel d’urgence est effectué. Pour ce faire, en **mode Notification**, sélectionnez l’une des options suivantes :
    - **Envoyer une notification uniquement** : un message de conversation Teams est envoyé aux utilisateurs et aux groupes que vous spécifiez.
    - **Téléconférence désactivée et impossible de désactiver le son** : un message de conversation Teams est envoyé aux utilisateurs et groupes que vous spécifiez et ils peuvent écouter (mais pas participer) à la conversation entre l’appelant et l’opérateur PSAP.
    - **Téléconférence en mode muet, mais capable de désactiver le son** : un message de conversation Teams est envoyé aux utilisateurs et groupes que vous spécifiez et ils peuvent désactiver le son pour écouter et participer à la conversation entre l’appelant et l’opérateur PSAP.
5.  Définissez l’exclusion de responsabilité du **service d’urgence** pour afficher une bannière pour rappeler à vos utilisateurs finaux de confirmer leur emplacement d’urgence.
6.  Si vous avez sélectionné l’une des **conférences en** mode de notification désactivée, dans la zone **Numéros à composer pour les notifications d’appels d’urgence** , vous pouvez entrer un numéro de téléphone RTC d’un utilisateur ou d’un groupe pour appeler et rejoindre l’appel d’urgence. Par exemple, entrez le numéro du bureau de sécurité de votre organisation, qui recevra un appel lorsqu’un appel d’urgence sera effectué, puis pourra écouter l’appel. Le téléphone RTC ne peut pas être désactivé même lorsque le mode est défini sur **Conferenced en mode désactivé, mais qu’il est en mesure de désactiver le son**.
7. Recherchez et sélectionnez un ou plusieurs utilisateurs ou groupes, tels que le bureau de sécurité de votre organisation, pour les avertir lorsqu’un appel d’urgence est effectué.  La notification peut être envoyée aux adresses e-mail des utilisateurs, des groupes de distribution et des groupes de sécurité. Un maximum de 50 utilisateurs peuvent être avertis.
8. Cliquez sur **Appliquer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [New-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/new-csteamsemergencycallingpolicy).

## <a name="edit-an-emergency-calling-policy"></a>Modifier une stratégie d’appel d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

Vous pouvez modifier la stratégie globale ou les stratégies personnalisées que vous créez.

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez aux **stratégies VoiceEmergency** > , puis cliquez sur l’onglet **Stratégies d’appel**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis cliquez sur **Modifier**.
3. Apportez les modifications **souhaitées**, puis cliquez sur Appliquer.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Affecter une stratégie d’appel d’urgence personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Voir aussi [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>Affecter une stratégie d’appel d’urgence personnalisée à un site réseau

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

Vous pouvez affecter la stratégie globale ou les stratégies personnalisées que vous créez.

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez à la **topologie** **LocationsNetwork** > , puis cliquez sur l’onglet **Sites réseau**.
2. Sélectionnez le site en cliquant à gauche du nom, puis cliquez sur **Modifier**.
3. Sous Stratégie **d’appel d’urgence**, sélectionnez la stratégie, puis cliquez sur **Enregistrer**.

### <a name="using-powershell"></a>Utiliser PowerShell
Utilisez l’applet [de commande Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) pour affecter une stratégie d’appel d’urgence à un site réseau.

L’exemple suivant montre comment affecter une stratégie appelée Contoso Emergency Calling Policy 1 au site Site1.

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>Voir aussi

[Gérer les stratégies de routage des appels d’urgence dans Teams](manage-emergency-call-routing-policies.md)

[Présentation de Teams PowerShell](teams-powershell-overview.md)

[Attribuer des stratégies à vos utilisateurs](policy-assignment-overview.md)
