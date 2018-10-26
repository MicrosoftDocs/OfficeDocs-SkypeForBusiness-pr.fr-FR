---
title: 'Lync Server 2013 : Options de déploiement SIP direct'
TOCTitle: Options de déploiement SIP direct
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398672(v=OCS.15)
ms:contentKeyID: 49297937
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Options de déploiement SIP direct dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Cette rubrique propose des exemples de topologies pour le déploiement de connexions SIP directes.

## Serveur Lync Server autonome

Si votre organisation utilise l’un des déploiements décrits dans cette section, vous pouvez utiliser Lync Server 2013 comme solution de téléphonie unique pour une partie ou l’ensemble d’une organisation. Cette section décrit les déploiements suivants dans le détail :

  - **Déploiement incrémentiel :** Cette option part du principe que vous disposez d’une infrastructure PBX existante et envisagez d’introduire Voix Entreprise de manière incrémentielle à des plus petits groupes ou équipes de votre organisation.

  - **Déploiement Lync Server VoIP uniquement** Cette option suppose que vous envisagez de déployer Voix Entreprise dans un site ne disposant d’aucune infrastructure de téléphonie traditionnelle.

## Déploiement incrémentiel

Dans un déploiement incrémentiel, Lync Server 2013 est la seule solution de téléphonie pour des équipes ou services particuliers, tandis que le reste des utilisateurs de l’organisation continue à utiliser un système PBX. La stratégie de déploiement incrémentiel permet d’introduire la téléphonie IP dans votre entreprise par le biais de programmes pilotes contrôlés. Les groupes de travail dont les besoins en communication sont le mieux servis par les communications unifiées de Microsoft sont déplacés vers Voix Entreprise, alors que les autres utilisateurs restent sur le système PBX existant. Il est possible d’effectuer la migration de groupes de travail supplémentaires vers Voix Entreprise si nécessaire.

L’option de déploiement incrémentiel est conseillée pour les groupes d’utilisateurs clairement définis qui partagent des exigences en termes de communications et acceptent une gestion centralisée. Cette option est également efficace si vous avez des équipes ou services dispersés sur des zones géographiques étendues, un scénario où les économies sur les frais d’appels longue distance peuvent être considérables. En fait, cette option est utile pour la création d’équipes virtuelles dont les membres peuvent être éparpillés dans le monde entier. Vous pouvez créer, modifier ou dissoudre ces équipes pour répondre rapidement aux besoins de l’entreprise en termes de rotation.

La figure suivante illustre la topologie générique pour le déploiement d’Voix Entreprise derrière un système PBX. Il s’agit de la topologie recommandée pour le déploiement incrémentiel.

**Option de déploiement incrémentiel**

