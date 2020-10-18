---
title: 'Lync Server 2013 : dépendances opérationnelles'
description: 'Lync Server 2013 : dépendances opérationnelles.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e240981f5dfded7c27f123c8483794ea3ffedff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579190"
---
# <a name="operational-dependencies-in-lync-server-2013"></a>Dépendances opérationnelles dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-05-15_

L’architecture de référence décrite dans ce document vous permettra de vous assurer que vous disposez d’un déploiement Lync Server 2013 non seulement adapté aux besoins de l’organisation, mais qu’il est conçu conformément aux meilleures pratiques de Microsoft. Il est possible que l’implémentation de Lync Server 2013 soit un service dynamique et que tous les autres services de l’entreprise nécessitent toujours une surveillance et une gestion proactive pour maintenir un niveau élevé de disponibilité de service et de qualité de service pour l’entreprise.

Dans la mesure où Lync Server 2013 devient profondément ingranulaire dans le secteur quotidien de l’organisation, il est important que le service soit géré par une gestion des niveaux de service précise et tangible. L’architecture système de Lync peut devenir complexe et très intégrée et, afin de maintenir une gestion efficace du niveau de service et établir des SLA pour Lync Server 2013, il est essentiel de comprendre les dépendances du système sur d’autres plateformes et serveurs. Tout aussi important est de noter quels services d’entreprise, tels que les applications vocales et de communications unifiées, dépendent de Lync.

Lync Server 2013 doit être établi en notant toutes ces dépendances. Le plan de service vous permettra de formuler un accord SLA entre Lync et son service dépendant et de fournir un emplacement de départ pour la négociation SLA.

Le tableau suivant répertorie les services de dépendance typiques d’une infrastructure Lync. Chacune de ces technologies doit avoir sa propre surveillance proactive.

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
<td><p>Matériel de serveur</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Active Directory</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>infrastructure à clé publique</p></td>
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
<td><p>Services de stockage</p></td>
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
<td><p>Infrastructure réseau : interne (LAN/WAN)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Infrastructure de téléphonie – IP-PBX et passerelles</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Services Cloud</p></td>
<td></td>
</tr>
</tbody>
</table>


Il est supposé que l’organisation est très mature dans l’exercice des fonctions de base de gestion du niveau de service, telles que les modifications, la gestion des incidents et des versions, comme le préconise la structure MOF. La solution Lync doit être adoptée par ces fonctions et être soumise aux mêmes processus de gestion des opérations opérationnelles.

En s’appuyant sur les informations recueillies ci-dessus, nous avons désormais une meilleure compréhension de ce qui peut avoir un impact sur le service Lync dans l’entreprise. Pour garantir la qualité et la disponibilité du service Lync Server 2013, les outils de surveillance suivants doivent accompagner le déploiement de l’architecture de référence :

