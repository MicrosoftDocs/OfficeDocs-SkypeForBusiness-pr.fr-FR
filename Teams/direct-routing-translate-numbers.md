---
title: Traduire des numéros de téléphone pour le routage direct
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Apprenez à configurer le routage direct du système Microsoft Phone.
ms.openlocfilehash: 545d6a77fd9b3ee0462437b5b710d1d4eb782138
ms.sourcegitcommit: c8b5d4dd70d183f7ca480fb735a19290a3457b30
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/08/2020
ms.locfileid: "45077649"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>Traduire des numéros de téléphone dans un autre format

Cet article décrit comment traduire des numéros pour les appels sortants et entrants vers une autre mise en forme.  Pour configurer le routage direct, vous devez procéder comme suit :

- Étape 1. [Connecter l’SBC avec un système Microsoft Phone et valider la connexion](direct-routing-connect-the-sbc.md) 
- Étape 2. [Permettre aux utilisateurs d’utiliser le routage direct, les appels vocaux et la messagerie vocale](direct-routing-enable-users.md)   
- Étape 3. [Configurer le routage de la voix](direct-routing-voice-routing.md)
- **Étape 4. Traduire des numéros dans un autre format** (cet article)

Pour plus d’informations sur la procédure de configuration du routage direct, voir [configurer le routage direct](direct-routing-configure.md).

Il arrive que les administrateurs de clients souhaitent modifier le numéro pour les appels sortants et/ou entrants en fonction des modèles qu’ils ont créés pour garantir l’interopérabilité avec les contrôleurs de frontière de session (SBCs). Cet article décrit la manière dont vous pouvez spécifier une stratégie de règles de correspondance de numéro pour traduire les numéros dans un autre format. 

Vous pouvez utiliser la stratégie de règles de traduction du numéro pour traduire des numéros pour les éléments suivants :

- Appels entrants : appels d’un point de terminaison PSTN (appelant) vers un client Teams (appelé)
- Appels sortants : appels d’un client Teams (appelant) vers un point de terminaison PSTN (appelé)

La stratégie est appliquée au niveau du SBC. Vous pouvez affecter plusieurs règles de traduction à une SBC, qui sont appliquées dans l’ordre dans lequel elles apparaissent lorsque vous les affichez dans PowerShell. Vous pouvez également modifier l’ordre des règles dans la stratégie.

Pour créer, modifier, afficher et supprimer des règles de manipulation de nombre, utilisez les applets de [CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/new-csteamstranslationrule), [Set-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/set-csteamstranslationrule), [Get-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/get-csteamstranslationrule)et [Remove-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/remove-csteamstranslationrule) .

Pour attribuer, configurer et répertorier les règles de manipulation de numéros sur SBCs, utilisez les applets de [nouvelle-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) et [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) conjointement avec les paramètres InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules, OutboundPSTNNumberTranslationRules, InboundTeamsNumberTranslationRulesList, InboundPSTNNumberTranslationRulesList, OutboundTeamsNumberTranslationRulesList et OutboundPSTNNumberTranslationRulesList.

>[!NOTE]
> Le nombre maximal de règles de traduction est de 400, le nombre maximal de noms de paramètres de traduction correspond à 100 symboles, la longueur maximale du modèle de paramètre de traduction est de 1024 symboles et la longueur de traduction du paramètre de traduction maximum est de 256 symboles.


## <a name="example-sbc-configuration"></a>Exemple de configuration de SBC

