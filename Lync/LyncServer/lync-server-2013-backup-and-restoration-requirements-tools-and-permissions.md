---
title: 'Lync Server 2013 : conditions requises en matière de sauvegarde et de restauration : outils et autorisations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b273674d1f2ad20a0379c65e35e85ae0300df3dc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a>Configuration requise pour la sauvegarde et la restauration dans Lync Server 2013 : outils et autorisations

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-17_

Cette rubrique identifie les outils que vous pouvez utiliser pour sauvegarder et restaurer Lync Server 2013, les autorisations dont vous avez besoin et si vous pouvez exécuter des commandes à distance ou localement. Plus précisément, cette rubrique se concentre sur les outils fournis avec Lync Server pour la sauvegarde et la restauration.

<div>

## <a name="backups"></a>Sauvegardes

Pour sauvegarder Lync Server, utilisez les outils identifiés dans le tableau suivant. Toutes les commandes dont vous avez besoin pour sauvegarder Lync Server peuvent être scriptées et exécutées à distance.

### <a name="tools-for-backing-up-lync-server"></a>Outils de sauvegarde de Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Pour sauvegarder ces éléments, procédez comme suit :</th>
<th>Utilisez cet outil ou cette applet de commande :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Données de configuration de topologie (XDS. mdf)</p></td>
<td><p>Export-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Données de service d’informations d’emplacement (E9-1-1) (LIS. mdf)</p></td>
<td><p>Export-CsLisConfiguration</p></td>
</tr>
<tr class="odd">
<td><p>Données de configuration de Response Group (RgsConfig. mdf)</p></td>
<td><p>Export-applet csrgsconfiguration</p></td>
</tr>
<tr class="even">
<td><p>Données utilisateur persistantes (base de données Rtcxds. mdf)</p>
<p>ID de conférence</p></td>
<td><p>Export-applet csuserdata</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>Base de données d’archivage (LcsLog. mdf)</p></li>
<li><p>Base de données d’enregistrement des détails des appels de surveillance (LcsCDR. mdf)</p></li>
<li><p>Surveillance de la base de données QoE (QoEMetrics. mdf)</p></li>
</ul></td>
<td><p>Outil de base de données SQL Server, tel que SQL Server Management Studio</p></td>
</tr>
<tr class="even">
<td><p>Base de données de conversation permanente (MGC. mdf)</p></td>
<td><p>Procédures de sauvegarde SQL Server ou Export-applet cspersistentchatdata. Export-applet cspersistentchatdata exporte les données de conversation permanente sous forme de fichier.</p></td>
</tr>
<tr class="odd">
<td><p>Tous les magasins de fichiers : magasin de fichiers Lync Server, magasin de fichiers d’archivage</p>
<div>

> [!NOTE]  
> Les fichiers nommés <STRONG>Meeting. active</STRONG> ne doivent pas être sauvegardés. Ces fichiers sont en cours d’utilisation et verrouillés lors d’une réunion.


</div></td>
<td><p>Outil de gestion de système de fichiers standard, tel que Robocopy.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a>Generation

Pour restaurer Lync Server, utilisez les outils dans le tableau suivant. Toutes les commandes dont vous avez besoin pour restaurer Lync Server peuvent être scriptées. Certaines peuvent être exécutées à distance, mais d’autres doivent être exécutées localement, comme indiqué dans le tableau suivant.

### <a name="tools-for-restoring-lync-server"></a>Outils de restauration de Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Pour ce faire :</th>
<th>Utilisez cet outil ou cette applet de commande :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Créer un ordinateur nouveau ou propre</p></td>
<td><ul>
<li><p>Logiciel d’installation du système d’exploitation Windows</p></li>
<li><p>Logiciel d’installation de SQL Server</p></li>
<li><p>Composant logiciel enfichable Certificats de la console MMC (Microsoft Management Console), si vous restaurez des certificats avec une clé privée exportable</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Restaurer les données du magasin de fichiers</p></td>
<td><p>Outil de gestion de système de fichiers standard, tel que Robocopy</p></td>
</tr>
<tr class="odd">
<td><p>Recréez les bases de données vides et définissez des autorisations pour les éléments suivants :</p>
<ul>
<li><p>magasin central de gestion</p></li>
<li><p>serveur principal</p></li>
<li><p>Base de données de surveillance</p></li>
<li><p>Base de données d’archivage</p></li>
</ul></td>
<td><p>Install-applet csdatabase</p></td>
</tr>
<tr class="even">
<td><p>Restaurer le pointeur des services de domaine Active Directory vers le magasin central de gestion</p>
<div>

