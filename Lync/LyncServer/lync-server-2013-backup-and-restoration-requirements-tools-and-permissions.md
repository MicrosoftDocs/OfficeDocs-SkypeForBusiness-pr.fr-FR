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

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a><span data-ttu-id="d07d5-102">Configurations requises pour la sauvegarde et la restauration dans Lync Server 2013 : outils et autorisations</span><span class="sxs-lookup"><span data-stu-id="d07d5-102">Backup and restoration requirements in Lync Server 2013: tools and permissions</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d07d5-103">_**Dernière modification de la rubrique :** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="d07d5-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="d07d5-104">Cette rubrique identifie les outils que vous pouvez utiliser pour sauvegarder et restaurer Lync Server 2013, les autorisations dont vous avez besoin et si vous pouvez exécuter des commandes à distance ou localement.</span><span class="sxs-lookup"><span data-stu-id="d07d5-104">This topic identifies the tools that you can use to back up and restore Lync Server 2013, the permissions that you need, and whether you can run commands remotely or locally.</span></span> <span data-ttu-id="d07d5-105">Ce sujet décrit en particulier les outils fournis avec Lync Server pour la sauvegarde et la restauration.</span><span class="sxs-lookup"><span data-stu-id="d07d5-105">Specifically, this topic focuses on tools that are provided with Lync Server for backup and restoration.</span></span>

<div>

## <a name="backups"></a><span data-ttu-id="d07d5-106">Sauvegardes</span><span class="sxs-lookup"><span data-stu-id="d07d5-106">Backups</span></span>

<span data-ttu-id="d07d5-107">Pour sauvegarder Lync Server, utilisez les outils identifiés dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="d07d5-107">To back up Lync Server, use the tools identified in the following table.</span></span> <span data-ttu-id="d07d5-108">Toutes les commandes dont vous avez besoin pour sauvegarder Lync Server peuvent être rédigées en scripts et peuvent être exécutées à distance.</span><span class="sxs-lookup"><span data-stu-id="d07d5-108">All the commands that you need to back up Lync Server can be scripted and can be run remotely.</span></span>

