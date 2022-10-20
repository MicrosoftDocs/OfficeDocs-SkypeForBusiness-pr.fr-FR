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
- highpri
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
description: 'Découvrez le type de plans d’appel à la numérotation (plans de numérotation d’appel RTC) disponibles avec Teams et comment en choisir un pour votre organisation.  '
ms.openlocfilehash: 77ee7801d43bd6a7cf9ae9a9e3fc74c302f8caa0
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614247"
---
# <a name="what-are-dial-plans"></a>Qu’est-ce que les plans de numérotation ?

Un plan de numérotation est un ensemble nommé de règles de normalisation qui traduisent les numéros de téléphone composés par un utilisateur individuel dans un autre format (généralement E.164) à des fins d’autorisation d’appel et de routage vocal.

Un plan de numérotation se compose d’une ou de plusieurs règles de normalisation qui définissent la façon dont les numéros de téléphone exprimés dans différents formats sont traduits dans un autre format. La même chaîne de numérotation peut être interprétée et traduite différemment dans différents plans de numérotation. Par conséquent, selon le plan de numérotation attribué à un utilisateur donné, le même numéro composé peut être traduit et routé différemment. Il peut y avoir un maximum de 1 000 plans de numérotation client.

Consultez [Créer et gérer des plans de numérotation](create-and-manage-dial-plans.md) pour créer et gérer des plans de numérotation de locataire.

## <a name="tenant-dial-plan-scope"></a>Étendue du plan de numérotation client

L'étendue d'un plan de numérotation détermine le niveau hiérarchique auquel celui-ci est appliqué. Les clients obtiennent le plan de numérotation approprié par le biais des paramètres d’approvisionnement qui sont automatiquement fournis lorsque les utilisateurs se connectent à Teams. En tant qu’administrateur, vous pouvez gérer et affecter des niveaux d’étendue de plan de numérotation à l’aide du Centre d’administration Microsoft Teams ou de Remote PowerShell.

Dans Teams, il existe deux types de plans de numérotation : l’étendue du service et l’étendue du locataire (qui concerne votre organisation). Un plan de numérotation étendu au service est défini pour chaque pays ou région où le système téléphonique est disponible. Chaque utilisateur reçoit automatiquement le plan de numérotation de pays de service qui correspond à l’emplacement d’utilisation attribué à l’utilisateur. Vous ne pouvez pas modifier le plan de numérotation de pays de service, mais vous pouvez créer des plans de numérotation étendus au locataire, ce qui augmente le plan de numérotation du pays de service. À mesure que les clients sont approvisionnés, ils obtiennent un « plan de numérotation effectif », qui est une combinaison du plan de numérotation du pays de service et du plan de numérotation du locataire dont l’étendue est appropriée. Il nʼest donc pas nécessaire de définir toutes les règles de normalisation dans les plans de numérotation client car elles peuvent déjà exister dans le plan de numérotation du pays de service.

Les plans de numérotation de locataire peuvent être divisés en deux étendues : l’étendue du locataire ou l’étendue utilisateur. Si un locataire définit et affecte un plan de numérotation étendu à l’utilisateur, cet utilisateur est approvisionné avec un plan de numérotation effectif du plan de numérotation du pays de service de l’utilisateur et du plan de numérotation de l’utilisateur affecté. Si un locataire définit un plan de numérotation étendu au locataire mais n’affecte pas de plan de numérotation étendu à l’utilisateur, cet utilisateur est approvisionné avec un plan de numérotation effectif du plan de numérotation du pays de service de l’utilisateur et du plan de numérotation du locataire.

Voici le modèle d’héritage des plans de numérotation dans Teams.

