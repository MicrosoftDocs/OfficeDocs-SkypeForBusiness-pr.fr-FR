---
title: Qu’est-ce que les plans de numérotation ?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.dialplans.overview
- Calling Plans
description: 'Découvrez quels types de plans d’appel (plans de numérotation PSTN) sont disponibles avec Teams et comment en choisir un pour votre organisation.  '
ms.openlocfilehash: 405a8902c9c367c09f7f467cb00358d75112de1f
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727373"
---
# <a name="what-are-dial-plans"></a>Qu’est-ce que les plans de numérotation ?

Un plan de numérotation est un ensemble nommé de règles de normalisation qui traduisent les numéros de téléphone composés par un utilisateur individuel dans un autre format (généralement E.164) à des fins d’autorisation d’appel et de routage vocal.

Un plan de numérotation est constitué d’une ou de plusieurs règles de normalisation qui définissent comment les numéros de téléphone exprimés dans des formats différents sont convertis dans un autre format. Une chaîne de numérotation identique peut être interprétée et convertie différemment par des plans de numérotation différents. Ainsi, en fonction du plan de numérotation attribué à un utilisateur donné, un même numéro peut être converti et acheminé différemment. Vous pouvez utiliser un maximum de 1 000 plans de numérotation client.

Pour créer et gérer des [plans de numérotation,](create-and-manage-dial-plans.md) voir Créer et gérer des plans de numérotation client.

## <a name="tenant-dial-plan-scope"></a>Étendue du plan de numérotation client

L'étendue d'un plan de numérotation détermine le niveau hiérarchique auquel celui-ci est appliqué. Les clients obtiennent le plan de numérotation approprié via les paramètres d’approvisionnement qui sont automatiquement fournis lorsque les utilisateurs se connectent Teams. En tant qu’administrateur, vous pouvez gérer et affecter les niveaux d’étendue des plans de numérotation à l’aide du centre d Microsoft Teams d’administration d’entreprise ou de Remote PowerShell.

Dans Teams, il existe deux types de plans de numérotation : dans l’étendue du service et dans l’étendue du client (pour votre organisation). Un plan de numérotation à l’étendue du service est défini pour chaque pays ou région où Système téléphonique est disponible. Chaque utilisateur se voit automatiquement attribuer le plan de numérotation du pays de service qui correspond à l’emplacement d’utilisation attribué à l’utilisateur. Vous ne pouvez pas modifier le plan de numérotation du pays de service, mais vous pouvez créer des plans de numérotation étendues au client, ce qui augmente le plan de numérotation du pays de service. Au cours de la mise en service des clients, ceux-ci obtiennent un « plan de numérotation efficace », qui est une combinaison du plan de numérotation du pays de service et du plan de numérotation client de manière appropriée. Il nʼest donc pas nécessaire de définir toutes les règles de normalisation dans les plans de numérotation client car elles peuvent déjà exister dans le plan de numérotation du pays de service.

Les plans de numérotation client peuvent être davantage décomposés en deux étendues : l’étendue client ou l’étendue utilisateur. Si un client définit et attribue un plan de numérotation étendue à l’utilisateur, cet utilisateur est fourni avec un plan de numérotation efficace du plan de numérotation de son pays de service et du plan de numérotation utilisateur qui lui est attribué. Si un client définit un plan de numérotation à l’échelle du client sans affecter de plan de numérotation à l’étendue de l’utilisateur, cet utilisateur est alors fourni avec un plan de numérotation efficace défini par le plan de numérotation de son pays de service et le plan de numérotation client.

Voici le modèle d’héritage des plans de numérotation Teams.