### <a name="tools-for-backing-up-lync-server"></a><span data-ttu-id="d07d5-109">Outils de sauvegarde de Lync Server</span><span class="sxs-lookup"><span data-stu-id="d07d5-109">Tools for Backing Up Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d07d5-110">Pour sauvegarder ce problème, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d07d5-110">To back up this:</span></span></th>
<th><span data-ttu-id="d07d5-111">Utilisez cet outil ou cette applet de applet :</span><span class="sxs-lookup"><span data-stu-id="d07d5-111">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d07d5-112">Données de configuration topologique (XDS. mdf)</span><span class="sxs-lookup"><span data-stu-id="d07d5-112">Topology configuration data (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="d07d5-113">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="d07d5-113">Export-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d07d5-114">Données du service d’information d’emplacement (E9-1-1) (LIS. mdf)</span><span class="sxs-lookup"><span data-stu-id="d07d5-114">Location information service (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="d07d5-115">Export-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="d07d5-115">Export-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d07d5-116">Données de configuration de Response Group (RgsConfig. mdf)</span><span class="sxs-lookup"><span data-stu-id="d07d5-116">Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="d07d5-117">Export-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="d07d5-117">Export-CsRgsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d07d5-118">Données utilisateur persistantes (base de données Rtcxds. mdf)</span><span class="sxs-lookup"><span data-stu-id="d07d5-118">Persistent user data (Rtcxds.mdf database)</span></span></p>
<p><span data-ttu-id="d07d5-119">ID de conférence</span><span class="sxs-lookup"><span data-stu-id="d07d5-119">Conference IDs</span></span></p></td>
<td><p><span data-ttu-id="d07d5-120">Export-CsUserData</span><span class="sxs-lookup"><span data-stu-id="d07d5-120">Export-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="d07d5-121">Archivage de la base de données (LcsLog. mdf)</span><span class="sxs-lookup"><span data-stu-id="d07d5-121">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="d07d5-122">Surveillance de la base de données d’enregistrement des détails des appels (LcsCDR. mdf)</span><span class="sxs-lookup"><span data-stu-id="d07d5-122">Monitoring call detail record database (LcsCDR.mdf)</span></span></p></li>
<li><p><span data-ttu-id="d07d5-123">Surveillance de la base de données QoE (QoEMetrics. mdf)</span><span class="sxs-lookup"><span data-stu-id="d07d5-123">Monitoring QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d07d5-124">Outil de base de données SQL Server, tel que SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d07d5-124">SQL Server database tool, such as SQL Server Management Studio</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d07d5-125">Base de données de discussions permanentes (MGC. mdf)</span><span class="sxs-lookup"><span data-stu-id="d07d5-125">Persistent Chat database (Mgc.mdf)</span></span></p></td>
<td><p><span data-ttu-id="d07d5-126">Procédures de sauvegarde SQL Server ou Export-CsPersistentChatData.</span><span class="sxs-lookup"><span data-stu-id="d07d5-126">SQL Server backup procedures or Export-CsPersistentChatData.</span></span> <span data-ttu-id="d07d5-127">Export-CsPersistentChatData exporte les données de conversation persistante dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="d07d5-127">Export-CsPersistentChatData exports Persistent Chat data as a file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d07d5-128">Tous les magasins de fichiers : magasin de fichiers Lync Server et magasin de fichiers d’archivage</span><span class="sxs-lookup"><span data-stu-id="d07d5-128">All file stores: Lync Server file store, Archiving file store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="d07d5-129">Les fichiers nommés <STRONG>réunion. actif</STRONG> ne doivent pas être sauvegardés.</span><span class="sxs-lookup"><span data-stu-id="d07d5-129">Files named <STRONG>Meeting.Active</STRONG> should not be backed up.</span></span> <span data-ttu-id="d07d5-130">Ces fichiers sont utilisés et verrouillés lors d’une réunion.</span><span class="sxs-lookup"><span data-stu-id="d07d5-130">These files are in use and locked while a meeting takes place.</span></span>


</div></td>
<td><p><span data-ttu-id="d07d5-131">Outil standard de gestion du système de fichiers, tel que Robocopy.</span><span class="sxs-lookup"><span data-stu-id="d07d5-131">Standard file system management tool, such as Robocopy.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a><span data-ttu-id="d07d5-132">Répétition</span><span class="sxs-lookup"><span data-stu-id="d07d5-132">Restoration</span></span>

<span data-ttu-id="d07d5-133">Pour restaurer Lync Server, utilisez les outils figurant dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="d07d5-133">To restore Lync Server, use the tools in the following table.</span></span> <span data-ttu-id="d07d5-134">Toutes les commandes dont vous avez besoin pour restaurer Lync Server peuvent être scripts.</span><span class="sxs-lookup"><span data-stu-id="d07d5-134">All the commands that you need to restore Lync Server can be scripted.</span></span> <span data-ttu-id="d07d5-135">Certains peuvent être exécutés à distance, mais d’autres doivent être exécutés localement, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="d07d5-135">Some can be run remotely, but others need to be run locally, as specified in the following table.</span></span>

### <a name="tools-for-restoring-lync-server"></a><span data-ttu-id="d07d5-136">Outils de restauration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="d07d5-136">Tools for Restoring Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d07d5-137">Pour ce faire :</span><span class="sxs-lookup"><span data-stu-id="d07d5-137">To do this:</span></span></th>
<th><span data-ttu-id="d07d5-138">Utilisez cet outil ou cette applet de applet :</span><span class="sxs-lookup"><span data-stu-id="d07d5-138">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d07d5-139">Créer un nouvel ordinateur ou nettoyer votre ordinateur</span><span class="sxs-lookup"><span data-stu-id="d07d5-139">Build a new or clean computer</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d07d5-140">Programme d’installation du système d’exploitation Windows</span><span class="sxs-lookup"><span data-stu-id="d07d5-140">Windows operating system installation software</span></span></p></li>
<li><p><span data-ttu-id="d07d5-141">Programme d’installation de SQL Server</span><span class="sxs-lookup"><span data-stu-id="d07d5-141">SQL Server installation software</span></span></p></li>
<li><p><span data-ttu-id="d07d5-142">Composant logiciel enfichable Certificats de la console de gestion des certificats, si vous restaurez des certificats à l’aide d’une clé privée exportable</span><span class="sxs-lookup"><span data-stu-id="d07d5-142">Certificates Microsoft Management Console (MMC) snap-in, if restoring certificates with an exportable private key</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d07d5-143">Restaurer les données du magasin de fichiers</span><span class="sxs-lookup"><span data-stu-id="d07d5-143">Restore file store data</span></span></p></td>
<td><p><span data-ttu-id="d07d5-144">Outil standard de gestion du système de fichiers, tel que Robocopy</span><span class="sxs-lookup"><span data-stu-id="d07d5-144">Standard file system management tool, such as Robocopy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d07d5-145">Recréer des bases de données vides et définir des autorisations pour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="d07d5-145">Recreate empty databases and set permissions for the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d07d5-146">magasin central de gestion</span><span class="sxs-lookup"><span data-stu-id="d07d5-146">Central Management store</span></span></p></li>
<li><p><span data-ttu-id="d07d5-147">serveur principal</span><span class="sxs-lookup"><span data-stu-id="d07d5-147">Back End Server</span></span></p></li>
<li><p><span data-ttu-id="d07d5-148">base de données de surveillance</span><span class="sxs-lookup"><span data-stu-id="d07d5-148">Monitoring database</span></span></p></li>
<li><p><span data-ttu-id="d07d5-149">base de données d’archivage</span><span class="sxs-lookup"><span data-stu-id="d07d5-149">Archiving database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d07d5-150">Install-CsDatabase</span><span class="sxs-lookup"><span data-stu-id="d07d5-150">Install-CsDatabase</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d07d5-151">Restaurer le pointeur services de domaine Active Directory (AD FS) vers le magasin de gestion central</span><span class="sxs-lookup"><span data-stu-id="d07d5-151">Restore the Active Directory Domain Services pointer to the Central Management store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="d07d5-152">Si vous perdez le point de connexion de service à tout moment, vous pouvez réexécuter cette cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d07d5-152">If you lose the service connection point at any time, you can rerun this cmdlet.</span></span>


</div></td>
<td><p><span data-ttu-id="d07d5-153">Set-CsConfigurationStoreLocation</span><span class="sxs-lookup"><span data-stu-id="d07d5-153">Set-CsConfigurationStoreLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d07d5-154">Importer les paramètres de topologie, de stratégie et de configuration dans le magasin de gestion central (XDS. mdf)</span><span class="sxs-lookup"><span data-stu-id="d07d5-154">Import the topology, policies, and configuration settings to the Central Management store (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="d07d5-155">Importation-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="d07d5-155">Import-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d07d5-156">Publier et activer la topologie</span><span class="sxs-lookup"><span data-stu-id="d07d5-156">Publish and enable the topology</span></span></p></td>
<td><p><span data-ttu-id="d07d5-157">Générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="d07d5-157">Topology Builder</span></span></p>
<p><span data-ttu-id="d07d5-158">ou</span><span class="sxs-lookup"><span data-stu-id="d07d5-158">-or-</span></span></p>
<p><span data-ttu-id="d07d5-159">Publisher-CsTopology et Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="d07d5-159">Publish-CsTopology and Enable-CsTopology</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d07d5-160">Activer la dernière topologie publiée</span><span class="sxs-lookup"><span data-stu-id="d07d5-160">Enable the last published topology</span></span></p></td>
<td><p><span data-ttu-id="d07d5-161">Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="d07d5-161">Enable-CsTopology</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d07d5-162">Réinstaller les composants du serveur Lync</span><span class="sxs-lookup"><span data-stu-id="d07d5-162">Reinstall Lync Server components</span></span></p></td>
<td><p><span data-ttu-id="d07d5-163">Configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="d07d5-163">Lync Server Setup</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="d07d5-164">Trouve dans le dossier d’installation ou le média de Lync Server sur \setup\amd64\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="d07d5-164">Located in the Lync Server installation folder or media at \setup\amd64\Setup.exe.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d07d5-165">Restaurer des informations d’emplacement (E9-1-1) (LIS. mdf)</span><span class="sxs-lookup"><span data-stu-id="d07d5-165">Restore location information (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="d07d5-166">Import-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="d07d5-166">Import-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d07d5-167">Restaurer des données utilisateur persistantes (Rtcxds. mdf)</span><span class="sxs-lookup"><span data-stu-id="d07d5-167">Restore persistent user data (Rtcxds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="d07d5-168">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="d07d5-168">Import-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d07d5-169">Restauration des données de configuration de Response Group (RgsConfig. mdf)</span><span class="sxs-lookup"><span data-stu-id="d07d5-169">Restore Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="d07d5-170">Import-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="d07d5-170">Import-CsRgsConfiguration</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="d07d5-171">Si la configuration est restaurée dans un nouveau pool déployé qui ne possède pas de données de groupe de réponse dans la base de données, vous devez utiliser l’option – OverwriteOwner.</span><span class="sxs-lookup"><span data-stu-id="d07d5-171">If the configuration is being restored in a newly deployed pool that has no Response Group data in the database, then you should use the –OverwriteOwner option.</span></span> <span data-ttu-id="d07d5-172">Utilisez cette option même si les données en cours de restauration se trouvent dans un pool portant le même nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="d07d5-172">Use this option even if the data being restored is in a pool with the same fully qualified domain name (FQDN).</span></span> <span data-ttu-id="d07d5-173">Dans le cas contraire, l’importation échoue en raison des objets de contact dans les groupes de réponse déjà présents dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d07d5-173">Otherwise, the import will not succeed, due to the contact objects to the Response Groups already existing in Active Directory.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d07d5-174">Restaurez les bases de données suivantes :</span><span class="sxs-lookup"><span data-stu-id="d07d5-174">Restore the following databases:</span></span></p>
<ul>
<li><p><span data-ttu-id="d07d5-175">Archivage de la base de données (LcsLog. mdf)</span><span class="sxs-lookup"><span data-stu-id="d07d5-175">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="d07d5-176">Surveiller des bases de données : base de données d’enregistrement des détails des appels (LcsCDR. mdf) et base de données QoE (QoEMetrics. mdf)</span><span class="sxs-lookup"><span data-stu-id="d07d5-176">Monitoring databases: call detail record database (LcsCDR.mdf) and QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d07d5-177">Outils de gestion de base de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="d07d5-177">SQL Server database management tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d07d5-178">Base de données de discussions permanentes (MGS. mdf)</span><span class="sxs-lookup"><span data-stu-id="d07d5-178">Persistent Chat database (Mgs.mdf)</span></span></p></td>
<td><p><span data-ttu-id="d07d5-179">Procédures de restauration SQL Server ou Import-CsPersistentChatData.</span><span class="sxs-lookup"><span data-stu-id="d07d5-179">SQL Server restore procedures or Import-CsPersistentChatData.</span></span> <span data-ttu-id="d07d5-180">Vous pouvez utiliser import-CsPersistentChatData avec un fichier créé par Export-CsPersistentChatData, et les données sont importées dans la base de données de chat persistant.</span><span class="sxs-lookup"><span data-stu-id="d07d5-180">You can use Import-CsPersistentChatData with a file created by Export-CsPersistentChatData, and the data will be imported into the Persistent Chat database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a><span data-ttu-id="d07d5-181">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="d07d5-181">Required Permissions</span></span>

<span data-ttu-id="d07d5-182">Les utilisateurs doivent être membres du groupe **RTCUniversalServerAdmins** pour effectuer toutes les commandes décrites dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="d07d5-182">Users must be a member of the **RTCUniversalServerAdmins** group to perform all the commands described in this topic.</span></span> <span data-ttu-id="d07d5-183">La plupart des commandes de sauvegarde et de restauration ne prennent pas en charge le contrôle d’accès basé sur les rôles (RBAC).</span><span class="sxs-lookup"><span data-stu-id="d07d5-183">Most backup and restore commands do not support role-based access control (RBAC).</span></span> <span data-ttu-id="d07d5-184">Les applets de contrôle de chat permanent Export-CsPersistentChatData et Import-CsPersistentChatData doivent être exécutés par un utilisateur membre du groupe CsPersistentChatAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d07d5-184">Two exceptions are the Persistent Chat cmdlets Export-CsPersistentChatData and Import-CsPersistentChatData, which must be run by a user who is a member of the CsPersistentChatAdministrator group.</span></span> <span data-ttu-id="d07d5-185">Pour exécuter l’Assistant Déploiement de Lync Server, un utilisateur doit également être membre du groupe administrateurs locaux.</span><span class="sxs-lookup"><span data-stu-id="d07d5-185">To run Lync Server Deployment Wizard, a user must also be a member of the Local Adminstrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