> [!NOTE]  
> Si vous perdez le point de connexion de service à tout moment, vous pouvez réexécuter cette applet de commande.


</div></td>
<td><p>Set-CsConfigurationStoreLocation</p></td>
</tr>
<tr class="odd">
<td><p>Importer la topologie, les stratégies et les paramètres de configuration dans le magasin central de gestion (XDS. mdf)</p></td>
<td><p>Import-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Publier et activer la topologie</p></td>
<td><p>Générateur de topologies</p>
<p>- ou -</p>
<p>Publish-CsTopology et Enable-CsTopology</p></td>
</tr>
<tr class="odd">
<td><p>Activer la dernière topologie publiée</p></td>
<td><p>Enable-CsTopology</p></td>
</tr>
<tr class="even">
<td><p>Réinstaller les composants Lync Server</p></td>
<td><p>Programme d’installation de Lync Server</p>
<div>

> [!NOTE]  
> Situé dans le dossier ou le support d’installation de Lync Server sur \setup\amd64\Setup.exe.


</div></td>
</tr>
<tr class="odd">
<td><p>Restaurer les données d’informations d’emplacement (E9-1-1) (LIS. mdf)</p></td>
<td><p>Import-CsLisConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Restaurer les données utilisateur persistantes (Rtcxds. mdf)</p></td>
<td><p>Import-applet csuserdata</p></td>
</tr>
<tr class="odd">
<td><p>Restaurer les données de configuration du groupe Response Group (RgsConfig. mdf)</p></td>
<td><p>Import-applet csrgsconfiguration</p>
<div>

> [!NOTE]  
> Si la configuration est restaurée dans un pool nouvellement déployé sans données Response Group dans la base de données, vous devez utiliser l’option – OverwriteOwner. Utilisez cette option même si les données en cours de restauration se trouvent dans un pool avec le même nom de domaine complet (FQDN). Dans le cas contraire, l’importation échouera, car les objets contact sont déjà présents dans Active Directory.


</div></td>
</tr>
<tr class="even">
<td><p>Restaurez les bases de données suivantes :</p>
<ul>
<li><p>Base de données d’archivage (LcsLog. mdf)</p></li>
<li><p>Bases de données de surveillance : base de données d’enregistrements des détails des appels (LcsCDR. mdf) et base de données QoE (QoEMetrics. mdf)</p></li>
</ul></td>
<td><p>Outils de gestion de base de données SQL Server</p></td>
</tr>
<tr class="odd">
<td><p>Base de données de conversation permanente (MGS. mdf)</p></td>
<td><p>Procédures de restauration SQL Server ou Import-applet cspersistentchatdata. Vous pouvez utiliser import-applet cspersistentchatdata avec un fichier créé par Export-applet cspersistentchatdata, et les données seront importées dans la base de données de conversation permanente.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a>Autorisations requises

Les utilisateurs doivent être membres du groupe **RTCUniversalServerAdmins** pour effectuer toutes les commandes décrites dans cette rubrique. La plupart des commandes de sauvegarde et de restauration ne prennent pas en charge le contrôle d’accès basé sur un rôle (RBAC). Il existe deux exceptions : les cmdlets de conversation permanente Export-applet cspersistentchatdata et Import-applet cspersistentchatdata, qui doivent être exécutées par un utilisateur membre du groupe CsPersistentChatAdministrator. Pour exécuter l’Assistant Déploiement Lync Server, un utilisateur doit également être membre du groupe Administrateurs local.

</div>

</div>

<span> </span>

</div>

</div>

</div>

