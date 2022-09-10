---
title: Conférence sur le réseau pour l’audioconférence
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Les éléments suivants décrivent le réseau pour l’audioconférence.
ms.openlocfilehash: 56e2addc3b924d7d73df7475ad217a999dc0aca0
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641875"
---
# <a name="on-network-conferencing-for-audio-conferencing"></a>Conférence sur le réseau pour l’audioconférence

La conférence sur le réseau permet aux organisations d’envoyer des appels audioconférence entrants et sortants à des numéros de rendez-vous Microsoft via le routage direct. Cette fonctionnalité n’est pas destinée à étendre la prise en charge de l’audioconférence à des numéros de connexion tiers. La conférence sur le réseau n’est pas prise en charge si elle est utilisée pour acheminer les appels entrants vers le service d’audioconférence par le biais de numéros de téléphone entrants tiers ou d’appels sortants vers le rtc à partir de Microsoft Audio Conferencing Bridge.

Cet article décrit les prérequis et les étapes de configuration nécessaires pour activer la conférence sur le réseau pour votre organisation.

> [!IMPORTANT]
> La conférence sur le réseau ne doit PAS être déployée avec n’importe quel équipement de téléphonie en Inde.

## <a name="prerequisites"></a>Conditions préalables

Avant de configurer la conférence sur le réseau, assurez-vous que votre organisation répond aux conditions préalables suivantes :

- Vérifiez que tous les utilisateurs de votre organisation qui sont activés ou seront activés pour l’audioconférence utilisent Teams pour toutes les réunions. Le routage des appels audioconférence entrants et sortants via la conférence sur le réseau est pris en charge uniquement pour les réunions Teams.

- Attribuez des licences d’audioconférence à tous les utilisateurs qui utiliseront la conférence sur le réseau.

- Configurez le service d’audioconférence. Pour plus d’informations, consultez [Configurer l’audioconférence pour Microsoft Teams](set-up-audio-conferencing-in-teams.md).

- Configurez votre contrôleur de frontière de session (SBC) pour le routage direct. Pour plus d’informations, consultez [Planifier le routage direct](direct-routing-plan.md) et [configurer le routage direct](direct-routing-configure.md).

  Si vous configurez le routage direct uniquement pour les besoins de l’audioconférence, vous n’avez besoin que de l’étape 1 : Connecter votre SBC pour la conférence sur le réseau.

## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>Activer le routage des appels entrants à l’audioconférence Microsoft via le routage direct

Pour acheminer les appels rendez-vous effectués par vos utilisateurs locaux vers le service d’audioconférence par le biais du routage direct, vous devez configurer les règles de routage appropriées pour vos SBC et les pbX (Private Branch Exchange).

Vous devez configurer l’équipement de téléphonie de vos sites pour acheminer les appels vers n’importe quel numéro de service du pont de conférence de votre organisation via une jonction de routage direct.

Vous trouverez les numéros de service dans le Centre d’administration Teams sous **Meetings -> Conferencing Bridges** ou à l’aide de l’applet de commande Teams PowerShell Get-CsOnlineDialInConferencingBridge. Pour plus d’informations, consultez la liste des [numéros d’audioconférence dans Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).

> [!NOTE]
> Cette fonctionnalité n’est pas disponible pour les utilisateurs disposant de la licence d’audioconférence à la minute.

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>Activer le routage des appels sortants de réunion Teams via le routage direct

Les appels sortants de réunion Teams sont lancés à partir d’une réunion de votre organisation vers des numéros RTC, y compris des appels par appel et des appels pour amener de nouveaux participants à une réunion.

Pour activer le routage rendez-vous de réunion Teams via le routage direct vers les utilisateurs sur le réseau, vous devez créer et attribuer une stratégie de routage d’audioconférence appelée « OnlineAudioConferencingRoutingPolicy ».

La stratégie OnlineAudioConferencingRoutingPolicy est équivalente à la stratégie CsOnlineVoiceRoutingPolicy pour les appels RTC 1:1 via le routage direct. La stratégie OnlineAudioConferencingRoutingPolicy peut être gérée à l’aide des applets de commande suivantes :

- New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

Pour plus d’informations sur le routage pour le routage direct, consultez [Configurer le routage vocal pour le routage direct](direct-routing-voice-routing.md).

Pour activer le routage des appels de rendez-vous de réunion via le routage direct, vous devez :

- Configurer des stratégies de routage d’audioconférence
- Configurer le routage sur l’équipement de téléphonie de votre organisation
- (Facultatif) Configurer un plan de numérotation

