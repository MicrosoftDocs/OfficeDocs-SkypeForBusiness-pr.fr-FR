---
title: Routage direct - Connexion de périphériques analogiques
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Lisez cet article pour découvrir comment utiliser des périphériques analogiques avec Téléphone Microsoft routage direct de système informatique.
ms.openlocfilehash: 86875f7c4cf3206f673c652487e896adf91b1ce5
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766407"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a>Utilisation de dispositifs analogiques avec un Système téléphonique direct

Cet article décrit comment utiliser des périphériques analogiques avec un Système téléphonique direct. Pour connecter des périphériques analogiques au routage direct, vous devez utiliser un adaptateur téléphonique analogique (ATA), qui doit être pris en charge par le fournisseur de contrôleur de bordure de session certifié (SBC). 

Lorsqu’un utilisateur effectue un appel à partir d’un périphérique analogique, le trafic de signalisation et le trafic de médias circulent entre la carte téléphonique analogique (ATA) et le SBC.  Le SBC envoie l’appel à un point de terminaison Microsoft Teams public ou au réseau téléphonique commuté (RST) basé sur la table de routage interne.  Quand un appareil effectue un appel, l’itinéraire qu’il prend dépend des stratégies de routage créées pour l’appareil.

Dans le diagramme suivant, le routage direct est configuré de façon à ce que tout Teams appelant et provenant des numéros entre +1425 4XX XX XX et +1425 5XX XX XX doit suivre le itinéraire rouge (ligne en pointillés), et tout appel PSTN entre +1425 4XX XX XX et tout autre nombre à l’exception de la plage de numéros +1425 5XX XX XX doit prendre le itinéraire bleu (trait plein). 

> [!div class="mx-imgBorder"]
> ![Diagramme montrant la configuration du routage direct.](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a>Exemple : configuration de l’utilisation de dispositifs analogiques avec le routage direct

Pour configurer l’utilisation de dispositifs analogiques avec un routage direct, vous devez connecter la carte téléphonique analogique au SBC et configurer ce dernier pour qu’il fonctionne avec le routage direct. 

Cet exemple vous fait suivre les étapes suivantes :

1. Connecter le routage SBC vers direct.
2. Créez l’utilisation PSTN.
3. Créez un itinéraire vocal et associez-le à l’utilisation PSTN.
4. Affectez l’itinéraire vocal à l’utilisation PSTN.
5. Activez l’utilisateur en ligne.
6. Affectez la stratégie de route vocale à l’utilisateur.
7. Créez une route vocale pour un appareil analogique.

Pour plus d’informations sur la connexion d’un contrôle d’accès (ATA) à un SBC et la configuration de ce dernier, consultez votre guide de configuration de fabricant SBC :

- [Documentation sur la configuration de AudioCodes](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [Documentation sur la configuration du ruban](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)
- [Documentation sur la configuration d’Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a>Étape 1.  Connecter le routage SBC vers direct

La commande suivante configure la connexion SBC comme suit :

- Sbc.contoso.com de sbc.contoso.com
- Port de signalisation 5068
- Mode de dérivation média
- Informations de l’historique des appels transmis au dossier SBC-
- En-tête P-Ed-Identity (NT) transmis avec l’appel 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a>Étape 2 : créer l’utilisation PSTN 

La commande suivante crée une utilisation PSTN vide. Les utilisations PSTN en ligne sont des valeurs de chaîne utilisées pour l’autorisation d’appel. Une utilisation PSTN en ligne lie une stratégie vocale en ligne à un itinéraire. Cet exemple ajoute la chaîne « Interop » à la liste actuelle des utilisations PSTN disponibles. 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a>Étape 3 : créez un itinéraire vocal et associez-le à l’utilisation PSTN :

Cette commande crée une nouvelle route vocale en ligne avec l’identité « analogique-interop » pour la plage de nombres +1425 XXX XX XX.  L’itinéraire vocal est applicable à une liste de passerelles en sbc.contoso.com et associe l’itinéraire à une utilisation PSTN en ligne « Interop ». Une route vocale inclut une expression régulière qui identifie les numéros de téléphone qui seront acheminés via une route vocale donnée :

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7})$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a>Étape 4 : affecter la route vocale à l’utilisation PSTN :

Cette commande crée une stratégie de routage voix par utilisateur en ligne avec l’identité « AnalogInteropPolicy ». Cette stratégie n’a qu’une utilisation PSTN en ligne : « Interop ».

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a>Étape 5 : activer l’utilisateur en ligne

Cette commande modifie le compte d’utilisateur avec le groupe de exampleuser@contoso.com. Dans ce cas, le compte est modifié pour activer Voix Entreprise, implémentation Microsoft de VoIP, avec la messagerie vocale activée et affecte le numéro +1425500000 à cet utilisateur.  Cette commande doit être exécuté pour chaque Teams utilisateur (à l’exception des utilisateurs d’appareils ATA) dans le client de l’entreprise.

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a>Étape 6 : affecter la stratégie de route vocale à un utilisateur

Cette commande affecte la stratégie de routage vocal en ligne per-user AnalogInteropPolicy à l’utilisateur ayant le exampleuser@contoso.com.  Cette commande doit être exécuté pour chaque Teams utilisateur (à l’exception des utilisateurs d’appareils ATA) dans le client de l’entreprise.

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a>Étape 7 : créer une route vocale pour un appareil analogique

Cette commande crée un itinéraire vocal en ligne avec l’identité « analogique-interop » pour la plage de nombres +1425 4XX XX XX applicable à une liste de passerelles en ligne sbc.contoso.com et l’associe à l’utilisation PSTN en ligne « Interop ».  Cette commande doit être exécuté pour chaque appareil analogique ayant un modèle de numéro de téléphone approprié. Vous pouvez également utiliser un modèle de nombre approprié pour les dispositifs analogiques lors de la configuration de la route vocale en ligne au cours de l’une des étapes précédentes.

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6})$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a>Considérations

- Sauf indication contraire, un appareil analogique est tout appareil qui peut envoyer des chiffres DTMF pour passer un appel. Par exemple, des téléphones analogiques, des télécopieurs et des pages généraux.

- Les téléphones analogiques connectés à un ata ne peuvent pas faire l’objet d’Teams. Teams utilisateurs doivent entrer manuellement le numéro de téléphone associé à l’appareil pour appeler ce périphérique.  
 

## <a name="see-also"></a>Voir aussi

[Planifier le routage direct](direct-routing-plan.md)

[Configurer le routage direct](direct-routing-configure.md)
