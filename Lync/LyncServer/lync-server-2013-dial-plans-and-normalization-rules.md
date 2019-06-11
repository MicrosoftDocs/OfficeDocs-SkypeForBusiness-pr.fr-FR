---
title: 'Lync Server 2013: plans de numérotation et règles de normalisation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d399c49db109a7bac1a1cd3ac430280cb70f665
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a>Plans de numérotation et règles de normalisation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-21_

Un plan de numérotation est un ensemble nommé de règles de normalisation qui convertissent des numéros de téléphone pour un emplacement, un utilisateur individuel ou un objet contact nommé, en un format standard (E.164) à des fins d’autorisation téléphonique et de routage des appels.

Les règles de normalisation définissent la façon dont les numéros de téléphone exprimés en divers formats sont routés vers chaque emplacement, utilisateur ou objet contact. La même chaîne de numérotation peut être interprétée et convertie différemment selon l’emplacement d’origine de la numérotation et la personne ou l’objet contact passant l’appel.

<div>

## <a name="dial-plan-scope"></a>Étendue du plan de numérotation

L’*étendue* d’un plan de numérotation détermine le niveau hiérarchique auquel le plan de numérotation peut être appliqué. Dans Lync Server, un utilisateur peut se voir attribuer un plan de numérotation spécifique par utilisateur. Si aucun plan de numérotation utilisateur n’est attribué, le plan de numérotation du pool d’inscriptions est appliqué. S’il n’y a pas de plan de numérotation de bureaux d’enregistrement, le plan de numérotation de site est appliqué. Enfin, si aucun autre plan de numérotation ne peut être appliqué à l’utilisateur, le plan de numérotation global est appliqué.

Les clients obtiennent les niveaux d’étendue du plan de numérotation via les paramètres de mise en service in-band qui sont fournis lorsque les utilisateurs se connectent à Lync Server. En tant qu’administrateur, vous pouvez gérer et affecter des niveaux d’étendue de plan de numérotation en utilisant le panneau de configuration de Lync Server.

<div>


> [!NOTE]  
> Le plan de numérotation de la passerelle PSTN au niveau du service est appliqué aux appels entrant depuis une passerelle donnée.



</div>

Les niveaux d’étendue du plan de numérotation sont définis comme suit :

  - **Plan de numérotation utilisateur:** Peuvent être attribués à des utilisateurs, des groupes ou des objets de contact individuels. Les applications vocales peuvent chercher un plan de numérotation par utilisateur lors de la réception d’un appel avec le contexte du téléphone défini sur la valeur par défaut de l’utilisateur. Dans le cadre de l’attribution d’un plan de numérotation, un objet contact est considéré comme un utilisateur individuel.

  - Plan de numérotation de la **liste:** Peut être créé au niveau de service pour n’importe quelle passerelle PSTN ou bureau d’enregistrement dans votre topologie. Pour définir un plan de numérotation de groupe, vous devez spécifier le service spécifique (passerelle PSTN ou pool de bureau d’enregistrement) auquel s’applique le plan de numérotation.

  - **Plan de numérotation de site:** Peuvent être créés pour un site entier, à l’exception de tous les utilisateurs, groupes ou objets de contact auxquels un plan de numérotation de groupe ou un plan de numérotation est attribué. Pour définir un plan de numérotation de site, vous devez spécifier le site auquel s’applique le plan de numérotation.

  - **Plan de numérotation globale:** Plan de numérotation par défaut installé avec le produit. Vous pouvez modifier le plan de numérotation global, mais vous ne pouvez pas le supprimer. Ce plan de numérotation s’applique à tous les utilisateurs, à tous les groupes et aux objets de contact Enterprise Voice dans votre déploiement, sauf si vous configurez et attribuez un plan de numérotation avec une étendue plus spécifique.

</div>

<div>

## <a name="planning-for-dial-plans"></a>Planification des plans de numérotation

