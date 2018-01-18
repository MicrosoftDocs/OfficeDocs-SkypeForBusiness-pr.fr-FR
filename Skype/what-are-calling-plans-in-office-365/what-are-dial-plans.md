---
title: "Quels sont les plans de numérotation ?"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: "Découvrez comment choisir une pour votre organisation et quel type d’accès appelant les plans (plans de numérotation PSTN appel) sont disponibles avec Office 365.  "
ms.openlocfilehash: ad46cf8f6c204f69cf7f1075f79468ddd37f8268
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="what-are-dial-plans"></a>Quels sont les plans de numérotation ?

[] Un plan de numérotation est un jeu nommé de règles de normalisation qui convertissent les numéros de téléphones appelés par un utilisateur individuel dans un autre format (typiquement E.164) pour l'autorisation et le routage des appels.
  
Un plan de numérotation se compose d’une ou plusieurs règles de normalisation qui définissent comment les exprimée dans différents formats de numéros de téléphone sont traduits en un autre format. La même chaîne de connexion peut être interprétée et traduite différemment dans différents plans de numérotation, selon le plan de numérotation est affecté à un utilisateur donné, le même composé nombre peut être traduit et routé différemment par rapport.
  
Consultez [créer et gérer des plans d’appel de](create-and-manage-dial-plans.md) pour créer et gérer des plans de numérotation des clients.
  
## <a name="tenant-dial-plan-scope"></a>Étendue du plan de numérotation client

L’étendue d’un plan d’accès détermine le niveau hiérarchique auquel le plan de numérotation peut être appliqué. Les étendues sont différentes de celles dans un Skype pour Business Server 2015 déploiement local. Les clients obtiennent le plan d’appel approprié de provisionnement des paramètres qui sont fournies automatiquement lorsque les utilisateurs ouvrir une session sur Skype pour l’activité en ligne. En tant qu’administrateur, vous pouvez gérer et attribuer des niveaux de portée de plan à distance à l’aide du PowerShell distant.
  
Dans Skype pour professionnels en ligne, il existe deux types de plans de numérotation - service de portée et des clients (ce qui est de votre organisation) portée. Un plan d’appel de service portée est défini pour chaque pays/région où le système du téléphone Office 365 est disponible. Le plan de numérotation de pays de service qui correspond à l’emplacement de l’utilisation de Microsoft Office 365 affecté à l’utilisateur est automatiquement affecté à chaque utilisateur. Vous ne pouvez pas modifier le plan de numérotation de pays de service, mais vous pouvez créer des plans de numérotation de portée des clients, qui augmentent le plan de numérotation de pays de service. Comme les clients sont mis en service, ils obtiennent un « plan de numérotation efficace, » qui est une combinaison du plan de numérotation de pays de service et le plan de numérotation de clients étendue de manière appropriée. Par conséquent, il n’est pas nécessaire de définir toutes les règles de normalisation dans les plans de numérotation de clients qu’ils existe peut-être déjà dans le plan de numérotation de pays de service.
  
Les plans de numérotation client peuvent être encore répartis dans deux étendues : l'étendue client ou l'étendue utilisateur. Si un client définit et attribue un plan de numérotation étendu à un utilisateur, cet utilisateur sera alors approvisionné avec un plan de numérotation efficace constitué du plan de numérotation de son pays de service et du plan de numérotation utilisateur qui lui est attribué. Si un client définit un plan de numérotation étendu au client mais n'attribue pas de plan de numérotation étendu à un utilisateur, cet utilisateur sera alors approvisionné avec un plan de numérotation efficace constitué du plan de numérotation de son pays de service et du plan de numérotation client.
  
Voici le modèle d'héritage des plans de numérotation dans Skype Entreprise Online.
  
![How dial plans are inherited in Skype for Business Online.](../images/b2744f33-ebbd-4c23-bfba-1747312ab178.png)
  
Voici les différents plans de numérotation efficace possibles :
  
 **Pays du service** Si aucun plan de numérotation de portée des clients n’est défini et aucun plan de numérotation de portée des utilisateurs de clients n’est affecté à l’utilisateur mis en service, l’utilisateur recevra un plan de numérotation d’efficaces mappé vers le pays de service associé à leur emplacement d’utilisation Office 365.
  
 **Clients Global - pays de Service** Si un plan de numérotation de clients utilisateur est défini, mais pas affecté à un utilisateur, l’utilisateur mis en service reçoit un plan d’accès efficace constitué d’un plan de numérotation de clients fusionnées et le plan de numérotation service pays associés à leur emplacement d’utilisation Office 365.
  
 **Utilisateur de clients - pays de Service** Si un plan de numérotation de clients utilisateur est défini et affecté à un utilisateur, l’utilisateur mis en service reçoit un plan d’accès efficace constitué par le plan de numérotation utilisateur locataire fusionnées et le plan de numérotation service pays associés à leur emplacement d’utilisation Office 365.
  
Consultez [créer et gérer des plans d’appel de](create-and-manage-dial-plans.md) pour créer des plans de numérotation de votre client.
  
