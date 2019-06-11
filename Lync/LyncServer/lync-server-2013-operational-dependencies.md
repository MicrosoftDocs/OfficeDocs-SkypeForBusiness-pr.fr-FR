---
title: 'Lync Server 2013: dépendances opérationnelles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d54ef9959f48c085ad4f5f28f182b86442ebec8c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826058"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a>Dépendances opérationnelles dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2015-05-15_

L’architecture de référence décrite dans ce document permet de vérifier que vous disposez d’un déploiement 2013 Server Lync qui n’est pas uniquement destiné aux besoins de l’organisation, mais qu’il est structuré conformément aux meilleures pratiques Microsoft. Soyez qu’il est possible que l’implémentation de Lync Server 2013 soit un service dynamique et que tous les autres services de l’entreprise requièrent une analyse et une gestion proactive pour maintenir un niveau élevé de disponibilité et de qualité de service pour l’entreprise.

Dans la mesure où Lync Server 2013 devient profondément en grain dans l’entreprise, il est important que le service soit géré par une gestion précise et tangible du niveau de service. L’architecture système de Lync peut devenir complexe et très intégrée et permettre de maintenir une gestion de niveau de service effective et de définir les SLA pour Lync Server 2013 il est essentiel de comprendre les dépendances du système sur d’autres plateformes et serveurs. Il est également important de noter quels services d’entreprise, tels que les applications vocales et les applications intégrées de Cu, dépendent de Lync.

Lync Server 2013 doit être établi en indiquant toutes les dépendances. Le plan de service vous permet d’élaborer un SLA entre Lync et son service dépendant et de fournir un emplacement de départ pour la négociation SLA.

Le tableau suivant répertorie les services de dépendance typiques pour une infrastructure Lync. Chacune de ces technologies doit avoir son propre contrôle proactif.

### <a name="typical-dependency-services"></a>Services de dépendance typiques

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Service de dépendance</th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Systèmes d’exploitation</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Matériel du serveur</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Active Directory</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Infrastructure à clé publique</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Service d’attribution de noms de domaine</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Services de base de données</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Storage Services</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Gestion du système – surveillance et distribution</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Services de sécurité-antivirus</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Infrastructure réseau-Internet</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Infrastructure réseau-interne (LAN/WAN)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Infrastructure de téléphonie – PBX IP et passerelles</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Services Cloud</p></td>
<td></td>
</tr>
</tbody>
</table>


Il est supposé que l’organisation s’est imposée par le biais des fonctions de gestion de niveau de service de base, telles que la modification, l’incident et la gestion des versions, conformément au programme MOF. La solution Lync doit être adoptée par ces fonctions et être soumise aux mêmes processus de gestion opérationnels.

Outre les informations fournies ci-dessus, nous avons à présent une connaissance plus approfondie des éléments qui peuvent avoir un impact sur le service Lync au sein de l’entreprise. Pour garantir la disponibilité et la qualité du service Lync Server 2013, les outils d’analyse suivants doivent accompagner le déploiement de l’architecture de référence:

