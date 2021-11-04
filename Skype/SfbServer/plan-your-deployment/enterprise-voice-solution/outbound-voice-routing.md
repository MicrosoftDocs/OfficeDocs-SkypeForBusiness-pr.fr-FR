---
title: Planifier le routage des voix sortantes dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
description: Découvrez le routage des appels sortants dans Skype Entreprise Server Voix Entreprise, notamment les paramètres de routage des appels, les plans de numérotation, les règles de normalisation, les stratégies de voix, les enregistrements d’utilisation PSTN et les itinéraires des messages vocaux.
ms.openlocfilehash: 47b0b196579d69612c3c9d62c8ca9aade008535e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759506"
---
# <a name="plan-for-outbound-voice-routing-in-skype-for-business-server"></a>Planifier le routage des voix sortantes dans Skype Entreprise Server
 
Découvrez le routage des appels sortants dans Skype Entreprise Server Voix Entreprise, notamment les paramètres de routage des appels, les plans de numérotation, les règles de normalisation, les stratégies de voix, les enregistrements d’utilisation PSTN et les itinéraires des messages vocaux.
  
Le routage des appels sortants s’applique aux appels Voix Entreprise qui sont destinés à une passerelle, une passerelle PSTN (réseau téléphonique commuté), une trunke ou un PBX (Private Branch Exchange). Lorsqu’un Skype Entreprise passe un appel, le serveur normalise le numéro de téléphone au format E.164, si nécessaire, et tente de le faire correspondre à un URI SIP. Si le serveur ne parvient pas à établir de correspondance, il applique la logique de routage des appels sortants en fonction de la chaîne de numérotation fournie. Les paramètres de serveur du tableau ci-dessous permettent de configurer la logique de routage des appels sortants.
  
**Skype Entreprise Server Routage des appels sortants Paramètres**

|**Objet**|**Description**|
|:-----|:-----|
|Plan de numérotation  <br/> |Un plan de numérotation est un ensemble nommé de règles de normalisation qui convertissent des numéros de téléphone pour un emplacement, un utilisateur individuel ou un objet contact nommé, en un format standard (E.164) à des fins d’autorisation téléphonique et de routage des appels.  <br/> |
|Règle de normalisation  <br/> |Les règles de normalisation définissent la façon dont les numéros de téléphone exprimés en divers formats sont acheminés vers chaque emplacement, utilisateur ou objet contact. La même chaîne de numérotation peut être interprétée et traduite différemment selon l’emplacement d’origine de la numérotation et la personne ou l’objet contact passant l’appel. Un ensemble de règles de normalisation associées à un emplacement particulier constitue un plan de numérotation.  <br/> |
|Stratégie de la voix  <br/> |Une stratégie de voix associe un ou plusieurs enregistrements d’utilisation PSTN à un utilisateur ou groupe d’utilisateurs. Elle fournit également une liste de fonctionnalités d’appel que vous pouvez activer ou désactiver.  <br/> |
|Enregistrement d’utilisation PSTN  <br/> |Un enregistrement d’utilisation PTSN indique une classe d’appel (interne, local ou longue distance) qui peut être passée par différents utilisateurs, ou groupes d’utilisateurs, dans une organisation.  <br/> |
|Itinéraire d’appel  <br/> |Un itinéraire d’appel associe les numéros de téléphone cibles à des jonctions et des enregistrements d’utilisation PTSN spécifiques. Une passerelle PSTN est considérée comme une jonction.  <br/> |
   
## <a name="dial-plans-and-normalization-rules"></a>Plans de numérotation et règles de normalisation

Un plan de numérotation est un ensemble nommé de règles de normalisation qui convertissent des numéros de téléphone pour un emplacement, un utilisateur individuel ou un objet contact nommé, en un format standard (E.164) à des fins d’autorisation téléphonique et de routage des appels. 
  
Les règles de normalisation définissent la façon dont les numéros de téléphone exprimés en divers formats sont routés vers chaque emplacement, utilisateur ou objet contact. La même chaîne de numérotation peut être interprétée et traduite différemment, selon l’emplacement à partir duquel elle est composé et la personne ou l’objet contact qui passe l’appel.
  
### <a name="dial-plan-scope"></a>Étendue du plan de numérotation

