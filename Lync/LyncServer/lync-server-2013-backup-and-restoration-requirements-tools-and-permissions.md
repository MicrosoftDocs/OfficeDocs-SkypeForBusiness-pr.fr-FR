---
title: 'Lync Server 2013 : configuration requise pour la sauvegarde et la restauration : outils et autorisations'
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
ms.openlocfilehash: ea5e4ce57e61be50bfd1e2a78529830b4a40e3ed
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a>Configurations requises pour la sauvegarde et la restauration dans Lync Server 2013 : outils et autorisations

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-17_

Cette rubrique identifie les outils que vous pouvez utiliser pour sauvegarder et restaurer Lync Server 2013, les autorisations dont vous avez besoin et si vous pouvez exécuter des commandes à distance ou localement. Ce sujet décrit en particulier les outils fournis avec Lync Server pour la sauvegarde et la restauration.

<div>

## <a name="backups"></a>Sauvegardes

Pour sauvegarder Lync Server, utilisez les outils identifiés dans le tableau suivant. Toutes les commandes dont vous avez besoin pour sauvegarder Lync Server peuvent être rédigées en scripts et peuvent être exécutées à distance.

### <a name="tools-for-backing-up-lync-server"></a>Outils de sauvegarde de Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Pour sauvegarder ce problème, procédez comme suit :</th>
<th>Utilisez cet outil ou cette applet de applet :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Données de configuration topologique (XDS. mdf)</p></td>
<td><p>Export-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Données du service d’information d’emplacement (E9-1-1) (LIS. mdf)</p></td>
<td><p>Export-CsLisConfiguration</p></td>
</tr>
<tr class="odd">
<td><p>Données de configuration de Response Group (RgsConfig. mdf)</p></td>
<td><p>Export-CsRgsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Données utilisateur persistantes (base de données Rtcxds. mdf)</p>
<p>ID de conférence</p></td>
<td><p>Export-CsUserData</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>Archivage de la base de données (LcsLog. mdf)</p></li>
<li><p>Surveillance de la base de données d’enregistrement des détails des appels (LcsCDR. mdf)</p></li>
<li><p>Surveillance de la base de données QoE (QoEMetrics. mdf)</p></li>
</ul></td>
<td><p>Outil de base de données SQL Server, tel que SQL Server Management Studio</p></td>
</tr>
<tr class="even">
<td><p>Base de données de discussions permanentes (MGC. mdf)</p></td>
<td><p>Procédures de sauvegarde SQL Server ou Export-CsPersistentChatData. Export-CsPersistentChatData exporte les données de conversation persistante dans un fichier.</p></td>
</tr>
<tr class="odd">
<td><p>Tous les magasins de fichiers : magasin de fichiers Lync Server et magasin de fichiers d’archivage</p>
<div>

> [!NOTE]  
> Les fichiers nommés <STRONG>réunion. actif</STRONG> ne doivent pas être sauvegardés. Ces fichiers sont utilisés et verrouillés lors d’une réunion.


</div></td>
<td><p>Outil standard de gestion du système de fichiers, tel que Robocopy.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a>Répétition

Pour restaurer Lync Server, utilisez les outils figurant dans le tableau suivant. Toutes les commandes dont vous avez besoin pour restaurer Lync Server peuvent être scripts. Certains peuvent être exécutés à distance, mais d’autres doivent être exécutés localement, comme indiqué dans le tableau suivant.

### <a name="tools-for-restoring-lync-server"></a>Outils de restauration de Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Pour ce faire :</th>
<th>Utilisez cet outil ou cette applet de applet :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Créer un nouvel ordinateur ou nettoyer votre ordinateur</p></td>
<td><ul>
<li><p>Programme d’installation du système d’exploitation Windows</p></li>
<li><p>Programme d’installation de SQL Server</p></li>
<li><p>Composant logiciel enfichable Certificats de la console de gestion des certificats, si vous restaurez des certificats à l’aide d’une clé privée exportable</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Restaurer les données du magasin de fichiers</p></td>
<td><p>Outil standard de gestion du système de fichiers, tel que Robocopy</p></td>
</tr>
<tr class="odd">
<td><p>Recréer des bases de données vides et définir des autorisations pour les éléments suivants :</p>
<ul>
<li><p>magasin central de gestion</p></li>
<li><p>serveur principal</p></li>
<li><p>base de données de surveillance</p></li>
<li><p>base de données d’archivage</p></li>
</ul></td>
<td><p>Install-CsDatabase</p></td>
</tr>
<tr class="even">
<td><p>Restaurer le pointeur services de domaine Active Directory (AD FS) vers le magasin de gestion central</p>
<div>

