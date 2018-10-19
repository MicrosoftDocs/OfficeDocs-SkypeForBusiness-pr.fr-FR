---
title: Qu'est-ce que les plans de numérotation ?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Découvrez comment choisir votre organisation et quel type de numérotation appelant plans (plans de numérotation appel PSTN) sont disponibles avec Office 365.  '
ms.openlocfilehash: a823e3665229eeb1292c4f027bda7d7e8eff79a9
ms.sourcegitcommit: 044286f9dec2743a622bdaeac03469418cfdfa0d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/19/2018
ms.locfileid: "25678425"
---
# <a name="what-are-dial-plans"></a>Qu'est-ce que les plans de numérotation ?

Un plan de numérotation est un jeu nommé de règles de normalisation qui convertissent les numéros de téléphones appelés par un utilisateur individuel dans un autre format (typiquement E.164) pour l'autorisation et le routage des appels.

Un plan de numérotation se compose d’une ou plusieurs règles de normalisation qui définissent comment les numéros de téléphone exprimés sous différents formats sont converties en un autre format. La même chaîne de numérotation peut être interprétée et convertie différemment dans différents plans de numérotation, afin que, selon le plan de numérotation est attribué à un utilisateur donné, les mêmes composé numéro peut être traduit routé différemment.

Voir [créer et gérer des plans de numérotation](create-and-manage-dial-plans.md) pour créer et gérer des plans de numérotation client.

## <a name="tenant-dial-plan-scope"></a>Étendue du plan de numérotation client

L'étendue d'un plan de numérotation détermine le niveau hiérarchique auquel celui-ci est appliqué. Les étendues sont différentes de celles d’un Skype pour le déploiement local de Business Server. Les clients obtiennent le plan de numérotation approprié via les paramètres dʼapprovisionnement qui sont automatiquement fournis lorsque les utilisateurs se connectent à Skype Entreprise Online. En tant qu'administrateur, vous pouvez gérer et attribuer les niveaux d'étendue des plans de numérotation en utilisant une session PowerShell à distance.