Pour ce scénario, l' ```New-CsOnlinePSTNGateway``` applet de commande est exécutée pour créer la configuration SBC suivante :

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRulesList ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRulesList ‘AddPlus1’ -OnboundPSTNNumberTranslationRulesList ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRulesList ‘StripPlus1’
```

Les règles de traduction affectées aux SBC sont résumées dans le tableau suivant :

|Nom  |Modèle |Conversion  |
|---------|---------|---------|
|AddPlus1     |^ (\d {10} ) $          |+1$1          |
|AddE164SeattleAreaCode      |^ (\d {4} ) $          | commande + 1206555 $1         |
|AddSeattleAreaCode    |^ (\d {4} ) $          | 425555 $1         |
|StripPlus1    |^ + 1 (\d {10} ) $          | $1         |

Dans les exemples suivants, il existe deux utilisateurs, Alice et Bob. Alice est un utilisateur d’équipe dont le numéro est + 1 206 555 0100. Bob est un utilisateur RTC dont le numéro est + 1 425 555 0100.

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Exemple 1 : appel entrant vers un numéro à dix chiffres

Bob appelle Alice en utilisant un numéro à 10 chiffres non-E. 164. Bob compose 2065550100 pour joindre Alice.
SBC utilise 2065550100 dans le RequestURI et les en-têtes et 4255550100 dans l’en-tête de.


|Titre  |Langue source |En-tête traduit |Paramètre et règle appliqués  |
|---------|---------|---------|---------|
|RequestURI  |INVITER sip :2065550100@sbc.contoso.com|INVITER sip :+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRulesList 'AddPlus1'|
|À    |À:\<sip:2065550100@sbc.contoso.com>|À:\<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddPlus1'|
|De   |De:\<sip:4255550100@sbc.contoso.com>|De:\<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRulesList 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>Exemple 2 : appel entrant vers un numéro à quatre chiffres

Bob appelle Alice en utilisant un numéro à quatre chiffres. Bob compose 0100 pour joindre Alice.
SBC utilise 0100 dans le RequestURI et les en-têtes et 4255550100 dans l’en-tête de.


|Titre  |Langue source |En-tête traduit |Paramètre et règle appliqués  |
|---------|---------|---------|---------|
|RequestURI  |INVITER sip :0100@sbc.contoso.com          |INVITER sip :+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'        |
|À    |À:\<sip:0100@sbc.contoso.com>|À:\<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'         |
|De   |De:\<sip:4255550100@sbc.contoso.com>|De:\<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRulesList 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Exemple 3 : appel sortant avec un numéro à dix chiffres non-E. 164

Alice appelle Bob par le biais d’un numéro à dix chiffres. Alice compose le numéro 425 555 0100 pour joindre Bob.
SBC est configuré de manière à utiliser des numéros non-E. 164 à dix chiffres pour les équipes et les utilisateurs PSTN.

Dans ce scénario, un plan de numérotation traduit le numéro avant de l’envoyer à l’interface de routage directe. Lorsque Alice entre 425 555 0100 dans le client Teams, le numéro est converti en + 14255550100 par le plan de numérotation pays. Les numéros obtenus sont une normalisation cumulative des règles de plan de numérotation et des règles de traduction d’équipes. Les règles de traduction des équipes suppriment le « + 1 » ajouté par le plan de numérotation.


|Titre  |Langue source |En-tête traduit |Paramètre et règle appliqués  |
|---------|---------|---------|---------|
|RequestURI  |INVITER sip :+14255550100@sbc.contoso.com          |INVITER sip :4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRulesList 'StripPlus1'         |
|À    |À:\<sip:+14255550100@sbc.contoso.com>|À:\<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRulesList 'StripPlus1'       |
|De   |De:\<sip:+12065550100@sbc.contoso.com>|De:\<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRulesList 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Exemple 4 : appel sortant avec un numéro à quatre chiffres non-E. 164

Alice appelle Bob par le biais d’un numéro à quatre chiffres. Alice utilise 0100 pour joindre Bob depuis les appels ou à l’aide d’un contact.
SBC est configuré pour utiliser des numéros à quatre chiffres non-E. 164 pour les utilisateurs de teams et des numéros à dix chiffres pour les utilisateurs PSTN. Le plan de numérotation n’est pas appliqué dans ce scénario.


|Titre  |Langue source |En-tête traduit |Paramètre et règle appliqués  |
|---------|---------|---------|---------|
|RequestURI  |INVITER sip :0100@sbc.contoso.com           |INVITER sip :4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'         |
|À    |À:\<sip:0100@sbc.contoso.com>|À:\<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|De   |De:\<sip:+12065550100@sbc.contoso.com>|De:\<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRulesList 'StripPlus1' |

## <a name="see-also"></a>Voir aussi

[Planifier le routage direct](direct-routing-plan.md)

[Configurer le routage direct](direct-routing-configure.md)