> [!NOTE]  
> Si vous perdez le point de connexion de service à tout moment, vous pouvez réexécuter cette cmdlet.


</div></td>
<td><p>Set-CsConfigurationStoreLocation</p></td>
</tr>
<tr class="odd">
<td><p>Importer les paramètres de topologie, de stratégie et de configuration dans le magasin de gestion central (XDS. mdf)</p></td>
<td><p>Importation-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Publier et activer la topologie</p></td>
<td><p>Générateur de topologie</p>
<p>ou</p>
<p>Publisher-CsTopology et Enable-CsTopology</p></td>
</tr>
<tr class="odd">
<td><p>Activer la dernière topologie publiée</p></td>
<td><p>Enable-CsTopology</p></td>
</tr>
<tr class="even">
<td><p>Réinstaller les composants du serveur Lync</p></td>
<td><p>Configuration de Lync Server</p>
<div>

> [!NOTE]  
> Trouve dans le dossier d’installation ou le média de Lync Server sur \setup\amd64\Setup.exe.


</div></td>
</tr>
<tr class="odd">
<td><p>Restaurer des informations d’emplacement (E9-1-1) (LIS. mdf)</p></td>
<td><p>Import-CsLisConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Restaurer des données utilisateur persistantes (Rtcxds. mdf)</p></td>
<td><p>Import-CsUserData</p></td>
</tr>
<tr class="odd">
<td><p>Restauration des données de configuration de Response Group (RgsConfig. mdf)</p></td>
<td><p>Import-CsRgsConfiguration</p>
<div>

> [!NOTE]  
> Si la configuration est restaurée dans un nouveau pool déployé qui ne possède pas de données de groupe de réponse dans la base de données, vous devez utiliser l’option – OverwriteOwner. Utilisez cette option même si les données en cours de restauration se trouvent dans un pool portant le même nom de domaine complet (FQDN). Dans le cas contraire, l’importation échoue en raison des objets de contact dans les groupes de réponse déjà présents dans Active Directory.


</div></td>
</tr>
<tr class="even">
<td><p>Restaurez les bases de données suivantes :</p>
<ul>
<li><p>Archivage de la base de données (LcsLog. mdf)</p></li>
<li><p>Surveiller des bases de données : base de données d’enregistrement des détails des appels (LcsCDR. mdf) et base de données QoE (QoEMetrics. mdf)</p></li>
</ul></td>
<td><p>Outils de gestion de base de données SQL Server</p></td>
</tr>
<tr class="odd">
<td><p>Base de données de discussions permanentes (MGS. mdf)</p></td>
<td><p>Procédures de restauration SQL Server ou Import-CsPersistentChatData. Vous pouvez utiliser import-CsPersistentChatData avec un fichier créé par Export-CsPersistentChatData, et les données sont importées dans la base de données de chat persistant.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a>Autorisations requises

Les utilisateurs doivent être membres du groupe **RTCUniversalServerAdmins** pour effectuer toutes les commandes décrites dans cette rubrique. La plupart des commandes de sauvegarde et de restauration ne prennent pas en charge le contrôle d’accès basé sur les rôles (RBAC). Les applets de contrôle de chat permanent Export-CsPersistentChatData et Import-CsPersistentChatData doivent être exécutés par un utilisateur membre du groupe CsPersistentChatAdministrator. Pour exécuter l’Assistant Déploiement de Lync Server, un utilisateur doit également être membre du groupe administrateurs locaux.

</div>

</div>

<span> </span>

</div>

</div>

</div>