![Comment les plans de numérotation sont hérités dans Teams.](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

Voici les différents plans de numérotation efficace possibles :

 **Pays de service** Si aucun plan de numérotation limité au locataire n’est défini et qu’aucun plan de numérotation étendu à l’utilisateur client n’est affecté à l’utilisateur approvisionné, l’utilisateur reçoit un plan de numérotation effectif mappé au pays de service associé à son emplacement d’utilisation.

 **Locataire global - Pays de service** Si un plan de numérotation utilisateur client est défini, mais qu’il n’est pas affecté à un utilisateur, l’utilisateur approvisionné reçoit un plan de numérotation effectif composé d’un plan de numérotation de locataire fusionné et du plan de numérotation de pays de service associé à son emplacement d’utilisation.

 **Utilisateur client - Pays de service** Si un plan de numérotation utilisateur client est défini et affecté à un utilisateur, l’utilisateur approvisionné reçoit un plan de numérotation effectif composé du plan de numérotation utilisateur client fusionné et du plan de numérotation du pays de service associé à son emplacement d’utilisation.

Consultez [Créer et gérer des plans de numérotation](create-and-manage-dial-plans.md) pour créer vos plans de numérotation de locataire.

> [!NOTE]
> Dans le scénario où aucune règle de normalisation de plan de numérotation ne s’applique à un numéro composé, la chaîne numérotée est toujours normalisée pour ajouter « + CC », où CC est le code de pays de l’emplacement d’utilisation de l’utilisateur de numérotation. Cela s’applique aux plans d’appel, au routage direct et aux scénarios de numérotation de conférence RTC. En outre, si une règle de normalisation de plan de numérotation de locataire génère un nombre qui ne commence pas par « + », le service appelant tente de normaliser le numéro reçu du client Teams en fonction du plan de numérotation du locataire et, s’il n’est pas mis en correspondance, sur le plan de numérotation de région. Pour éviter la double normalisation, il est recommandé que les clients de routage direct normalisent les nombres pour inclure un +, puis suppriment le + à l’aide des règles de traduction de jonction. 

## <a name="planning-for-tenant-dial-plans"></a>Planification des plans de numérotation utilisateur

Pour planifier des plans de numérotation personnalisés, procédez comme suit :

- **Étape 1** Déterminez si un plan de numérotation personnalisé est nécessaire pour améliorer l’expérience de numérotation des utilisateurs. En règle générale, il faudrait prendre en charge la numérotation non E.164, comme les extensions ou la numérotation nationale abrégée.

- **Étape 2** Déterminez si des plans de numérotation globaux ou étendus à l’utilisateur client sont nécessaires, ou les deux. Les plans de numérotation étendus aux utilisateurs sont nécessaires si les configurations d'appel local sont différentes en fonction des utilisateurs.

- **Step 3** Identify valid number patterns for each required dial plan. Only the number patterns that are not defined in the service level country dial plans are required.

- **Step 4** Develop an organization-wide scheme for naming dial plans. Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.


## <a name="creating-your-new-dial-plan"></a>Création de votre plan de numérotation

Lorsque vous créez un nouveau plan de numérotation client, vous devez entrer les informations requises.

### <a name="name-and-simple-name"></a>Nom et Nom simplifié

Pour les plans de numérotation utilisateur, vous devez spécifier un nom descriptif qui identifie les utilisateurs auxquels le plan de numérotation sera affecté. Le nom simple du plan de numérotation est prérempli avec une chaîne dérivée du nom du plan de numérotation. Le champ Nom simplifié est modifiable, ce qui vous permet de créer une convention d'appellation plus descriptive pour vos plans de numérotation. La valeur du Nom simplifié ne peut être vide et doit être unique. Les meilleures pratiques suggèrent de développer une convention d'appellation pour l'ensemble de votre organisation et d'utiliser systématiquement cette convention pour tous les sites et tous les utilisateurs.

### <a name="description"></a>Description

Nous vous recommandons d'écrire le nom habituel, connu, de l'emplacement géographique ou du groupe d'utilisateurs pour lequel le plan de numérotation correspondant s'applique.

### <a name="external-access-prefix"></a>Préfixe d'accès extérieur
<a name="bkexternalprefix"> </a>

Vous pouvez spécifier un préfixe d'accès extérieur de 1 à 4 caractères (#, * et 0-9) si les utilisateurs doivent composer un ou plusieurs chiffres supplémentaires (par exemple, 9) pour joindre une ligne extérieure.

> [!NOTE]
> Si vous spécifiez un préfixe d'accès extérieur, vous n'avez pas besoin de créer une règle de normalisation supplémentaire pour vous adapter au préfixe.

Consultez [Créer et gérer des plans de numérotation](create-and-manage-dial-plans.md) pour créer vos plans de numérotation de locataire.

## <a name="normalization-rules"></a>Règles de normalisation
<a name="bknormalizationrule"> </a>

Normalization rules define how phone numbers expressed in various formats are to be translated. The same number string may be interpreted and translated differently, depending on the locale from which it is dialed. Normalization rules may be necessary if users need to be able to dial abbreviated internal or external numbers.

Vous devez attribuer une ou plusieurs règles de normalisation au plan de numérotation. Les règles de normalisation étant mises en correspondance de haut en bas, l’ordre dans lequel elles apparaissent dans un plan de numérotation de locataire est important. Par exemple, si un plan de numérotation client possède 10 règles de normalisation, la logique de correspondance d'un numéro composé sera vérifiée en commençant par la première règle de normalisation, puis, en lʼabsence de correspondance, par la seconde, etc. Si une correspondance est trouvée, cette règle est utilisée et les autres règles définies ne sont pas vérifiées. Il peut y avoir un maximum de 50 règles de normalisation dans un plan de numérotation de locataire donné.

### <a name="determining-the-required-normalization-rules"></a>Déterminer les règles de normalisation requises

Étant donné que tout plan de numérotation de locataire est fusionné efficacement avec le plan de numérotation de pays de service d’un utilisateur donné, il est probable que les règles de normalisation du plan de numérotation du pays de service doivent être évaluées afin de déterminer les règles de normalisation du plan de numérotation du locataire qui sont nécessaires. L'applet de commande **Get-CsEffectiveTenantDialPlan** peut être utilisée à cet effet. Cette applet de commande utilise l'identité d'un utilisateur comme paramètre d'entrée et indique en retour toutes les règles de normalisation appliquées à cet utilisateur.

### <a name="creating-normalization-rules"></a>Créer des règles de normalisation
<a name="createrule"> </a>

Les règles de normalisation utilisent des expressions régulières .NET Framework pour spécifier des modèles de correspondance numériques que le serveur utilise pour traduire les chaînes de numérotation au format E.164. Les règles de normalisation peuvent être créées en spécifiant lʼexpression régulière de la correspondance et la conversion à effectuer lorsquʼune correspondance est trouvée. Quand vous avez terminé, vous pouvez entrer un numéro test pour vérifier que la règle de normalisation fonctionne correctement.

Pour plus d’informations sur l’utilisation d’expressions régulières .NET Framework, consultez [.NET Framework Regular Expressions](/dotnet/standard/base-types/regular-expressions).

Consultez [Créer et gérer des plans de numérotation](create-and-manage-dial-plans.md) pour créer et gérer des règles de normalisation pour vos plans de numérotation de locataire.

> [!NOTE]
> Les règles de normalisation avec le premier jeton comme facultatif ne sont actuellement pas prises en charge sur les appareils 3pip (par exemple, le modèle Polycom VVX 601). Si vous souhaitez appliquer des règles de normalisation avec facultatif sur des appareils 3pip, vous devez créer deux règles de normalisation au lieu d’une. Par exemple, la règle ^0 ? (999)$ doit être remplacé par les deux règles suivantes : (999)$ (Translation:$1) et ^0(999)$ (Translation:$1).


### <a name="sample-normalization-rules"></a>Exemples de règles de normalisation

The following table shows sample normalization rules that are written as .NET Framework regular expressions. The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.

<a name="regularexpression"> </a>
**Règles de normalisation à l’aide d’expressions régulières .NET Framework**

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
> Les noms des règles de normalisation indiqués dans le tableau précédent n’incluent pas d’espaces, mais il s’agit d’une question de choix. Le premier nom du tableau, par exemple, aurait pu s'écrire « 5 digit extension » ou « 5-digit Extension » et être toujours valide.

## <a name="related-topics"></a>Rubriques connexes

[Créer et gérer les plans de numérotation](create-and-manage-dial-plans.md)

[Différents types de numéros de téléphone utilisés pour les offres d'appel](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gérer des numéros de téléphone pour votre entreprise](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Conditions générales relatives aux appels d'urgence](emergency-calling-terms-and-conditions.md)

[Étiquette d’exclusion de responsabilité d’appel d’urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
