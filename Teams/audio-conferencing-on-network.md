---
title: Conférence sur réseau pour l’audioconférence
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Les suivantes décrivent le réseau pour l’audioconférence.
ms.openlocfilehash: c6820bade333b6672d00e4f52a361280c10c8771
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055664"
---
# <a name="on-network-conferencing-for-audio-conferencing"></a>Conférence sur réseau pour l’audioconférence

Les conférences sur réseau permettent aux organisations d’envoyer des appels d’audioconférence entrants et sortants à des numéros de connexion Microsoft par le biais d’un routage direct. Cette fonctionnalité n’est pas destinée à étendre la prise en charge de l’audioconférence à des numéros d’accès tiers. La fonction de conférence sur réseau n’est pas prise en charge si elle est utilisée pour router les appels entrants vers le service d’audioconférence par le biais de numéros de téléphone tiers ou d’appels sortants vers le réseau PSTN à partir du pont de conférence audio Microsoft.

Cet article décrit les conditions préalables et les étapes de configuration requises pour activer la conférence sur réseau pour votre organisation.

> [!IMPORTANT]
> La conférence sur réseau ne doit PAS être déployée avec n’importe quel équipement téléphonique en Inde.
  
## <a name="prerequisites"></a>Conditions préalables

Avant de configurer la conférence sur réseau, assurez-vous que votre organisation répond aux conditions préalables suivantes :

- Assurez-vous que tous les utilisateurs de votre organisation qui sont activés ou seront activés pour l’audioconférence utilisent des Teams pour toutes les réunions. Le routage des appels d’audioconférence entrants et sortants via la conférence réseau est pris en charge uniquement pour Teams réunions.

- Attribuez des licences d’audioconférence à tous les utilisateurs qui utiliseront la conférence sur réseau.

- Configurer le service d’audioconférence. Pour plus d’informations, [consultez Configurer l’audioconférence pour Microsoft Teams.](set-up-audio-conferencing-in-teams.md)

- Configurer votre contrôleur de session SBC (Session Border Controller) pour le routage direct. Pour plus d’informations, [voir Planifier le routage direct et](direct-routing-plan.md) Configurer le [routage direct.](direct-routing-configure.md)

  Si vous configurationnez le routage direct uniquement dans le cadre de l’audioconférence, vous devez seulement effectuer l'« étape 1 : Connecter SBC » pour les conférences réseau.
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>Activer le routage des appels d’accès vers l’audioconférence Microsoft par le biais d’un routage direct

Pour router les appels d’accès effectués par vos utilisateurs locaux vers le service d’audioconférence via un routage direct, vous devez configurer les règles de routage appropriées pour vos SBCs et vos Exchange privés (PBX).

Vous devez configurer l’équipement téléphonique de vos sites pour router les appels vers n’importe quel numéro de service du pont de conférence de votre organisation via une ligne de routage direct.

Vous trouverez les numéros de service dans le Centre d’administration Teams sous Réunions **-> Ponts** de conférence ou à l’aide de l’cmdlet PowerShell Skype Entreprise Online Get-CsOnlineDialInConferencingBridge. Pour plus d’informations, consultez la liste des numéros [d’audioconférence Microsoft Teams.](see-a-list-of-audio-conferencing-numbers-in-teams.md)

> [!NOTE]
> Cette fonctionnalité n’est pas disponible pour les utilisateurs titulaires d’une licence d’audioconférence à la minute.

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>Activer le routage des appels sortants Teams des réunions via un routage direct

Teams appels sortants de réunion sont lancés à partir d’une réunion de votre organisation vers des numéros PSTN, y compris les appels de participation et les appels pour amener de nouveaux participants à une réunion.

Pour activer Teams routage d’appels sortants de réunion via un routage direct vers des utilisateurs du réseau, vous devez créer et affecter une stratégie de routage audioconférence nommée « OnlineAudioConferencingRoutingPolicy ».

La stratégie OnlineAudioConferencingRoutingPolicy équivaut à la stratégie CsOnlineVoiceRoutingPolicy pour les appels PSTN 1:1 via un routage direct. La stratégie OnlineAudioConferencingRoutingPolicy peut être gérée à l’aide des cmdlets suivantes :

-   New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

Pour plus d’informations sur le routage pour le routage direct, voir [Configurer le routage vocal pour le routage direct.](direct-routing-voice-routing.md)

Pour permettre le routage des appels sortants de réunion via un routage direct, vous devez :

- Configurer les stratégies de routage de l’audioconférence
- Configurer le routage sur l’équipement téléphonique de votre organisation
- (Facultatif) Configurer un plan de numérotation