![Comment les plans de numérotation sont hérités dans Teams.](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

Voici les différents plans de numérotation efficace possibles :

 **Pays de service** Si aucun plan de numérotation étendue au client n’est défini et qu’aucun plan de numérotation étendue à l’utilisateur client n’est attribué à l’utilisateur, l’utilisateur reçoit un plan de numérotation efficace mappé au pays de service associé à son emplacement d’utilisation.

 **Client global - Pays de service** Si un plan de numérotation d’utilisateur client est défini mais non attribué, l’utilisateur pourra bénéficier d’un plan de numérotation efficace constitué d’un plan de numérotation client fusionné avec le plan de numérotation du pays de service associé à l’emplacement d’utilisation.

 **Utilisateur client - Pays de service** Si un plan de numérotation d’utilisateur client est défini et attribué à un utilisateur, l’utilisateur pourra bénéficier d’un plan de numérotation efficace constitué d’un plan de numérotation utilisateur fusionné avec le plan de numérotation du pays de service associé à l’emplacement d’utilisation.

Voir [Créer et gérer des plans de](create-and-manage-dial-plans.md) numérotation pour créer vos plans de numérotation client.

> [!NOTE]
> Dans le cas où aucune règle de normalisation de plan de numérotation ne s’applique à un numéro composé, la chaîne de numérotation est toujours normalement en précédant « + CC » où CC est le code du pays de l’emplacement d’utilisation de l’utilisateur de numérotation. Cela s’applique aux plans d’appel, au routage direct et aux scénarios d’appels sortants de conférence RSTN. De plus, si une règle de normalisation du plan de numérotation client entraîne un numéro qui ne commence pas par « + », le service d’appel essaiera de normaliser le numéro reçu du client Teams en fonction du plan de numérotation client et, s’il n’est pas en correspondance, sur le plan de numérotation de la région. Pour éviter une normalisation en double, il est recommandé que les clients du routage direct normalisent les nombres afin d’inclure un + et de supprimer les règles de traduction de ligne + à l’aide de ligne. 

## <a name="planning-for-tenant-dial-plans"></a>Planification des plans de numérotation utilisateur

Pour planifier des plans de numérotation personnalisés, procédez comme suit :

- **Étape 1** Décidez si un plan de numérotation personnalisé est nécessaire pour améliorer l’expérience de numérotation des utilisateurs. En règle générale, la prise en charge d’une numérotation autre qu’E.164, telle que les extensions ou la numérotation nationale abrégée, serait nécessaire.

- **Étape 2** Déterminez si les plans de numérotation du client global, du plan de numérotation étendue à l’utilisateur client sont nécessaires ou les deux. Les plans de numérotation étendus aux utilisateurs sont nécessaires si les configurations d'appel local sont différentes en fonction des utilisateurs.

- **Étape 3** Identifiez des schémas de numéros valides pour chaque plan de numérotation nécessaire. Les seuls schémas de numéros nécessaires sont ceux qui ne sont pas définis dans les plans de numérotation au niveau du pays de service.

- **Étape 4** Développez un modèle d'appellation des plans de numérotation à l'échelle de votre organisation. Adopter un modèle d'appellation standard à toute une organisation permet de s'assurer de la cohérence d'un système et facilite la maintenance et les mises à jour.


## <a name="creating-your-new-dial-plan"></a>Création de votre plan de numérotation

Lorsque vous créez un nouveau plan de numérotation client, vous devez entrer les informations requises.

### <a name="name-and-simple-name"></a>Nom et Nom simplifié

Pour les plans de numérotation utilisateur, vous devez spécifier un nom descriptif qui identifie les utilisateurs à qui le plan de numérotation sera attribué. Le nom simple du plan de numérotation est pré-rempli avec une chaîne dérivée du nom du plan de numérotation. Le champ Nom simplifié est modifiable, ce qui vous permet de créer une convention d'appellation plus descriptive pour vos plans de numérotation. La valeur du Nom simplifié ne peut être vide et doit être unique. Les meilleures pratiques suggèrent de développer une convention d'appellation pour l'ensemble de votre organisation et d'utiliser systématiquement cette convention pour tous les sites et tous les utilisateurs.

### <a name="description"></a>Description

Nous vous recommandons d'écrire le nom habituel, connu, de l'emplacement géographique ou du groupe d'utilisateurs pour lequel le plan de numérotation correspondant s'applique.

### <a name="external-access-prefix"></a>Préfixe d'accès extérieur
<a name="bkexternalprefix"> </a>

Vous pouvez spécifier un préfixe d'accès extérieur de 1 à 4 caractères (#, * et 0-9) si les utilisateurs doivent composer un ou plusieurs chiffres supplémentaires (par exemple, 9) pour joindre une ligne extérieure.

> [!NOTE]
> Si vous spécifiez un préfixe d'accès extérieur, vous n'avez pas besoin de créer une règle de normalisation supplémentaire pour vous adapter au préfixe.

Voir [Créer et gérer des plans de](create-and-manage-dial-plans.md) numérotation pour créer vos plans de numérotation client.

## <a name="normalization-rules"></a>Règles de normalisation
<a name="bknormalizationrule"> </a>

Les règles de normalisation définissent comment les numéros de téléphone exprimés dans des formats variés doivent être convertis. Une chaîne de numérotation identique peut être interprétée et convertie différemment en fonction du pays d'où elle est composée. Des règles de normalisation peuvent être nécessaires si des utilisateurs ont besoin de composer des numéros extérieurs ou des numéros internes abrégés.

Vous devez attribuer une ou plusieurs règles de normalisation au plan de numérotation. Les règles de normalisation correspondent de haut en bas, l’ordre dans lequel elles apparaissent dans un plan de numérotation client est donc importante. Par exemple, si un plan de numérotation client possède 10 règles de normalisation, la logique de correspondance d'un numéro composé sera vérifiée en commençant par la première règle de normalisation, puis, en lʼabsence de correspondance, par la seconde, etc. Si une correspondance est trouvée, cette règle est utilisée et les autres règles définies ne sont pas vérifiées. Un plan de numérotation client donné peut respecter un maximum de 50 règles de normalisation.

### <a name="determining-the-required-normalization-rules"></a>Déterminer les règles de normalisation requises

Dans la mesure où un plan de numérotation client est fusionné efficacement avec le plan de numérotation du pays de service d’un utilisateur donné, il est probable que les règles de normalisation du plan de numérotation du pays de service doivent être évaluées afin de déterminer les règles de normalisation du plan de numérotation client nécessaires. L'applet de commande **Get-CsEffectiveTenantDialPlan** peut être utilisée à cet effet. Cette applet de commande utilise l'identité d'un utilisateur comme paramètre d'entrée et indique en retour toutes les règles de normalisation appliquées à cet utilisateur.

### <a name="creating-normalization-rules"></a>Créer des règles de normalisation
<a name="createrule"> </a>

Les règles de normalisation utilisent .NET Framework expressions régulières pour spécifier des modèles de correspondance numérique que le serveur utilise pour traduire des chaînes de numérotation au format E.164. Les règles de normalisation peuvent être créées en spécifiant lʼexpression régulière de la correspondance et la conversion à effectuer lorsquʼune correspondance est trouvée. Quand vous avez terminé, vous pouvez entrer un numéro test pour vérifier que la règle de normalisation fonctionne correctement.

Pour plus d’informations sur l'.NET Framework expressions régulières, voir [.NET Framework expressions régulières.](/dotnet/standard/base-types/regular-expressions)

Pour [créer et gérer des règles de](create-and-manage-dial-plans.md) normalisation pour vos plans de numérotation client, voir Créer et gérer des plans de numérotation.

> [!NOTE]
> Les règles de normalisation avec le premier jeton facultatif ne sont pas actuellement pris en charge sur les appareils 3pip (par exemple, le modèle Polycom VVX 601). Si vous voulez appliquer des règles de normalisation avec une optionalité sur les appareils 3pip, vous devez créer deux règles de normalisation au lieu d’une. Par exemple, la règle ^0? (999)$ doit être remplacé par les deux règles suivantes : (999)$ (Traduction :$1) et ^0(999)$ (traduction :$1).


### <a name="sample-normalization-rules"></a>Exemples de règles de normalisation

Le tableau ci-dessous illustre des exemples de règles de normalisation écrites sous la forme d'expressions régulières .NET Framework. Il s'agit uniquement d'exemples qui ne doivent pas être considérés comme une référence normative pour la création de règles de normalisation.

<a name="regularexpression"> </a> 
 **Règles de normalisation utilisant .NET Framework expressions régulières**

| Nom de la règle<br/> | Description<br/> | Type de numéro<br/> | Conversion<br/> | Exemple<br/> |
|:-----|:-----|:-----|:-----|:-----|
|4digitExtension  <br/> |Convertit les extensions à 4 chiffres.  <br/> |^(\\d{4})$  <br/> |+1425555$1  <br/> |0100 est converti en +14255550100  <br/> |
|5digitExtension  <br/> |Convertit les extensions à 5 chiffres.  <br/> |^5(\\d{4})$  <br/> |+1425555$1  <br/> |50100 est converti en +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Convertit les numéros à 7 chiffres en numéros locaux à Redmond.  <br/> |^(\\d{7})$  <br/> |+1425$1  <br/> |5550100 est converti en +14255550100  <br/>|
|RedmondOperator  <br/> |Convertit 0 vers l'Opérateur de Redmond.  <br/> |^0$  <br/> |+14255550100  <br/> |0 est converti en +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Convertit les numéros avec un préfixe on-net (6) et le code du site de Redmond (222).  <br/> |^6222(\\d{4})$  <br/> |+1425555$1  <br/> |62220100 est converti en +14255550100  <br/> |
|5digitRange  <br/> |Convertit les extensions à 5 chiffres avec la plage de chiffres 3-7 inclusive.  <br/> |^([3-7]\\d{4})$  <br/> |+142555$1 <br/> |54567 est converti en +14255554567  <br/> |
|PrefixAdded  <br/> |Ajoute un préfixe pays devant un numéro à 9 chiffres avec des restrictions sur le premier et le troisième chiffre.  <br/> |^([2-9]\\d\\d[2-9]\\d{6})$  <br/> |1$1  <br/> |4255554567 est converti en 14255554567  <br/> |
|NoTranslation  <br/> |Fait correspondre 5 chiffres mais sans conversion.  <br/> |^(\\d{5})$  <br/> |$1  <br/> |34567 est converti en 34567  <br/> |

 **Plan de numérotation de Redmond basé sur les règles de normalisation indiquées ci-dessus.**

 Le tableau suivant illustre un exemple de plan de numérotation pour Redmond, Washington, États-unis, basé sur les règles de normalisation indiquées dans le tableau précédent.

| Plan de numérotation de Redmond<br/> |
|:-----------------------|                                                                                                                      
| 5digitExtension <br/> |                                                                                                                                    
| 7digitcallingRedmond <br/> |
| RedmondSitePrefix <br/> |
| RedmondOperator <br/> |

> [!NOTE]
> Les noms des règles de normalisation indiqués dans le tableau précédent n’incluent pas d’espaces, mais c’est une question de choix. Le premier nom du tableau, par exemple, aurait pu s'écrire « 5 digit extension » ou « 5-digit Extension » et être toujours valide.

## <a name="related-topics"></a>Sujets associés

[Créer et gérer les plans de numérotation](create-and-manage-dial-plans.md)

[Différents types de numéros de téléphone utilisés pour les offres d'appel](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gérer des numéros de téléphone pour votre entreprise](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Conditions générales relatives aux appels d'urgence](emergency-calling-terms-and-conditions.md)

[Étiquette d’exclusion de responsabilité d’appel d’urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
