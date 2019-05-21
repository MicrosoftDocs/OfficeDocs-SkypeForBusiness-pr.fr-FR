---
title: Planifier le routage des communications sortantes dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
description: En savoir plus sur le routage des communications sortantes dans Skype entreprise Server Voice, y compris les paramètres de routage des appels, les plans de numérotation, les règles de normalisation, les politiques vocales, les enregistrements d’utilisation RTC et les itinéraires vocaux.
ms.openlocfilehash: bb57d824d9d44886973f60b3061b2e86e949f071
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276581"
---
# <a name="plan-for-outbound-voice-routing-in-skype-for-business-server"></a>Planifier le routage des communications sortantes dans Skype entreprise Server
 
En savoir plus sur le routage des communications sortantes dans Skype entreprise Server Voice, y compris les paramètres de routage des appels, les plans de numérotation, les règles de normalisation, les politiques vocales, les enregistrements d’utilisation RTC et les itinéraires vocaux.
  
Le routage des appels sortants s’applique aux appels vocaux d’entreprise destinés à une passerelle PSTN (réseau téléphonique commuté), un Trunk ou un échange de succursale privée (PBX). Lorsqu’un utilisateur de Skype entreprise place un appel, le serveur normalise le numéro de téléphone au format E. 164, si nécessaire, et tente de correspondre à un URI SIP. Si le serveur ne parvient pas à établir de correspondance, il applique la logique de routage des appels sortants en fonction de la chaîne de numérotation fournie. Les paramètres de serveur du tableau ci-dessous permettent de configurer la logique de routage des appels sortants.
  
**Paramètres de routage des appels sortants de Skype entreprise Server**

|**Objet**|**Description**|
|:-----|:-----|
|Plan de numérotation  <br/> |Un plan de numérotation est un ensemble nommé de règles de normalisation qui convertissent des numéros de téléphone pour un emplacement, un utilisateur individuel ou un objet contact nommé, en un format standard (E.164) à des fins d’autorisation téléphonique et de routage des appels.  <br/> |
|Règle de normalisation  <br/> |Les règles de normalisation définissent la façon dont les numéros de téléphone exprimés en divers formats sont acheminés vers chaque emplacement, utilisateur ou objet contact. La même chaîne de numérotation peut être interprétée et convertie différemment selon l’emplacement d’origine de la numérotation et la personne ou l’objet contact passant l’appel. Un ensemble de règles de normalisation associées à un emplacement particulier constitue un plan de numérotation.  <br/> |
|Stratégie de voix  <br/> |Une stratégie de voix associe un ou plusieurs enregistrements d’utilisation PSTN à un utilisateur ou groupe d’utilisateurs. Elle fournit également une liste de fonctionnalités d’appel que vous pouvez activer ou désactiver.  <br/> |
|Enregistrement d’utilisation PSTN  <br/> |Un enregistrement d’utilisation PTSN indique une classe d’appel (interne, local ou longue distance) qui peut être passée par différents utilisateurs, ou groupes d’utilisateurs, dans une organisation.  <br/> |
|Itinéraire d’appel  <br/> |Un itinéraire d’appel associe les numéros de téléphone cibles à des jonctions et des enregistrements d’utilisation PTSN spécifiques. Une passerelle PSTN est considérée comme une jonction.  <br/> |
   
## <a name="dial-plans-and-normalization-rules"></a>Plans de numérotation et règles de normalisation

Un plan de numérotation est un ensemble nommé de règles de normalisation qui convertissent des numéros de téléphone pour un emplacement, un utilisateur individuel ou un objet contact nommé, en un format standard (E.164) à des fins d’autorisation téléphonique et de routage des appels. 
  
Les règles de normalisation définissent la façon dont les numéros de téléphone exprimés en divers formats sont routés vers chaque emplacement, utilisateur ou objet contact. La même chaîne de numérotation peut être interprétée et convertie différemment selon l’emplacement d’origine de la numérotation et la personne ou l’objet contact passant l’appel.
  
### <a name="dial-plan-scope"></a>Étendue du plan de numérotation

