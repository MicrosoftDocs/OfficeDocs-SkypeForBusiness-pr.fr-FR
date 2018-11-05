---
title: 'Lync Server 2013 : Plans de numérotation et règles de normalisation'
TOCTitle: Plans de numérotation et règles de normalisation
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg413082(v=OCS.15)
ms:contentKeyID: 49299459
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Plans de numérotation et règles de normalisation dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Un plan de numérotation est un ensemble nommé de règles de normalisation qui convertissent des numéros de téléphone pour un emplacement, un utilisateur individuel ou un objet contact nommé, en un format standard (E.164) à des fins d’autorisation téléphonique et de routage des appels.

Les règles de normalisation définissent la façon dont les numéros de téléphone exprimés en divers formats sont routés vers chaque emplacement, utilisateur ou objet contact. La même chaîne de numérotation peut être interprétée et convertie différemment selon l’emplacement d’origine de la numérotation et la personne ou l’objet contact passant l’appel.

## Étendue du plan de numérotation

L’*étendue* d’un plan de numérotation détermine le niveau hiérarchique auquel le plan de numérotation peut être appliqué. Dans Lync Server, un plan de numérotation par utilisateur spécifique peut être affecté à un utilisateur. Si aucun plan de numération de l’utilisateur n’est affecté, le plan de numérotation du pool de serveurs d’inscriptions est appliqué. En l’absence de plan de numérotation du pool de serveurs d’inscriptions, le plan de numérotation du site est appliqué. Enfin, si aucun autre plan de numérotation ne peut être appliqué à l’utilisateur, le plan de numérotation global sera appliqué.

Les clients obtiennent des niveaux d’étendue du plan de numérotation par l’intermédiaire des paramètres de provisionnement intrabande fournis lorsque les utilisateurs se connectent à Lync Server. En tant qu’administrateur, vous pouvez gérer et affecter des niveaux d’étendue du plan de numérotation à l’aide de Panneau de configuration Lync Server.

> [!NOTE]  
> Le plan de numérotation de la passerelle RTC au niveau du service est appliqué aux appels entrant depuis une passerelle donnée.

Les niveaux d’étendue du plan de numérotation sont définis comme suit :

  - **Plan de numérotation de l’utilisateur** : peut être affecté à des utilisateurs individuels, des groupes ou des objets contact. Les applications Voix peuvent rechercher un plan de numérotation par utilisateur lorsqu’un appel est reçu tandis que le contexte du téléphone est défini sur Utilisateur par défaut. Dans le but d’affecter un plan de numérotation, un objet contact est traité comme s’il s’agissait d’un utilisateur individuel.

  - **Plan de numérotation du pool** : peut être créé au niveau du service pour n’importe quelle passerelle ou n’importe quel serveur d’inscriptions de votre topologie. Pour définir un plan de numérotation du pool, vous devez spécifier le service donné (passerelle RTC ou pool de serveurs d’inscriptions) auquel le plan de numérotation s’applique.

  - **Plan de numérotation de site** : peut être créé pour un site entier, sauf pour les utilisateurs, groupes ou objets contact affectés à un plan de numérotation de pool ou de l’utilisateur. Pour définir un plan de numérotation de site, vous devez spécifier le site auquel le plan s’applique.

  - **Plan de numérotation global** : le plan de numérotation par défaut installé avec le produit. Vous pouvez modifier le plan de numérotation global mais vous ne pouvez pas le supprimer. Ce plan de numérotation s’applique à tous les utilisateurs, groupes et objets contact de Voix Entreprise dans votre déploiement, à moins que vous ne configuriez et affectez un plan de numérotation doté d’une étendue plus spécifique.

## Planification des plans de numérotation

