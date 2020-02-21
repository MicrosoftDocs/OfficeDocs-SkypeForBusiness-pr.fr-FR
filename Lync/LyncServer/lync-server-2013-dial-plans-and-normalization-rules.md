---
title: 'Lync Server 2013 : plans de numérotation et règles de normalisation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edd44cbb1e54e811fc646a99362b18a284376953
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a>Plans de numérotation et règles de normalisation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Un plan de numérotation est un ensemble nommé de règles de normalisation qui convertissent des numéros de téléphone pour un emplacement, un utilisateur individuel ou un objet contact nommé, en un format standard (E.164) à des fins d’autorisation téléphonique et de routage des appels.

Les règles de normalisation définissent la façon dont les numéros de téléphone exprimés en divers formats sont routés vers chaque emplacement, utilisateur ou objet contact. La même chaîne de numérotation peut être interprétée et traduite différemment, en fonction de l’emplacement à partir duquel elle est numérotée et de l’objet contact ou de la personne à l’origine de l’appel.

<div>

## <a name="dial-plan-scope"></a>Étendue du plan de numérotation

L' *étendue* d’un plan de numérotation détermine le niveau hiérarchique auquel le plan de numérotation peut être appliqué. Dans Lync Server, un plan de numérotation par utilisateur peut être affecté à un utilisateur. Si aucun plan de numérotation utilisateur n’est affecté, le plan de numérotation du pool de serveurs d’inscriptions est appliqué. S’il n’existe pas de plan de numérotation de pool de serveurs d’inscriptions, le plan de numérotation de site est appliqué. Enfin, s’il n’existe aucun autre plan de numérotation applicable à l’utilisateur, le plan de numérotation globale est appliqué.

Les clients obtiennent des niveaux d’étendue de plan de numérotation via des paramètres de mise en service intrabande qui sont fournis lorsque les utilisateurs se connectent à Lync Server. En tant qu’administrateur, vous pouvez gérer et affecter des niveaux d’étendue de plan de numérotation à l’aide du panneau de configuration Lync Server.

<div>


> [!NOTE]  
> Le plan de numérotation de la passerelle PSTN (réseau téléphonique commuté) du niveau de service est appliqué aux appels entrants d’une passerelle particulière.



</div>

Les niveaux d’étendue du plan de numérotation sont définis comme suit :

  - **Plan de numérotation utilisateur :** Peuvent être attribués à des utilisateurs individuels, des groupes ou des objets contact. Les applications vocales peuvent rechercher un plan de numérotation par utilisateur lorsqu’un appel est reçu avec le contexte téléphonique défini sur User-default. Pour l’affectation d’un plan de numérotation, un objet contact est considéré comme un utilisateur individuel.

  - **Plan de numérotation du pool :** Peuvent être créés au niveau du service pour toute passerelle PSTN ou serveur d’inscriptions dans votre topologie. Pour définir un plan de numérotation de pool, vous devez spécifier le service particulier (passerelle PSTN ou pool de serveurs d’inscriptions) auquel le plan de numérotation s’applique.

  - **Plan de numérotation de site :** Peut être créé pour un site entier, à l’exception des utilisateurs, des groupes ou des objets contact auxquels un plan de numérotation de pool ou un plan de numérotation utilisateur est affecté. Pour définir un plan de numérotation de site, vous devez spécifier le site auquel le plan de numérotation s’applique.

  - **Plan de numérotation global :** Plan de numérotation par défaut installé avec le produit. Vous pouvez modifier le plan de numérotation global, mais vous ne pouvez pas le supprimer. Ce plan de numérotation s’applique à tous les utilisateurs voix entreprise, les groupes et les objets contact de votre déploiement, sauf si vous configurez et affectez un plan de numérotation avec une étendue plus spécifique.

</div>

<div>

## <a name="planning-for-dial-plans"></a>Planification des plans de numérotation