L'étendue d'un plan de numérotation détermine le niveau hiérarchique auquel celui-ci est appliqué. Dans Skype entreprise Server, un utilisateur peut se voir attribuer un plan de numérotation spécifique par utilisateur. Si aucun plan de numérotation utilisateur n’est attribué, le plan de numérotation de la liste frontale est appliqué. S’il n’y a pas de plan de numérotation frontale, le plan de numérotation de site est appliqué. Enfin, si aucun autre plan de numérotation ne peut être appliqué à l’utilisateur, le plan de numérotation global est appliqué.
  
Les clients obtiennent les niveaux d’étendue du plan de numérotation à l’aide des paramètres de mise en service intrabande fournis lorsque les utilisateurs se connectent à Skype entreprise. En tant qu’administrateur, vous pouvez gérer et affecter des niveaux d’étendue de plan de numérotation en utilisant le panneau de configuration Skype entreprise Server.
  
> [!NOTE]
> Le plan de numérotation de la passerelle PSTN au niveau du service est appliqué aux appels entrant depuis une passerelle donnée. 
  
Les niveaux d’étendue du plan de numérotation sont définis comme suit :
  
- **Plan de numérotation de l’utilisateur** : peut être affecté à des utilisateurs individuels, des groupes ou des objets contact. Les applications Voix peuvent rechercher un plan de numérotation par utilisateur lorsqu’un appel est reçu tandis que le contexte du téléphone est défini sur Utilisateur par défaut. Dans le but d’affecter un plan de numérotation, un objet contact est traité comme s’il s’agissait d’un utilisateur individuel.
    
- **Plan de numérotation du pool** : peut être créé au niveau du service pour n’importe quelle passerelle ou n’importe quel serveur d’inscriptions de votre topologie. Pour définir un plan de numérotation du pool, vous devez spécifier le service donné (passerelle PSTN ou pool de serveurs d’inscriptions) auquel le plan de numérotation s’applique. 
    
- **Plan de numérotation de site** : peut être créé pour un site entier, sauf pour les utilisateurs, groupes ou objets contact affectés à un plan de numérotation de pool ou de l’utilisateur. Pour définir un plan de numérotation de site, vous devez spécifier le site auquel le plan s’applique.
    
- **Plan de numérotation globale**: plan de numérotation par défaut installé avec le produit. Vous pouvez modifier le plan de numérotation global, mais vous ne pouvez pas le supprimer. Ce plan de numérotation s’applique à tous les utilisateurs, à tous les groupes et aux objets de contact Enterprise Voice dans votre déploiement, sauf si vous configurez et attribuez un plan de numérotation avec une étendue plus spécifique.
    
### <a name="planning-for-dial-plans"></a>Planification des plans de numérotation

Pour planifier un plan de numérotation, procédez comme suit :
  
- Répertoriez tous les paramètres régionaux dans lesquels votre organisation a un bureau.
    
    Cette liste doit être à jour et complète. Elle doit être revue à mesure que la société ou l’organisation évolue. Dans une multinationale de grande taille avec de nombreuses petites succursales, cette tâche peut nécessiter un certain temps.
    
- Identifiez des modèles de numéro valides pour chaque site.
    
    La partie de la planification de vos plans de numérotation qui prend le plus de temps est l’identification des modèles de numéro valides pour chaque site. Dans certains cas, vous pouvez être en mesure de copier les règles de normalisation que vous avez écrites pour un plan de numérotation vers d’autres plan, particulièrement si les site correspondants se trouvent dans les mêmes pays/région ou continent. Dans d’autres cas, de petites modifications apportées aux numéros d’un plan de numérotation peuvent être suffisantes pour permettre leur utilisation dans d’autres plans de numérotation.
    
- Développez un schéma à l’échelle de l’organisation pour nommer les plans de numérotation.
    
    L’adoption d’un schéma d’appellation standard assure une cohérence à l’échelle de l’organisation et facilite la maintenance et les mises à jour.
    
- Déterminez la nécessité de plusieurs plans de numérotation pour un seul emplacement. 
    
    Si votre organisation maintient un seul plan de numérotation sur plusieurs emplacements, vous devrez éventuellement créer un plan de numérotation distinct pour les utilisateurs de la voix entreprise qui effectuent la migration à partir d’un système PBX (Private Branch Exchange) et qui doivent conserver leurs extensions existantes.
    
