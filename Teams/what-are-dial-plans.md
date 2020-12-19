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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.dialplans.overview
- Calling Plans
description: 'Apprenez-en davantage sur les types de plans d’appel d’appels RTC disponibles avec les équipes et en choisissant une pour votre organisation.  '
ms.openlocfilehash: 9e6b9930c5106ec143563e0f69dd61ccb30d550c
ms.sourcegitcommit: 9c1f3a72fb166b49a4b68bcdb9a2868bf86ca680
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/19/2020
ms.locfileid: "49718588"
---
# <a name="what-are-dial-plans"></a>Qu’est-ce que les plans de numérotation ?

Un plan de numérotation est un jeu nommé de règles de normalisation qui convertissent les numéros de téléphones appelés par un utilisateur individuel dans un autre format (typiquement E.164) pour l'autorisation et le routage des appels.

Un plan de numérotation se compose d’une ou de plusieurs règles de normalisation qui définissent la façon dont les numéros de téléphone exprimés dans différents formats sont convertis dans un autre format. La même chaîne de numérotation peut être interprétée et traduite différemment selon le plan de numérotation, donc selon le plan de numérotation affecté à un utilisateur donné, le même numéro peut être traduit et routé différemment. Il peut y avoir au maximum un plan de numérotation client 1 000.

Consultez [créer et gérer les plans de numérotation](create-and-manage-dial-plans.md) pour créer et gérer les plans de numérotation client.

## <a name="tenant-dial-plan-scope"></a>Étendue du plan de numérotation client

L'étendue d'un plan de numérotation détermine le niveau hiérarchique auquel celui-ci est appliqué. Les clients obtiennent le plan de numérotation approprié via les paramètres de mise en service fournis automatiquement lorsque les utilisateurs se connectent à Teams. En tant qu’administrateur, vous pouvez gérer et affecter des niveaux d’étendue de plan de numérotation à l’aide du centre d’administration Microsoft teams ou de PowerShell distant.

Dans Teams, il existe deux types de plans de numérotation : à l’étendue du service et dans le cadre de votre organisation. Un plan de numérotation à portée de service est défini pour chaque pays ou région où le système téléphonique est disponible. Un plan de numérotation pays correspondant au lieu d’utilisation attribué à l’utilisateur est automatiquement affecté à chaque utilisateur. Vous ne pouvez pas modifier le plan de numérotation des pays de service, mais vous pouvez créer des plans de numérotation de locataire pour compléter le plan de numérotation pays. À mesure que les clients sont approvisionnés, ils obtiennent un plan de numérotation efficace, qui est une combinaison du plan de numérotation national des services et du plan de numérotation client de portée appropriée. Par conséquent, il n’est pas nécessaire de définir toutes les règles de normalisation dans les plans de numérotation client tels qu’ils existent déjà dans le plan de numérotation des pays de service.

Les plans de numérotation client peuvent être divisés en deux étendues : le client-étendue ou l’étendue utilisateur. Si un client définit et attribue un plan de numérotation d’étendue utilisateur, il est configuré avec un plan de numérotation efficace du plan de numérotation de l’utilisateur et le plan de numérotation de l’utilisateur affecté. Si un client définit un plan de numérotation de niveau client et qu’il n’affecte pas de plan de numérotation, il est mis en place avec un plan de numérotation efficace du plan de numérotation de l’utilisateur et du plan de numérotation client.

Voici le modèle d’héritage des plans de numérotation dans Teams.