Pour planifier un plan de numérotation, procédez comme suit :

  - Répertoriez tous les paramètres régionaux dans lesquels votre organisation a un bureau.
    
    La liste doit être à jour et complète. Il doit être révisé au fur et à mesure que l’organisation de l’entreprise évolue. Dans une grande entreprise multinationale avec de nombreuses petites succursales, il peut s’agir d’une tâche longue.

  - Identifiez les modèles de numéros valides pour chaque site.
    
    La partie la plus longue de la planification de vos plans de numérotation consiste à identifier les modèles de numéro valides pour chaque site. Dans certains cas, vous pouvez copier les règles de normalisation que vous avez écrites pour un plan de numérotation vers d’autres plans de numérotation, en particulier si les sites correspondants se trouvent dans le même continent ou pays ou région. Dans les autres cas, les petites modifications apportées aux numéros dans un plan de numérotation peuvent être suffisantes pour les utiliser dans d’autres plans de numérotation.

  - Développez un modèle à l’échelle de l’Organisation pour nommer les plans de numérotation.
    
    L’adoption d’un modèle de dénomination standard garantit la cohérence au sein d’une organisation et facilite la maintenance et les mises à jour.

  - Déterminez si plusieurs plans de numérotation sont requis pour un seul emplacement.
    
    Si votre organisation gère un plan de numérotation unique sur plusieurs emplacements, il se peut que vous deviez créer un plan de numérotation distinct pour les utilisateurs de voix entreprise qui migrent à partir d’un PBX (Private Branch Exchange) et qui doivent conserver leurs extensions existantes.

  - Déterminez si des plans de numérotation par utilisateur sont requis. Par exemple, si des utilisateurs d’un site de succursale sont inscrits auprès du site central ou si vous avez des utilisateurs inscrits sur un Survivable Branch appliance, vous pouvez envisager des scénarios de numérotation spéciaux pour ces utilisateurs qui utilisent des plans de numérotation par utilisateur et des règles de normalisation . Pour plus d’informations, consultez la rubrique [Configuration requise pour la résistance des sites de succursale pour Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).

  - Déterminez l’étendue du plan de numérotation (tel que décrit précédemment dans cette rubrique).

Pour créer un plan de numérotation, vous spécifiez des valeurs dans les champs suivants, selon vos besoins, à l’aide du panneau de configuration Lync Server ou de Lync Server Management Shell.

<div>

## <a name="name-and-simple-name"></a>Nom et nom simple

Pour les plans de numérotation utilisateur, vous devez spécifier un nom descriptif qui identifie les utilisateurs, groupes ou objets contact auxquels le plan de numérotation sera affecté. Pour les plans de numérotation de site, le champ Nom contient déjà le nom du site qui ne peut pas être modifié. Pour les plans de numérotation du pool, le champ nom contient déjà le nom de domaine complet de la passerelle PSTN ou du pool frontal et ne peut pas être modifié.

Le *nom simple* du plan de numérotation est pré-rempli avec une chaîne dérivée du nom du plan de numérotation. Le champ nom simple est modifiable, ce qui vous permet de créer une convention d’affectation de noms plus descriptive pour vos plans de numérotation. La valeur de *nom simple* ne peut pas être vide et doit être unique. Il est recommandé de développer une convention d’affectation de noms pour l’ensemble de votre organisation, puis d’utiliser cette Convention de façon cohérente sur tous les sites et les utilisateurs.

</div>

<div>

## <a name="description"></a>Description

Nous vous recommandons de taper le nom commun et reconnaissable de l’emplacement géographique auquel le plan de numérotation correspondant s’applique. Par exemple, si le nom du plan de numérotation est London.Contoso.com, la description recommandée est London.

</div>

<div>

## <a name="dial-in-conferencing-region"></a>Région de conférence rendez-vous

Si vous déployez la Conférence rendez-vous, vous devez spécifier une région de conférence rendez-vous pour associer les numéros d’accès aux conférences rendez-vous avec un plan de numérotation.

</div>

<div>

## <a name="external-access-prefix"></a>Préfixe d’accès externe

Vous pouvez spécifier un préfixe d’accès externe de quatre caractères maximum\#( \*,, et 0-9) si les utilisateurs doivent composer un ou plusieurs chiffres supplémentaires (par exemple, 9) pour obtenir une ligne externe.

<div>


> [!NOTE]  
> Si vous spécifiez un préfixe d’accès externe, il n’est pas nécessaire de créer une règle de normalisation supplémentaire pour prendre en compte le préfixe.



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a>Règles de normalisation

Les règles de normalisation définissent la façon dont les numéros de téléphone exprimés dans différents formats doivent être routés pour l’emplacement nommé. La même chaîne de numérotation peut être interprétée et traduite différemment, selon les paramètres régionaux à partir desquels elle est numérotée. Les règles de normalisation sont nécessaires pour le routage des appels car les utilisateurs peuvent utiliser différents formats lors de la saisie de numéros de téléphone dans leurs listes de contacts.

La normalisation des numéros de téléphone fournis par l’utilisateur offre un format cohérent qui facilite les tâches suivantes :

  - Associez un numéro composé à l’URI SIP du destinataire concerné.

  - Appliquez les règles d’autorisation de numérotation à l’appelant.

Les champs numériques suivants figurent parmi ceux que vos règles de normalisation devront peut-être tenir compte des éléments suivants :

  - Plan de numérotation

  - Indicatif du pays

  - Indicatif régional

  - Longueur du poste

  - Préfixe de site

<div>

## <a name="creating-normalization-rules"></a>Création de règles de normalisation