![Diagramme d’option de migration départementale](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Diagramme d’option de migration départementale")

> [!NOTE]  
> Si vous connectez votre déploiement Lync Server sur un partenaire SIP direct approuvé, aucune passerelle RTC n’est nécessaire entre le serveur de médiation et le système PBX. Pour obtenir la liste des partenaires SIP directs approuvés, reportez-vous au site web Microsoft Unified Communications Open Interoperability Program à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</a>.

> [!NOTE]  
> La déviation du trafic multimédia est activée pour le chemin d’accès des médias affiché dans cette figure (configuration recommandée). Si vous envisagez de désactiver la déviation du trafic multimédia, le chemin d’accès des médias est routé par le biais du serveur de médiation.

Dans cette topologie, les services ou groupes de travail sélectionnés sont activés pour Voix Entreprise. Une passerelle RTC relie le groupe de travail VoIP au système PBX. Les utilisateurs activés pour Voix Entreprise, notamment les travailleurs à distance, communiquent sur le réseau IP. Les appels d’utilisateurs Voix Entreprise au réseau RTC et aux collaborateurs qui ne sont pas activés pour Voix Entreprise sont acheminés vers la passerelle RTC appropriée. Les appels de collègues qui se trouvent toujours sur le système PBX, ou d’appelants sur le réseau RTC, sont acheminés vers la passerelle RTC, qui les transmet à Lync Server à des fins de routage.

Il existe deux topologies recommandées pour la connexion d’Voix Entreprise à une infrastructure PBX existante à des fins d’interopérabilité : Voix Entreprise derrière et Voix Entreprise devant le système PBX.

## Voix Entreprise derrière le système PBX

Quand Voix Entreprise est déployé derrière le PBX, tous les appels du réseau RTC arrivent dans le système PBX, qui achemine les appels destinés aux utilisateurs Voix Entreprise vers une passerelle RTC, tandis que les appels destinés aux utilisateurs du système PBX continuent à être routés vers le système PBX.

## Voix Entreprise devant le système PBX

Quand Voix Entreprise est déployé devant le PBX, tous les appels du réseau RTC arrivent dans la passerelle RTC, qui achemine les appels destinés aux utilisateurs Voix Entreprise vers Lync Server, tandis que les appels destinés aux utilisateurs du système PBX continuent à être acheminés vers le système PBX. Les appels destinés au réseau RTC provenant d’utilisateurs Voix Entreprise et PBX sont acheminés sur le réseau IP vers la passerelle RTC la plus rentable. Le tableau suivant indique les avantages et les inconvénients de cette configuration.

### Avantages et inconvénients du déploiement de Voix Entreprise devant le système PBX

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Avantages</th>
<th>Inconvénients</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Le système PBX continue de desservir les utilisateurs non activés pour Voix Entreprise.</p></td>
<td><p>Les passerelles existantes peuvent ne pas prendre en charge la capacité ou les fonctionnalités voulues.</p></td>
</tr>
<tr class="even">
<td><p>Le système PBX gère tous les dispositifs d’ancienne génération.</p></td>
<td><p>Nécessite une jonction de la passerelle vers le système PBX et de la passerelle vers le serveur de médiation. Vous aurez peut-être besoin de plus de jonctions de la part de votre fournisseur de services.</p></td>
</tr>
<tr class="odd">
<td><p>Les utilisateurs Voix Entreprise conservent les mêmes numéros de téléphone.</p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


## Déploiement Lync Server VoIP uniquement

Voix Entreprise permet aux nouvelles entreprises et aux nouveaux sites d’implémenter une solution VoIP complète sans avoir à se soucier de l’intégration PBX ni à subir les coûts substantiels de déploiement et de maintenance d’une infrastructure IP-PBX. Cette solution prend en charge à la fois les travailleurs locaux et à distance.

Dans ce déploiement, tous les appels sont acheminés sur le réseau IP. Les appels destinés au réseau RTC sont acheminés vers la passerelle RTC appropriée. Lync 2013 ou Lync Phone Edition sert de téléphone logiciel. Étant donné qu’aucun téléphone PBX n’est contrôlé par les utilisateurs, le contrôle d’appel distant n’est pas disponible. Le déploiement facultatif de la messagerie unifiée Exchange offre les services de messagerie vocale et de standard automatique.

> [!NOTE]  
> Outre l’infrastructure réseau requise pour prendre en charge Lync Server 2013, un déploiement VoIP uniquement peut utiliser une petite passerelle qualifiée pour la prise en charge des télécopieurs et des périphériques analogiques.

La figure suivante illustre une topologie classique pour un déploiement dans un environnement VoIP uniquement.

**Option de déploiement VoIP uniquement**

![Option de déploiement dans un environnement vierge](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Option de déploiement dans un environnement vierge")

> [!NOTE]  
> La déviation du trafic multimédia est activée pour le chemin d’accès des médias affiché dans cette figure (configuration recommandée). Si vous envisagez de désactiver la déviation du trafic multimédia, le chemin d’accès des médias est routé par le biais du serveur de médiation.
