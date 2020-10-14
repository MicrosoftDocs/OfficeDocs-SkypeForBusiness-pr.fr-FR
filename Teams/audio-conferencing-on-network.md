---
title: Audioconférence sur réseau pour les conférences audio
ms.author: crowe
author: CarolynRowe
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Les rubriques suivantes décrivent les fonctionnalités d’aperçu ouvert pour l’audioconférence sur le réseau.
ms.openlocfilehash: 18bd33281379efe7dd2e64019e20a66a2dbec920
ms.sourcegitcommit: c48a5aca37220ac6a797ac88b09cf80090b1b7df
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48444210"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a>Aperçu avant impression de l’audioconférence sur réseau pour les conférences audio

L’aperçu avant ouverture des conférences sur réseau est disponible pour tous les clients. Les conférences sur réseau permettent aux organisations d’envoyer des appels de conférence rendez-vous entrants et sortants vers des numéros de connexion Microsoft par le biais du routage direct. Cette fonctionnalité n’est pas destinée à étendre la prise en charge de l’audioconférence aux numéros d’accès tiers. L’audioconférence sur réseau n’est pas prise en charge si elle est utilisée pour diriger les appels entrants vers le service d’audioconférence via des numéros de téléphone tiers.

Cet article décrit les prérequis et les étapes de configuration nécessaires à l’activation de conférences sur le réseau pour votre organisation.

> [!IMPORTANT]
> L’audioconférence sur réseau ne doit pas être déployée avec un équipement de téléphonie en Inde.
  
## <a name="prerequisites"></a>Conditions préalables

Avant de configurer une conférence sur le réseau, assurez-vous que votre organisation remplit les conditions préalables suivantes : 

- Assurez-vous que tous les utilisateurs de votre organisation qui sont activés ou qui sont activés pour les conférences audio utilisent teams pour toutes les réunions. Le routage des appels de conférences audio entrants et sortants par le biais de conférences sur le réseau est uniquement pris en charge pour les réunions Teams.

- Attribuez des licences de conférence audio à tous les utilisateurs qui utiliseront une conférence sur le réseau.

- Configurez le service de conférence audio. Pour plus d’informations, consultez la rubrique [configurer l’audioconférence pour Microsoft teams](set-up-audio-conferencing-in-teams.md).

- Configurez votre contrôleur de bordure de session (SBC) pour le routage direct. Pour plus d’informations, voir [planifier le routage direct](direct-routing-plan.md) et [configurer le routage direct](direct-routing-configure.md). 

  Si vous configurez le routage direct uniquement dans le cadre de l’audioconférence, vous n’avez besoin que de l’étape 1 : connecter votre SBC» pour les conférences sur le réseau.
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>Activez le routage des appels de conférence rendez-vous dans l’audioconférence Microsoft via le routage direct. 

Pour acheminer les appels de conférence rendez-vous effectuées par vos utilisateurs locaux vers le service d’audioconférence par le biais du routage direct, vous devez configurer les règles de routage appropriées pour les PBX (Private Branch Exchange).

Vous devez configurer l’équipement de téléphonie de vos sites pour diriger les appels vers n’importe quel numéro de service du pont de conférence de votre organisation via un Trunk de routage direct.

Vous pouvez trouver les numéros de service dans le centre d’administration teams sous **réunions-> des ponts de conférence** ou en utilisant l’applet de cmdlet PowerShell de Skype entreprise Online Get-CsOnlineDialInConferencingBridge. Pour plus d’informations, reportez-vous à la liste des [numéros de conférence audio dans Microsoft teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).

> [!NOTE]
> Cette fonctionnalité n’est pas disponible pour les utilisateurs disposant d’une licence de conférence par minute.

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>Activez le routage des appels sortants de réunion à l’aide du routage direct.

Les appels sortants de réunion teams sont initiés à partir d’une réunion au sein de votre organisation aux numéros RTC, y compris les appels-moi et les appels pour amener de nouveaux participants à une réunion. 

