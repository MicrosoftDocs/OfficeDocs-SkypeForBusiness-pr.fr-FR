---
title: Traduire des numéros de téléphone pour le routage direct
ms.reviewer: filippse
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
description: Découvrez comment configurer le routage direct du système téléphonique Microsoft.
ms.openlocfilehash: ac6dbd46d525232235d957b7d47f1fe108e3e4a3
ms.sourcegitcommit: eb0e754d7e2877f686021d3ab75b6d8d44db3a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/06/2023
ms.locfileid: "69727766"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>Traduire des numéros de téléphone dans un autre format

Cet article explique comment traduire des numéros pour les appels sortants et entrants dans un autre format. Il s’agit de l’étape 4 des étapes suivantes pour configurer le routage direct :

- Étape 1. [Connecter le SBC au système téléphonique Microsoft et valider la connexion](direct-routing-connect-the-sbc.md) 
- Étape 2. [Activer les utilisateurs pour le routage direct, la voix et la messagerie vocale](direct-routing-enable-users.md)   
- Étape 3. [Configurer le routage des communications vocales](direct-routing-voice-routing.md)
- **Étape 4. Traduire des nombres dans un autre format**   (Cet article)

Pour plus d’informations sur toutes les étapes requises pour configurer le routage direct, consultez [Configurer le routage direct](direct-routing-configure.md).

Parfois, les administrateurs de locataire peuvent vouloir modifier le numéro des appels sortants et/ou entrants en fonction des modèles qu’ils ont créés pour garantir l’interopérabilité avec les contrôleurs de frontière de session (SBC). Cet article explique comment spécifier une stratégie de règles de traduction de nombres pour traduire des nombres dans un autre format. 

Vous pouvez utiliser la stratégie Règles de traduction de nombres pour traduire des nombres pour les éléments suivants :

- Appels entrants : appels à partir d’un point de terminaison PSTN (appelant) vers un client Teams (appelé)
- Appels sortants : appels d’un client Teams (appelant) vers un point de terminaison RTC (appelé)

La stratégie est appliquée au niveau du SBC. Vous pouvez affecter plusieurs règles de traduction à un SBC, qui sont appliquées dans l’ordre dans lequel elles apparaissent lorsque vous les répertoriez dans PowerShell. Vous pouvez également modifier l’ordre des règles dans la stratégie.

Pour créer, modifier, afficher et supprimer des règles de manipulation de nombre, utilisez les applets de commande [New-CsTeamsTranslationRule](/powershell/module/skype/new-csteamstranslationrule), [Set-CsTeamsTranslationRule](/powershell/module/skype/set-csteamstranslationrule), [Get-CsTeamsTranslationRule](/powershell/module/skype/get-csteamstranslationrule) et [Remove-CsTeamsTranslationRule](/powershell/module/skype/remove-csteamstranslationrule) .

Pour affecter, configurer et lister des règles de manipulation de nombres sur des SBC, utilisez les applets de commande [New-CSOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) et [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) avec les paramètres InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules et OutboundPSTNNumberTranslationRules.

> [!NOTE]
> Le nombre total maximal de règles de traduction est de 400, la longueur maximale du nom des paramètres de traduction est de 100 symboles, la longueur maximale du modèle de paramètre de traduction est de 1 024 symboles et la longueur maximale des paramètres de traduction est de 256 symboles.


## <a name="example-sbc-configuration"></a>Exemple de configuration SBC

Pour ce scénario, l’applet de commande New-CsOnlinePSTNGateway est exécutée pour créer la configuration SBC suivante :

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,‘StripPlus1’  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

Les règles de traduction affectées au SBC sont résumées dans le tableau suivant :

|Nom  |Modèle |Conversion  |
|---------|---------|---------|
|AddPlus1     |^(\d{10})$          |+1$1          |
|AddE164SeattleAreaCode      |^(\d{4})$          | +1206555$1         |
|AddSeattleAreaCode    |^(\d{4})$          | 425555$1         |
|StripPlus1    |^\+1(\d{10})$          | $1         |