Les règles de normalisation utilisent des expressions régulières .NET Framework pour spécifier des modèles de correspondance numérique que le serveur utilise pour convertir des chaînes de numérotation au format E. 164 dans le but d’effectuer une recherche inversée des numéros. Vous pouvez créer des règles de normalisation dans le panneau de configuration Lync Server en saisissant les expressions manuellement ou en saisissant les chiffres de départ et la longueur des chaînes de numérotation à mettre en correspondance et en laissant le panneau de configuration Lync Server générer le expression régulière pour vous. Dans les deux cas, lorsque vous avez terminé, vous pouvez entrer un numéro de test pour vérifier que la règle de normalisation fonctionne comme prévu.

Pour plus d’informations sur l’utilisation des expressions régulières .NET Framework, voir « .NET [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927)Framework regular expressions » à l’adresse.

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a>Exemples de règles de normalisation

Le tableau suivant présente des exemples de règles de normalisation écrites sous la forme d’expressions régulières .NET Framework. Les exemples ne sont que des exemples et ne sont pas destinés à être une référence normative pour la création de règles de normalisation.

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a>Tableau 1. règles de normalisation à l’aide d’expressions régulières .NET Framework

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
<td><p>Traduit les extensions à 4 chiffres</p></td>
<td><p>^ (\d{4}) $</p></td>
<td><p>+ 1425555 $1</p></td>
<td><p>0100 est converti en + 14255550100</p></td>
</tr>
<tr class="even">
<td><p>5digitExtension</p></td>
<td><p>Traduit les extensions à 5 chiffres</p></td>
<td><p>^ 5 (\d{4}) $</p></td>
<td><p>+ 1425555 $1</p></td>
<td><p>50100 est converti en + 14255550100</p></td>
</tr>
<tr class="odd">
<td><p>7digitcallingRedmond</p></td>
<td><p>Traduit les numéros à 7 chiffres en numéros locaux Redmond</p></td>
<td><p>^ (\d{7}) $</p></td>
<td><p>+ 1425 $1</p></td>
<td><p>5550100 est converti en + 14255550100</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingDallas</p></td>
<td><p>Traduit les numéros à 7 chiffres en numéros locaux Dallas</p></td>
<td><p>^ (\d{7}) $</p></td>
<td><p>+ 1972 $1</p></td>
<td><p>5550100 est converti en + 19725550100</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
<td><p>Traduit les numéros à 10 chiffres aux États-Unis</p></td>
<td><p>^ (\d{10}) $</p></td>
<td><p>+ 1 $1</p></td>
<td><p>2065550100 est converti en + 12065550100</p></td>
</tr>
<tr class="even">
<td><p>LDCallingUS</p></td>
<td><p>Traduit les numéros avec des préfixes longue distance aux États-Unis</p></td>
<td><p>^ 1 (\d{10}) $</p></td>
<td><p>+ $1</p></td>
<td><p>12145550100 est converti en + 2145550100</p></td>
</tr>
<tr class="odd">
<td><p>IntlCallingUS</p></td>
<td><p>Traduit des numéros avec des préfixes internationaux aux États-Unis</p></td>
<td><p>^ 011 (\d *) $</p></td>
<td><p>+ $1</p></td>
<td><p>01191445550100 est converti en + 91445550100</p></td>
</tr>
<tr class="even">
<td><p>RedmondOperator</p></td>
<td><p>Traduit les opérateurs 0 à Redmond</p></td>
<td><p>^ $0</p></td>
<td><p>+ 14255550100</p></td>
<td><p>0 est converti en + 14255550100</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
<td><p>Traduit les numéros avec un préfixe réseau (6) et le code de site de Redmond (222)</p></td>
<td><p>^ 6222 (\d{4}) $</p></td>
<td><p>+ 1425555 $1</p></td>
<td><p>62220100 est converti en + 14255550100</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
<td><p>Traduit les numéros avec un préfixe réseau (6) et le code de site NY (333)</p></td>
<td><p>^ 6333 (\d{4}) $</p></td>
<td><p>+ 1202555 $1</p></td>
<td><p>63330100 est converti en + 12025550100</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
<td><p>Traduit les numéros avec un préfixe sur le réseau (6) et le code de site Dallas (444)</p></td>
<td><p>^ 6444 (\d{4}) $</p></td>
<td><p>+ 1972555 $1</p></td>
<td><p>64440100 est converti en + 19725550100</p></td>
</tr>
</tbody>
</table>


Le tableau suivant illustre un exemple de plan de numérotation pour Redmond, Washington, États-Unis, basé sur les règles de normalisation indiquées dans le tableau précédent.

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a>Tableau 2. Plan de numérotation de Redmond basé sur les règles de normalisation indiquées dans le tableau 1

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th>Redmond. forestFQDN</th>
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
> Les noms des règles de normalisation indiqués dans le tableau précédent n’incluent pas d’espaces, mais c’est une question de choix. Le premier nom de la table, par exemple, aurait pu avoir été écrit « extension de 5 chiffres » ou « poste à 5 chiffres » et être toujours valide.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

