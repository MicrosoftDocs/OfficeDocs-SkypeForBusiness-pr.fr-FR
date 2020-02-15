---
title: 'Lync Server 2013 : emplacement des fichiers journaux et de données SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b15af558ed6082d28b7ae918d72dd7da94b1e499
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a>Emplacement des fichiers journaux et de données SQL Server pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Lors de la planification et du déploiement de Microsoft SQL Server 2012 ou Microsoft SQL Server 2008 R2 SP1 pour votre pool frontal Lync Server 2013, il est important de prendre en compte le placement des données et des fichiers journaux sur des disques durs physiques pour des performances optimales. La configuration de disque recommandée consiste à implémenter un ensemble RAID 1 + 0 à l’aide de 6 piles de disques. Placement de tous les fichiers de base de données et de journaux utilisés par le pool frontal et les rôles serveur et services associés (c’est-à-dire, le serveur d’archivage et de surveillance, le service de groupe réponse de Lync Server, le service de parcage d’appel Lync Server) sur le jeu de lecteurs RAID à l’aide de Lync Server L’Assistant Déploiement entraîne une configuration qui a été testée pour des performances optimales. Le tableau suivant présente les différents fichiers de base de données ainsi que leur rôle.

<div>


> [!NOTE]  
> Si vos stratégies et configurations SQL Server nécessitent une installation plus spécialisée, la base de données et les fichiers journaux peuvent être installés sur un emplacement prédéfini à l’aide de Lync Server Management Shell. Pour plus d’informations, voir <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">installation de la base de données à l’aide de Lync Server Management Shell dans Lync server 2013</A> .



</div>