Pour activer le routage de numérotation des réunions teams via le routage direct, vous devez créer et affecter une stratégie de routage de conférence audio nommée « OnlineAudioConferencingRoutingPolicy ». 

La stratégie OnlineAudioConferencingRoutingPolicy est équivalente au CsOnlineVoiceRoutingPolicy pour les appels RTC 1:1 via le routage direct. La stratégie OnlineAudioConferencingRoutingPolicy peut être gérée à l’aide des applets de commande suivantes :

-   New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

Pour plus d’informations sur le routage pour le routage direct, voir [configurer le routage vocal pour le routage direct](direct-routing-voice-routing.md).


Pour permettre le routage des appels sortants de réunion via le routage direct, vous devez : 

- Configuration des stratégies de routage de l’audioconférence
- Configurer le routage sur l’équipement de téléphonie de votre organisation
- Facultatif Configurer un plan de numérotation

Les appels sortants provenant des réunions teams proviennent du numéro de service par défaut sur le pont de conférence. Pour plus d’informations sur le numéro de service par défaut de votre pont de conférence audio, voir [modifier les numéros de téléphone de votre pont de conférence audio](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

### <a name="configure-audio-conferencing-routing-policies"></a>Configuration des stratégies de routage de l’audioconférence

Le OnlineAudioConferencingRoutingPolicy de stratégie de routage de l’audioconférence détermine les appels vers les appels sortants de réunion qui sont routés vers les Trunks de routage directs. Si vous connaissez bien la politique CsOnlineVoiceRoutingPolicy, cette politique fonctionne de manière très similaire.

Les étapes suivantes sont nécessaires pour configurer les stratégies de routage de l’audioconférence :
1.  Créer des utilisations PSTN
2.  Configurer des itinéraires vocaux
3.  Créer des stratégies de routage vocal pour les conférences audio
4.  Attribuer une stratégie à vos utilisateurs


#### <a name="create-pstn-usages"></a>Créer des utilisations PSTN

Les utilisations RTC sont des collections d’itinéraires vocaux. Lorsqu’un appel sortant est lancé depuis la réunion d’un organisateur donné, les itinéraires vocaux sont utilisés pour déterminer le chemin de routage de l’appel en fonction des utilisations RTC associées à l’utilisateur via la stratégie de routage vocale de l’utilisateur.

Vous pouvez créer une utilisation PSTN à l’aide de l’applet de commande « Set-CsOnlinePstnUsage ». Par exemple :

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>Configurer des itinéraires vocaux

Les itinéraires vocaux déterminent la passerelle RTC qui doit être utilisée pour acheminer les appels en fonction du numéro de téléphone composé par le biais d’une réunion Teams. Les itinéraires vocaux déterminent la passerelle RTC qui doit être utilisée pour acheminer un appel donné en correspondant au numéro de téléphone composé par une réunion teams à l’aide d’un modèle Regex. Lors de la création d’un itinéraire vocal, l’itinéraire doit être associé à une ou plusieurs utilisations PSTN.

Vous pouvez créer un itinéraire vocal et définir la fonction Regex et les passerelles à associer à l’itinéraire vocal à l’aide de l’applet de nouvelle applet de nouvelle-CsOnlineVoiceRoute. Par exemple :

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>Créer des stratégies de routage vocal pour les conférences audio

Les stratégies de routage vocal de l’audioconférence déterminent les itinéraires possibles qui peuvent être utilisés pour acheminer un appel provenant des réunions d’un organisateur en fonction du numéro de téléphone cible de l’appel sortant de la réunion. Les stratégies de routage de la voix de l’audioconférence sont associées à une ou plusieurs utilisations RTC, qui, à leur tour, déterminent les itinéraires possibles qui seront utilisés pour les appels sortants des organisateurs associés à la stratégie.

Vous pouvez créer une stratégie de routage téléphonique de l’audioconférence à l’aide de l’applet de nouvelle applet de nouvelle-CsOnlineAudioConferencingRoutingPolicy. Par exemple :

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

Lorsque la stratégie est attribuée à un utilisateur et qu’un appel sortant de réunion est lancé à partir de l’une des réunions de l’utilisateur, les itinéraires vocaux dans les utilisations RTC associées à l’organisateur via la stratégie de routage vocale de l’utilisateur sont évalués. Si la destination de l’appel sortant de la réunion correspond à une expression régulière dans l’un des itinéraires vocaux associés à l’organisateur, l’appel sortant de la réunion est acheminé vers la passerelle RTC définie dans l’itinéraire vocal. Si la destination des appels sortants de la réunion ne correspond à aucun des itinéraires vocaux associés à l’organisateur, l’appel sortant de la réunion est acheminé par Microsoft.

#### <a name="assign-a-policy-to-your-users"></a>Attribuer une stratégie à vos utilisateurs

Une fois les stratégies de routage de l’audioconférence définies, vous pouvez désormais les affecter aux utilisateurs. Une fois les stratégies affectées, les appels sortants de la réunion sont évalués par rapport à cette dernière pour déterminer leur chemin d’acheminement. Les stratégies de routage de l’audioconférence sont toujours évaluées en fonction de l’organisateur de la réunion, indépendamment de l’utilisateur participant à la réunion qui initie l’appel sortant à une réunion.

Vous pouvez assigner une stratégie de routage téléphonique de l’audioconférence à un utilisateur à l’aide de l’applet de cmdlet « Grant-CsOnlineAudioConferencingRoutingPolicy ». Par exemple :

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>Configurer le routage sur l’équipement de téléphonie de votre organisation

Sur l’équipement de téléphonie de votre organisation, vous devez vous assurer que les appels dial-out de réunion routés via le routage direct sont routés vers la destination sur le réseau prévue.


### <a name="optional-configure-a-dial-plan"></a>Facultatif Configurer un plan de numérotation

Un plan de numérotation est un ensemble de règles de normalisation qui permettent de traduire les numéros de téléphone numérotés d’un utilisateur individuel dans un autre format (généralement E. 164) à des fins d’autorisation d’appel et de routage des appels.

Par défaut, les utilisateurs de teams peuvent appeler des numéros RTC au format E. 164, c’est-à-dire + \<country code\> \<number\> . Toutefois, les plans de numérotation peuvent être utilisés pour permettre aux utilisateurs de composer des numéros de téléphone dans d’autres formats, par exemple des extensions à 4 chiffres.

Si vous souhaitez activer la numérotation basée sur une extension via l’audioconférence sur le réseau, vous pouvez configurer des plans de numérotation pour qu’ils correspondent au modèle de numérotation des numéros de téléphone de votre organisation. Pour configurer des plans de numérotation, reportez-vous à [créer et gérer des plans de numérotation](create-and-manage-dial-plans.md).


## <a name="known-issues-in-open-preview"></a>Problèmes connus dans l’aperçu ouvert

Vous trouverez ci-dessous une liste des problèmes connus actuellement présents dans la version d’évaluation d’une conférence sur le réseau. Microsoft travaille actuellement à la résolution de ces problèmes.

| Problème | Moyens |
| :--- | :--- |
| Les appels entrants avec des ID d’appelant anonyme/caché routés via l’audioconférence sur le réseau ne peuvent pas être connectés à la réunion. | Dans la mesure du possible, définissez une configuration dans votre système PBX ou SBC pour toujours envoyer un ID d’appelant pour les appels routés via une conférence sur le réseau.|
| Dans certains cas, le message de bienvenue qui est lu aux utilisateurs lorsqu’ils se connectent au service (« Bienvenue dans le service d’audioconférence ») est tronqué et les utilisateurs n’entendent pas le mot « Bienvenue ».| Il n’existe pas de solution de contournement pour ce problème pour le moment. |




## <a name="related-topics"></a>Rubriques connexes


