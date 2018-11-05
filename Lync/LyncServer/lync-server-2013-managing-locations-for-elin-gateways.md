---
title: 'Lync Server 2013 : Gestion des emplacements pour les passerelles ELIN'
TOCTitle: Gestion des emplacements pour les passerelles ELIN
ms:assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205288(v=OCS.15)
ms:contentKeyID: 49298908
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gestion des emplacements pour les passerelles ELIN dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Pour que Lync Server fournisse automatiquement les emplacements pour les clients au sein d’un réseau, vous devez effectuer les tâches suivantes :

  - Renseignez la base de données service d’informations sur l’emplacement avec un schéma de câblage réseau, et incluez les numéros d’identification de l’emplacement en cas d’urgence dans le champ CompanyName.

  - Publiez les emplacements afin qu’ils soient disponibles pour les clients dans votre réseau.

  - Téléchargez les numéros d’identification de l’emplacement en cas d’urgence vers la base de données ALI (Automatic Location Identification) de votre opérateur RTC.

Pour plus d’informations sur l’exécution de ces tâches, reportez-vous à [Configurer la base de données d’emplacements dans Lync Server 2013](lync-server-2013-configure-the-location-database.md) dans la documentation de déploiement.

> [!NOTE]  
> Les emplacements ajoutés à la base de données centrale des emplacements ne sont accessibles au client qu’une fois publiés à l’aide d’une commande Lync Server Management Shell et répliqués vers les magasins locaux du pool. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-publish-the-location-database.md">Publier la base de données d’emplacements</a> dans la documentation de déploiement.

Cette section décrit les éléments à prendre en compte lorsque vous prévoyez de mettre à jour ou maintenir la base de données des emplacements.

## Planification des emplacements d’urgence

Lorsque vous utilisez des passerelles ELIN, vous renseignez la base de données du service d’informations sur l’emplacement avec des adresses géographiques et au moins un numéro d’identification de l’emplacement en cas d’urgence pour chaque emplacement d’intervention d’urgence. Durant la phase de planification, il est recommandé de décider du nom des emplacements et de l’affectation des numéros d’identification de l’emplacement en cas d’urgence.

## Planification des noms d’emplacement

Le champ **Location** du service d’informations sur l’emplacement, qui contient l’emplacement spécifique au sein d’un bâtiment, a une longueur maximale de 20 caractères (espaces compris). En respectant cette limite, essayez d’inclure les éléments suivants :

  - Nom facile à comprendre qui identifie l’emplacement de l’appelant 911 pour s’assurer que les agents des services d’urgence trouvent l’emplacement spécifique rapidement lorsqu’ils arrivent à l’adresse géographique. Ce nom d’emplacement peut inclure un numéro d’immeuble, un numéro d’étage, un indicateur d’aile, un numéro de chambre, etc. Évitez les surnoms connus des seuls employés, qui peuvent induire les agents des services d’urgence en erreur.

  - Identificateur d’emplacement qui aide les utilisateurs à vérifier que leur client Lync a sélectionné l’emplacement correct. Le client Lync concatène et affiche automatiquement les champs **Location** et **City** découverts dans son en-tête. Il est recommandé d’ajouter l’adresse postale de l’immeuble à chaque identificateur d’emplacement (par exemple, « 1er étage \<numéro de rue\> »). Sans l’adresse postale, un identificateur d’emplacement générique tel que « 1er étage » peut s’appliquer à n’importe quel immeuble de la ville.

  - Si l’emplacement est approximatif car il est déterminé par un point d’accès sans fil, vous pouvez ajouter le mot Near (par exemple, « À proximité du 1er étage 1234 »).

## Planification des numéros d’identification de l’emplacement en cas d’urgence (ELIN)

Après avoir déterminé comment diviser l’espace de votre bâtiment en emplacements, vous devez décider du nombre de numéros ELIN à affecter à chaque emplacement. Par exemple, dans un immeuble à plusieurs étages ou multilocatif, différentes zones ERL peuvent être affectées à différentes zones d’urgence. En général, chaque étage d’un immeuble est désigné comme un emplacement. Chaque emplacement se voit alors affecté un ou plusieurs numéros ELIN, utilisés comme numéros d’appel durant un appel d’urgence. Contactez votre opérateur RTC pour connaître les numéros de téléphone que vous pouvez utiliser pour les numéros ELIN. Le tableau ci-dessous fournit des exemples d’emplacements pour une adresse postale spécifique.