### <a name="data-and-log-files-for-central-management-store"></a>Fichiers de données et fichiers journaux pour le magasin central de gestion

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Fichiers de base de données du magasin central de gestion</th>
<th>Objectif du fichier de données ou du fichier journal</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XDS. ldf</p></td>
<td><p>Fichier journal des transactions pour le magasin central de gestion</p></td>
</tr>
<tr class="even">
<td><p>XDS. mdf</p></td>
<td><p>Gère la configuration de la topologie Lync Server 2013 actuelle, telle que définie et publiée par le générateur de topologies</p></td>
</tr>
<tr class="odd">
<td><p>Lis. mdf</p></td>
<td><p>Fichier de données du service informations d’emplacement</p></td>
</tr>
<tr class="even">
<td><p>Lis. ldf</p></td>
<td><p>Journal des transactions pour le fichier de données du service informations d’emplacement</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a>Fichiers de données et fichiers journaux pour l’utilisateur, la conférence et le carne d’adresses

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Principaux fichiers de base de données Lync Server 2013</th>
<th>Objectif du fichier de données ou du fichier journal</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTC. mdf</p></td>
<td><p>Données utilisateur persistantes (par exemple, listes de contrôle d’accès (ACL), contacts, conférences planifiées)</p></td>
</tr>
<tr class="even">
<td><p>RTC. ldf</p></td>
<td><p>Journal des transactions pour les données RTC</p></td>
</tr>
<tr class="odd">
<td><p>RTCDyn. mdf</p></td>
<td><p>Gère les données utilisateur temporaires (données d’exécution de présence)</p></td>
</tr>
<tr class="even">
<td><p>RTCDyn. ldf</p></td>
<td><p>Journal des transactions pour les données RTCDyn</p></td>
</tr>
<tr class="odd">
<td><p>RTCAb. mdf</p></td>
<td><p>La base de données de carnet d’adresses RTC est le référentiel SQL Server où les informations de service de carnet d’adresses sont stockées</p></td>
</tr>
<tr class="even">
<td><p>RTCAb. ldf</p></td>
<td><p>Fichier journal des transactions pour le service de carnet d’adresses</p></td>
</tr>
<tr class="odd">
<td><p>Rtclocal. mdb</p></td>
<td><p>Héberge l’annuaire des conférences</p></td>
</tr>
<tr class="even">
<td><p>Rtcxds. mdf</p></td>
<td><p>Conserve la sauvegarde des données utilisateur</p></td>
</tr>
<tr class="odd">
<td><p>Rtcxds. ldf</p></td>
<td><p>Journal des transactions pour les données Rtcxds</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a>Fichiers de données et fichiers journaux pour le parcage d’appel et le groupe Response Group

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Base de données d’applications</th>
<th>Objectif du fichier de données ou du fichier journal</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cpsdyn. mdf</p></td>
<td><p>Base de données d’informations dynamiques pour l’application de parcage d’appel</p></td>
</tr>
<tr class="even">
<td><p>Cpsdyn. ldf</p></td>
<td><p>Journal des transactions pour le fichier de données de l’application de parcage d’appel</p></td>
</tr>
<tr class="odd">
<td><p>Rgsconfig. mdf</p></td>
<td><p>Fichier de données du service Lync Server Response Group pour la configuration des services</p></td>
</tr>
<tr class="even">
<td><p>Rgsconfig. ldf</p></td>
<td><p>Fichier journal des transactions pour la configuration de l’application Response Group</p></td>
</tr>
<tr class="odd">
<td><p>Rgsdyn. mdf</p></td>
<td><p>Fichier de données du service Response Group pour les opérations d’exécution</p></td>
</tr>
<tr class="even">
<td><p>Rgsdyn. ldf</p></td>
<td><p>Fichier journal des transactions pour le fichier de données d’exécution du service Response Group</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a>Fichiers de données et fichiers journaux pour le serveur d’archivage et de surveillance

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Fichiers de base de données d’archivage et de surveillance</th>
<th>Objectif du fichier de données ou du fichier journal</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LcsCdr. mdf</p></td>
<td><p>Magasin de données pour le processus d’enregistrement des détails des appels (CDR) du serveur de surveillance</p></td>
</tr>
<tr class="even">
<td><p>LcsCdr. ldf</p></td>
<td><p>Fichier journal des transactions pour les données d’enregistrement des détails des appels (CDR)</p></td>
</tr>
<tr class="odd">
<td><p>QoEMetrics. mdf</p></td>
<td><p>Fichier de données de qualité de l’expérience stocké à partir du serveur de surveillance</p></td>
</tr>
<tr class="even">
<td><p>QoEMetrics. ldf</p></td>
<td><p>Fichier journal des transactions pour les données de surveillance</p></td>
</tr>
<tr class="odd">
<td><p>LcsLog. mdf</p></td>
<td><p>Fichier de données pour la rétention des données de messagerie instantanée et de conférence sur un serveur d’archivage</p></td>
</tr>
<tr class="even">
<td><p>LcsLog. ldf</p></td>
<td><p>Fichier journal des transactions pour les données d’archivage</p></td>
</tr>
</tbody>
</table>


Cette rubrique fait référence au disque et au jeu RAID. Veuillez noter que dans la configuration des ressources SQL Server, on appelle disque un périphérique matériel unique. Un disque dur à deux partitions, la première comportant les fichiers journaux et l’autre comportant les fichiers de données, est différent de deux disques dont l’un est dédié aux fichiers journaux et l’autre aux fichiers de données.

Concernant les jeux RAID, il existe diverses technologies RAID proposées par différents fournisseurs. En outre, avec la prolifération des réseaux SAN (Storage Area Network), les jeux RAID dédiés à un seul système sont plus rares. Vous devez consulter votre fournisseur de RAID ou SAN pour déterminer la configuration la plus adaptée à votre disposition de disque lors de la configuration des performances de SQL Server avec Lync Server 2013.

Veuillez noter que tous les disques n’offrent pas les mêmes performances initialement. Les performances de disques provenant d’un même fabricant peuvent aussi varier en raison de la vitesse de rotation, de la taille du cache matériel et d’autres facteurs.

</div>

<span> </span>

</div>

</div>

</div>