### <a name="monitoring-tools"></a>Outils d’analyse

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Composant</th>
<th>Description</th>
<th>Site applicable</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serveur de surveillance Lync Server 2013</p></td>
<td><p>Déploiement d’au moins un rôle de serveur Lync Server 2013 de surveillance par site central et de configuration du Pack de rapport qualité de l’interface (QoE).</p>
<p>Pour plus d’informations, reportez-vous à la documentation sur le déploiement de Lync Server 2013:</p>
<p><a href="lync-server-2013-deploying-monitoring.md">Déploiement de la surveillance dans Lync Server 2013</a></p></td>
<td><p>Sites centraux</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Attachez chaque liste à l’instance la plus proche du rôle serveur de surveillance.</p></td>
<td><p>Sites centraux</p>
<p>Sites de succursales</p></td>
</tr>
<tr class="odd">
<td><p>System Center Operations Manager 2012</p></td>
<td><p>L’importation de System Center Operations Manager 2012 avec le pack d’administration Microsoft Lync Server 2013.</p>
<p>Le pack d’administration implémente le journal des événements traditionnel et l’instrumentation basée sur le compteur de performance, ainsi que l’activation de l’instrumentation nouvellement disponible dans Lync Server 2013.</p></td>
<td><p>Sites centraux</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Assurez-vous que la recherche centralisée de rôles et de composants à surveiller est effectuée automatiquement en fonction d’un script de découverte centralisé qui lit le document de topologie publié dans la base de données de gestion centrale.</p></td>
<td><p>Site central</p>
<p>Site de succursale</p>
<p>Site Edge</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Déployez les agents 2007 de System Center Operations Manager sur tous les serveurs déployés exécutant Lync Server.</p></td>
<td><p>Site central</p>
<p>Site de succursale</p>
<p>Site Edge</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Vérifiez que les alertes classées sont configurées pour la notification:</p>
<p>Alertes de priorité élevée</p>
<p>Alertes de priorité moyenne</p>
<p>Autres alertes.</p></td>
<td><p>Site central</p>
<p>Site de succursale</p>
<p>Site Edge</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Configurer le contrôle de port pour votre déploiement.</p></td>
<td><p>Site central</p>
<p>Site de succursale</p>
<p>Site Edge</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Configurer le contrôle d’URL pour votre déploiement</p></td>
<td><p>Site central</p></td>
</tr>
<tr class="odd">
<td><p>Intégration de Lync et System Center Operations Manager</p></td>
<td><p>Déploiement de la fiabilité des appels et de la qualité multimédia MonitoringCall de la fiabilité et de la qualité multimédia utilisez l’ordinateur de surveillance serveur comme nœud d’observation pour contrôler la fiabilité des appels et la qualité multimédia de Lync Server. Ces deux fonctionnalités interrogeront les bases de données du serveur de surveillance pour analyse.</p></td>
<td><p>Site central</p>
<p>Site de succursale</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Vérifiez que les seuils d’avertissement de qualité multimédia sont correctement configurés. Le tableau suivant indique le nombre maximal d’avis de moyenne réseau par codec. En production, ces scores doivent être surveillés pour une période donnée et le seuil acceptable doit être établi en fonction des scores de NMOS spécifiques de l’organisation.</p></td>
<td><p>Site central</p>
<p>Site de succursale</p></td>
</tr>
<tr class="odd">
<td><p>Observateur de transactions synthétiques de Lync Server 2013</p></td>
<td><p>Déploiement d’un serveur Lync dédié en tant qu’observateur de transactions synthétiques.</p>
<p>Les transactions synthétiques sont des cmdlets Windows PowerShell Lync Server 2013 qui sont automatiquement déclenchées par le pack d’administration sur un intervalle prédéfini. Celles-ci sont exécutées sur un nœud d’observateur de transactions synthétique qui est un serveur désigné par un administrateur responsable de la découverte et de l’exécution de STs pour chaque pool.</p>
<p>Nous vous déconseillons d’utiliser un serveur Microsoft Lync Server 2013 existant en tant que nœud de l’observateur de transactions synthétiques. En raison de la configuration requise pour l’utilisation du service STs. Utilisez un nouvel ordinateur serveur (ou un serveur virtuel) pour le nœud de l’observateur de transactions synthétique.</p></td>
<td><p>Site central</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Déploiement du nœud d’observation de transactions synthétiques.</p>
<p>Reportez-vous au document MonitoringCS_withSCOM. docx à partir de la documentation UCTAP Connect.</p></td>
<td><p>Site central</p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a>Scores de réseau maximal par codec

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Scénario</th>
<th>Codec</th>
<th>NMOS Max</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UC UC-appel d’UC</p></td>
<td><p>RTAudio WB</p></td>
<td><p>4,10</p></td>
</tr>
<tr class="even">
<td><p>UC UC-appel d’UC</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2,95</p></td>
</tr>
<tr class="odd">
<td><p>Téléconférence</p></td>
<td><p>Siren</p></td>
<td><p>3,72</p></td>
</tr>
<tr class="even">
<td><p>UC-appel RTC</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2,95</p></td>
</tr>
<tr class="odd">
<td><p>UC-appel RTC</p></td>
<td><p>G-711</p></td>
<td><p>3,61</p></td>
</tr>
</tbody>
</table>


Au-dessus ou au-dessus des activités d’analyse plus courantes, les tâches de maintenance doivent être exécutées pour les sites centraux, latéraux et succursales sur une base quotidienne, hebdomadaire et mensuelle, telle qu’elle est définie dans le Guide de fonctionnement de Lync RA.

</div>

<span> </span>

</div>

</div>

</div>