### <a name="monitoring-tools"></a>Outils de surveillance

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
<td><p>Déployez au moins un rôle serveur de surveillance Lync Server 2013 par site central et configurez le Pack de rapports qualité de l’expérience (QoE).</p>
<p>Pour plus d’informations, reportez-vous à la documentation de déploiement de Lync Server 2013 :</p>
<p><a href="lync-server-2013-deploying-monitoring.md">Déploiement de la surveillance dans Lync Server 2013</a></p></td>
<td><p>Sites centraux</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Attachez chaque pool à l’instance la plus proche du rôle serveur de surveillance.</p></td>
<td><p>Sites centraux</p>
<p>Sites de succursale</p></td>
</tr>
<tr class="odd">
<td><p>System Center Operations Manager 2012</p></td>
<td><p>System Center Operations Manager 2012 avec le pack d’administration Microsoft Lync Server 2013 (MP) importé.</p>
<p>Le pack d’administration met en œuvre le journal des événements traditionnels et l’instrumentation basée sur les compteurs de performances, ainsi que l’activation de l’instrumentation nouvellement disponible dans Lync Server 2013.</p></td>
<td><p>Sites centraux</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Assurez-vous que la découverte centrale pour la découverte de rôles et de composants qui doivent être surveillés est automatiquement effectuée en fonction d’un script de découverte central qui lit le document de topologie publié dans la base de données de gestion centrale.</p></td>
<td><p>Site central</p>
<p>Site de succursale</p>
<p>Site Edge</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Déployez les agents System Center Operations Manager 2007 sur tous les serveurs déployés exécutant Lync Server.</p></td>
<td><p>Site central</p>
<p>Site de succursale</p>
<p>Site Edge</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Assurez-vous que les alertes classées par ordre de priorité sont configurées pour la notification :</p>
<p>Alertes à priorité élevée</p>
<p>Alertes de priorité moyenne</p>
<p>Autres alertes.</p></td>
<td><p>Site central</p>
<p>Site de succursale</p>
<p>Site Edge</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Configurez la surveillance des ports pour votre déploiement.</p></td>
<td><p>Site central</p>
<p>Site de succursale</p>
<p>Site Edge</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Configurer la surveillance d’URL pour votre déploiement</p></td>
<td><p>Site central</p></td>
</tr>
<tr class="odd">
<td><p>Intégration de Lync et de System Center Operations Manager</p></td>
<td><p>Déploiement de la fiabilité des appels et de la qualité des médias MonitoringCall fiabilité et surveillance de la qualité des médias utilisez le serveur de surveillance comme nœud observateur pour surveiller la fiabilité des appels et la qualité des médias de Lync Server. Ces deux fonctionnalités interrogent les bases de données du serveur de surveillance pour effectuer une analyse.</p></td>
<td><p>Site central</p>
<p>Site de succursale</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Vérifier que les seuils d’avertissement de qualité des médias sont correctement configurés. Le tableau suivant indique les notes moyennes d’opinion réseau maximales par codec. En production, ces scores doivent être surveillés pendant une période déterminée et des seuils acceptables doivent être établis en fonction des scores NMOS spécifiques de l’organisation.</p></td>
<td><p>Site central</p>
<p>Site de succursale</p></td>
</tr>
<tr class="odd">
<td><p>Observateur de transactions synthétiques Lync Server 2013</p></td>
<td><p>Déployez un serveur Lync dédié pour qu’il soit un observateur de transactions synthétiques.</p>
<p>Les transactions synthétiques sont des applets de commande Lync Server 2013 Windows PowerShell qui sont automatiquement déclenchées par le pack d’administration sur un intervalle prédéfini. Ceux-ci sont exécutés sur un nœud observateur de transactions synthétiques qui est un serveur désigné par l’administrateur responsable de la découverte et de l’exécution du service STs pour chaque pool.</p>
<p>Nous vous déconseillons d’utiliser un serveur Microsoft Lync Server 2013 existant comme nœud observateur de transactions synthétiques. Cela est dû à l’utilisation élevée de la mémoire et de l’UC pour l’exécution de STs. Utilisez un nouvel ordinateur serveur (ou un serveur virtuel) pour le nœud observateur de transactions synthétiques.</p></td>
<td><p>Site central</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Déploiement du nœud observateur de transactions synthétiques.</p>
<p>Reportez-vous au document MonitoringCS_withSCOM.docx de la documentation UCTAP Connect.</p></td>
<td><p>Site central</p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a>Nombre maximal de scores MOS réseau par codec

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
<th>Nombre maximal de NMOS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Appels UC-UC</p></td>
<td><p>RTAudio WB</p></td>
<td><p>4.10</p></td>
</tr>
<tr class="even">
<td><p>Appels UC-UC</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2,95</p></td>
</tr>
<tr class="odd">
<td><p>Téléconférence</p></td>
<td><p>Siren</p></td>
<td><p>3,72</p></td>
</tr>
<tr class="even">
<td><p>Appels UC-PSTN</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2,95</p></td>
</tr>
<tr class="odd">
<td><p>Appels UC-PSTN</p></td>
<td><p>G-711</p></td>
<td><p>3,61</p></td>
</tr>
</tbody>
</table>


Au-delà et au-delà des activités de surveillance plus anciennes, les tâches de maintenance doivent être exécutées pour les sites centraux, Edge et de succursale sur une base périodique quotidienne, hebdomadaire et mensuelle, comme défini dans le guide des opérations de l’autorité de session Lync.

</div>

<span> </span>

</div>

</div>

</div>

