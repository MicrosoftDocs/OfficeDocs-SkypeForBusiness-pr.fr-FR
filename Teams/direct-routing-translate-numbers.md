---
title: Traduire des numéros de téléphone pour un routage direct
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Découvrez comment configurer Téléphone Microsoft routage direct du système.
ms.openlocfilehash: 2e94da39c23c10a912f4b3f0433467439b5ecf77
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766367"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>Traduire des numéros de téléphone dans un autre format

Cet article explique comment traduire les numéros des appels entrants et sortants dans un autre format.  Voici l’étape 4 de la procédure de configuration du routage direct :

- Étape 1. [Connecter SBC avec votre système Téléphone Microsoft données et valider la connexion](direct-routing-connect-the-sbc.md) 
- Étape 2. [Activer les utilisateurs pour le routage direct, la voix et la messagerie vocale](direct-routing-enable-users.md)   
- Étape 3. [Configurer le routage vocal](direct-routing-voice-routing.md)
- **Étape 4. Traduire des nombres dans un autre format**   (cet article)

Pour plus d’informations sur les étapes requises pour configurer le routage direct, voir [Configurer le routage direct.](direct-routing-configure.md)

Il arrive que les administrateurs des locataires souhaitent modifier le numéro des appels sortants et/ou entrants en fonction des modèles qu’ils ont créés pour garantir l’interopérabilité avec les contrôleurs de session en bordure. Cet article explique comment spécifier une stratégie de règles de traduction de nombres pour traduire les nombres dans un autre format. 

Vous pouvez utiliser la stratégie Règles de traduction des nombres pour traduire les nombres des suivants :

- Appels entrants : appels d’un point de terminaison PSTN (appelant) à un client Teams (appelé)
- Appels sortants : appels d’un client Teams (appelant) à un point de terminaison PSTN (appelé)

La stratégie est appliquée au niveau SBC. Vous pouvez affecter plusieurs règles de traduction à un SBC, qui sont appliquées dans l’ordre dans lequel elles apparaissent lorsque vous les énumérez dans PowerShell. Vous pouvez également modifier l’ordre des règles dans la stratégie.

Pour créer, modifier, afficher et supprimer des règles de manipulation de nombre, utilisez les cmdlets [New-CsTeamsTranslationRule,](/powershell/module/skype/new-csteamstranslationrule) [Set-CsTeamsTranslationRule,](/powershell/module/skype/set-csteamstranslationrule) [Get-CsTeamsTranslationRule](/powershell/module/skype/get-csteamstranslationrule)et [Remove-CsTeamsTranslationRule.](/powershell/module/skype/remove-csteamstranslationrule)

Pour attribuer, configurer et lister des règles de manipulation des nombres sur les SBCs, utilisez les cmdlets [New-CSOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) et [Set-CSOnlinePSTNGateway,](/powershell/module/skype/set-csonlinepstngateway) ainsi que les cmdlets InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules, OutboundPSTNNumberTranslationRules, InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules et OutboundPSTNNumberTranslationRules paramètres.

> [!NOTE]
> Le nombre maximal de règles de traduction est de 400, la longueur maximale des noms de paramètres de traduction est de 100 symboles, la longueur maximale des modèles de paramètres de traduction est de 1 024 symboles et la longueur maximale de traduction de 256 symboles.


## <a name="example-sbc-configuration"></a>Exemple de configuration SBC

Dans ce scénario, ```New-CsOnlinePSTNGateway``` l’cmdlet est exécuté pour créer la configuration SBC suivante :

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,‘StripPlus1’  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

Les règles de traduction attribuées au SBC sont résumées dans le tableau suivant :

|Nom  |Modèle |Conversion  |
|---------|---------|---------|
|AddPlus1     |^(\d {10} )$          |+1$1          |
|AddE164TtleAreaCode      |^(\d {4} )$          | +1206555$1         |
|AddTtleAreaCode    |^(\d {4} )$          | 425555$1         |
|StripPlus1    |^+1(\d {10} )$          | $1         |

