---
title: Routage direct-connexion de périphériques analogiques
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Lisez cet article pour découvrir comment utiliser des appareils analogiques avec le routage direct du système Microsoft Phone.
ms.openlocfilehash: 45128b8806644e4399687787bcce251ccb807d85
ms.sourcegitcommit: a6425a536746e129ab8bda3984b5ae63fb316192
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42558514"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a>Utilisation de périphériques analogiques avec le routage direct du système téléphonique

Cet article décrit comment utiliser les appareils analogiques avec le routage direct du système téléphonique. Pour connecter des appareils analogiques au routage direct, vous devez utiliser une carte de téléphonie analogique (ATA), et cette carte doit être prise en charge par le fournisseur de services de technologie SBC. 

Lorsqu’un utilisateur effectue un appel à partir d’un appareil analogique, le signalement et le flux multimédia sont acheminés par l’intermédiaire de la carte de téléphonie analogique (ATA) vers l’SBC.  La SBC envoie l’appel à un point de terminaison Microsoft teams ou au réseau téléphonique public commuté (RTC) en fonction de la table de routage interne.  Lorsqu’un appareil effectue un appel, l’itinéraire qu’il utilise dépend des stratégies de routage créées pour l’appareil.

Dans le schéma suivant, le routage direct est configuré de façon à ce que toutes les équipes appellent et à partir des numéros compris entre + 1425 4XX XX XX et + 1425 5XX XX XX doivent prendre l’itinéraire rouge (ligne pointillée), et n’importe quel numéro de téléphone compris entre + 1425 4XX XX XX et tout autre numéro sauf  plage de chiffres + 1425 5XX XX XX doit prendre la direction bleue (ligne pleine). 

![Diagramme montrant une configuration de routage directe](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a>Exemple : configuration de l’utilisation de périphériques analogiques avec le routage direct

Pour configurer l’utilisation de périphériques analogiques avec le routage direct, vous devez connecter la carte de téléphonie analogique à l’SBC et configurer l’SBC pour qu’il fonctionne avec le routage direct. 

Cet exemple vous guide à travers les étapes suivantes :

1. Connectez l’SBC au routage direct.
2. Créer une utilisation PSTN ;
3. Créez un itinéraire et associez-le à l’utilisation de PSTN.
4. Attribuez l’itinéraire de la voix à l’utilisation RTC.
5. Activez l’utilisateur en ligne.
6. Affectez la stratégie d’itinéraire vocale à l’utilisateur.
7. Créer un itinéraire vocal pour un appareil analogique.

Pour plus d’informations sur la connexion d’un disque ATA à un SBC et sur la configuration de l’SBC, voir le Guide de configuration de votre fabricant SBC :
- [Documentation de configuration de AudioCodes](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)
- [Documentation de configuration du ruban](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a>Étape 1.  Connecter l’SBC au routage direct

La commande suivante configure la connexion SBC comme suit :

- Nom de domaine complet sbc.contoso.com
- Port de signalisation 5068
- Mode de contournement de média
- Informations de l’historique des appels transmises à l’SBC-
- En-tête P-assertion-Identity (PAI) transmis en même temps que l’appel 

```
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a>Étape 2 : créer une utilisation PSTN 

La commande Next crée une utilisation PSTN vide. Les utilisations RTC en ligne sont des valeurs de chaîne utilisées pour l’autorisation d’appels. Une utilisation RTC en ligne relie une politique vocale en ligne à un itinéraire. Dans cet exemple, la chaîne « Interop » est ajoutée à la liste actuelle des utilisations RTC disponibles. 

```
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a>Étape 3 : créez un itinéraire vocal et associez-le à l’utilisation de PSTN :

Cette commande crée un nouvel itinéraire vocal en ligne avec l’identité « Analog-Interop » pour la plage de numéros + 1425 XXX XX XX.  L’itinéraire vocal s’applique à une liste de passerelles en ligne sbc.contoso.com et associe l’itinéraire avec l' « interopérabilité » de l’utilisation RTC en ligne. Un itinéraire vocal inclut une expression régulière qui identifie les numéros de téléphone qui doivent être routés par le biais d’un itinéraire vocal donné :

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a>Étape 4 : affecter l’itinéraire vocal à l’utilisation RTC :

Cette commande crée une stratégie de routage vocale par utilisateur en utilisant l’identité « AnalogInteropPolicy ». Une utilisation RTC en ligne unique est affectée à cette stratégie : « interopérabilité ».

```
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a>Étape 5 : activer l’utilisateur en ligne

Cette commande modifie le compte d’utilisateur avec l’identité exampleuser@contoso.com. Dans ce cas, le compte est modifié de façon à activer voix entreprise, l’implémentation Microsoft de VoIP, avec la messagerie vocale activée et attribue le numéro + 14255000000 à cet utilisateur.  Cette commande doit être exécutée pour chaque utilisateur Teams (à l’exception des utilisateurs d’appareils ATA) dans le client de l’entreprise.

```
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a>Étape 6 : affecter la stratégie d’itinéraire vocale à un utilisateur

Cette commande affecte la stratégie de routage vocale AnalogInteropPolicy en ligne par utilisateur à l’utilisateur avec l’identité exampleuser@contoso.com.  Cette commande doit être exécutée pour chaque utilisateur Teams (à l’exception des utilisateurs d’appareils ATA) dans le client de l’entreprise.

```
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a>Étape 7 : créer un itinéraire vocal pour un appareil analogique

Cette commande crée un itinéraire vocal en ligne avec identité « Analog-Interop » pour le numéro de série + 1425 4XX XX XX applicable à une liste de passerelles sbc.contoso.com et l’associe à l’utilisation RTC en ligne.  Cette commande doit être exécutée pour chaque appareil analogique dont le modèle de numéro de téléphone est approprié. Par ailleurs, il est possible d’utiliser un modèle de nombre approprié pour les appareils analogiques lorsque vous configurez l’itinéraire vocal en ligne au cours de l’une des étapes précédentes.

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a>Inconvénients

- Sauf indication contraire, un dispositif analogique est un appareil qui peut envoyer des chiffres DTMF pour effectuer un appel. Par exemple, les téléphones analogiques, les télécopieurs et les recharges du temps.
- Les téléphones analogiques connectés à un disque ATA ne peuvent pas être recherchés par Teams. Les utilisateurs d’équipes doivent entrer manuellement le numéro de téléphone associé à l’appareil pour appeler cet appareil.  
 

## <a name="see-also"></a>Voir aussi

[Planifier le routage direct](direct-routing-plan.md)

[Configurer le routage direct](direct-routing-configure.md)