- Déterminez la nécessité de plans de numérotation par utilisateur. Par exemple, si vous avez des utilisateurs dans un site de succursale qui sont inscrits auprès du site central ou si certains de vos utilisateurs sont inscrits sur une unité de succursale Survivable, vous pouvez utiliser des scénarios de numérotation spéciaux pour ces utilisateurs à l’aide de plans de numérotation par utilisateur et de règles de normalisation . Pour plus d’informations, reportez-vous à [Plan for Enterprise Voice resiliency in Skype for Business Server](enterprise-voice-resiliency.md).
    
- Déterminez l’étendue d’un plan de numérotation (tel que décrit plus haut dans cette rubrique).
    
Pour créer un plan de numérotation, vous devez spécifier les valeurs dans les champs suivants, le cas échéant, à l’aide du panneau de configuration Skype entreprise Server ou de Skype entreprise Server Management Shell.
  
#### <a name="name-and-simple-name"></a>Nom et nom simple

Pour les plans de numérotation de l’utilisateur, spécifiez un nom descriptif qui identifie les utilisateurs, groupes ou objets contact auxquels le plan de numérotation sera affecté. Pour les plans de numérotation de site, le champ Nom est pré-rempli avec le nom du site et ne peut pas être modifié. Pour les plans de numérotation de groupe, le champ nom est déjà rempli avec la passerelle RTC ou le nom de domaine complet (FQDN) du pool frontal et ne peut pas être modifié.
  
Le nom simple de plan de numérotation est déjà rempli avec une chaîne dérivée du nom du plan de numérotation. Le champ Nom simplifié est modifiable, ce qui vous permet de créer une convention d'appellation plus descriptive pour vos plans de numérotation. TheSimple valeur Name ne peut pas être vide et doit être unique. Une meilleure pratique consiste à développer une convention d’appellation pour votre organisation puis d’utiliser cette convention de manière cohérente sur tous les sites et les utilisateurs.
  
#### <a name="description"></a>Description

Nous vous conseillons de taper le nom commun et reconnaissable du lieu géographique auquel le plan de numérotation s’applique. Par exemple, si le nom du plan de numérotation est Londres.Contoso.com, il est recommandé d’indiquer Londres dans la zone Description. 
  
#### <a name="dial-in-conferencing-region"></a>Région de la conférence rendez-vous

Si vous déployez une conférence rendez-vous, vous devrez spécifier une région en vue d’associer les numéros d’accès de conférence rendez-vous à un plan de numérotation. 
  
#### <a name="external-access-prefix"></a>Préfixe d’accès externe