Les appels sortants des réunions Teams proviennent du numéro de service par défaut sur le pont de conférence. Pour plus d’informations sur le numéro de service par défaut de votre pont d’audioconférence, consultez [Modifier les numéros de téléphone sur votre pont d’audioconférence](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

### <a name="configure-audio-conferencing-routing-policies"></a>Configurer des stratégies de routage d’audioconférence

La stratégie de routage d’audioconférence OnlineAudioConferencingRoutingPolicy détermine les appels de rendez-vous de réunion routés vers les jonctions de routage direct. Si vous êtes familiarisé avec la stratégie CsOnlineVoiceRoutingPolicy, cette stratégie fonctionne de façon très similaire.

Les étapes suivantes sont nécessaires pour configurer les stratégies de routage de l’audioconférence :

1. Créer des utilisations RTC
1. Configurer des itinéraires vocaux
1. Créer des stratégies de routage vocal d’audioconférence
1. Affecter une stratégie à vos utilisateurs

#### <a name="create-pstn-usages"></a>Créer des utilisations RTC

Les utilisations RTC sont des collections d’itinéraires vocaux. Lorsqu’un appel sortant est lancé à partir de la réunion d’un organisateur donné, les itinéraires vocaux sont utilisés pour déterminer le chemin de routage de l’appel en fonction des utilisations RTC associées à l’utilisateur via la stratégie de routage vocal de l’utilisateur.

Vous pouvez créer une utilisation RTC à l’aide de l’applet de commande « Set-CsOnlinePstnUsage ». Par exemple :

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>Configurer des itinéraires vocaux

Les itinéraires vocaux déterminent la passerelle RTC qui doit être utilisée pour acheminer un appel en fonction du numéro de téléphone composé à partir d’une réunion Teams. Les itinéraires vocaux déterminent la passerelle RTC qui doit être utilisée pour acheminer un appel donné en mettant en correspondance le numéro de téléphone composé à partir d’une réunion Teams avec un modèle d’expression régulière. Lors de la création d’un itinéraire vocal, l’itinéraire doit être associé à une ou plusieurs utilisations RTC.

Vous pouvez créer un itinéraire vocal et définir l’expression régulière et les passerelles à associer à l’itinéraire vocal à l’aide de l’applet de commande « New-CsOnlineVoiceRoute ». Par exemple :

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>Créer des stratégies de routage vocal d’audioconférence

Les stratégies de routage vocal d’audioconférence déterminent les itinéraires possibles qui peuvent être utilisés pour acheminer un appel provenant des réunions d’un organisateur en fonction du numéro de téléphone cible de l’appel sortant de la réunion. Les stratégies de routage audioconférence vocale sont associées à une ou plusieurs utilisations RTC, qui à leur tour déterminent les itinéraires possibles qui seront tentés d’être utilisés pour les appels sortants de réunion des organisateurs associés à la stratégie.

Vous pouvez créer une stratégie de routage vocal d’audioconférence à l’aide de l’applet de commande « New- CsOnlineAudioConferencingRoutingPolicy ». Par exemple :

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

Une fois la stratégie affectée à un utilisateur et lorsqu’un appel de numérotation de réunion est lancé à partir d’une des réunions de l’utilisateur, les itinéraires vocaux dans les utilisations RTC associées à l’organisateur via la stratégie de routage vocal de l’utilisateur sont évalués. Si la destination de l’appel sortant de la réunion correspond à une expression régulière dans l’un des itinéraires vocaux associés à l’organisateur, l’appel de numérotation de réunion est routé vers la passerelle RTC définie dans l’itinéraire vocal. Si la destination de l’appel sortant de la réunion ne correspond à aucun des itinéraires vocaux associés à l’organisateur, l’appel sortant de la réunion est routée par Microsoft.

#### <a name="assign-a-policy-to-your-users"></a>Affecter une stratégie à vos utilisateurs

Une fois les stratégies de routage d’audioconférence définies, vous pouvez désormais les affecter aux utilisateurs. Une fois les stratégies affectées, les appels de rendez-vous de réunion sont évalués par rapport à celui-ci pour déterminer leur chemin d’accès de routage. Les stratégies de routage de l’audioconférence sont toujours évaluées en fonction de l’organisateur de la réunion, indépendamment de l’utilisateur de la réunion qui lance un appel sortant de réunion.

Vous pouvez affecter une stratégie de routage vocal d’audioconférence à un utilisateur à l’aide de l’applet de commande « Grant-CsOnlineAudioConferencingRoutingPolicy ». Par exemple :

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1"
```

### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>Configurer le routage sur l’équipement de téléphonie de votre organisation

Sur l’équipement téléphonique de votre organisation, vous devez vous assurer que les appels de rendez-vous de réunion acheminés via le routage direct sont acheminés vers la destination réseau prévue.

### <a name="optional-configure-a-dial-plan"></a>(Facultatif) Configurer un plan de numérotation

Un plan de numérotation est un ensemble de règles de normalisation qui traduisent les numéros de téléphone composés par un utilisateur individuel dans un autre format (généralement E.164) à des fins d’autorisation d’appel et de routage des appels.

Par défaut, les utilisateurs Teams peuvent composer des numéros RTC au format E.164, c’est-à-dire +\<country code\>\<number\>. Toutefois, les plans de numérotation peuvent être utilisés pour permettre aux utilisateurs de composer des numéros de téléphone dans d’autres formats, par exemple des extensions à 4 chiffres.

Si vous souhaitez activer la numérotation basée sur les extensions via la conférence sur le réseau, vous pouvez configurer des plans de numérotation pour qu’ils correspondent au modèle de numérotation d’extension aux plages de numéros de téléphone du numéro de téléphone de votre organisation. Pour configurer des plans de numérotation, consultez [Créer et gérer des plans de numérotation](create-and-manage-dial-plans.md).

## <a name="related-topics"></a>Rubriques connexes