Pour planifier un plan de numérotation, procédez comme suit :

  - Répertoriez tous les paramètres régionaux dans lesquels votre organisation a un bureau.
    
    Cette liste doit être à jour et complète. Elle doit être revue à mesure que la société ou l’organisation évolue. Dans une multinationale de grande taille avec de nombreuses petites succursales, cette tâche peut nécessiter un certain temps.

  - Identifiez des modèles de numéro valides pour chaque site.
    
    La partie de la planification de vos plans de numérotation qui prend le plus de temps est l’identification des modèles de numéro valides pour chaque site. Dans certains cas, vous pouvez être en mesure de copier les règles de normalisation que vous avez écrites pour un plan de numérotation vers d’autres plan, particulièrement si les site correspondants se trouvent dans les mêmes pays/région ou continent. Dans d’autres cas, de petites modifications apportées aux numéros d’un plan de numérotation peuvent être suffisantes pour permettre leur utilisation dans d’autres plans de numérotation.

  - Développez un schéma à l’échelle de l’organisation pour nommer les plans de numérotation.
    
    L’adoption d’un schéma d’appellation standard assure une cohérence à l’échelle de l’organisation et facilite la maintenance et les mises à jour.

  - Déterminez la nécessité de plusieurs plans de numérotation pour un seul emplacement.
    
    Si votre organisation maintient un seul plan de numérotation sur plusieurs emplacements, vous devrez éventuellement créer un plan de numérotation distinct pour les utilisateurs de la voix entreprise qui effectuent la migration à partir d’un système PBX (Private Branch Exchange) et qui doivent conserver leurs extensions existantes.

  - Déterminez la nécessité de plans de numérotation par utilisateur. Par exemple, si vous avez des utilisateurs dans un site de succursale qui sont inscrits auprès du site central ou si certains de vos utilisateurs sont inscrits sur une unité de succursale Survivable, vous pouvez utiliser des scénarios de numérotation spéciaux pour ces utilisateurs à l’aide de plans de numérotation par utilisateur et de règles de normalisation . Pour plus d’informations, reportez-vous à [Configuration requise pour la résilience de site de succursale pour Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).

  - Déterminez l’étendue d’un plan de numérotation (tel que décrit plus haut dans cette rubrique).

Pour créer un plan de numérotation, vous devez spécifier les valeurs dans les champs suivants, le cas échéant, à l’aide du panneau de configuration de Lync Server ou de Lync Server Management Shell.

<div>

## <a name="name-and-simple-name"></a>Nom et nom simple

Pour les plans de numérotation de l’utilisateur, spécifiez un nom descriptif qui identifie les utilisateurs, groupes ou objets contact auxquels le plan de numérotation sera affecté. Pour les plans de numérotation de site, le champ nom est prérempli avec le nom du site et ne peut pas être modifié. Dans le cas d’un plan de numérotation, le champ nom est précédé de la passerelle RTC ou du nom de domaine complet (FQDN) du pool frontal et ne peut pas être modifié.

Le *nom simple* de plan de numérotation est prérempli avec une chaîne dérivée du nom du plan de numérotation. Le champ Nom simple peut être modifié, ce qui vous permet de créer une convention d’appellation plus descriptive pour vos plans de numérotation. La valeur *Nom simple* ne peut pas être vide et doit être unique. Une meilleure pratique consiste à développer une convention d’appellation pour votre organisation puis d’utiliser cette convention de manière cohérente sur tous les sites et les utilisateurs.

</div>

<div>

## <a name="description"></a>Description

Nous vous conseillons de taper le nom commun et reconnaissable du lieu géographique auquel le plan de numérotation s’applique. Par exemple, si le nom du plan de numérotation est Londres.Contoso.com, il est recommandé d’indiquer Londres dans la zone Description.

</div>

<div>

## <a name="dial-in-conferencing-region"></a>Région de la conférence rendez-vous

Si vous déployez une conférence rendez-vous, vous devrez spécifier une région en vue d’associer les numéros d’accès de conférence rendez-vous à un plan de numérotation.

</div>

<div>

## <a name="external-access-prefix"></a>Préfixe d’accès externe