L’étendue d’un plan de numérotation détermine le niveau hiérarchique auquel le plan de numérotation peut être appliqué. Dans Skype Entreprise Server, un plan de numérotation par utilisateur spécifique peut être affecté à un utilisateur. Si un plan de numérotation utilisateur n’est pas affecté, le plan de numérotation du pool frontal est appliqué. S’il n’existe aucun plan de numérotation de pool frontal, le plan de numérotation de site est appliqué. Enfin, si aucun autre plan de numérotation n’est applicable à l’utilisateur, le plan de numérotation global est appliqué.
  
Les clients obtiennent les niveaux d’étendue du plan de numérotation par le biais des paramètres d’approvisionnement de la bande in-band fournis lorsque les utilisateurs se connectent Skype Entreprise. En tant qu’administrateur, vous pouvez gérer et affecter des niveaux d’étendue de plan de numérotation à l’aide Skype Entreprise Server Panneau de contrôle.
  
> [!NOTE]
> Le plan de numérotation de passerelle de réseau téléphonique commuté (PSTN) au niveau du service est appliqué aux appels entrants provenant d’une passerelle particulière. 
  
Les niveaux d’étendue du plan de numérotation sont définis comme suit :
  
- **Plan de numérotation** utilisateur : peut être affecté à des utilisateurs individuels, des groupes ou des objets contact. Les applications vocales peuvent rechercher un plan de numérotation par utilisateur lorsqu’un appel est reçu avec le contexte téléphonique par défaut de l’utilisateur. Dans le but d’affecter un plan de numérotation, un objet contact est traité comme un utilisateur individuel.
    
- **Plan de numérotation** de pool : peut être créé au niveau du service pour une passerelle PSTN ou un bureau d’enregistrement dans votre topologie. Pour définir un plan de numérotation de pool, vous devez spécifier le service particulier (passerelle PSTN ou pool de bureaux d’inscriptions) auquel s’applique le plan de numérotation. 
    
- **Plan de numérotation** de site : peut être créé pour un site entier, à l’exception des utilisateurs, groupes ou objets contact affectés à un plan de numérotation de pool ou à un plan de numérotation utilisateur. Pour définir un plan de numérotation de site, vous devez spécifier le site auquel le plan de numérotation s’applique.
    
- **Plan de numérotation global**: plan de numérotation par défaut installé avec le produit. Vous pouvez modifier le plan de numérotation global, mais vous ne pouvez pas le supprimer. Ce plan de numérotation s’applique à tous les Voix Entreprise utilisateurs, groupes et objets contact de votre déploiement, sauf si vous configurez et affectez un plan de numérotation avec une étendue plus spécifique.
    
### <a name="planning-for-dial-plans"></a>Planification des plans de numérotation

Pour planifier un plan de numérotation, suivez les étapes suivantes :
  
- List all the locales in which your organization has an office.
    
    La liste doit être à jour et complète. Il devra être révisé à mesure que l’organisation évolue. Dans une grande entreprise multinationale avec de nombreuses petites succursales, cette tâche peut prendre beaucoup de temps.
    
- Identifiez les modèles de numéro valides pour chaque site.
    
    La partie la plus longue de la planification de vos plans de numérotation consiste à identifier les modèles de numéros valides pour chaque site. Dans certains cas, vous pouvez copier les règles de normalisation que vous avez écrites pour un plan de numérotation vers d’autres plans de numérotation, en particulier si les sites correspondants se trouve dans le même pays/la même région ou même le même continent. Dans d’autres cas, de petites modifications apportées aux numéros d’un plan de numérotation peuvent suffire à les utiliser dans d’autres plans de numérotation.
    
- Développer un schéma à l’échelle de l’organisation pour nommer des plans de numérotation.
    
    L’adoption d’un schéma d’attribution de noms standard garantit la cohérence au sein d’une organisation et facilite la maintenance et les mises à jour.
    
- Déterminez si plusieurs plans de numérotation sont requis pour un seul emplacement. 
    
    Si votre organisation maintient un plan de numérotation unique sur plusieurs emplacements, vous devrez peut-être créer un plan de numérotation distinct pour les utilisateurs Voix Entreprise qui migrent à partir d’un pbX (private branch exchange) et qui doivent conserver leurs extensions existantes.
    