## <a name="planning-for-tenant-dial-plans"></a>Planification des plans de numérotation utilisateur

Pour planifier des plans de numérotation personnalisés, procédez comme suit :
  
- **Étape 1** Décider si un personnalisé composer le plan est nécessaire pour améliorer l’expérience de numérotation d’utilisateur. En règle générale, la nécessité d’une consisterait à prendre en charge la numérotation non-E.164, telles que les extensions ou abrégé de numérotation nationale.
    
- **Étape 2** Déterminez si les clients global ou les plans de numérotation utilisateur portée de clients sont nécessaires, ou les deux. Les plans de numérotation utilisateur portée sont nécessaires si les utilisateurs ont des exigences de numérotation locale.
    
- **Étape 3** Identifiez des schémas de numéros valides pour chaque plan de numérotation nécessaire. Les seuls schémas de numéros nécessaires sont ceux qui ne sont pas définis dans les plans de numérotation au niveau du pays de service.
    
- **Étape 4** Développez un modèle d'appellation des plans de numérotation à l'échelle de votre organisation. Adopter un modèle d'appellation standard à toute une organisation permet de s'assurer de la cohérence d'un système et facilite la maintenance et les mises à jour.
    
Le [FastTrack](https://fasttrack.microsoft.com/microsoft365/capabilities?view=voice) a des ressources supplémentaires et partenaires qui peuvent vous aider à la mise en oeuvre des plans de numérotation des clients.
  
## <a name="creating-your-new-tenant-dial-plan"></a>Créer votre plan de numérotation client

Lorsque vous créez un nouveau plan de numérotation client, vous devez entrer les informations requises.
  
### <a name="name-and-simple-name"></a>Nom et Nom simplifié

Pour les plans d’accès utilisateur, vous devez spécifier recevra un nom descriptif qui identifie les utilisateurs le plan de numérotation. Le nom Simple du plan de numérotation est préremplie avec une chaîne qui est dérivée à partir du nom de plan d’accès à distance. Le champ Nom simple peut être modifié, ce qui vous permet de créer une convention d’appellation plus descriptive pour vos plans de numérotation. La valeur de nom Simple ne peut pas être vide et doit être unique. Une meilleure pratique consiste à développer une convention d’appellation pour votre organisation puis d’utiliser cette convention de manière cohérente sur tous les sites et les utilisateurs.
  
### <a name="description"></a>Description

Nous vous recommandons d'écrire le nom habituel, connu, de l'emplacement géographique ou du groupe d'utilisateurs pour lequel le plan de numérotation correspondant s'applique.
  
### <a name="external-access-prefix"></a>Préfixe d'accès extérieur

> [!CAUTION]
> Le préfixe dʼaccès extérieur nʼest actuellement pas pris en charge. 
  
Vous pouvez spécifier un préfixe d'accès extérieur de 1 à 4 caractères (#, * et 0-9) si les utilisateurs doivent composer un ou plusieurs chiffres supplémentaires (par exemple, 9) pour joindre une ligne extérieure.
  
> [!NOTE]
> Si vous spécifiez un préfixe d'accès extérieur, vous n'avez pas besoin de créer une règle de normalisation supplémentaire pour vous adapter au préfixe. 
  
Consultez [créer et gérer des plans d’appel de](create-and-manage-dial-plans.md) pour créer des plans de numérotation de votre client.
  
## <a name="normalization-rules"></a>Règles de normalisation

Les règles de normalisation définissent comment les numéros de téléphone exprimés dans des formats variés doivent être convertis. Une chaîne de numérotation identique peut être interprétée et convertie différemment en fonction du pays d'où elle est composée. Des règles de normalisation peuvent être nécessaires si des utilisateurs ont besoin de composer des numéros extérieurs ou des numéros internes abrégés.
  
Une ou plusieurs règles de normalisation doivent être affectés au plan de numérotation. Règles de normalisation sont mises en correspondance de haut en bas, l’ordre dans lequel ils apparaissent dans un plan de numérotation de clients est important. Par exemple, si un plan de numérotation de clients a 10 règles de normalisation, la logique de correspondance numérique composée sera essayé en commençant par la première règle de normalisation, si il n’est pas une correspondance puis le deuxième et ainsi de suite. Si une correspondance est établie, cette règle est utilisée et qu’il n’y a aucun effort pour le correspond à toutes les autres règles qui sont définies. Un plan de numérotation client donné peut contenir un maximum de 25 règles de normalisation.
  
### <a name="determining-the-required-normalization-rules"></a>Déterminer les règles de normalisation requises

Puisque tout plan de numérotation client est fusionné de manière efficace avec le plan de numérotation du pays de service d'un utilisateur, il est logique d'évaluer les règles de normalisation de celui-ci afin de déterminer quelles sont les règles de normalisation du plan de numérotation client nécessaires. L'applet de commande **Get-CsEffectiveTenantDialPlan** peut être utilisée à cet effet. Cette applet de commande utilise l'identité d'un utilisateur comme paramètre d'entrée et indique en retour toutes les règles de normalisation appliquées à cet utilisateur.
  
### <a name="creating-normalization-rules"></a>Créer des règles de normalisation

Les règles de normalisation utilisent les expressions régulières du .NET Framework pour spécifier les schémas de correspondance numérique que le serveur utilise pour convertir des chaînes de numérotation dans un format E.164 afin d'effectuer une recherche inversée de numéro. Les règles de normalisation peuvent être créées en spécifiant lʼexpression régulière de la correspondance et la conversion à effectuer lorsquʼune correspondance est trouvée. Quand vous avez terminé, vous pouvez entrer un numéro test pour vérifier que la règle de normalisation fonctionne correctement.
  
Pour plus d’informations sur l’utilisation des expressions régulières du.NET Framework, consultez [Expressions régulières du.NET Framework](https://go.microsoft.com/fwlink/p/?linkId=140927).
  
Consultez [créer et gérer des plans d’appel de](create-and-manage-dial-plans.md) pour créer et gérer la normalisation les plans de numérotation des règles pour vos clients.
  
### <a name="sample-normalization-rules"></a>Exemples de règles de normalisation

Le tableau ci-dessous illustre des exemples de règles de normalisation écrites sous la forme d'expressions régulières .NET Framework. Il s'agit uniquement d'exemples qui ne doivent pas être considérés comme une référence normative pour la création de règles de normalisation.
  
 **Règles de normalisation à l’aide d’expressions régulières du.NET Framework**
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Nom de la règle** <br/> |**Description** <br/> |**Schéma de numéro** <br/> |**Conversion** <br/> |**Exemple** <br/> |
|4digitExtension  <br/> |Convertit les extensions à 4 chiffres.  <br/> |^(\\d{4})$  <br/> |+1425555$1  <br/> |0100 est converti en +14255550100  <br/> |
|5digitExtension  <br/> |Convertit les extensions à 5 chiffres.  <br/> |^5(\\d{4})$  <br/> |+1425555$1  <br/> |50100 est converti en +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Convertit les numéros à 7 chiffres en numéros locaux à Redmond.  <br/> |^(\\d{7})$  <br/> |+1425$1  <br/> |5550100 est converti en +14255550100  <br/>|
|RedmondOperator  <br/> |Convertit 0 vers l'Opérateur de Redmond.  <br/> |^0$  <br/> |+14255550100  <br/> |0 est converti en +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Convertit les numéros avec un préfixe on-net (6) et le code du site de Redmond (222).  <br/> |^6222(\\d{4})$  <br/> |+1425555$1  <br/> |62220100 est converti en +14255550100  <br/> |
|5digitRange  <br/> |Convertit les extensions à 5 chiffres avec la plage de chiffres 3-7 inclusive.  <br/> |^([3-7]\\d{4})$  <br/> |+142570$1  <br/> |54567 est converti en +14255554567  <br/> |
|PrefixAdded  <br/> |Ajoute un préfixe pays devant un numéro à 9 chiffres avec des restrictions sur le premier et le troisième chiffre.  <br/> |^([2-9]\\d\\d[2-9]\\d{6})$  <br/> |1$1  <br/> |4255554567 est converti en 14255554567  <br/> |
|NoTranslation  <br/> |Fait correspondre 5 chiffres mais sans conversion.  <br/> |^(\\d{5})$  <br/> |$1  <br/> |34567 est converti en 34567  <br/> |
   
 **Plan de numérotation de Redmond basé sur les règles de normalisation indiquées ci-dessus.**
  
Le tableau suivant illustre un exemple de plan de numérotation pour Redmond, Washington, États-unis, basé sur les règles de normalisation indiquées dans le tableau précédent.
|:-----| | **Plan de numérotation de Redmond** <br/> | | 5digitExtension <br/> | | 7digitcallingRedmond <br/> | | RedmondSitePrefix <br/> | | RedmondOperator <br/> |
   
> [!NOTE]
> Les noms des règles de normalisation indiqués dans le tableau précédent n'incluent pas d'espaces, mais c'est une question de choix. Le premier nom du tableau, par exemple, aurait pu s'écrire « 5 digit extension » ou « 5-digit Extension » et être toujours valide. 
  
## <a name="related-topics"></a>Rubriques connexes
[Créer et gérer des plans de numérotation](create-and-manage-dial-plans.md)

Pour en savoir plus, reportez-vous à la rubrique [Conférence rendez-vous dans Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

[Transfert de questions courantes des numéros de téléphone](transferring-phone-numbers-common-questions.md)

[Différents types de numéros de téléphone utilisés pour les Plans d’appel](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gérer les numéros de téléphone pour votre organisation](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Conditions générales relatives aux appels d'urgence](emergency-calling-terms-and-conditions.md)

[Skype pour Business Online : étiquette de décharge de responsabilité d’appel d’urgence](https://go.microsoft.com/fwlink/?LinkID=692099)