Vous pouvez spécifier un préfixe d’accès externe de quatre caractères (#, \*et 0-9) si les utilisateurs doivent composer au moins un chiffre de début supplémentaire (par exemple, 9) pour obtenir une ligne externe.
  
> [!NOTE]
> Si vous spécifiez un préfixe d’accès externe, il n’est pas nécessaire de créer une règle de normalisation supplémentaire pour inclure le préfixe. 
  
### <a name="normalization-rules"></a>Règles de normalisation

Les règles de normalisation définissent la façon dont les numéros de téléphone exprimés sous différents formats doivent être acheminés pour l’emplacement nommé. La même chaîne de numéros peut être interprétée et convertie différemment en fonction des paramètres régionaux à partir desquels elle est composée. Les règles de normalisation sont nécessaires au routage des appels car les collaborateurs d’une organisation peuvent utiliser (et utilisent) différents formats lorsqu’ils entrent des numéros de téléphone dans leurs listes de contacts.
  
La normalisation des numéros de téléphone fournis par l’utilisateur offre un format cohérent qui facilite les tâches suivantes :
  
- Associez un numéro composé à l’URI SIP du destinataire prévu.
    
- Appliquer des règles d’autorisation de numérotation à l’appelant.
    
Les champs numériques suivants figurent parmi ceux que vos règles de normalisation devront peut-être prendre en compte :
  
- Plan de numérotation
    
- Indicatif du pays
    
- Indicatif régional
    
- Longueur du poste
    
- Préfixe de site
    
#### <a name="creating-normalization-rules"></a>Création de règles de normalisation

Les règles de normalisation utilisent des expressions régulières .NET Framework pour spécifier des modèles de correspondance numérique que le serveur utilise pour convertir des chaînes de numérotation au format E.164 dans le but d’effectuer une recherche inversée du numéro. Vous pouvez créer des règles de normalisation dans le panneau de configuration Skype entreprise Server en entrant les expressions manuellement ou en entrant les chiffres de début et la durée des chaînes de numérotation à mettre en correspondance et en laissant le panneau de configuration Skype entreprise Server. générer l’expression régulière correspondante pour vous. Quelle que soit la méthode choisie, lorsque vous avez terminé, vous pouvez entrer un numéro test afin de vérifier que la règle de normalisation fonctionne comme prévu.
  
Pour plus d’informations sur l’utilisation des expressions régulières du .NET Framework, consultez la rubrique [expressions régulières .NET Framework](https://go.microsoft.com/fwlink/p/?linkId=140927).
  
#### <a name="sample-normalization-rules"></a>Exemples de règles de normalisation
<a name="BKMK_SampleNormalizationRules"> </a>

Le tableau ci-dessous illustre des exemples de règles de normalisation écrites sous la forme d'expressions régulières .NET Framework. Il s'agit uniquement d'exemples qui ne doivent pas être considérés comme une référence normative pour la création de règles de normalisation.
  
**Tableau 1. Règles de normalisation à l’aide d’expressions régulières .NET Framework**

|**Nom de la règle**|**Description**|**Schéma de numéro**|**Conversion**|**Exemple**|
|:-----|:-----|:-----|:-----|:-----|
|4digitExtension  <br/> |Traduit les numéros de poste à 4 chiffres  <br/> |^ (\d{4}) $  <br/> |+1425555$1  <br/> |0100 est converti en +14255550100  <br/> |
|5digitExtension  <br/> |Traduit les numéros de poste à 5 chiffres  <br/> |^ 5 (\d{4}) $  <br/> |+1425555$1  <br/> |50100 est converti en +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Traduit les numéros à 7 chiffres en numéros locaux Redmond  <br/> |^ (\d{7}) $  <br/> |+1425$1  <br/> |5550100 est converti en +14255550100  <br/> |
|7digitcallingDallas  <br/> |Traduit les numéros à 7 chiffres en numéros locaux Dallas  <br/> |^ (\d{7}) $  <br/> |+1972$1  <br/> |5550100 est converti en +19725550100  <br/> |
|10digitcallingUS  <br/> |Traduit des numéros à 10 chiffres aux États-Unis  <br/> |^ (\d{10}) $  <br/> |+1$1  <br/> |2065550100 est converti en +12065550100  <br/> |
|LDCallingUS  <br/> |Traduit des numéros avec des préfixes longue distance aux États-Unis  <br/> |^ 1 (\d{10}) $  <br/> |+$1  <br/> |12145550100 est converti en +2145550100  <br/> |
|IntlCallingUS  <br/> |Traduit des numéros avec des préfixes internationaux aux États-Unis  <br/> |^ 011 (\d\*) $  <br/> |+$1  <br/> |01191445550100 est converti en +91445550100  <br/> |
|RedmondOperator  <br/> |Traduit 0 par l’opérateur de Redmond  <br/> |^0$  <br/> |+14255550100  <br/> |0 est converti en +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Traduit les numéros avec un préfixe réseau (6) et le code de site de Redmond (222)  <br/> |^ 6222 (\d{4}) $  <br/> |+1425555$1  <br/> |62220100 est converti en +14255550100  <br/> |
|NYSitePrefix  <br/> |Traduit les numéros avec un préfixe réseau (6) et le code de site New York (333)  <br/> |^ 6333 (\d{4}) $  <br/> |+1202555$1  <br/> |63330100 est converti en +12025550100  <br/> |
|DallasSitePrefix  <br/> |Traduit les numéros avec un préfixe réseau (6) et le code de site Dallas (444)  <br/> |^ 6444 (\d{4}) $  <br/> |+1972555$1  <br/> |64440100 est converti en +19725550100  <br/> |
   
Le tableau ci-dessous illustre un exemple de plan de numérotation pour Redmond, Washington, États-Unis, basé sur les règles de normalisation indiquées dans le tableau précédent.
  
**Tableau 2. Plan de numérotation pour Redmond basé sur les règles de normalisation mentionnées dans le Tableau 1**

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
> Les noms des règles de normalisation indiqués dans le tableau précédent n’incluent pas d’espaces, mais c’est une question de choix. Le premier nom du tableau, par exemple, aurait pu s’écrire « 5 digit extension » ou « 5-digit Extension » et être toujours valide. 
  
## <a name="voice-policies"></a>Stratégies de voix

Politiques vocales Skype entreprise Server définissez les éléments suivants pour chaque utilisateur, site ou organisation affecté à la stratégie:
  
- Un ensemble de fonctionnalités d’appel qui peuvent être activées ou désactivées pour déterminer la fonctionnalité voix entreprise disponible aux utilisateurs.
    
- un ensemble d’enregistrements de l’utilisation du réseau téléphonique commuté (PSTN) qui définissent le type des appels autorisés. 
    
Les étapes suivantes vous aideront à planifier les stratégies vocales dont vous aurez besoin pour votre déploiement voix entreprise:
  
- Déterminez la configuration prévue de votre stratégie de voix globale (stratégie de voix par défaut installée avec le produit). Ce paramètre s’applique à tous les utilisateurs de l’entreprise voix qui n’ont pas explicitement reçu une stratégie de niveau site ou par utilisateur.
    
- Identifiez les stratégies de voix de niveau site dont vous avez éventuellement besoin.
    
- Identifiez les stratégies de voix par utilisateur dont vous avez éventuellement besoin.
    
- Décidez des fonctionnalités d’appel à activer pour chaque stratégie de voix.
    
- Déterminez les enregistrements d’utilisation DNS à configurer pour chaque stratégie de voix.
    
### <a name="voice-policy-scope"></a>Étendue de stratégie de voix

L’étendue de stratégie de voix détermine le niveau hiérarchique auquel la stratégie peut être appliquée. Dans Skype entreprise Server, vous pouvez configurer des politiques vocales avec les niveaux d’étendue suivants (classés du plus spécifique au plus général).
  
- Une **stratégie de voix d’utilisateur** peut être affectée à des utilisateurs individuels, à des groupes ou à des objets contact. Il s’agit de la stratégie de plus bas niveau. Les stratégies de voix d’utilisateur peuvent être déployées afin d’activer des fonctionnalités pour certains utilisateurs ou groupes au niveau d’un site, mais pas pour les autres du même site. Par exemple, il peut être utile de désactiver la numérotation longue distance pour certains employés. Dans le cadre de l’affectation d’une stratégie de voix, un objet contact est traité comme un utilisateur individuel.
    
    > [!NOTE]
    > Nous vous recommandons de déployer une stratégie de voix utilisateur pour les utilisateurs de la voix de votre site de succursale et ceux qui sont inscrits auprès du déploiement de site central, ou les utilisateurs enregistrés sur une unité de succursale Survivable. 
  
- Une **stratégie de voix de site** s’applique à un site entier, à l’exception des utilisateurs, groupes ou objets contact affectés à une stratégie de voix d’utilisateur. Pour définir une stratégie de voix de site, vous devez spécifier le site auquel la stratégie s’applique. Si aucune stratégie de voix d’utilisateur n’est affectée, la stratégie de voix de site est utilisée.
    
- La **stratégie de voix globale** est la stratégie de voix par défaut installée avec le produit. Vous pouvez modifier la stratégie de voix globale pour l’adapter aux besoins spécifiques de votre organisation, mais vous ne pouvez pas la renommer ou la supprimer. Cette politique vocale s’applique à tous les utilisateurs, à tous les groupes et aux objets de contact Enterprise Voice dans votre déploiement, sauf si vous configurez et attribuez une stratégie vocale avec une étendue plus spécifique. Si vous souhaitez désactiver entièrement cette stratégie, assurez-vous que tous les sites et utilisateurs disposent de stratégies personnalisées affectées.
    
### <a name="call-features"></a>Fonctionnalités d’appel

Vous pouvez activer ou désactiver les fonctionnalités d’appel suivantes pour chaque stratégie de voix :
  
- **Transfert d’appel** permet aux utilisateurs de transférer des appels vers d’autres téléphones et périphériques clients. Activée par défaut.
    
- **Délégation** permet aux utilisateurs de spécifier d’autres utilisateurs pouvant passer et recevoir des appels à leur place. Activée par défaut.
    
- **Transfert d’appel** permet aux utilisateurs de transférer des appels à d’autres utilisateurs. Activée par défaut.
    
- **Parcage d’appel** permet aux utilisateurs de parquer des appels pour décrocher l’appel depuis un téléphone ou un client distinct. Désactivée par défaut.
    
- **Sonnerie simultanée** permet aux appels entrants de sonner sur un téléphone supplémentaire (par exemple, un téléphone mobile) ou sur d’autres périphériques de terminaison. Activée par défaut.
    
- **Appel d’équipe** permet aux utilisateurs d’une équipe définie de répondre aux appels destinés à d’autres membres de l’équipe. Activée par défaut.
    
- **Réacheminement PSTN** permet de réacheminer sur le réseau téléphonique commuté les appels effectués depuis des utilisateurs auxquels cette stratégie est affectée vers d’autres utilisateurs d’entreprise, si le réseau étendu est saturé ou indisponible. Activée par défaut.
    
- **Remplacement de stratégie de bande passante** permet aux administrateurs de remplacer les décisions de stratégie du contrôle d’admission des appels pour un utilisateur particulier. Désactivée par défaut.
    
- Le **suivi des appels malveillants** permet aux utilisateurs de signaler des appels malveillants à l’aide du client Skype entreprise, puis de marquer ces appels dans les enregistrements des détails des appels. Désactivé par défaut.
    
- La boîte **vocale** d’arrêt empêche le routage des appels vers le système de messagerie vocale du téléphone mobile de l’utilisateur lorsqu’une sonnerie simultanée est configurée et que le téléphone est éteint, hors batterie ou en dehors de la plage et repose sur une valeur de minuteur. Ce paramètre active et désactive le minuteur et définit la valeur de Timer. Il peut être configuré uniquement à l’aide de Skype entreprise Server Management Shell. Désactivé par défaut.
    
- Le **transfert d’appel et la sonnerie simultanée des utilisations RTC** permettent aux administrateurs de spécifier la même utilisation PSTN que la politique vocale pour le transfert d’appel et la sonnerie simultanée, limiter le transfert d’appel et la sonnerie simultanée à Skype pour Utilisateurs professionnels uniquement, ou spécifier une utilisation PSTN personnalisée qui est différente de l’utilisation du RTC de la stratégie vocale. L’utilisation de la même utilisation PSTN que la stratégie de voix pour le transfert d’appel et la sonnerie simultanée est la valeur par défaut.
    
### <a name="pstn-usage-records"></a>Enregistrements d’utilisation PSTN

Chaque stratégie de voix doit disposer d’un ou de plusieurs enregistrements d’utilisation PSTN associés. Les utilisations PSTN peuvent être associées à la stratégie de voix pour les besoins de la sonnerie simultanée et du transfert d’appel uniquement. 
  
> [!NOTE]
> L’ordre des utilisations PSTN est important parce que, lors de la mise en correspondance des utilisateurs et des itinéraires, la fonctionnalité de routage sortant compare les utilisations PSTN du haut vers le bas. Si la première utilisation correspond à l’itinéraire d’appel, cet itinéraire est utilisé. Sinon, la fonctionnalité de routage sortant examine l’utilisation PSTN suivante dans la liste et continue jusqu’à trouver une correspondance. Ainsi, les utilisations PSTN suivantes assurent une alternative si la première de la liste est indisponible. 
  
## <a name="pstn-usage-records"></a>enregistrements d’utilisation PSTN

La planification des enregistrements d’utilisation PSTN consiste principalement à répertorier toutes les autorisations d’appel actuellement en vigueur dans votre organisation, du PDG aux travailleurs temporaires, consultants et subordonnés. Ce processus donne également la possibilité de revérifier les autorisations d’appel existantes et de les modifier. Vous pouvez créer des enregistrements d’utilisation RTC uniquement pour les autorisations d’appel qui s’appliquent aux utilisateurs vocaux de votre entreprise, mais une meilleure solution de grande gamme peut être de créer des enregistrements d’utilisation RTC pour toutes les autorisations d’appel, qu’il soit ou non Appliquez au groupe d’utilisateurs à activer pour voix entreprise. Si les autorisations d’appel changent ou que de nouveaux utilisateurs avec des autorisations d’appel différentes sont ajoutés, vous aurez déjà créé les enregistrements d’utilisation PSTN requis.
  
Le tableau ci-dessous présente un exemple d’utilisation PSTN standard :
  
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
  
- des stratégies de voix, affectées aux utilisateurs ;
    
- des itinéraires, affectés aux numéros de téléphone.
    
## <a name="voice-routes"></a>Itinéraires des communications vocales

Les itinéraires d’appel indiquent la manière dont Skype entreprise Server gère les appels sortants placés par des utilisateurs d’Enterprise Voice. Lorsqu’un utilisateur compose un numéro, le serveur frontal normalise la chaîne de numérotation au format E. 164, si nécessaire, et tente de correspondre à un URI SIP. Si le serveur ne parvient pas à établir de correspondance, il applique la logique de routage des appels sortants en fonction du numéro. La dernière étape de la définition de cette logique consiste à créer un itinéraire téléphonique nommé distinct pour chaque ensemble de numéros de téléphone de destination répertorié dans chaque plan de numérotation.
  
Avant de définir des itinéraires d’appels sortants, vous devez effectuer les étapes suivantes :
  
- Déployer une ou plusieurs jonctions.
    
- Créer des plans de numérotation selon les besoins des sites, des personnes, ainsi que des objets Contact.
    
- Créer des enregistrements d’utilisation PSTN (réseau téléphonique commuté).
    
En outre, pour activer le routage des appels sortants, vous devez créer et affecter une ou plusieurs stratégies de voix. Vous pouvez effectuer cette tâche avant ou après la définition des itinéraires des appels sortants.
  
Pour chaque itinéraire, vous devez indiquer :
  
- un nom sous lequel l’itinéraire peut être facilement identifié ;
    
- une description facultative pour les cas où le nom seul peut ne pas être suffisant pour décrire l’itinéraire ;
    
- le modèle correspondant à l’expression régulière qui identifie les numéros de téléphone de destination auxquels l’itinéraire est appliqué, ainsi que les exceptions auxquelles le modèle ne doit pas être appliqué ;
    
- une ou plusieurs jonctions que vous souhaitez affecter à l’itinéraire ;
    
- les enregistrements d’utilisation PSTN dont doivent disposer les utilisateurs afin d’appeler des numéros qui correspondent à l’expression régulière du numéro de téléphone de destination.
    
Vous pouvez spécifier des itinéraires d’appels dans le panneau de configuration Skype entreprise Server. Ces itinéraires d’appel remplissent la table de routage du serveur, que Skype entreprise Server utilise pour diriger les appels destinés au RTC.
  
### <a name="mn-trunk-support"></a>M:N Prise en charge des jonctions

Skype entreprise Server offre une souplesse pour le routage des appels vers PSTN. Un itinéraire des communications vocales spécifie un ensemble de jonctions au PSTN qui peuvent être utilisées pour un appel vocal particulier. Un Trunk associe un serveur de médiation et un numéro de port avec une passerelle PSTN et un numéro de port d’écoute. Cette association logique permet d’associer un serveur de médiation à plusieurs passerelles et de disposer de plusieurs connexions à la même passerelle. Lors de la définition d’un itinéraire d’appel, vous spécifiez les Trunks associés à cet itinéraire, mais vous ne spécifiez pas les serveurs de médiation associés à l’itinéraire. Pour créer des Trunks en définissant les relations entre les serveurs de médiation et les passerelles RTC, PBX IP et contrôleurs de frontière de session (SBCs), utilisez le générateur de topologie.
  
### <a name="least-cost-routing"></a>Routage à moindre coût

La possibilité de spécifier les jonctions vers lesquelles différents numéros sont routés permet de déterminer les itinéraires qui offrent les coûts les plus bas et de les mettre en œuvre en conséquence. La règle générale concernant la sélection des jonctions consiste à choisir celle possédant la passerelle la plus proche du numéro de destination afin de réduire les coûts des appels longue distance. Par exemple, si vous vous trouvez à New York et que vous appelez un numéro à Rome, vous transférerez l’appel via le réseau IP vers la jonction avec la passerelle de votre bureau romain, ne subissant ainsi que le coût d’un appel local.
  
Voici un exemple d’utilisation du routage à moindre coût : Fabrikam décide d’autoriser les utilisateurs allemands à composer des numéros américains à l’aide de la jonction correspondante. Fabrikam veut également configurer le système de manière à ce que tous les appels des utilisateurs de Skype entreprise Server vers l’Allemagne et les pays/régions adjacents se terminent sur le Trunk avec la passerelle en Allemagne. Ce routage est économique car un appel passé de l’Allemagne vers l’Australie, par exemple, est moins onéreux qu’un appel émis des États-Unis en direction de l’Australie.
  
### <a name="translating-outbound-dial-strings"></a>Conversion des chaînes de numérotation sortantes

Dans Skype entreprise Server, toutes les chaînes de numérotation doivent être normalisées au format E. 164 pour pouvoir effectuer une recherche de numéro inverse (RNL). S’il s’agit de circuits avec passerelles ou d’échangeurs de succursales privées qui nécessitent des numéros traduits au format de numérotation locale, Skype entreprise Server vous permet de créer une ou plusieurs règles qui vous aident à manipuler le numéro appelé (URI de demande) avant de procéder au routage. au Trunk. Par exemple, vous pouvez rédiger une règle pour supprimer la valeur « +44 » au début de la chaîne de numérotation et la remplacer par « 0144 ».
  
Avec Skype entreprise Server, il est possible de créer une ou plusieurs règles qui vous aident à manipuler le numéro d’appel avant de le diriger vers le Trunk.
  
Dans la planification de vos Trunks qui associent les paires passerelle: port et serveur de médiation: paires de port, il peut être utile de regrouper les Trunks avec des exigences de numérotation locales similaires, et donc de réduire le nombre de règles de traduction requises et le temps nécessaire pour les écrire.
  
### <a name="configuring-caller-id"></a>Configuration d’un ID d’appelant

Skype entreprise Server offre un moyen de manipuler l’ID de l’appelant pour les appels sortants. Par exemple, si une organisation veut masquer les extensions de numérotation directe des employés et les remplacer par le numéro générique d’entreprise ou de département, un administrateur peut le faire en utilisant le panneau de configuration Skype entreprise Server pour supprimer l’ID de l’appelant et le remplacer. avec un ID d’appelant différent. Lors de la planification de votre logique de routage, considérez les personnes, les groupes et les sites pour lesquels vous souhaitez utiliser cette option, peut-être, même pour tous les employés.
  
> [!NOTE]
> Pour les appels réacheminés sur le réseau téléphonique commuté, l’ID de l’appelant générique s’affiche à la place de l’ID initial. L’appel peut alors contourner les paramètres de confidentialité ou « Ne pas déranger » éventuellement configurés par l’appelé. 
  
### <a name="additional-routing-logic"></a>Logique de routage supplémentaire

Lors de la création d’itinéraires téléphoniques sortants, vous devez avoir conscience des facteurs suivants susceptibles d’affecter la logique de routage :
  
- Lorsqu’un appel est établi sur une limite fédérée, la partie domaine de l’URI permet d’acheminer l’appel vers l’entreprise chargée de l’application de la logique du routage sortant.
    
- Si la partie domaine de l’URI demandé ne contient pas de domaine pris en charge pour l’entreprise, le composant de routage sortant sur le serveur ne traite pas l’appel.
    
- Si un utilisateur n’est pas activé pour voix entreprise, le serveur applique une autre logique de routage, selon le cas.
    
- Si un appel est acheminé vers une passerelle totalement occupée (toutes les lignes de la jonction sont occupées), la passerelle refuse l’appel et la logique de routage des appels sortants le redirige vers l’itinéraire à moindre coût suivant. Vous devez tenir compte de ces éléments, car une passerelle dont la taille est adaptée à un petit bureau à l’étranger (par exemple, Zurich) peut en réalité transporter une quantité considérable de trafic non local pour des appels internationaux vers la Suisse. Si la taille de la passerelle ne convient pas à ce trafic supplémentaire, les appels vers la Suisse peuvent être acheminés via une passerelle située en Allemagne, ce qui augmente les frais téléphoniques.
    

