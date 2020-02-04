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
ms.openlocfilehash: c2e6516ee1162c02f2bebc8c385c2f41e87d7781
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-to-restore-lync-server-2013"></a>Préparation de la restauration de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Avant de procéder à la restauration de serveurs et de bases de données après un échec, vous devez déterminer les éléments suivants :

  - Ce qui doit être restauré.

  - Le matériel, les logiciels, les données et les outils dont vous avez besoin pour la restauration.

<div>

## <a name="determining-what-to-restore"></a>Déterminer les données à restaurer

Cette rubrique décrit la restauration des pannes du serveur Lync qui se produisent au niveau du serveur, du pool ou du magasin de gestion central. En cas d’échec du magasin de gestion central, votre déploiement de Lync Server continue de fonctionner, mais vous ne pouvez pas apporter de modifications à la configuration. En cas d’échec d’un serveur principal ou d’un serveur Standard Edition Server, le pool d’utilisateurs cesse de fonctionner. En cas d’échec d’un autre serveur, l’amplitude de l’échec dépend du rôle de serveur exécuté sur le serveur et de l’hébergement d’une ou plusieurs bases de données par le serveur.

### <a name="what-to-restore"></a>Restauration

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Si ce n’est pas le cas</th>
<th>Consultez cette section :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>serveur Standard Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restauration d’un serveur Standard Edition Server dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>magasin central de gestion</p></td>
<td><p><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restauration du serveur qui héberge le magasin de gestion central dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Version back-end de l’entreprise</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restauration d’un serveur principal Enterprise Edition dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Serveur principal principal en miroir d’Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restauration d’un serveur principal Enterprise Edition en miroir sur Lync Server 2013-principal</a></p></td>
</tr>
<tr class="odd">
<td><p>Serveur secondaire de l’édition Enterprise en miroir</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restauration d’un serveur principal Enterprise Edition en miroir sur Lync Server 2013-Mirror</a></p></td>
</tr>
<tr class="even">
<td><p>Tout serveur Enterprise Edition exécutant un rôle serveur, tel qu’un serveur frontal, un serveur Edge, un directeur, un serveur de médiation, ou un serveur de chat permanent.</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restauration d’un serveur membre Enterprise Edition dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Ensemble d’un pool de serveurs Lync</p></td>
<td><p><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restauration d’un pool de serveurs Lync dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Magasin de fichiers Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-file-store.md">Restauration d’un magasin de fichiers dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Une base de données de surveillance autonome ou une base de données d’archivage</p></td>
<td><p><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restauration de données d’analyse ou d’archivage dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Une base de données de conversation permanente autonome</p></td>
<td><p><a href="lync-server-2013-restoring-persistent-chat-data.md">Restauration de données de conversations permanentes dans Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a>Rassemblement de matériel, de logiciels et d’outils

Lorsque vous restaurez un serveur, vous devez commencer avec un nouvel ordinateur ou nettoyer. Par ailleurs, vous devez disposer des éléments matériels et logiciels suivants :

  - Serveur propre ou nouveau avec le même nom de domaine complet (FQDN) que le serveur qui a échoué.
    
    <div>
    

    > [!IMPORTANT]  
    > Lorsque vous installez le système d’exploitation, assurez-vous de ne pas supprimer le compte d’ordinateur dans les services de domaine Active Directory (AD FS) et vérifiez que les autorisations de groupe associées au compte sont conservées.

    
    </div>

  - Programme d’installation du système d’exploitation. Pour installer le système d’exploitation, utilisez les procédures et configurations de déploiement de serveur établies par votre organisation. Pour restaurer le service, vous devez disposer de ces procédures et de vos exigences relatives à la configuration.

  - Programme d’installation de SQL Server 2012 ou SQL Server 2008 R2. Pour installer un serveur de base de données, utilisez la version appropriée de SQL Server, ainsi que les procédures et configurations de déploiement du serveur de base de données établies par votre organisation. Pour restaurer le service, vous devez disposer de ces procédures et de vos exigences relatives à la configuration.
    
    <div>
    

    > [!NOTE]  
    > L’Assistant Déploiement de Lync Server installe automatiquement SQL Server 2012 Express sur chaque serveur Standard Edition et sur n’importe quel autre serveur Lync Server lors de l’installation d’un magasin de configuration local, sauf si vous avez préinstallé SQL Server 2012 ou SQL Server 2008 R2 sur serveur.

    
    </div>

  - Logiciel pour la capture d’images système.
    
    <div>
    

    > [!TIP]  
    > Nous vous conseillons de prendre une copie d’image du système après l’installation du système d’exploitation et de SQL Server, et avant de commencer la restauration, afin que vous puissiez utiliser cette image comme point de restauration en cas de problème de restauration.

    
    </div>

  - Programme d’installation de Lync Server 2013. L’Assistant Déploiement de Lync Server se trouve dans le dossier d’installation ou le média \\de\\Lync\\Server lors de l’installation de l’application. exe.

Lors de la restauration, vous devez utiliser les outils suivants :

  - Cmdlets Lync Server Management Shell

  - Import-CsUserData

  - Outils de restauration de dossiers Windows

  - Générateur de topologie

  - Utilitaires de base de données SQL Server tels que SQL Server Management Studio

</div>

<div>

## <a name="preparing-to-restore-a-server"></a>Préparation de la restauration d’un serveur

Avant de restaurer le serveur, vous devez effectuer les étapes suivantes :

1.  Installez le système d’exploitation.

2.  S’il s’agit d’un serveur principal, installez SQL Server 2012 ou SQL Server 2008 R2.

3.  Restaurez ou réinscrivez vos certificats. Pour plus d’informations sur les certificats, voir « exigences de sauvegarde supplémentaires » dans [les exigences de sauvegarde et de restauration dans Lync Server 2013 : données](lync-server-2013-backup-and-restoration-requirements-data.md).

4.  Prenez une photo du système avant de commencer la restauration à utiliser comme point de restauration, en cas de problème de restauration.

<div>


> [!NOTE]  
> L’Assistant Déploiement de Lync Server et les applets de commande décrits dans les procédures décrites dans cette rubrique, ainsi que les rubriques connexes, définissent toutes les listes de contrôle d’accès (ACL) requises.



</div>

Vérifiez que le matériel et le logiciel dont vous avez besoin pour les composants que vous envisagez de restaurer sont disponibles avant de commencer la restauration. Après avoir installé le système d’exploitation et SQL Server, la plupart des étapes de la procédure de restauration suivantes peuvent être exécutées à distance. Les exceptions sont indiquées dans les procédures.

Pour plus d’informations, reportez-vous au plan de sauvegarde et de restauration de votre organisation ainsi qu’aux informations de votre dernière sauvegarde, telles que les informations figurant dans les feuilles de calcul de ce document (pour plus d’informations, reportez-vous à la rubrique [sauvegarde et restauration de feuilles de calcul pour Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), disponible avant de procéder à la restauration.

</div>

</div>

<span> </span>

</div>

</div>

</div>