- Déterminez si des plans de numérotation par utilisateur sont requis. Par exemple, si des utilisateurs d’un site de succursale sont inscrits auprès du site central ou si des utilisateurs sont inscrits sur un Survivable Branch Appliance, vous pouvez envisager des scénarios de numérotation spéciaux pour ces utilisateurs à l’aide de plans de numérotation et de règles de normalisation par utilisateur. Pour plus d’informations, [voir Plan for Voix Entreprise resiliency in Skype Entreprise Server](enterprise-voice-resiliency.md).
    
- Déterminer l’étendue du plan de numérotation (comme décrit précédemment dans cette rubrique).
    
Pour créer un plan de numérotation, vous devez spécifier des valeurs dans les champs suivants, le cas échéant, à l’aide du Panneau de Skype Entreprise Server ou de Skype Entreprise Server Management Shell.
  
#### <a name="name-and-simple-name"></a>Nom et nom simple

Pour les plans de numérotation utilisateur, vous devez spécifier un nom descriptif qui identifie les utilisateurs, les groupes ou les objets contact auquel le plan de numérotation sera affecté. Pour les plans de numérotation de site, le champ Nom est pré-rempli avec le nom du site et ne peut pas être modifié. Pour les plans de numérotation de pool, le champ Nom est pré-rempli avec la passerelle PSTN ou le nom de domaine complet du pool frontal et ne peut pas être modifié.
  
Le nom simple du plan de numérotation est pré-rempli avec une chaîne dérivée du nom du plan de numérotation. Le champ Nom simple est modifiable, ce qui vous permet de créer une convention d’attribution de noms plus descriptive pour vos plans de numérotation. La valeur Nom de l’exemple ne peut pas être vide et doit être unique. Une meilleure pratique consiste à développer une convention d’attribution de noms pour l’ensemble de votre organisation, puis à utiliser cette convention de manière cohérente sur tous les sites et tous les utilisateurs.
  
#### <a name="description"></a>Description

Nous vous recommandons de taper le nom commun et reconnaissable de l’emplacement géographique auquel s’applique le plan de numérotation correspondant. Par exemple, si le nom du plan de numérotation London.Contoso.com, la description recommandée est Londres. 
  
#### <a name="dial-in-conferencing-region"></a>Région de conférences téléphoniques

Si vous déployez des conférences téléphoniques, vous devez spécifier une région de conférence d’accès pour associer des numéros d’accès aux conférences à un plan de numérotation. 
  
#### <a name="external-access-prefix"></a>Préfixe d’accès externe