Dans les exemples suivants, il y a deux utilisateurs, Alice et Bob. Alice est un utilisateur Teams dont le numéro est +1 206 555 0100. Bob est un utilisateur RTC dont le numéro est +1 425 555 0100.

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Exemple 1 : appel entrant à un numéro à dix chiffres

Bob appelle Alice à l’aide d’un numéro à dix chiffres autre que E.164. Bob compose 2065550100 pour joindre Alice.
SBC utilise 2065550100 dans les en-têtes RequestURI et To et 4255550100 dans l’en-tête From.


|En-tête  |Langue source |En-tête traduit |Paramètre et règle appliqués  |
|---------|---------|---------|---------|
|Requesturi  |INVITE sip:2065550100@sbc.contoso.com|INVITE sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRules 'AddPlus1'|
|À    |À: \<sip:2065550100@sbc.contoso.com>|À: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddPlus1'|
|DE   |DE: \<sip:4255550100@sbc.contoso.com>|DE: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>Exemple 2 : appel entrant à un numéro à quatre chiffres

Bob appelle Alice à l’aide d’un numéro à quatre chiffres. Bob compose le 0100 pour atteindre Alice.
SBC utilise 0100 dans les en-têtes RequestURI et To et 4255550100 dans l’en-tête From.


|En-tête  |Langue source |En-tête traduit |Paramètre et règle appliqués  |
|---------|---------|---------|---------|
|Requesturi  |INVITE sip:0100@sbc.contoso.com          |INVITE sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|À    |À: \<sip:0100@sbc.contoso.com>|À: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|DE   |DE: \<sip:4255550100@sbc.contoso.com>|DE: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Exemple 3 : Appel sortant utilisant un numéro à dix chiffres autre que E.164

Alice appelle Bob à l’aide d’un numéro à dix chiffres. Alice compose le 425 555 0100 pour joindre Bob.
SBC est configuré pour utiliser des numéros à dix chiffres autres que E.164 pour les utilisateurs Teams et RTC.

Dans ce scénario, un plan de numérotation traduit le numéro avant de l’envoyer à l’interface de routage direct. Quand Alice entre 425 555 0100 dans le client Teams, le numéro est traduit en +14255550100 par le plan de numérotation du pays. Les nombres obtenus sont une normalisation cumulative des règles de plan de numérotation et des règles de traduction Teams. Les règles de traduction Teams suppriment le « +1 » ajouté par le plan de numérotation.


|En-tête  |Langue source |En-tête traduit |Paramètre et règle appliqués  |
|---------|---------|---------|---------|
|Requesturi  |INVITE sip:+14255550100@sbc.contoso.com          |INVITER sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRules 'StripPlus1'         |
|À    |À: \<sip:+14255550100@sbc.contoso.com>|À: \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRules 'StripPlus1'       |
|DE   |DE: \<sip:+12065550100@sbc.contoso.com>|DE: \<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Exemple 4 : Appel sortant utilisant un numéro à quatre chiffres autre que E.164

Alice appelle Bob à l’aide d’un numéro à quatre chiffres. Alice utilise 0100 pour contacter Bob à partir d’appels ou à l’aide d’un contact.
SBC est configuré pour utiliser des numéros à quatre chiffres non-E.164 pour les utilisateurs Teams et des numéros à dix chiffres pour les utilisateurs RTC. Le plan de numérotation n’est pas appliqué dans ce scénario.


|En-tête  |Langue source |En-tête traduit |Paramètre et règle appliqués  |
|---------|---------|---------|---------|
|Requesturi  |INVITE sip:0100@sbc.contoso.com           |INVITER sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|À    |À: \<sip:0100@sbc.contoso.com>|À: \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|DE   |DE: \<sip:+12065550100@sbc.contoso.com>|DE: \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>Voir aussi

[Planifier le routage direct](direct-routing-plan.md)

[Configurer le routage direct](direct-routing-configure.md)
