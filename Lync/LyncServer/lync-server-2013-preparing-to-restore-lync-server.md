---
title: Préparation à la restauration de Lync Server
TOCTitle: Préparation à la restauration de Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh202179(v=OCS.15)
ms:contentKeyID: 53095469
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Préparation à la restauration de Lync Server

 

_**Dernière rubrique modifiée :** 2015-03-09_

Avant de commencer la restauration des serveurs et des bases de données après une défaillance, vous devez déterminer :

  - les éléments à restaurer ;

  - le matériel, les logiciels, les données et les outils nécessaires à la restauration.

## Détermination des éléments à restaurer

Cette rubrique décrit comment effectuer une restauration suite à une défaillance de Lync Server qui s’est produite au niveau du serveur, du pool ou du magasin central de gestion. En cas de défaillance du magasin central de gestion, votre déploiement de Lync Server continue de fonctionner, mais la modification de la configuration est impossible. En cas de défaillance d’un serveur principal ou d’un serveur Standard Edition, le pool d’utilisateurs cesse de fonctionner. En cas de défaillance d’un autre serveur, l’étendue de la défaillance dépend du rôle du serveur et du fait qu’il héberge ou non une ou plusieurs bases de données.

### Éléments à restaurer

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>En cas de défaillance de cet élément</th>
<th>Voir cette section :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serveur Standard Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restauration d’un serveur Standard Edition</a></p></td>
</tr>
<tr class="even">
<td><p>magasin central de gestion</p></td>
<td><p><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restauration du serveur hébergeant le magasin central de gestion</a></p></td>
</tr>
<tr class="odd">
<td><p>Serveur principal Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restauration du serveur principal Enterprise Edition</a></p></td>
</tr>
<tr class="even">
<td><p>Serveur principal en miroir Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restauration d’un serveur principal Enterprise Edition en miroir - Base de données primaire</a></p></td>
</tr>
<tr class="odd">
<td><p>Serveur secondaire en miroir Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restauration d’un serveur principal Enterprise Edition en miroir - Miroir</a></p></td>
</tr>
<tr class="even">
<td><p>Tout serveur Enterprise Edition exécutant un seul rôle serveur, tel qu’un serveur frontal, serveur Edge, directeur, serveur de médiation ou serveur de conversation permanente.</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restauration d’un serveur membre Enterprise Edition</a></p></td>
</tr>
<tr class="odd">
<td><p>Un pool Lync Server entier</p></td>
<td><p><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restauration d’un pool Lync Server</a></p></td>
</tr>
<tr class="even">
<td><p>magasin de fichiers Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-file-store.md">Restauration d’un magasin de fichiers</a></p></td>
</tr>
<tr class="odd">
<td><p>Une base de données d’archivage ou de surveillance autonome</p></td>
<td><p><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restauration des données de surveillance ou d’archivage</a></p></td>
</tr>
<tr class="even">
<td><p>Une base de données de conversation permanente autonome</p></td>
<td><p><a href="lync-server-2013-restoring-persistent-chat-data.md">Restauration de données de conversation permanente</a></p></td>
</tr>
</tbody>
</table>


## Collecte du matériel, des logiciels et des outils

Lors de la restauration d’un serveur, vous devez prendre pour base un nouvel ordinateur et disposer du matériel et des logiciels suivants :

  - Un nouveau serveur ayant le même nom de domaine complet que le serveur ayant subi une défaillance.
    
    > [!IMPORTANT]  
    > Lors de l’installation du système d’exploitation, veillez à ne pas supprimer le compte d’ordinateur dans les services de domaine Active Directory et vérifiez que les autorisations de groupe pour le compte sont conservées.

  - Logiciel d’installation pour le système d’exploitation. Pour installer le système d’exploitation, utilisez les configurations et procédures de déploiement de serveur établies par votre organisation. Celles-ci doivent être à votre disposition lors de la restauration du service.

  - Logiciel d’installation pour SQL Server 2012 ou SQL Server 2008 R2. Pour installer un serveur de bases de données, utilisez la version appropriée de SQL Server et les procédures et configurations de déploiement de serveur de bases de données établies par votre organisation. Celles-ci doivent être à votre disposition lors de la restauration du service.
    
    > [!NOTE]  
    > L’Assistant Déploiement de Lync Server installe automatiquement SQL Server 2012 Express sur chaque serveur Standard Edition et sur tout autre serveur Lync Server lors de l’installation d’un magasin de configurations local, à moins que vous n’ayez préinstallé SQL Server 2012 ou SQL Server 2008 R2 Express sur le serveur.

  - Logiciels de prise d’images système
    
    > [!TIP]  
    > Nous vous recommandons de créer une image du système après avoir installé le système d’exploitation et SQL Server et avant de commencer la restauration, de manière à pouvoir utiliser cette image comme point de restauration dans l’éventualité où un problème surviendrait lors de la restauration.

  - Logiciel d’installation de Lync Server 2013. L’Assistant Déploiement de Lync Server se trouve sur le support ou dans le dossier d’installation de Lync Server à l’emplacement \\setup\\amd64\\Setup.exe.

Durant la restauration, vous utilisez les outils suivants :

  - Applets de commande Lync Server Management Shell

  - Import-CsUserData

  - Outils de restauration des dossiers Windows

  - Générateur de topologie

  - Utilitaires de bases de données SQL Server, tels que SQL Server Management Studio

## Préparation à la restauration d’un serveur

Avant de restaurer le serveur, vous devez effectuer les étapes suivantes :

1.  Installez le système d’exploitation.

2.  S’il s’agit d’un serveur principal, installez SQL Server 2012, ou SQL Server 2008 R2.

3.  Restaurez ou réinscrivez vos certificats. Pour plus d’informations sur les certificats, voir « Exigences supplémentaires relatives à la sauvegarde » dans [Besoins de sauvegarde et de restauration dans Lync Server 2013 : données](lync-server-2013-backup-and-restoration-requirements-data.md).

4.  Créez une image du système avant de commencer la restauration. Celle-ci servira de point de restauration en cas de problème.

> [!NOTE]  
> L’Assistant Déploiement de Lync Server et les applets de commande décrites dans les procédures de cette section, et dans les sections associées, définissent toutes les listes de contrôle d’accès requises.

Avant de commencer la restauration, vérifiez que le matériel et les logiciels dont vous avez besoin pour les éléments que vous prévoyez de restaurer sont disponibles. Une fois le système d’exploitation et SQL Server installés, la plupart des étapes des procédures de restauration suivantes peuvent être effectuées à distance. Les exceptions sont notées dans les procédures.

Avant de commencer la restauration, vous devez également avoir à votre disposition le plan de sauvegarde et de restauration de votre organisation, ainsi que les informations relatives à votre dernière sauvegarde, telles que celles décrites dans les feuilles de calcul de ce document (pour plus de détails, voir [Feuilles de travail de sauvegarde et de restauration](lync-server-2013-backup-and-restoration-worksheets.md)).