Pour planifier un plan de numérotation, procédez comme suit :

  - Répertoriez tous les paramètres régionaux dans lesquels votre organisation a un bureau.
    
    Cette liste doit être à jour et complète. Elle doit être revue à mesure que la société ou l’organisation évolue. Dans une multinationale de grande taille avec de nombreuses petites succursales, cette tâche peut nécessiter un certain temps.

  - Identifiez des modèles de numéro valides pour chaque site.
    
    La partie de la planification de vos plans de numérotation qui prend le plus de temps est l’identification des modèles de numéro valides pour chaque site. Dans certains cas, vous pouvez être en mesure de copier les règles de normalisation que vous avez écrites pour un plan de numérotation vers d’autres plan, particulièrement si les site correspondants se trouvent dans les mêmes pays/région ou continent. Dans d’autres cas, de petites modifications apportées aux numéros d’un plan de numérotation peuvent être suffisantes pour permettre leur utilisation dans d’autres plans de numérotation.

  - Développez un schéma à l’échelle de l’organisation pour nommer les plans de numérotation.
    
    L’adoption d’un schéma d’appellation standard assure une cohérence à l’échelle de l’organisation et facilite la maintenance et les mises à jour.

  - Déterminez la nécessité de plusieurs plans de numérotation pour un seul emplacement.
    
    Si votre organisation gère un seul plan de numérotation sur plusieurs emplacements, il est possible que vous deviez quand même créer un plan de numérotation distinct pour les utilisateurs Voix Entreprise qui effectuent une migration à partir d’un système PBX (autocommutateur privé) et ont besoin de conserver leurs poste existants.

  - Déterminez de la nécessité de plans de numérotation par utilisateur. Par exemple, si vous avez des utilisateurs sur un site de succursale inscrits auprès du site central ou si vous avez des utilisateurs inscrits sur un Survivable Branch Appliance, vous pouvez étudier des scénarios de numérotation spéciaux pour de tels utilisateurs en utilisant des plans de numérotation et des règles de normalisation. Pour plus d’informations, reportez-vous à [Configuration requise pour la résistance des sites de succursale pour Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).

  - Déterminez l’étendue d’un plan de numérotation (tel que décrit plus haut dans cette rubrique).

Pour créer un plan de numérotation, spécifiez des valeurs dans les champs suivants, selon les besoins, à l’aide du Panneau de configuration Lync Server ou de Lync Server Management Shell.

## Nom et nom simple

Pour les plans de numérotation de l’utilisateur, spécifiez un nom descriptif qui identifie les utilisateurs, groupes ou objets contact auxquels le plan de numérotation sera affecté. Pour les plans de numérotation de site, le champ Nom est pré-rempli avec le nom du site et ne peut pas être modifié. Pour les plans de numérotation de pool, le champ Nom est pré-rempli avec la passerelle RTC ou le nom de domaine complet (FQDN) du pool frontal et ne peut pas être modifié.

Le *Nom simple* du plan de numérotation est pré-rempli avec une chaîne dérivée du nom du plan de numérotation. Le champ Nom simple peut être modifié, ce qui vous permet de créer une convention d’appellation plus descriptive pour vos plans de numérotation. La valeur *Nom simple* ne peut pas être vide et doit être unique. Une meilleure pratique consiste à développer une convention d’appellation pour votre organisation puis d’utiliser cette convention de manière cohérente sur tous les sites et les utilisateurs.

## Description

Nous vous conseillons de taper le nom commun et reconnaissable du lieu géographique auquel le plan de numérotation s’applique. Par exemple, si le nom du plan de numérotation est Londres.Contoso.com, il est recommandé d’indiquer Londres dans la zone Description.

## Région de la conférence rendez-vous

Si vous déployez une conférence rendez-vous, vous devrez spécifier une région en vue d’associer les numéros d’accès de conférence rendez-vous à un plan de numérotation.

## Préfixe d’accès externe