Les appels sortants des Teams sont issus du numéro de service par défaut sur le pont de conférence. Pour plus d’informations sur le numéro de service par défaut de votre pont d’audioconférence, consultez Modifier les numéros de téléphone de votre pont [d’audioconférence.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

### <a name="configure-audio-conferencing-routing-policies"></a>Configurer les stratégies de routage de l’audioconférence

La stratégie de routage de l’audioconférence OnlineAudioConferencingRoutingPolicy détermine les appels sortants de réunion acheminés vers des itinéraires de routage direct. Si vous êtes familiarisé avec la stratégie CsOnlineVoiceRoutingPolicy, cette stratégie fonctionne de façon très similaire.

Les étapes suivantes sont nécessaires pour configurer les stratégies de routage des audioconférences :

1. Créer des utilisations PSTN
1. Configurer les itinéraires vocables
1. Créer des stratégies de routage audioconférence
1. Affecter une stratégie à vos utilisateurs

#### <a name="create-pstn-usages"></a>Créer des utilisations PSTN

Les utilisations PSTN sont des collections d’itinéraires vocaux. Lorsqu’un appel sortant est lancé à partir de la réunion d’un organisateur donné, les itinéraires vocaux sont utilisés pour déterminer l’itinéraire de routage de l’appel en fonction des utilisations PSTN associées à l’utilisateur via la stratégie de routage vocale de l’utilisateur.

Vous pouvez créer une utilisation PSTN à l’aide de l’cmdlet « Set-CsOnlinePstnUsage ». Par exemple :

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>Configurer les itinéraires vocables

Les itinéraires vocux déterminent la passerelle PSTN à utiliser pour router un appel en fonction du numéro de téléphone qui est composé à partir d’Teams réunion. Les itinéraires vocables déterminent la passerelle PSTN qui doit être utilisée pour router un appel donné en faisant correspondre le numéro de téléphone composé à partir d’une réunion Teams avec un modèle de regex. Lors de la création d’un itinéraire vocal, l’itinéraire doit être associé à une ou plusieurs utilisations PSTN.

Vous pouvez créer un itinéraire vocal et définir les regex et passerelles à associer à l’itinéraire vocal à l’aide de l’cmdlet « New-CsOnlineVoiceRoute ». Par exemple :

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>Créer des stratégies de routage audioconférence

Les stratégies de routage audio de l’audioconférence déterminent les itinéraires possibles qui peuvent être utilisés pour router un appel en provenance des réunions d’un organisateur en fonction du numéro de téléphone cible de l’appel sortant de la réunion. Les stratégies de routage audio de l’audioconférence sont associées à une ou plusieurs utilisations PSTN, qui, à leur tour, déterminent les itinéraires possibles qui seront tentés d’être utilisés pour les appels sortants de réunion des organisateurs associés à la stratégie.

Vous pouvez créer une stratégie de routage audio de conférence audio à l’aide de l’cmdlet « New- CsOnlineAudioConferencingRoutingPolicy ». Par exemple :

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

Une fois la stratégie affectée à un utilisateur et lorsqu’un appel sortant de réunion est lancé à partir de l’une des réunions de l’utilisateur, les itinéraires vocaux dans les utilisations PSTN associés à l’organisateur via la stratégie de routage vocal de l’utilisateur sont évalués. Si la destination d’appel sortant de la réunion correspond à une connexion regex dans l’un des itinéraires vocaux associés à l’organisateur, l’appel sortant de la réunion est acheminé vers la passerelle PSTN définie dans l’itinéraire vocal. Si la destination d’appel sortant de la réunion ne correspond pas aux itinéraires vocux associés à l’organisateur, l’appel sortant de la réunion est acheminé par Microsoft.

#### <a name="assign-a-policy-to-your-users"></a>Affecter une stratégie à vos utilisateurs

Une fois les stratégies de routage d’audioconférence définies, vous pouvez les affecter aux utilisateurs. Une fois les stratégies affectées, les appels sortants de la réunion sont évalués par rapport à celui-ci afin de déterminer leur itinéraire de routage. Les stratégies de routage des audioconférences sont toujours évaluées sur la base de l’organisateur de la réunion, indépendamment de l’utilisateur qui déclenche un appel sortant de réunion.

Vous pouvez affecter une stratégie de routage audio de conférence audio à un utilisateur à l’aide de l’cmdlet « Grant-CsOnlineAudioConferencingRoutingPolicy ». Par exemple :

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```

### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>Configurer le routage sur l’équipement téléphonique de votre organisation

Sur l’équipement téléphonique de votre organisation, vous devez vous assurer que les appels sortants de la réunion acheminés via le routage direct sont acheminés vers la destination réseau prévue.

### <a name="optional-configure-a-dial-plan"></a>(Facultatif) Configurer un plan de numérotation

Un plan de numérotation est un ensemble de règles de normalisation qui traduisent les numéros de téléphone composés par un utilisateur individuel dans un autre format (généralement E.164) pour l’autorisation et le routage des appels.

Par défaut, Teams utilisateurs peuvent appeler des numéros PSTN au format E.164, c’est-à-dire + \<country code\> \<number\> . Toutefois, les plans de numérotation peuvent être utilisés pour permettre aux utilisateurs de composer des numéros de téléphone dans d’autres formats, par exemple des extensions à 4 chiffres.

Si vous souhaitez activer la numérotation basée sur un numéro de poste par le biais de conférences réseau, vous pouvez configurer des plans de numérotation pour qu’ils correspondent au modèle de numérotation de poste et aux plages de numéros de téléphone du numéro de téléphone de votre organisation. Pour configurer des plans de numérotation, voir [Créer et gérer des plans de numérotation.](create-and-manage-dial-plans.md)

## <a name="related-topics"></a>Sujets associés