### Exemples d’affectations d’emplacements et de numéros ELIN

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Zone de l’immeuble</th>
<th>Emplacement</th>
<th>ELIN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Premier étage</p></td>
<td><p>1</p></td>
<td><p>425-555-0100</p></td>
</tr>
<tr class="even">
<td><p>Deuxième étage</p></td>
<td><p>2</p></td>
<td><p>425-555-0111</p></td>
</tr>
<tr class="odd">
<td><p>Troisième étage</p></td>
<td><p>3</p></td>
<td><p>425-555-0123</p></td>
</tr>
</tbody>
</table>


Les emplacements définis doivent satisfaire les exigences suivantes :

  - être conformes aux réglementations locales et nationales/régionales en termes de surface maximale par emplacement et nombre d’emplacements par adresse postale ;

  - être assez spécifiques pour faciliter la localisation de l’appel d’urgence.

## Remplissage de la base de données d’emplacements

Les questions suivantes vous permettront de déterminer comment remplir la base de données des emplacements.

  - **Quel processus allez-vous adopter pour remplir la base de données d’emplacements ?**  
    Où sont stockées les données et quelles étapes devez-vous suivre pour les convertir au format requis par la base de données d’emplacements ? Allez-vous ajouter des emplacements individuellement ou en bloc en utilisant un fichier CSV ?

<!-- end list -->

  - **Disposez-vous d’une base de données tierce qui contient déjà un mappage des emplacements ?**  
    En utilisant l’option du service d’informations sur l’emplacement secondaire de Lync Server pour vous connecter à une base de données tierce, vous pouvez regrouper et gérer les emplacements à l’aide d’une plateforme hors ligne. Outre la possibilité d’associer des emplacements à des identificateurs réseau, cette approche vous offre l’avantage d’associer des emplacements à un utilisateur. Par conséquent, le service d’informations sur l’emplacement peut renvoyer plusieurs adresses provenant du service d’informations sur l’emplacement vers un client Lync Server. L’utilisateur peut alors choisir l’emplacement le plus approprié.
    
    Pour permettre l’intégration au service d’informations sur l’emplacement, la base de données tierce doit respecter le schéma Demande/Réponse d’emplacement de Lync Server. Pour plus d’informations, reportez-vous à <http://go.microsoft.com/fwlink/p/?linkid=213819>. Pour plus d’informations sur le déploiement d’un service d’informations sur l’emplacement secondaire, reportez-vous à [Configurer un service Informations d’emplacement secondaire](lync-server-2013-configure-a-secondary-location-information-service.md) dans la documentation de déploiement.

Pour plus d’informations sur le renseignement de la base de données d’emplacements, reportez-vous à [Configurer la base de données d’emplacements dans Lync Server 2013](lync-server-2013-configure-the-location-database.md) dans la documentation de déploiement.

## Mise à jour de la base de données d’emplacements

Une fois que vous avez renseigné la base de données des emplacements, vous devez développer une stratégie pour la mettre à jour au fur et à mesure que la configuration réseau change. Les questions suivantes vous permettront de déterminer comment maintenir la base de données des emplacements.

  - **Comment allez-vous mettre à jour la base de données d’emplacements ?**  
    L’ajout de points d’accès sans fil, le recâblage du bureau (qui implique des affectations de commutateur différentes) et l’extension des sous-réseaux font partie des nombreux scénarios qui requièrent la mise à jour de la base de données des emplacements. Mettrez-vous directement à jour chaque emplacement individuel ou effectuerez-vous une mise à jour en bloc de tous les emplacements en utilisant un fichier CSV ?

<!-- end list -->

  - **Ferez-vous appel à une application SNMP pour associer des adresses MAC de client Lync aux identificateurs de port et de commutateur ?**  
    Si vous utilisez une application SNMP, vous devez développer un processus manuel permettant de garder les informations de châssis de commutateur et de port cohérentes entre l’application SNMP et la base de données des emplacements. Si l’application SNMP renvoie une adresse IP de châssis ou un ID de port qui ne figure pas dans la base de données, le service d’informations sur l’emplacement ne pourra pas renvoyer un emplacement au client.