Vous pouvez spécifier un préfixe d’accès externe de 4 caractères maximum (\#, \* et 0 à 9) si les utilisateurs doivent numéroter un ou plusieurs chiffres supplémentaires (par exemple, 9) pour obtenir une ligne externe.

> [!NOTE]  
> Si vous spécifiez un préfixe d’accès externe, il n’est pas nécessaire de créer une règle de normalisation supplémentaire pour inclure le préfixe.

## Règles de normalisation

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

## Création de règles de normalisation

Les règles de normalisation utilisent des expressions régulières .NET Framework pour spécifier des modèles de correspondance numérique que le serveur utilise pour convertir des chaînes de numérotation au format E.164 dans le but d’effectuer une recherche inversée du numéro. Créez les règles de normalisation dans le Panneau de configuration Lync Server soit en entrant les expressions manuellement, soit en entrant les premiers chiffres et la longueur de la chaîne de numérotation à faire correspondre et en laissant le Panneau de configuration Lync Server créer l’expression correspondante pour vous. Quelle que soit la méthode choisie, lorsque vous avez terminé, vous pouvez entrer un numéro test afin de vérifier que la règle de normalisation fonctionne comme prévu.

Pour plus d’informations sur l’utilisation des expressions régulières .NET Framework, reportez-vous à « Expressions régulières .NET Framework » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).

## Exemples de règles de normalisation

Le tableau ci-dessous illustre des exemples de règles de normalisation écrites sous la forme d’expressions régulières .NET Framework. Il s’agit uniquement d’exemples qui ne doivent pas être considérés comme une référence normative pour la création de règles de normalisation.

### Tableau 1. Règles de normalisation à l’aide d’expressions régulières .NET Framework

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
<td><p>^(\d{4})$</p></td>
<td><p>+1425555$1</p></td>
<td><p>0100 est converti en +14255550100</p></td>
</tr>
<tr class="even">
<td><p>5digitExtension</p></td>
<td><p>Traduit les numéros de poste à 5 chiffres</p></td>
<td><p>^5(\d{4})$</p></td>
<td><p>+1425555$1</p></td>
<td><p>50100 est converti en +14255550100</p></td>
</tr>
<tr class="odd">
<td><p>7digitcallingRedmond</p></td>
<td><p>Traduit les numéros à 7 chiffres en numéros locaux Redmond</p></td>
<td><p>^(\d{7})$</p></td>
<td><p>+1425$1</p></td>
<td><p>5550100 est converti en +14255550100</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingDallas</p></td>
<td><p>Traduit les numéros à 7 chiffres en numéros locaux Dallas</p></td>
<td><p>^(\d{7})$</p></td>
<td><p>+1972$1</p></td>
<td><p>5550100 est converti en +19725550100</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
<td><p>Traduit des numéros à 10 chiffres aux États-Unis</p></td>
<td><p>^(\d{10})$</p></td>
<td><p>+1$1</p></td>
<td><p>2065550100 est converti en +12065550100</p></td>
</tr>
<tr class="even">
<td><p>LDCallingUS</p></td>
<td><p>Traduit des numéros avec des préfixes longue distance aux États-Unis</p></td>
<td><p>^1(\d{10})$</p></td>
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
<td><p>^6222(\d{4})$</p></td>
<td><p>+1425555$1</p></td>
<td><p>62220100 est converti en +14255550100</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
<td><p>Traduit les numéros avec un préfixe réseau (6) et le code de site New York (333)</p></td>
<td><p>^6333(\d{4})$</p></td>
<td><p>+1202555$1</p></td>
<td><p>63330100 est converti en +12025550100</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
<td><p>Traduit les numéros avec un préfixe réseau (6) et le code de site Dallas (444)</p></td>
<td><p>^6444(\d{4})$</p></td>
<td><p>+1972555$1</p></td>
<td><p>64440100 est converti en +19725550100</p></td>
</tr>
</tbody>
</table>


Le tableau ci-dessous illustre un exemple de plan de numérotation pour Redmond, Washington, États-Unis, basé sur les règles de normalisation indiquées dans le tableau précédent.

### Tableau 2. Plan de numérotation pour Redmond basé sur les règles de normalisation mentionnées dans le Tableau 1

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


> [!NOTE]  
> Les noms des règles de normalisation indiqués dans le tableau précédent n’incluent pas d’espaces, mais c’est une question de choix. Le premier nom du tableau, par exemple, aurait pu s’écrire « 5 digit extension » ou « 5-digit Extension » et être toujours valide.
