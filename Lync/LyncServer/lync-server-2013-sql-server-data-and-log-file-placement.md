---
title: 'Lync Server 2013 : Emplacement des fichiers journaux et des données SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a528ba7a348ebb5c8f865a795f8b1f1c1bc30cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a>Emplacement des fichiers journaux et des données SQL Server pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-21_

Lors de la planification et du déploiement de Microsoft SQL Server 2012 ou Microsoft SQL Server 2008 R2 SP1 pour votre pool frontal Lync Server 2013, il est important de tenir compte du placement des données et des fichiers journaux sur les disques durs physiques pour des performances. La configuration de disque recommandée consiste à implémenter un ensemble RAID de 1 + 0 avec 6 piles. Placement de tous les fichiers de base de données et fichiers journaux utilisés par le pool frontal, et les rôles et services de serveur associés (c’est-à-dire, archivage et analyse du serveur, service de groupe de réponse de Lync Server, service de parc de serveurs Lync Server L’Assistant Déploiement génère une configuration qui a été testée pour des performances optimales. Les fichiers de base de données et leurs responsables sont décrits dans le tableau ci-dessous.

<div>


> [!NOTE]  
> Si vos stratégies et configurations SQL Server nécessitent une installation plus spécialisée, les fichiers de base de données et les fichiers journaux peuvent être installés vers tout emplacement prédéfini à l’aide de Lync Server Management Shell. Pour plus d’informations, voir <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">installation de la base de données à l’aide de Lync Server Management Shell dans Lync server 2013</A> .



</div>

### <a name="data-and-log-files-for-central-management-store"></a>Données et fichiers journaux pour le centre de gestion central

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Fichiers de base de données du magasin de gestion centrale</th>
<th>Fichier de données ou objet du journal</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XDS. ldf</p></td>
<td><p>Fichier journal des transactions du magasin de gestion central</p></td>
</tr>
<tr class="even">
<td><p>XDS. mdf</p></td>
<td><p>Conserve la configuration de la topologie Lync Server 2013 actuelle, telle que définie et publiée par le générateur de topologie.</p></td>
</tr>
<tr class="odd">
<td><p>Lis. mdf</p></td>
<td><p>Fichier de données de service d’information d’emplacement</p></td>
</tr>
<tr class="even">
<td><p>Lis. ldf</p></td>
<td><p>Journal des transactions pour le fichier de données du service d’information d’emplacement</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a>Données et fichiers journaux pour l’utilisateur, les conférences et le carnet d’adresses

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Fichiers de base de données principaux de Lync Server 2013</th>
<th>Fichier de données ou objet du journal</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTC. mdf</p></td>
<td><p>Données utilisateur persistantes (telles que les listes de contrôle d’accès (ACL), les contacts, les conférences planifiées)</p></td>
</tr>
<tr class="even">
<td><p>RTC. ldf</p></td>
<td><p>Journal des transactions pour les données RTC</p></td>
</tr>
<tr class="odd">
<td><p>RTCDyn. mdf</p></td>
<td><p>Gère les données utilisateur temporaires (données d’exécution de la présence)</p></td>
</tr>
<tr class="even">
<td><p>RTCDyn. ldf</p></td>
<td><p>Journal des transactions pour les données RTCDyn</p></td>
</tr>
<tr class="odd">
<td><p>RTCAb. mdf</p></td>
<td><p>La base de données du carnet d’adresses RTC (Real-Time communications) est le référentiel SQL Server où sont stockés les informations de service de carnet d’adresses</p></td>
</tr>
<tr class="even">
<td><p>RTCAb. ldf</p></td>
<td><p>Journal des transactions pour le service de carnet d’adresses</p></td>
</tr>
<tr class="odd">
<td><p>Rtclocal. mdb</p></td>
<td><p>Héberge l’annuaire de conférences</p></td>
</tr>
<tr class="even">
<td><p>Rtcxds. mdf</p></td>
<td><p>Conserve la sauvegarde des données utilisateur.</p></td>
</tr>
<tr class="odd">
<td><p>Rtcxds. ldf</p></td>
<td><p>Journal des transactions pour les données Rtcxds</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a>Données et fichiers journaux pour le parc d’appels et le groupe Response

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>base de données d’applications</th>
<th>Fichier de données ou objet du journal</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cpsdyn. mdf</p></td>
<td><p>Base de données d’information dynamique pour l’application de parc d’appels</p></td>
</tr>
<tr class="even">
<td><p>Cpsdyn. ldf</p></td>
<td><p>Journal des transactions pour le fichier de données d’application de parc d’appels</p></td>
</tr>
<tr class="odd">
<td><p>Rgsconfig. mdf</p></td>
<td><p>Fichier de données du service de groupe de réponse Lync Server pour la configuration des services</p></td>
</tr>
<tr class="even">
<td><p>Rgsconfig. ldf</p></td>
<td><p>Fichier journal des transactions pour la configuration de l’application Response Group</p></td>
</tr>
<tr class="odd">
<td><p>Rgsdyn. mdf</p></td>
<td><p>Fichier de données du service Response Group pour les opérations d’exécution</p></td>
</tr>
<tr class="even">
<td><p>Rgsdyn. ldf</p></td>
<td><p>Journal des transactions pour le fichier de données Runtime du service de Response Group</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a>Données et fichiers journaux pour le serveur d’archivage et de surveillance

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Archivage et contrôle des fichiers de base de données</th>
<th>Fichier de données ou objet du journal</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LcsCdr. mdf</p></td>
<td><p>Magasin de données pour le processus d’enregistrement des détails des appels (CDR) du serveur de surveillance</p></td>
</tr>
<tr class="even">
<td><p>LcsCdr. ldf</p></td>
<td><p>Journal des transactions pour les données d’enregistrement des détails des appels (CDR)</p></td>
</tr>
<tr class="odd">
<td><p>QoEMetrics. mdf</p></td>
<td><p>Fichier de données de qualité de l’utilisateur stocké à partir du serveur de surveillance</p></td>
</tr>
<tr class="even">
<td><p>QoEMetrics. ldf</p></td>
<td><p>Journal des transactions d’analyse des données</p></td>
</tr>
<tr class="odd">
<td><p>LcsLog. mdf</p></td>
<td><p>Fichier de données pour la conservation des données de messagerie instantanée et de conférence sur un serveur d’archivage</p></td>
</tr>
<tr class="even">
<td><p>LcsLog. ldf</p></td>
<td><p>Journal des transactions d’archivage des données</p></td>
</tr>
</tbody>
</table>


Dans cette rubrique, les références sont prises sur le disque et sur le jeu RAID. Notez que dans la configuration des ressources SQL Server, le fait de faire référence à un disque correspond à un seul appareil matériel. Un disque dur doté de deux partitions, l’un contenant les fichiers journaux et l’autre partition contenant les fichiers de données, n’est pas le même que sur deux disques.

En ce qui concerne les jeux RAID, il existe plusieurs technologies RAID différentes de celles de différents fournisseurs. Par le biais de la prolifération des réseaux de zone de stockage, les jeux RAID dédiés à un seul système sont plus rares. Vous devez consulter votre fabricant de réseau ou de réseau pour déterminer la configuration qui correspond le mieux à votre disposition de disque lorsque vous configurez des performances SQL Server avec Lync Server 2013.

Notez également que tous les lecteurs de disque ne sont pas créés de la même manière; d’autres sont plus performantes que d’autres. Même les lecteurs du même fabricant peuvent varier en fonction de la vitesse de rotation, de la taille du cache matériel et d’autres facteurs.

</div>

<span> </span>

</div>

</div>

</div>

