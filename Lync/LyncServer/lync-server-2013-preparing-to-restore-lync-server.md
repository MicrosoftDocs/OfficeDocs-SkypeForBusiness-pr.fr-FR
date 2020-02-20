---
title: 'Lync Server 2013 : préparation de la restauration de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b397f389de461a04974fe063437caaabd9d4137
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-to-restore-lync-server-2013"></a>Préparation de la restauration de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Avant de commencer la restauration des serveurs et des bases de données après une défaillance, vous devez déterminer :

  - Ce qui doit être restauré.

  - Le matériel, les logiciels, les données et les outils dont vous avez besoin pour la restauration.

<div>

## <a name="determining-what-to-restore"></a>Détermination des éléments à restaurer

Cette rubrique décrit comment restaurer les pannes Lync Server qui se produisent au niveau du serveur, du pool ou du magasin central de gestion. Si le magasin central de gestion échoue, votre déploiement de Lync Server continue de fonctionner, mais vous ne pouvez pas modifier la configuration. En cas de défaillance d’un serveur principal ou d’un serveur Standard Edition, le pool d’utilisateurs cesse de fonctionner. En cas de défaillance d’un autre serveur, l’étendue de la défaillance dépend du rôle du serveur et du fait qu’il héberge ou non une ou plusieurs bases de données.

### <a name="what-to-restore"></a>Éléments à restaurer

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
<td><p><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restauration d’un serveur Standard Edition Server dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>magasin central de gestion</p></td>
<td><p><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restauration du serveur qui héberge le magasin central de gestion dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Serveur principal Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restauration d’un serveur principal Enterprise Edition dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Serveur principal principal en miroir Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restauration d’un serveur principal Enterprise Edition en miroir dans Lync Server 2013-principal</a></p></td>
</tr>
<tr class="odd">
<td><p>Serveur secondaire principal en miroir Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restauration d’un serveur principal Enterprise Edition en miroir dans Lync Server 2013-Mirror</a></p></td>
</tr>
<tr class="even">
<td><p>Tout serveur Enterprise Edition exécutant un rôle serveur, tel qu’un serveur frontal, un serveur Edge, un directeur, un serveur de médiation ou un serveur de conversation permanente.</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restauration d’un serveur membre Enterprise Edition dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Un pool Lync Server entier</p></td>
<td><p><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restauration d’un pool Lync Server dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Magasin de fichiers Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-file-store.md">Restauration d’un magasin de fichiers dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Une base de données de surveillance autonome ou une base de données d’archivage</p></td>
<td><p><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restauration des données de surveillance ou d’archivage dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Une base de données de conversation permanente autonome</p></td>
<td><p><a href="lync-server-2013-restoring-persistent-chat-data.md">Restauration des données de conversation permanente dans Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a>Collecte du matériel, des logiciels et des outils

Lorsque vous restaurez un serveur, vous devez démarrer avec un ordinateur nouveau ou propre. De plus, vous devez disposer des éléments suivants :

  - Un nouveau serveur ayant le même nom de domaine complet que le serveur ayant subi une défaillance.
    
    <div>
    

    > [!IMPORTANT]  
    > Lorsque vous installez le système d’exploitation, veillez à ne pas supprimer le compte d’ordinateur dans les services de domaine Active Directory et à vérifier que les autorisations de groupe pour le compte sont conservées.

    
    </div>

  - Logiciel d’installation pour le système d’exploitation. Pour installer le système d’exploitation, utilisez les configurations et procédures de déploiement de serveur établies par votre organisation. Ces procédures et conditions de configuration doivent être disponibles lorsque vous restaurez le service.

  - Logiciel d’installation pour SQL Server 2012 ou SQL Server 2008 R2. Pour installer un serveur de bases de données, utilisez la version appropriée de SQL Server et les procédures et configurations de déploiement de serveur de bases de données établies par votre organisation. Ces procédures et conditions de configuration doivent être disponibles lorsque vous restaurez le service.
    
    <div>
    

    > [!NOTE]  
    > L’Assistant Déploiement de Lync Server installe automatiquement SQL Server 2012 Express sur chaque serveur Standard Edition et sur tout autre serveur Lync Server lors de l’installation d’un magasin de configurations local, sauf si vous avez préinstallé SQL Server 2012 ou SQL Server 2008 R2 sur le serveur.

    
    </div>

  - Logiciels de prise d’images système
    
    <div>
    

    > [!TIP]  
    > Nous vous recommandons de prendre une copie de l’image du système après avoir installé le système d’exploitation et SQL Server, et avant de commencer la restauration, afin que vous puissiez utiliser cette image comme point de restauration en cas de problème lors de la restauration.

    
    </div>

  - Logiciel d’installation Lync Server 2013. L’Assistant Déploiement de Lync Server se trouve dans le dossier ou le support d’installation \\de\\Lync\\Server lors de l’installation de amd64 Setup. exe.

Durant la restauration, vous utilisez les outils suivants :

  - Applets de commande Lync Server Management Shell

  - Import-applet csuserdata

  - Outils de restauration des dossiers Windows

  - Générateur de topologies

  - Utilitaires de bases de données SQL Server, tels que SQL Server Management Studio

</div>

<div>

## <a name="preparing-to-restore-a-server"></a>Préparation à la restauration d’un serveur

Avant de restaurer le serveur, vous devez effectuer les étapes suivantes :

1.  Installez le système d’exploitation.

2.  Si le serveur est un serveur principal, installez SQL Server 2012 ou SQL Server 2008 R2.

3.  Restaurez ou réinscrivez vos certificats. Pour plus d’informations sur les certificats, voir « conditions de sauvegarde supplémentaires » dans Configuration de la [sauvegarde et de la restauration dans Lync Server 2013 : Data](lync-server-2013-backup-and-restoration-requirements-data.md).

4.  Prenez une image du système avant de commencer la restauration afin de l’utiliser comme point de restauration, en cas de problème lors de la restauration.

<div>


> [!NOTE]  
> L’Assistant Déploiement Lync Server et les cmdlets décrits dans les procédures de cette rubrique, ainsi que les rubriques connexes, définissent toutes les listes de contrôle d’accès (ACL) requises.



</div>

Vérifiez que le matériel et le logiciel dont vous avez besoin pour les composants que vous prévoyez de restaurer sont disponibles avant de commencer la restauration. Une fois que vous avez installé le système d’exploitation et SQL Server, la plupart des étapes des procédures de restauration suivantes peuvent être effectuées à distance. Les exceptions sont notées dans les procédures.

Vous devez également avoir le plan de sauvegarde et de restauration de votre organisation, ainsi que les informations de votre dernière sauvegarde, telles que les informations contenues dans les feuilles de calcul de ce document (pour plus de détails, voir [Backup and Restoring Worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), disponible avant de commencer la restauration.

</div>

</div>

<span> </span>

</div>

</div>

</div>

