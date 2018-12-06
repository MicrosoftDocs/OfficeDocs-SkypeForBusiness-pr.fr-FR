---
title: 'Lync Server 2013 : Emplacement des fichiers journaux et des données SQL Server'
TOCTitle: Emplacement des fichiers journaux et des données SQL Server
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398479(v=OCS.15)
ms:contentKeyID: 49297467
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Emplacement des fichiers journaux et des données SQL Server pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Lors de la planification et du déploiement de Microsoft SQL Server 2012 ou Microsoft SQL Server 2008 R2 SP1 pour votre pool de serveurs frontauxLync Server 2013, le placement des données et des fichiers journaux sur des disques durs physiques à des fins de performances est un exercice essentiel. La configuration de disques recommandée consiste à mettre en œuvre un jeu RAID 1+0 avec 6 piles. Le scénario optimal consiste à placer tous les fichiers journaux et de bases de données utilisés par le pool de serveurs frontaux et les rôles serveur et services associés (autrement dit, serveur d’archivage et de surveillance, service Response Group Lync Server, service de parcage d’appel Lync Server) sur le jeu de lecteurs RAID à l’aide de l’Assistant Déploiement de Lync Server. Le tableau ci-dessous présente les différents fichiers de bases de données ainsi que leur rôle.

> [!NOTE]  
> Si vos stratégies et configurations SQL Server nécessitent une installation plus spécialisée, les fichiers journaux et de bases de données peuvent être installés à tout emplacement prédéfini à l’aide de Lync Server Management Shell. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Installation de la base de données avec Lync Server Management Shell dans Lync Server 2013</a>.

### Fichiers de données et fichiers journaux pour le magasin central de gestion

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Fichiers de base de données magasin central de gestion</th>
<th>Objectif du fichier de données ou du fichier journal</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Xds.ldf</p></td>
<td><p>Fichier journal des transactions pour le magasin central de gestion</p></td>
</tr>
<tr class="even">
<td><p>Xds.mdf</p></td>
<td><p>Gère la configuration de la topologie Lync Server 2013 actuelle, telle que définie et publiée par le Générateur de topologie</p></td>
</tr>
<tr class="odd">
<td><p>Lis.mdf</p></td>
<td><p>Fichier de données du service d’informations sur l’emplacement</p></td>
</tr>
<tr class="even">
<td><p>Lis.ldf</p></td>
<td><p>Fichier journal des transactions pour le service d’informations sur l’emplacement</p></td>
</tr>
</tbody>
</table>


### Fichiers de données et fichiers journaux pour l’utilisateur, la conférence et le carne d’adresses

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Fichiers de base de données Lync Server 2013 principaux</th>
<th>Objectif du fichier de données ou du fichier journal</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Rtc.mdf</p></td>
<td><p>Données utilisateur permanentes (par exemple, listes de contrôle d’accès, contacts, conférences planifiées)</p></td>
</tr>
<tr class="even">
<td><p>Rtc.ldf</p></td>
<td><p>Journal des transactions pour les données Rtc</p></td>
</tr>
<tr class="odd">
<td><p>Rtcdyn.mdf</p></td>
<td><p>Tient à jour les données utilisateur transitoires (données d’exécution de présence)</p></td>
</tr>
<tr class="even">
<td><p>Rtcdyn.ldf</p></td>
<td><p>Journal des transactions pour les données Rtcdyn</p></td>
</tr>
<tr class="odd">
<td><p>Rtcab.mdf</p></td>
<td><p>La base de données de carnet d’adresses RTC est le référentiel SQL Server où les informations de service de carnet d’adresses sont stockées</p></td>
</tr>
<tr class="even">
<td><p>Rtcab.ldf</p></td>
<td><p>Fichier journal des transactions pour le service de carnet d’adresses</p></td>
</tr>
<tr class="odd">
<td><p>Rtclocal.mdb</p></td>
<td><p>Héberge l’annuaire des conférences</p></td>
</tr>
<tr class="even">
<td><p>Rtcxds.mdf</p></td>
<td><p>Tient à jour la sauvegarde des données utilisateur</p></td>
</tr>
<tr class="odd">
<td><p>Rtcxds.ldf</p></td>
<td><p>Journal des transactions pour les données Rtcxds</p></td>
</tr>
</tbody>
</table>