Vous pouvez spécifier un préfixe d’accès externe de quatre caractères (\#, \*et 0-9) si les utilisateurs doivent composer au moins un chiffre de début supplémentaire (par exemple, 9) pour obtenir une ligne externe.

<div>


> [!NOTE]  
> Si vous spécifiez un préfixe d’accès externe, il n’est pas nécessaire de créer une règle de normalisation supplémentaire pour inclure le préfixe.



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a>Règles de normalisation

Les règles de normalisation définissent la façon dont les numéros de téléphone exprimés sous différents formats doivent être acheminés pour l’emplacement nommé. La même chaîne de numéros peut être interprétée et convertie différemment en fonction des paramètres régionaux à partir desquels elle est composée. Les règles de normalisation sont nécessaires au routage des appels car les collaborateurs d’une organisation peuvent utiliser (et utilisent) différents formats lorsqu’ils entrent des numéros de téléphone dans leurs listes de contacts.

La normalisation des numéros de téléphone fournis par l’utilisateur offre un format cohérent qui facilite les tâches suivantes :

  - Faire correspondre un numéro composé et de l’URI SIP du destinataire concerné

  - Appliquer des règles d’autorisation de numérotation à l’appelant.

Les champs numériques suivants figurent parmi ceux que vos règles de normalisation devront peut-être prendre en compte :

  - Plan de numérotation

  - Indicatif du pays

  - Indicatif régional

  - Longueur du poste

  - Préfixe de site

<div>

## <a name="creating-normalization-rules"></a>Création de règles de normalisation

Les règles de normalisation utilisent des expressions régulières .NET Framework pour spécifier des modèles de correspondance numérique que le serveur utilise pour convertir des chaînes de numérotation au format E.164 dans le but d’effectuer une recherche inversée du numéro. Vous pouvez créer des règles de normalisation dans le panneau de configuration de Lync Server en entrant les expressions manuellement ou en entrant les chiffres de début et la durée des chaînes de numérotation à mettre en correspondance et en laissant le panneau de configuration de Lync Server générer le correspondant expression régulière. Quelle que soit la méthode choisie, lorsque vous avez terminé, vous pouvez entrer un numéro test afin de vérifier que la règle de normalisation fonctionne comme prévu.

Pour plus d’informations sur l’utilisation des expressions régulières du [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).NET Framework, consultez la rubrique expressions régulières .NET Framework.

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a>Exemples de règles de normalisation

Le tableau ci-dessous illustre des exemples de règles de normalisation écrites sous la forme d’expressions régulières .NET Framework. Il s’agit uniquement d’exemples qui ne doivent pas être considérés comme une référence normative pour la création de règles de normalisation.

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a>Tableau 1. Règles de normalisation à l’aide d’expressions régulières .NET Framework

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom de la règle</th>
<th>Description</th>
<th>Type de numéro</th>
<th>Conversion</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>4digitExtension</p></td>
<td><p>Traduit les numéros de poste à 4 chiffres</p></td>
<td><p>^ (\d{4}) $</p></td>
<td><p>+1425555$1</p></td>
<td><p>0100 est converti en +14255550100</p></td>
</tr>
<tr class="even">
<td><p>5digitExtension</p></td>
<td><p>Traduit les numéros de poste à 5 chiffres</p></td>
<td><p>^ 5 (\d{4}) $</p></td>
<td><p>+1425555$1</p></td>
<td><p>50100 est converti en +14255550100</p></td>
</tr>
<tr class="odd">
<td><p>7digitcallingRedmond</p></td>
<td><p>Traduit les numéros à 7 chiffres en numéros locaux Redmond</p></td>
<td><p>^ (\d{7}) $</p></td>
<td><p>+1425$1</p></td>
<td><p>5550100 est converti en +14255550100</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingDallas</p></td>
<td><p>Traduit les numéros à 7 chiffres en numéros locaux Dallas</p></td>
<td><p>^ (\d{7}) $</p></td>
<td><p>+1972$1</p></td>
<td><p>5550100 est converti en +19725550100</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
<td><p>Traduit des numéros à 10 chiffres aux États-Unis</p></td>
<td><p>^ (\d{10}) $</p></td>
<td><p>+1$1</p></td>
<td><p>2065550100 est converti en +12065550100</p></td>
</tr>
<tr class="even">
<td><p>LDCallingUS</p></td>
<td><p>Traduit des numéros avec des préfixes longue distance aux États-Unis</p></td>
<td><p>^ 1 (\d{10}) $</p></td>
<td><p>+$1</p></td>
<td><p>12145550100 est converti en +2145550100</p></td>
</tr>
<tr class="odd">
<td><p>IntlCallingUS</p></td>
<td><p>Traduit des numéros avec des préfixes internationaux aux États-Unis</p></td>
<td><p>^011(\d*)$</p></td>
<td><p>+$1</p></td>
<td><p>01191445550100 est converti en +91445550100</p></td>
</tr>
<tr class="even">
<td><p>RedmondOperator</p></td>
<td><p>Traduit 0 par l’opérateur de Redmond</p></td>
<td><p>^0$</p></td>
<td><p>+14255550100</p></td>
<td><p>0 est converti en +14255550100</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
<td><p>Traduit les numéros avec un préfixe réseau (6) et le code de site de Redmond (222)</p></td>
<td><p>^ 6222 (\d{4}) $</p></td>
<td><p>+1425555$1</p></td>
<td><p>62220100 est converti en +14255550100</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
<td><p>Traduit les numéros avec un préfixe réseau (6) et le code de site New York (333)</p></td>
<td><p>^ 6333 (\d{4}) $</p></td>
<td><p>+1202555$1</p></td>
<td><p>63330100 est converti en +12025550100</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
<td><p>Traduit les numéros avec un préfixe réseau (6) et le code de site Dallas (444)</p></td>
<td><p>^ 6444 (\d{4}) $</p></td>
<td><p>+1972555$1</p></td>
<td><p>64440100 est converti en +19725550100</p></td>
</tr>
</tbody>
</table>


Le tableau ci-dessous illustre un exemple de plan de numérotation pour Redmond, Washington, États-Unis, basé sur les règles de normalisation indiquées dans le tableau précédent.

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a>Tableau 2. Plan de numérotation pour Redmond basé sur les règles de normalisation mentionnées dans le Tableau 1

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th>Redmond.forestFQDN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5digitExtension</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingRedmond</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
</tr>
<tr class="even">
<td><p>IntlCallingUS</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
</tr>
<tr class="even">
<td><p>RedmondOperator</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Les noms des règles de normalisation indiqués dans le tableau précédent n'incluent pas d'espaces, mais c'est une question de choix. Le premier nom du tableau, par exemple, aurait pu s'écrire « 5 digit extension » ou « 5-digit Extension » et être toujours valide.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

