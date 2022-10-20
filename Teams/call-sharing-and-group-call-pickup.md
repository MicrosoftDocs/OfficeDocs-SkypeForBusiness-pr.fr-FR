---
title: Partage d’appel et prise d’appel de groupe
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 02/19/2019
ms.reviewer: jenstr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: Le partage d’appels et la prise en charge des appels de groupe dans Microsoft Teams permettent aux utilisateurs de partager des appels entrants avec des collègues afin que les appels puissent être capturés lorsque l’utilisateur n’est pas disponible.
ms.openlocfilehash: 420378ce6d75523bf51b18c17e733d13a76ad877
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68613846"
---
# <a name="call-sharing-and-group-call-pickup"></a>Partage d’appel et prise d’appel de groupe

Les fonctionnalités de partage d’appels et de prise en charge des appels de groupe de Microsoft Teams permettent aux utilisateurs de partager leurs appels entrants avec des collègues afin que les collègues puissent répondre aux appels qui se produisent lorsque l’utilisateur n’est pas disponible.

La prise en charge des appels de groupe est moins perturbatrice pour les destinataires que les autres formes de partage d’appels, car les utilisateurs peuvent configurer la façon dont ils souhaitent être avertis d’un appel partagé entrant et décider s’ils doivent y répondre. L’ordre dans lequel les membres du groupe d’appels sont avertis de l’appel entrant peut être spécifié comme simultané ou dans l’ordre (avec 5 membres ou moins).

> [!IMPORTANT]
> Les utilisateurs, le propriétaire du groupe d’appels et les membres du groupe d’appels doivent être en mode de déploiement Teams uniquement. Pour plus d’informations sur les modes de déploiement Teams, consultez [Comprendre Microsoft Teams et Skype Entreprise coexistence et interopérabilité](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

## <a name="license-required"></a>Licence requise

Une licence système Téléphonie Microsoft Teams doit être attribuée aux utilisateurs pour configurer et utiliser le partage d’appels et la prise d’appel de groupe. Pour plus d’informations sur le modèle de licence, consultez ce [que vous obtenez avec le système téléphonique](/MicrosoftTeams/here-s-what-you-get-with-phone-system).

## <a name="limitations"></a>Limites

Un utilisateur ne peut être propriétaire que d’un seul groupe d’appels. Chaque groupe d’appels configuré peut comporter un maximum de 25 utilisateurs ou 32 768 caractères. Un utilisateur peut être membre d’un maximum de 25 groupes d’appels.

Notez que les appareils mobiles ne seront avertis que s’ils sont définis pour la bannière et la sonnerie.

## <a name="enable-the-use-of-group-call-pickup"></a>Activer l’utilisation de la prise d’appel de groupe

Vous activez les groupes d’appels en configurant le paramètre **TeamsCallingPolicy AllowCallGroups** pour un utilisateur. Vous pouvez utiliser le Centre d’administration Teams ou PowerShell. Lorsqu’il est activé, l’utilisateur peut configurer ses groupes d’appels dans le client Teams. 

Important : lorsque vous désactivez les groupes d’appels pour les utilisateurs, vous devez nettoyer les relations de groupe d’appels pour les utilisateurs dans le Centre d’administration Teams afin d’éviter un routage d’appel incorrect. 

## <a name="use-teams-admin-center"></a>Utiliser le Centre d’administration Teams

Pour configurer la prise d’appel de groupe pour les utilisateurs à l’aide du Centre d’administration Teams, consultez [Configurer les paramètres d’appel pour vos utilisateurs](/MicrosoftTeams/user-call-settings).

## <a name="use-powershell"></a>Utiliser PowerShell

Pour configurer des groupes d’appels pour les utilisateurs, utilisez les applets de commande du module Teams PowerShell suivantes :

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings)

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings)

### <a name="examples"></a>Exemples

L’exemple suivant crée un groupe d’appels pour user1@contoso.com avec les membres user2@contoso.com et user3@contoso.com, et définit le transfert d’appel immédiat au groupe d’appels pour user1@contoso.com :

```powershell
$cgm = @("sip:user2@contoso.com","sip:user3@contoso.com")
Set-CsUserCallingSettings -Identity user1@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

L’exemple suivant montre comment mettre à jour le groupe d’appels de user1@contoso.com pour ajouter user5@contoso.com et supprimer user6@contoso.com :

```powershell
$ucs = Get-CsUserCallingSettings -Identity user1@contoso.com
$cgt = {$ucs.CallGroupTargets}.Invoke()
$cgt.Add("sip:user5@contoso.com")
$cgt.Remove("sip:user6@contoso.com")
Set-CsUserCallingSettings -Identity user1@contoso.com -CallGroupOrder $ucs.CallGroupOrder -CallGroupTargets $cgt
```

## <a name="more-information"></a>Plus d’informations

[Transfert d’appel et sonnerie simultanée dans Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)

[Stratégie d’appel Teams](/MicrosoftTeams/teams-calling-policy)

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)