### Fichiers de données et fichiers journaux pour le parcage d’appel et le groupe Response Group

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>base de données d’applications</th>
<th>Objectif du fichier de données ou du fichier journal</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cpsdyn.mdf</p></td>
<td><p>Base de données d’informations dynamiques pour l’application de parcage d’appel</p></td>
</tr>
<tr class="even">
<td><p>Cpsdyn.ldf</p></td>
<td><p>Fichier journal des transactions pour le fichier de données de l’application de parcage d’appel</p></td>
</tr>
<tr class="odd">
<td><p>Rgsconfig.mdf</p></td>
<td><p>Fichier de données du service Lync Server Response Group pour la configuration des services</p></td>
</tr>
<tr class="even">
<td><p>Rgsconfig.ldf</p></td>
<td><p>Fichier journal des transactions pour la configuration de l’application Response Group</p></td>
</tr>
<tr class="odd">
<td><p>Rgsdyn.mdf</p></td>
<td><p>Fichier de données du service Response Group pour les opérations d’exécution</p></td>
</tr>
<tr class="even">
<td><p>Rgsdyn.ldf</p></td>
<td><p>Fichier journal des transactions pour le fichier de données d’exécution du service Response Group</p></td>
</tr>
</tbody>
</table>


### Fichiers de données et fichiers journaux pour le serveur d’archivage et de surveillance

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
<td><p>LcsCdr.mdf</p></td>
<td><p>Magasin de données pour le processus d’enregistrement des détails des appels (CDR) du serveur de surveillance</p></td>
</tr>
<tr class="even">
<td><p>LcsCdr.ldf</p></td>
<td><p>Fichier journal des transactions pour les données d’enregistrement des détails des appels (CDR)</p></td>
</tr>
<tr class="odd">
<td><p>QoEMetrics.mdf</p></td>
<td><p>Fichier de données de qualité de l’expérience stocké sur le serveur de surveillance</p></td>
</tr>
<tr class="even">
<td><p>QoEMetrics.ldf</p></td>
<td><p>Fichier journal des transactions pour les données de surveillance</p></td>
</tr>
<tr class="odd">
<td><p>Lcslog.mdf</p></td>
<td><p>Fichier de données pour la conservation des données de messagerie instantanée et de conférence sur un serveur d’archivage</p></td>
</tr>
<tr class="even">
<td><p>Lcslog.ldf</p></td>
<td><p>Fichier journal des transactions pour les données d’archivage</p></td>
</tr>
</tbody>
</table>


Cette rubrique fait référence au disque et au jeu RAID. Veuillez noter que dans la configuration des ressources SQL Server, on appelle disque un périphérique matériel unique. Un disque dur à deux partitions, la première comportant les fichiers journaux et l’autre comportant les fichiers de données, est différent de deux disques dont l’un est dédié aux fichiers journaux et l’autre aux fichiers de données.

Concernant les jeux RAID, il existe diverses technologies RAID proposées par différents fournisseurs. En outre, avec la prolifération des réseaux SAN (Storage Area Network), les jeux RAID dédiés à un seul système sont plus rares. Contactez votre fournisseur de systèmes RAID ou SAN pour déterminer la meilleure configuration à appliquer à votre disposition de disque lors de la configuration des performances SQL Server avec Lync Server 2013.

Notez que tous les disques n’offrent pas les mêmes performances initiales. Les performances de disques provenant d’un même fabricant peuvent aussi varier en raison de la vitesse de rotation, de la taille du cache matériel et d’autres facteurs.