![Comment sont hérités les plans de numérotation dans teams](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

Voici les différents plans de numérotation efficace possibles :

 **Pays du service** Si aucun plan de numérotation de locataire n’est défini et qu’aucun plan de numérotation de l’utilisateur n’est affecté à l’utilisateur configuré, l’utilisateur reçoit un plan de numérotation efficace associé au pays de service associé à son lieu d’utilisation.

 **Service global du client-pays** Si un plan de numérotation utilisateur d’un client est défini, mais qu’il n’est pas attribué à un utilisateur, celui-ci recevra un plan de numérotation efficace, composé d’un plan de numérotation client et du plan de numérotation pays de service associés à son lieu d’utilisation.

 **Utilisateur du client-service** Si un plan de numérotation utilisateur d’un client est défini et attribué à un utilisateur, celui-ci recevra un plan de numérotation efficace, composé du plan de numérotation de l’utilisateur du client fusionné et du plan de numérotation pays du service associé à son lieu d’utilisation.

Consultez [créer et gérer les plans de numérotation](create-and-manage-dial-plans.md) pour créer vos plans de numérotation client.

> [!NOTE]
> Dans le cas où il n’y a pas de règles de normalisation de plan de numérotation s’appliquent à un numéro composé, la chaîne numérotée est toujours normalisée pour ajouter le code d’utilisation de l’utilisateur. Cela concerne les offres d’appel, le routage direct et les scénarios de numérotation de conférence RTC.

## <a name="planning-for-tenant-dial-plans"></a>Planification des plans de numérotation utilisateur

Pour planifier des plans de numérotation personnalisés, procédez comme suit :

- **Étape 1** Déterminez si un plan de numérotation personnalisé est requis pour améliorer l’interface de numérotation utilisateur. En règle générale, vous devez prendre en charge une numérotation non-E. 164, par exemple une extension ou une numérotation nationale.

- **Étape 2** Déterminez si les plans de numérotation sont nécessaires pour les utilisateurs généraux ou clients, ou les deux. Les plans de numérotation étendus aux utilisateurs sont nécessaires si les configurations d'appel local sont différentes en fonction des utilisateurs.

- **Étape 3** Identifiez des schémas de numéros valides pour chaque plan de numérotation nécessaire. Les seuls schémas de numéros nécessaires sont ceux qui ne sont pas définis dans les plans de numérotation au niveau du pays de service.

- **Étape 4** Développez un modèle d'appellation des plans de numérotation à l'échelle de votre organisation. Adopter un modèle d'appellation standard à toute une organisation permet de s'assurer de la cohérence d'un système et facilite la maintenance et les mises à jour.


## <a name="creating-your-new-tenant-dial-plan"></a>Créer votre plan de numérotation client

Lorsque vous créez un nouveau plan de numérotation client, vous devez entrer les informations requises.

### <a name="name-and-simple-name"></a>Nom et Nom simplifié

Pour les plans de numérotation des utilisateurs, vous devez spécifier un nom descriptif identifiant les utilisateurs auxquels le plan de numérotation sera attribué. Le nom simple de plan de numérotation est déjà rempli avec une chaîne dérivée du nom du plan de numérotation. Le champ Nom simplifié est modifiable, ce qui vous permet de créer une convention d'appellation plus descriptive pour vos plans de numérotation. La valeur du Nom simplifié ne peut être vide et doit être unique. Les meilleures pratiques suggèrent de développer une convention d'appellation pour l'ensemble de votre organisation et d'utiliser systématiquement cette convention pour tous les sites et tous les utilisateurs.

### <a name="description"></a>Description

Nous vous recommandons d'écrire le nom habituel, connu, de l'emplacement géographique ou du groupe d'utilisateurs pour lequel le plan de numérotation correspondant s'applique.

### <a name="external-access-prefix"></a>Préfixe d'accès extérieur
<a name="bkexternalprefix"> </a>

Vous pouvez spécifier un préfixe d'accès extérieur de 1 à 4 caractères (#, * et 0-9) si les utilisateurs doivent composer un ou plusieurs chiffres supplémentaires (par exemple, 9) pour joindre une ligne extérieure.

> [!NOTE]
> Si vous spécifiez un préfixe d'accès extérieur, vous n'avez pas besoin de créer une règle de normalisation supplémentaire pour vous adapter au préfixe.

Consultez [créer et gérer les plans de numérotation](create-and-manage-dial-plans.md) pour créer vos plans de numérotation client.

## <a name="normalization-rules"></a>Règles de normalisation
<a name="bknormalizationrule"> </a>

Les règles de normalisation définissent comment les numéros de téléphone exprimés dans des formats variés doivent être convertis. Une chaîne de numérotation identique peut être interprétée et convertie différemment en fonction du pays d'où elle est composée. Des règles de normalisation peuvent être nécessaires si des utilisateurs ont besoin de composer des numéros extérieurs ou des numéros internes abrégés.

Vous devez attribuer une ou plusieurs règles de normalisation au plan de numérotation. Les règles de normalisation sont mises en correspondance de haut en bas, de sorte que l’ordre dans lequel elles apparaissent dans un plan de numérotation client est important. Par exemple, si un plan de numérotation client possède 10 règles de normalisation, la logique de correspondance d'un numéro composé sera vérifiée en commençant par la première règle de normalisation, puis, en lʼabsence de correspondance, par la seconde, etc. Si une correspondance est trouvée, cette règle est utilisée et les autres règles définies ne sont pas vérifiées. Un plan de numérotation client peut contenir un maximum de règles de normalisation 50.

### <a name="determining-the-required-normalization-rules"></a>Déterminer les règles de normalisation requises

Dans la mesure où tout plan de numérotation client est fusionné efficacement avec le plan de numérotation du pays d’un utilisateur donné, il est probable que les règles de normalisation de votre plan de numérotation pays doivent être évaluées pour déterminer les règles de normalisation du plan de numérotation client nécessaires. L'applet de commande **Get-CsEffectiveTenantDialPlan** peut être utilisée à cet effet. Cette applet de commande utilise l'identité d'un utilisateur comme paramètre d'entrée et indique en retour toutes les règles de normalisation appliquées à cet utilisateur.

### <a name="creating-normalization-rules"></a>Créer des règles de normalisation
<a name="createrule"> </a>

Les règles de normalisation utilisent des expressions régulières du .NET Framework pour spécifier les modèles de correspondance numérique que le serveur utilise pour convertir les chaînes de numérotation au format E. 164. Les règles de normalisation peuvent être créées en spécifiant lʼexpression régulière de la correspondance et la conversion à effectuer lorsquʼune correspondance est trouvée. Quand vous avez terminé, vous pouvez entrer un numéro test pour vérifier que la règle de normalisation fonctionne correctement.

Pour plus d’informations sur l’utilisation des expressions régulières du .NET Framework, consultez la rubrique [expressions régulières du .NET Framework](https://go.microsoft.com/fwlink/p/?linkId=140927).

Consultez [créer et gérer les plans de numérotation](create-and-manage-dial-plans.md) pour créer et gérer des règles de normalisation pour vos plans de numérotation client.

> [!NOTE]
> Les règles de normalisation avec le premier jeton comme facultatif ne sont actuellement pas prises en charge sur les appareils 3pip (par exemple, Polycom VVX 601 modèle). Si vous voulez appliquer des règles de normalisation avec le mode facultatif sur les appareils 3pip, vous devez créer deux règles de normalisation au lieu d’une seule. Par exemple, la règle ^ 0 ? (999) $ doit être remplacé par les deux règles suivantes : (999) $ (traduction : $1) et ^ 0 (999) $ (traduction : $1).


### <a name="sample-normalization-rules"></a>Exemples de règles de normalisation

Le tableau ci-dessous illustre des exemples de règles de normalisation écrites sous la forme d'expressions régulières .NET Framework. Il s'agit uniquement d'exemples qui ne doivent pas être considérés comme une référence normative pour la création de règles de normalisation.

<a name="regularexpression"> </a> 
 **Règles de normalisation utilisant des expressions régulières du .NET Framework**

| Nom de la règle<br/> | Description<br/> | Type de numéro<br/> | Conversion<br/> | Exemple<br/> |
|:-----|:-----|:-----|:-----|:-----|
|4digitExtension  <br/> |Convertit les extensions à 4 chiffres.  <br/> |^(\\d{4})$  <br/> |+1425555$1  <br/> |0100 est converti en +14255550100  <br/> |
|5digitExtension  <br/> |Convertit les extensions à 5 chiffres.  <br/> |^5(\\d{4})$  <br/> |+1425555$1  <br/> |50100 est converti en +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Convertit les numéros à 7 chiffres en numéros locaux à Redmond.  <br/> |^(\\d{7})$  <br/> |+1425$1  <br/> |5550100 est converti en +14255550100  <br/>|
|RedmondOperator  <br/> |Convertit 0 vers l'Opérateur de Redmond.  <br/> |^0$  <br/> |+14255550100  <br/> |0 est converti en +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Convertit les numéros avec un préfixe on-net (6) et le code du site de Redmond (222).  <br/> |^6222(\\d{4})$  <br/> |+1425555$1  <br/> |62220100 est converti en +14255550100  <br/> |
|5digitRange  <br/> |Convertit les extensions à 5 chiffres avec la plage de chiffres 3-7 inclusive.  <br/> |^([3-7]\\d{4})$  <br/> |commande + 142555 $1 <br/> |54567 est converti en +14255554567  <br/> |
|PrefixAdded  <br/> |Ajoute un préfixe pays devant un numéro à 9 chiffres avec des restrictions sur le premier et le troisième chiffre.  <br/> |^([2-9]\\d\\d[2-9]\\d{6})$  <br/> |1$1  <br/> |4255554567 est converti en 14255554567  <br/> |
|Très traduction  <br/> |Fait correspondre 5 chiffres mais sans conversion.  <br/> |^(\\d{5})$  <br/> |$1  <br/> |34567 est converti en 34567  <br/> |

 **Plan de numérotation de Redmond basé sur les règles de normalisation indiquées ci-dessus.**

 Le tableau suivant illustre un exemple de plan de numérotation pour Redmond, Washington, États-unis, basé sur les règles de normalisation indiquées dans le tableau précédent.

| Plan de numérotation de Redmond<br/> |
|:-----------------------|                                                                                                                      
| 5digitExtension <br/> |                                                                                                                                    
| 7digitcallingRedmond <br/> |
| RedmondSitePrefix <br/> |
| RedmondOperator <br/> |

> [!NOTE]
> Les noms des règles de normalisation indiquées dans le tableau précédent n’incluent aucun espace, mais il s’agit d’une question de choix. Le premier nom du tableau, par exemple, aurait pu s'écrire « 5 digit extension » ou « 5-digit Extension » et être toujours valide.

## <a name="related-topics"></a>Sujets associés

[Créer et gérer les plans de numérotation](create-and-manage-dial-plans.md)

[Différents types de numéros de téléphone utilisés pour les offres d'appel](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gérer des numéros de téléphone pour votre entreprise](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Conditions générales relatives aux appels d'urgence](emergency-calling-terms-and-conditions.md)

[Libellé d’exclusion d’appel d’urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