Dans Skype pour Business Online, il existe deux types de plans de numérotation - service étendue et le client (c'est-à-dire pour votre organisation) étendue. Un plan de numérotation service étendue est défini pour chaque pays/région dans lequel le système de téléphone Office 365 est disponible. Le plan de numérotation pays service qui correspond à l’emplacement de l’utilisation de Office 365 attribuées à l’utilisateur est automatiquement affecté à chaque utilisateur. Vous ne pouvez pas modifier le plan de numérotation de pays de service, mais vous pouvez créer des plans de numérotation client étendue, lesquels augmentent le plan de numérotation service pays. Comme les clients sont configurés, ils obtiennent un « plan de numérotation effectives, » qui est une combinaison du plan de numérotation de pays de service et le plan de numérotation client correctement sur lesquelles porte. Il nʼest donc pas nécessaire de définir toutes les règles de normalisation dans les plans de numérotation client car elles peuvent déjà exister dans le plan de numérotation du pays de service.

Les plans de numérotation client peuvent être encore répartis dans deux étendues : l'étendue client ou l'étendue utilisateur. Si un client définit et attribue un plan de numérotation étendu à un utilisateur, cet utilisateur sera alors approvisionné avec un plan de numérotation efficace constitué du plan de numérotation de son pays de service et du plan de numérotation utilisateur qui lui est attribué. Si un client définit un plan de numérotation étendu au client mais n'attribue pas de plan de numérotation étendu à un utilisateur, cet utilisateur sera alors approvisionné avec un plan de numérotation efficace constitué du plan de numérotation de son pays de service et du plan de numérotation client.

Voici le modèle d'héritage des plans de numérotation dans Skype Entreprise Online.

![How dial plans are inherited in Skype for Business Online.](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

Voici les différents plans de numérotation efficace possibles :

 **Pays du service** Si aucun plan de numérotation client étendue n’est définie et aucun plan de numérotation de client utilisateur étendue n’est attribuée à l’utilisateur mis en service, l’utilisateur reçoit un plan de numérotation efficaces mappé au pays de service associé à leur emplacement d’utilisation Office 365.

 **Client Global - pays de Service** Si un plan de numérotation utilisateur client est défini, mais pas attribué à un utilisateur, l’utilisateur mis en service reçoit un plan de numérotation effectives constitué d’un plan de numérotation client fusionnée et le plan de numérotation pays service associé à leur emplacement d’utilisation Office 365.

 **Client utilisateur - pays de Service** Si un plan de numérotation utilisateur client est défini et affecté à un utilisateur, l’utilisateur mis en service reçoit un plan de numérotation effectives comprenant le plan de numérotation utilisateur fusionnée client et le plan de numérotation pays service associé à leur emplacement d’utilisation Office 365.

Voir [créer et gérer des plans de numérotation](create-and-manage-dial-plans.md) pour créer des plans de numérotation de votre client.

## <a name="planning-for-tenant-dial-plans"></a>Planification des plans de numérotation utilisateur

Pour planifier des plans de numérotation personnalisés, procédez comme suit :

- **Étape 1** Décider si un fichier personnalisé de numérotation plan est nécessaire pour améliorer l’utilisateur de l’expérience de numérotation. En règle générale, la nécessité d’une serait pour prendre en charge la numérotation non E.164, tels que des extensions ou abrégé composer le numéro national.

- **Étape 2** Déterminer si le client globale ou des plans de numérotation utilisateur étendue client sont nécessaires, ou les deux. Les plans de numérotation étendus aux utilisateurs sont nécessaires si les configurations d'appel local sont différentes en fonction des utilisateurs.

- **Étape 3** Identifiez des schémas de numéros valides pour chaque plan de numérotation nécessaire. Les seuls schémas de numéros nécessaires sont ceux qui ne sont pas définis dans les plans de numérotation au niveau du pays de service.

- **Étape 4** Développez un modèle d'appellation des plans de numérotation à l'échelle de votre organisation. Adopter un modèle d'appellation standard à toute une organisation permet de s'assurer de la cohérence d'un système et facilite la maintenance et les mises à jour.

Le [FastTrack](https://fasttrack.microsoft.com/microsoft365/capabilities?view=voice) dispose des ressources supplémentaires et les partenaires qui peuvent vous aider à implémenter des plans de numérotation client.

## <a name="creating-your-new-tenant-dial-plan"></a>Créer votre plan de numérotation client

Lorsque vous créez un nouveau plan de numérotation client, vous devez entrer les informations requises.

### <a name="name-and-simple-name"></a>Nom et Nom simplifié

Pour les plans de numérotation utilisateur, vous devez spécifier un nom descriptif qui identifie les utilisateurs le plan de numérotation sera attribué. Le Nom simplifié du plan de numérotation est prérempli par une chaîne dérivée du nom du plan de numérotation. Le champ Nom simplifié est modifiable, ce qui vous permet de créer une convention d'appellation plus descriptive pour vos plans de numérotation. La valeur du Nom simplifié ne peut être vide et doit être unique. Les meilleures pratiques suggèrent de développer une convention d'appellation pour l'ensemble de votre organisation et d'utiliser systématiquement cette convention pour tous les sites et tous les utilisateurs.

### <a name="description"></a>Description

Nous vous recommandons d'écrire le nom habituel, connu, de l'emplacement géographique ou du groupe d'utilisateurs pour lequel le plan de numérotation correspondant s'applique.

### <a name="external-access-prefix"></a>Préfixe d'accès extérieur

> [!CAUTION]
> Le préfixe dʼaccès extérieur nʼest actuellement pas pris en charge. 

Vous pouvez spécifier un préfixe d'accès extérieur de 1 à 4 caractères (#, * et 0-9) si les utilisateurs doivent composer un ou plusieurs chiffres supplémentaires (par exemple, 9) pour joindre une ligne extérieure.

> [!NOTE]
> Si vous spécifiez un préfixe d'accès extérieur, vous n'avez pas besoin de créer une règle de normalisation supplémentaire pour vous adapter au préfixe. 

Voir [créer et gérer des plans de numérotation](create-and-manage-dial-plans.md) pour créer des plans de numérotation de votre client.

## <a name="normalization-rules"></a>Règles de normalisation

Les règles de normalisation définissent comment les numéros de téléphone exprimés dans des formats variés doivent être convertis. Une chaîne de numérotation identique peut être interprétée et convertie différemment en fonction du pays d'où elle est composée. Des règles de normalisation peuvent être nécessaires si des utilisateurs ont besoin de composer des numéros extérieurs ou des numéros internes abrégés.

Vous devez attribuer une ou plusieurs règles de normalisation au plan de numérotation. Règles de normalisation sont mises en correspondance de haut en bas, l’ordre dans lequel ils apparaissent dans un plan de numérotation client est important. Par exemple, si un plan de numérotation client possède 10 règles de normalisation, la logique de correspondance d'un numéro composé sera vérifiée en commençant par la première règle de normalisation, puis, en lʼabsence de correspondance, par la seconde, etc. Si une correspondance est trouvée, cette règle est utilisée et les autres règles définies ne sont pas vérifiées. Dans un plan de numérotation client donné, il peut y avoir jusqu'à 25 règles de normalisation.

### <a name="determining-the-required-normalization-rules"></a>Déterminer les règles de normalisation requises

Puisque tout plan de numérotation client est fusionné de manière efficace avec le plan de numérotation du pays de service d'un utilisateur, il est logique d'évaluer les règles de normalisation de celui-ci afin de déterminer quelles sont les règles de normalisation du plan de numérotation client nécessaires. L'applet de commande **Get-CsEffectiveTenantDialPlan** peut être utilisée à cet effet. Cette applet de commande utilise l'identité d'un utilisateur comme paramètre d'entrée et indique en retour toutes les règles de normalisation appliquées à cet utilisateur.

### <a name="creating-normalization-rules"></a>Créer des règles de normalisation

Les règles de normalisation utilisent les expressions régulières du .NET Framework pour spécifier les schémas de correspondance numérique que le serveur utilise pour convertir des chaînes de numérotation dans un format E.164 afin d'effectuer une recherche inversée de numéro. Les règles de normalisation peuvent être créées en spécifiant lʼexpression régulière de la correspondance et la conversion à effectuer lorsquʼune correspondance est trouvée. Quand vous avez terminé, vous pouvez entrer un numéro test pour vérifier que la règle de normalisation fonctionne correctement.

Pour plus d’informations sur l’utilisation d’expressions régulières .NET Framework, consultez [Expressions régulières .NET Framework](https://go.microsoft.com/fwlink/p/?linkId=140927).

Voir [créer et gérer des plans de numérotation](create-and-manage-dial-plans.md) pour créer et gérer la normalisation des plans de numérotation règles pour votre client.

### <a name="sample-normalization-rules"></a>Exemples de règles de normalisation

Le tableau ci-dessous illustre des exemples de règles de normalisation écrites sous la forme d'expressions régulières .NET Framework. Il s'agit uniquement d'exemples qui ne doivent pas être considérés comme une référence normative pour la création de règles de normalisation.

 **Règles de normalisation à l’aide d’expressions régulières .NET Framework**

||||||
|:-----|:-----|:-----|:-----|:-----|
|**Nom de la règle** <br/> |**Description** <br/> |**Schéma de numéro** <br/> |**Conversion** <br/> |**Exemple** <br/> |
|4digitExtension  <br/> |Convertit les extensions à 4 chiffres.  <br/> |^(\\d{4})$  <br/> |+1425555$1  <br/> |0100 est converti en +14255550100  <br/> |
|5digitExtension  <br/> |Convertit les extensions à 5 chiffres.  <br/> |^5(\\d{4})$  <br/> |+1425555$1  <br/> |50100 est converti en +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Convertit les numéros à 7 chiffres en numéros locaux à Redmond.  <br/> |^(\\d{7})$  <br/> |+1425$1  <br/> |5550100 est converti en +14255550100  <br/>|
|RedmondOperator  <br/> |Convertit 0 vers l'Opérateur de Redmond.  <br/> |^0$  <br/> |+14255550100  <br/> |0 est converti en +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Convertit les numéros avec un préfixe on-net (6) et le code du site de Redmond (222).  <br/> |^6222(\\d{4})$  <br/> |+1425555$1  <br/> |62220100 est converti en +14255550100  <br/> |
|5digitRange  <br/> |Convertit les extensions à 5 chiffres avec la plage de chiffres 3-7 inclusive.  <br/> |^([3-7]\\d{4})$  <br/> |+ 142555$ 1 <br/> |54567 est converti en +14255554567  <br/> |
|PrefixAdded  <br/> |Ajoute un préfixe pays devant un numéro à 9 chiffres avec des restrictions sur le premier et le troisième chiffre.  <br/> |^([2-9]\\d\\d[2-9]\\d{6})$  <br/> |1$1  <br/> |4255554567 est converti en 14255554567  <br/> |
|NoTranslation  <br/> |Fait correspondre 5 chiffres mais sans conversion.  <br/> |^(\\d{5})$  <br/> |$1  <br/> |34567 est converti en 34567  <br/> |

 **Plan de numérotation de Redmond basé sur les règles de normalisation indiquées ci-dessus.**


| Le tableau suivant illustre un exemple de plan de numérotation pour Redmond, Washington, États-unis, basé sur les règles de normalisation indiquées dans le tableau précédent. |
|:---------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Plan de numérotation de Redmond** <br/>                                                                                                                              |
| 5digitExtension <br/>                                                                                                                                    |
| 7digitcallingRedmond <br/>                                                                                                                               |
| RedmondSitePrefix <br/>                                                                                                                                  |
| RedmondOperator <br/>                                                                                                                                    |

> [!NOTE]
> Les noms des règles de normalisation indiqués dans le tableau précédent n'incluent pas d'espaces, mais c'est une question de choix. Le premier nom du tableau, par exemple, aurait pu s'écrire « 5 digit extension » ou « 5-digit Extension » et être toujours valide. 


## <a name="related-topics"></a>Rubriques connexes

[Créer et gérer les plans de numérotation](create-and-manage-dial-plans.md)

[Questions fréquentes à propos du transfert de numéros de téléphone](transferring-phone-numbers-common-questions.md)

[Différents types de numéros de téléphone utilisés pour les offres d'appel](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gérer les numéros de téléphone de votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
[Conditions générales relatives aux appels d'urgence](emergency-calling-terms-and-conditions.md)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)