Vous pouvez spécifier un préfixe d’accès externe de quatre caractères au plus (#, et 0-9) si les utilisateurs doivent composer un ou plusieurs chiffres de début supplémentaires \* (par exemple, 9) pour obtenir une ligne externe.
  
> [!NOTE]
> Si vous spécifiez un préfixe d’accès externe, vous n’avez pas besoin de créer une règle de normalisation supplémentaire pour prendre en charge le préfixe. 
  
### <a name="normalization-rules"></a>Règles de normalisation

Les règles de normalisation définissent la façon dont les numéros de téléphone exprimés dans différents formats doivent être acheminés pour l’emplacement nommé. La même chaîne de numéros peut être interprétée et traduite différemment, en fonction des paramètres régionaux à partir des lesquels elle est composé. Les règles de normalisation sont nécessaires pour le routage des appels, car les utilisateurs peuvent et utilisent différents formats lors de la saisie de numéros de téléphone dans leurs listes de contacts.
  
La normalisation des numéros de téléphone fournis par l’utilisateur fournit un format cohérent qui facilite les tâches suivantes :
  
- Faire correspondre un numéro composé à l’URI SIP du destinataire prévu.
    
- Appliquer des règles d’autorisation de numérotation à l’appelant.
    
Les champs de nombre suivants sont parmi ceux que vos règles de normalisation devront peut-être prendre en compte :
  
- Plan de numérotation
    
- Code pays
    
- Code de zone
    
- Longueur de l’extension
    
- Préfixe de site
    
#### <a name="creating-normalization-rules"></a>Création de règles de normalisation

Les règles de normalisation utilisent .NET Framework expressions régulières pour spécifier des modèles de correspondance numérique que le serveur utilise pour traduire les chaînes de numérotation au format E.164 dans le but d’effectuer une recherche inversée de numéros. Vous créez des règles de normalisation dans le Panneau de Skype Entreprise Server en entrant les expressions manuellement ou en entrant les chiffres de début et la longueur des chaînes de numérotation à mettre en correspondance et en laissant le Panneau de Skype Entreprise Server générer l’expression régulière correspondante à votre place. Dans les deux cas, lorsque vous avez terminé, vous pouvez entrer un numéro de test pour vérifier que la règle de normalisation fonctionne comme prévu.
  
Pour plus d’informations sur l.NET Framework expressions régulières, voir « [.NET Framework Expressions régulières](/dotnet/standard/base-types/regular-expressions)».
  
#### <a name="sample-normalization-rules"></a>Exemples de règles de normalisation
<a name="BKMK_SampleNormalizationRules"> </a>

Le tableau suivant présente des exemples de règles de normalisation écrites sous la .NET Framework expressions régulières. Les exemples sont des exemples uniquement et ne sont pas destinés à être une référence normative pour la création de vos propres règles de normalisation.
  
**Tableau 1.Règles de normalisation utilisant .NET Framework expressions régulières**

|**Nom de la règle**|**Description**|**Modèle de numéro**|**Traduction**|**Exemple**|
|:-----|:-----|:-----|:-----|:-----|
|4digitExtension  <br/> |Traduit les extensions à 4 chiffres  <br/> |^(\d{4})$  <br/> |+1425555$1  <br/> |0100 est converti en +14255550100  <br/> |
|5digitExtension  <br/> |Traduit les extensions à 5 chiffres  <br/> |^5(\d {4} )$  <br/> |+1425555$1  <br/> |50100 est converti en +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Traduit les numéros à 7 chiffres en numéros locaux Redmond  <br/> |^(\d{7})$  <br/> |+1425$1  <br/> |5550100 est converti en +14255550100  <br/> |
|7digitcallingDallas  <br/> |Traduit les numéros à 7 chiffres en numéros locaux Dallas  <br/> |^(\d{7})$  <br/> |+1972$1  <br/> |5550100 est converti en +19725550100  <br/> |
|10digitcallingUS  <br/> |Traduit les numéros à 10 chiffres aux États-Unis  <br/> |^(\d{10})$  <br/> |+1$1  <br/> |2065550100 est converti en +12065550100  <br/> |
|LDCallingUS  <br/> |Traduit les nombres avec des préfixes longue distance aux États-Unis  <br/> |^1(\d {10} )$  <br/> |+$1  <br/> |12145550100 est converti en +2145550100  <br/> |
|IntlCallingUS  <br/> |Traduit des nombres avec des préfixes internationaux aux États-Unis  <br/> |^011(\d \* )$  <br/> |+$1  <br/> |01191445550100 est converti en +91445550100  <br/> |
|RedmondOperator  <br/> |Traduit 0 en Opérateur Redmond  <br/> |^0$  <br/> |+14255550100  <br/> |0 est converti en +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Traduit les numéros avec le préfixe sur net (6) et le code de site redmond (222)  <br/> |^6222(\d {4} )$  <br/> |+1425555$1  <br/> |62220100 est converti en +14255550100  <br/> |
|NYSitePrefix  <br/> |Traduit les numéros avec le préfixe sur net (6) et le code de site NY (333)  <br/> |^6333(\d {4} )$  <br/> |+1202555$1  <br/> |63330100 est converti en +12025550100  <br/> |
|DallasSitePrefix  <br/> |Traduit les numéros avec le préfixe sur net (6) et le code de site Dallas (444)  <br/> |^6444(\d {4} )$  <br/> |+1972555$1  <br/> |64440100 est converti en +19725550100  <br/> |
   
Le tableau suivant illustre un exemple de plan de numérotation pour Redmond, Washington, États-Unis, basé sur les règles de normalisation indiquées dans le tableau précédent.
  
**Tableau 2. Plan de numérotation de Redmond basé sur les règles de normalisation indiquées dans le tableau 1**

|**Redmond.forestFQDN**|
|:-----|
|5digitExtension  <br/> |
|7digitcallingRedmond  <br/> |
|10digitcallingUS  <br/> |
|IntlCallingUS  <br/> |
|RedmondSitePrefix  <br/> |
|NYSitePrefix  <br/> |
|DallasSitePrefix  <br/> |
|RedmondOperator  <br/> |
   
> [!NOTE]
> Les noms des règles de normalisation indiqués dans le tableau précédent n’incluent pas d’espaces, mais il s’agit d’une question de choix. Le prénom du tableau, par exemple, peut avoir été écrit « Poste à 5 chiffres » ou « Poste à 5 chiffres » et être toujours valide. 
  
## <a name="voice-policies"></a>Stratégies de voix

Skype Entreprise Server de voix définissent les stratégies suivantes pour chaque utilisateur, site ou organisation affecté à la stratégie :
  
- Ensemble de fonctionnalités d’appel qui peuvent être activées ou désactivées pour déterminer Voix Entreprise fonctionnalités disponibles pour les utilisateurs.
    
- un ensemble d’enregistrements de l’utilisation du réseau téléphonique commuté (RTC) qui définissent le type des appels autorisés. 
    
Les étapes suivantes vous aideront à planifier les stratégies de voix dont vous aurez besoin pour Voix Entreprise déploiement :
  
- Déterminez la configuration prévue de votre stratégie de voix globale (stratégie de voix par défaut installée avec le produit). Cette stratégie s’applique à tous Voix Entreprise utilisateurs qui ne sont pas explicitement affectés à une stratégie au niveau du site ou par utilisateur.
    
- Identifiez les stratégies de voix de niveau site dont vous avez éventuellement besoin.
    
- Identifiez les stratégies de voix par utilisateur dont vous avez éventuellement besoin.
    
- Décidez des fonctionnalités d’appel à activer pour chaque stratégie de voix.
    
- Déterminez les enregistrements d’utilisation DNS à configurer pour chaque stratégie de voix.
    
### <a name="voice-policy-scope"></a>Étendue de stratégie de voix

L’étendue de stratégie de voix détermine le niveau hiérarchique auquel la stratégie peut être appliquée. Dans Skype Entreprise Server, vous pouvez configurer des stratégies de voix avec les niveaux d’étendue suivants (répertoriés du plus spécifique au plus général).
  
- Une **stratégie de voix d’utilisateur** peut être affectée à des utilisateurs individuels, à des groupes ou à des objets contact. Il s’agit de la stratégie de plus bas niveau. Les stratégies de voix d’utilisateur peuvent être déployées afin d’activer des fonctionnalités pour certains utilisateurs ou groupes au niveau d’un site, mais pas pour les autres du même site. Par exemple, il peut être utile de désactiver la numérotation longue distance pour certains employés. Dans le cadre de l’affectation d’une stratégie de voix, un objet contact est traité comme un utilisateur individuel.
    
    > [!NOTE]
    > Nous vous recommandons de déployer une stratégie de voix utilisateur pour les Voix Entreprise utilisateurs inscrits auprès du déploiement du site central ou les utilisateurs inscrits sur un Survivable Branch Appliance. 
  
- Une **stratégie de voix de site** s’applique à un site entier, à l’exception des utilisateurs, groupes ou objets contact affectés à une stratégie de voix d’utilisateur. Pour définir une stratégie de voix de site, vous devez spécifier le site auquel la stratégie s’applique. Si aucune stratégie de voix d’utilisateur n’est affectée, la stratégie de voix de site est utilisée.
    
- La **stratégie de voix globale** est la stratégie de voix par défaut installée avec le produit. Vous pouvez modifier la stratégie de voix globale pour l’adapter aux besoins spécifiques de votre organisation, mais vous ne pouvez pas la renommer ou la supprimer. Cette stratégie de voix s’applique à tous Voix Entreprise utilisateurs, groupes et objets contact de votre déploiement, sauf si vous configurez et affectez une stratégie de voix avec une étendue plus spécifique. Si vous souhaitez désactiver entièrement cette stratégie, assurez-vous que tous les sites et utilisateurs disposent de stratégies personnalisées affectées.
    
### <a name="call-features"></a>Fonctionnalités d’appel

Vous pouvez activer ou désactiver les fonctionnalités d’appel suivantes pour chaque stratégie de voix :
  
- **Transfert d’appel** permet aux utilisateurs de transférer des appels vers d’autres téléphones et périphériques clients. Activée par défaut.
    
- **Délégation** permet aux utilisateurs de spécifier d’autres utilisateurs pouvant passer et recevoir des appels à leur place. Activée par défaut.
    
- **Transfert d’appel** permet aux utilisateurs de transférer des appels à d’autres utilisateurs. Activée par défaut.
    
- Le **parcage d’appel** permet aux utilisateurs de parquer des appels pour décrocher l’appel depuis un téléphone ou un client distinct. Désactivée par défaut.
    
- La **sonnerie simultanée** permet aux appels entrants de sonner sur un téléphone supplémentaire (par exemple un téléphone mobile) ou sur d’autres périphériques d’extrémité. Activée par défaut.
    
- **Appel d’équipe** permet aux utilisateurs d’une équipe définie de répondre aux appels destinés à d’autres membres de l’équipe. Activée par défaut.
    
- Le **réacheminement PSTN** permet de réacheminer sur le réseau téléphonique commuté les appels effectués depuis des utilisateurs auxquels cette stratégie est affectée vers d’autres utilisateurs d’entreprise, si le réseau WAN est saturé ou indisponible. Activée par défaut.
    
- Le **remplacement de stratégie de bande passante** permet aux administrateurs de remplacer les décisions de stratégie du contrôle d’admission des appels pour un utilisateur particulier. Désactivée par défaut.
    
- **Le suivi des** appels malveillants permet aux utilisateurs de signaler des appels malveillants à l’aide du client Skype Entreprise, puis de les signaler dans les enregistrements des détails des appels. Désactivé par défaut.
    
-  La fonction d’évitement de la messagerie vocale empêche l’itinéraire immédiat des appels vers le système de messagerie vocale du téléphone mobile de l’utilisateur lorsque la sonnerie simultanée est configurée et que le téléphone est éteint, hors batterie ou hors de portée, et est basé sur une valeur de timer. Ce paramètre active et désactive le timer et définit la valeur du timer. Il ne peut être configuré qu’à l’aide Skype Entreprise Server Management Shell. Désactivé par défaut.
    
- Le forwarding d’appel et les **utilisations PSTN** de sonnerie simultanée permettent aux administrateurs de spécifier la même utilisation PSTN que la stratégie de voix pour le forwarding d’appel et la sonnerie simultanée, de limiter le forwarding d’appel et la sonnerie simultanée aux utilisateurs de Skype Entreprise internes uniquement, ou de spécifier une utilisation PSTN personnalisée différente de l’utilisation PSTN de la stratégie de voix. L’utilisation de la même utilisation PSTN que la stratégie de voix pour le transfert d’appel et la sonnerie simultanée est la valeur par défaut.
    
### <a name="pstn-usage-records"></a>Enregistrements d’utilisation PSTN

Chaque stratégie de voix doit disposer d’un ou de plusieurs enregistrements d’utilisation PSTN associés. Les utilisations PSTN peuvent être associées à la stratégie de voix pour des besoins de la sonnerie simultanée et du transfert d’appel uniquement. 
  
> [!NOTE]
> L’ordre des utilisations PSTN est important parce que, lors de la mise en correspondance des utilisateurs et des itinéraires, la fonctionnalité de routage sortant compare les utilisations PSTN du haut vers le bas. Si la première utilisation correspond à l’itinéraire d’appel, cet itinéraire est utilisé. Sinon, la fonctionnalité de routage sortant examine l’utilisation PSTN suivante dans la liste et continue jusqu’à trouver une correspondance. Ainsi, les utilisations PSTN suivantes assurent une alternative si la première de la liste est indisponible. 
  
## <a name="pstn-usage-records"></a>Enregistrements d’utilisation PSTN

La planification des enregistrements d’utilisation PSTN consiste principalement à répertorier toutes les autorisations d’appel actuellement en vigueur dans votre organisation, du PDG aux travailleurs temporaires, consultants et subordonnés. Ce processus donne également la possibilité de revérifier les autorisations d’appel existantes et de les modifier. Vous pouvez créer des enregistrements d’utilisation PSTN uniquement pour les autorisations qui s’appliquent aux utilisateurs Voix Entreprise prévus, mais une meilleure solution à long terme peut consister à créer des enregistrements d’utilisation PSTN pour toutes les autorisations d’appel, même si certaines d’entre elles peuvent ne pas s’appliquer actuellement au groupe d’utilisateurs à activer pour Voix Entreprise. Si les autorisations d’appel changent ou que de nouveaux utilisateurs avec des autorisations d’appel différentes sont ajoutés, vous aurez déjà créé les enregistrements d’utilisation PSTN requis.
  
Le tableau suivant présente un exemple d’utilisation PSTN standard :
  
**Enregistrements d’utilisation PSTN**

|**Attribut de téléphone**|**Description**|
|:-----|:-----|
|Local  <br/> |Appels locaux  <br/> |
|Long-Distance  <br/> |Appels longue distance  <br/> |
|International  <br/> |Appels internationaux  <br/> |
|Delhi  <br/> |Employés à temps plein à Delhi  <br/> |
|Redmond  <br/> |Employés à temps plein à Redmond  <br/> |
|RedmondTemps  <br/> |Employés temporaires à Redmond  <br/> |
|Zurich  <br/> |Employés à temps plein à Zurich  <br/> |
   
Les enregistrements d’utilisation PSTN n’effectuent aucune action par eux-mêmes. Pour qu’ils fonctionnent, vous devez les associer aux éléments suivants :
  
- des stratégies de voix, qui sont assignées aux utilisateurs ;
    
- des itinéraires, qui sont assignés aux numéros de téléphone.
    
## <a name="voice-routes"></a>Itinéraires des communications vocales

Les itinéraires d’appels spécifient Skype Entreprise Server gérer les appels sortants Voix Entreprise utilisateurs. Lorsqu’un utilisateur compose un numéro, le serveur frontal normalise la chaîne de numérotation au format E.164, si nécessaire, et tente de le faire correspondre à un URI SIP. Si le serveur ne parvient pas à établir de correspondance, il applique la logique de routage des appels sortants en fonction du numéro. La dernière étape de la définition de cette logique consiste à créer un itinéraire téléphonique nommé distinct pour chaque ensemble de numéros de téléphone de destination répertorié dans chaque plan de numérotation.
  
Avant de définir des itinéraires d’appels sortants, vous devez effectuer les étapes suivantes :
  
- Déployer une ou plusieurs jonctions.
    
- Créer des plans de numérotation selon les besoins des sites, des personnes, ainsi que des objets Contact.
    
- Créer des enregistrements d’utilisation PSTN (réseau téléphonique commuté).
    
En outre, pour activer le routage des appels sortants, vous devez créer et assigner une ou plusieurs stratégies de voix. Vous pouvez effectuer cette tâche avant ou après la définition des itinéraires des appels sortants.
  
Pour chaque itinéraire, vous devez indiquer :
  
- un nom sous lequel l’itinéraire peut être facilement identifié ;
    
- une description facultative pour les cas où le nom seul peut ne pas être suffisant pour décrire l’itinéraire ;
    
- le modèle correspondant à l’expression régulière qui identifie les numéros de téléphone de destination auxquels l’itinéraire est appliqué, ainsi que les exceptions auxquelles le modèle ne doit pas être appliqué ;
    
- une ou plusieurs jonctions que vous souhaitez assigner à l’itinéraire ;
    
- les enregistrements d’utilisation PSTN dont doivent disposer les utilisateurs afin d’appeler des numéros qui correspondent à l’expression régulière du numéro de téléphone de destination.
    
Vous pouvez spécifier des itinéraires d’appels dans Skype Entreprise Server panneau de contrôle. Ces itinéraires d’appels remplit la table de routage du serveur, Skype Entreprise Server utilisé pour router les appels destinés au réseau téléphonique public (RST).
  
### <a name="mn-trunk-support"></a>M:N Prise en charge des jonctions

Skype Entreprise Server offre une flexibilité dans la façon dont les appels sont acheminés vers le PSTN. Un itinéraire des communications vocales spécifie un ensemble de jonctions au PSTN qui peuvent être utilisées pour un appel vocal particulier. Une trunk associe un serveur de médiation et un numéro de port à une passerelle PSTN et à un numéro de port d’écoute. Cette association logique permet à un serveur de médiation d’être associé à plusieurs passerelles et d’avoir plusieurs connexions à la même passerelle. Lors de la définition d’un itinéraire d’appels, vous spécifiez les liaisons associées à cet itinéraire, mais vous ne spécifiez pas les serveurs de médiation associés à l’itinéraire. Pour créer des trunks en définissant les relations entre les serveurs de médiation et les passerelles PSTN, les IP-PBX et les contrôleurs de frontière de session (SCS), utilisez le Générateur de topologie.
  
### <a name="least-cost-routing"></a>Routage à moindre coût

La possibilité de spécifier les jonctions vers lesquelles différents numéros sont routés permet de déterminer les itinéraires qui offrent les coûts les plus bas et de les mettre en œuvre en conséquence. La règle générale concernant la sélection des jonctions consiste à choisir celle possédant la passerelle la plus proche du numéro de destination, afin de réduire les coûts des appels longue distance. Par exemple, si vous vous trouvez à New York et que vous appelez un numéro à Rome, vous transférerez l’appel via le réseau IP vers la jonction avec la passerelle de votre bureau romain, ne subissant ainsi que le coût d’un appel local.
  
Voici un exemple d’utilisation du routage à moindre coût : Fabrikam décide d’autoriser les utilisateurs allemands à composer des numéros américains à l’aide de la jonction correspondante. Fabrikam souhaite également configurer le système de sorte que tous les appels des utilisateurs Skype Entreprise Server américains vers l’Allemagne et les pays/régions adjacents se terminent sur la ligne de la passerelle en Allemagne. Ce routage est économique car un appel passé de l’Allemagne vers l’Australie, par exemple, est moins onéreux qu’un appel émis des États-Unis en direction de l’Australie.
  
### <a name="translating-outbound-dial-strings"></a>Traduction des chaînes de numérotation sortantes

Skype Entreprise Server exige que toutes les chaînes de numérotation soient normalisées au format E.164 dans le but d’effectuer une recherche inversée de numéros. Pour les trunks avec passerelles ou PBX (Private Branch Exchanges) qui nécessitent des numéros traduits dans des formats de numérotation locaux, Skype Entreprise Server vous permet de créer une ou plusieurs règles qui vous aident à manipuler le numéro appelé (c’est-à-dire, l’URI de demande) avant de l’acheminement vers la trunk. Par exemple, vous pouvez rédiger une règle pour supprimer la valeur « +44 » au début de la chaîne de numérotation et la remplacer par « 0144 ».
  
Avec Skype Entreprise Server, il est possible de créer une ou plusieurs règles qui vous aident à manipuler le numéro d’appel avant de le router vers la trunk.
  
Lors de la planification de vos trunks qui associent des paires passerelle:port à des paires serveur de médiation :port, il peut être utile de grouper des trunks avec des exigences de numérotation locale similaires, et par conséquent de réduire le nombre de règles de traduction requises et le temps nécessaire pour les écrire.
  
### <a name="configuring-caller-id"></a>Configuration d’un ID d’appelant

Skype Entreprise Server permet de manipuler l’ID de l’appelant pour les appels sortants. Par exemple, si une organisation souhaite masquer les extensions de numérotation directe des employés et les remplacer par le numéro d’entreprise ou de service générique, un administrateur peut le faire à l’aide du Panneau de Skype Entreprise Server pour supprimer l’ID d’appelant et le remplacer par un autre ID d’appelant spécifié. Lors de la planification de votre logique de routage, réfléchissez aux personnes, groupes et sites pour lesquels vous souhaiterez cette option, peut-être même pour tous les employés.
  
> [!NOTE]
> Pour les appels réacheminés sur le réseau téléphonique commuté, l’ID de l’appelant générique s’affiche à la place de l’ID initial. L’appel peut alors contourner les paramètres de confidentialité ou « Ne pas déranger » éventuellement configurés par l’appelé. 
  
### <a name="additional-routing-logic"></a>Logique de routage supplémentaire

Lors de la création d’itinéraires téléphoniques sortants, vous devez avoir conscience des facteurs suivants susceptibles d’affecter la logique de routage :
  
- Lorsqu’un appel est établi sur une limite fédérée, la partie domaine de l’URI permet d’acheminer l’appel vers l’entreprise chargée de l’application de la logique du routage sortant.
    
- Si la partie domaine de l’URI demandé ne contient pas de domaine pris en charge pour l’entreprise, le composant de routage sortant sur le serveur ne traite pas l’appel.
    
- Si un utilisateur n’est pas activé pour Voix Entreprise, le serveur applique une autre logique de routage, selon le cas.
    
- Si un appel est acheminé vers une passerelle totalement occupée (toutes les lignes de la jonction sont occupées), la passerelle refuse l’appel et la logique de routage des appels sortants le redirige vers l’itinéraire à moindre coût suivant. Vous devez tenir compte de ces éléments, car une passerelle dont la taille est adaptée à un petit bureau à l’étranger (par exemple, Zurich) peut en réalité transporter une quantité considérable de trafic non local pour des appels internationaux vers la Suisse. Si la taille de la passerelle ne convient pas à ce trafic supplémentaire, les appels vers la Suisse peuvent être acheminés via une passerelle située en Allemagne, ce qui augmente les frais téléphoniques.