Dans les exemples suivants, il y a deux utilisateurs, Tous deux, Qun. et Bob. Il s’agit Teams utilisateur dont le numéro est +1 206 555 0100. Bob est un utilisateur PSTN dont le numéro est +1 425 555 0100.

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Exemple 1 : appel entrant vers un numéro à dix chiffres

Bob appelle Contrôle à l’aide d’un numéro non E.164 à dix chiffres. Bob compose un 2065550100 pour joindredessoy.
SBC utilise des 2065550100 dans les en-têtes RequestURI et To 4255550100'en-tête De.


|En-tête  |Langue source |En-tête traduit |Paramètre et règle appliqués  |
|---------|---------|---------|---------|
|RequestURI  |INVITE sip:2065550100@sbc.contoso.com|INVITE sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRules 'AddPlus1'|
|À    |À: \<sip:2065550100@sbc.contoso.com>|À: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddPlus1'|
|DE   |DE: \<sip:4255550100@sbc.contoso.com>|DE: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>Exemple 2 : appel entrant vers un numéro à quatre chiffres

Bob appelle Contrôle à l’aide d’un numéro à quatre chiffres. Bob compose le 0100 pour joindre Tous.
SBC utilise 0100 dans les en-têtes RequestURI et To 4255550100'en-tête De.


|En-tête  |Langue source |En-tête traduit |Paramètre et règle appliqués  |
|---------|---------|---------|---------|
|RequestURI  |INVITE sip:0100@sbc.contoso.com          |INVITE sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRules 'AddE164TtleAreaCode'        |
|À    |À: \<sip:0100@sbc.contoso.com>|À: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddE164TtleAreaCode'         |
|DE   |DE: \<sip:4255550100@sbc.contoso.com>|DE: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Exemple 3 : appel sortant avec un numéro autre que E.164 à dix chiffres

Contrôle appelle Bob à l’aide d’un numéro à dix chiffres. Il compose le 425 555 0100 pour joindre Bob.
SBC est configuré pour utiliser des numéros non E.164 à dix chiffres pour les utilisateurs Teams et PSTN.

Dans ce scénario, un plan de numérotation traduit le numéro avant de l’envoyer vers l’interface de routage direct. Lorsque Tous les deux entrent le numéro 425 555 0100 dans le client Teams, le numéro est converti en + 14255550100 par le plan de numérotation du pays. Les numéros qui en résultent sont une normalisation cumulative des règles de plan de numérotation et Teams de traduction. Les Teams de traduction suppriment le « + 1 » ajouté par le plan de numérotation.


|En-tête  |Langue source |En-tête traduit |Paramètre et règle appliqués  |
|---------|---------|---------|---------|
|RequestURI  |INVITE sip:+14255550100@sbc.contoso.com          |INVITE sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRules 'StripPlus1'         |
|À    |À: \<sip:+14255550100@sbc.contoso.com>|À: \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRules 'StripPlus1'       |
|DE   |DE: \<sip:+12065550100@sbc.contoso.com>|DE: \<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Exemple 4 : appel sortant avec un numéro autre qu’E.164 à quatre chiffres

Contrôle appelle Bob à l’aide d’un numéro à quatre chiffres. Ils utilisent 0100 pour joindre Bob depuis les Appels ou à l’aide d’un contact.
SBC est configuré pour utiliser des numéros à quatre chiffres autres que E.164 pour les utilisateurs Teams et des numéros à dix chiffres pour les utilisateurs PSTN. Le plan de numérotation n’est pas appliqué dans ce scénario.


|En-tête  |Langue source |En-tête traduit |Paramètre et règle appliqués  |
|---------|---------|---------|---------|
|RequestURI  |INVITE sip:0100@sbc.contoso.com           |INVITE sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRules 'AddTtleAreaCode'         |
|À    |À: \<sip:0100@sbc.contoso.com>|À: \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddTtleAreaCode'       |
|DE   |DE: \<sip:+12065550100@sbc.contoso.com>|DE: \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>Voir aussi

[Planifier le routage direct](direct-routing-plan.md)

[Configurer le routage direct](direct-routing-configure.md)
