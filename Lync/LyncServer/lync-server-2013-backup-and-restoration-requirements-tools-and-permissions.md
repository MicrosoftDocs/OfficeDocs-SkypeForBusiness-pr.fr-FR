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
ms.openlocfilehash: 96eee88d6055d7a66d858dc5c6324a2592616ceb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532641"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a><span data-ttu-id="70c0c-102">Configuration requise pour la sauvegarde et la restauration dans Lync Server 2013 : outils et autorisations</span><span class="sxs-lookup"><span data-stu-id="70c0c-102">Backup and restoration requirements in Lync Server 2013: tools and permissions</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70c0c-103">_**Dernière modification de la rubrique :** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="70c0c-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="70c0c-104">Cette rubrique identifie les outils que vous pouvez utiliser pour sauvegarder et restaurer Lync Server 2013, les autorisations dont vous avez besoin et si vous pouvez exécuter des commandes à distance ou localement.</span><span class="sxs-lookup"><span data-stu-id="70c0c-104">This topic identifies the tools that you can use to back up and restore Lync Server 2013, the permissions that you need, and whether you can run commands remotely or locally.</span></span> <span data-ttu-id="70c0c-105">Plus précisément, cette rubrique se concentre sur les outils fournis avec Lync Server pour la sauvegarde et la restauration.</span><span class="sxs-lookup"><span data-stu-id="70c0c-105">Specifically, this topic focuses on tools that are provided with Lync Server for backup and restoration.</span></span>

<div>

## <a name="backups"></a><span data-ttu-id="70c0c-106">Sauvegardes</span><span class="sxs-lookup"><span data-stu-id="70c0c-106">Backups</span></span>

<span data-ttu-id="70c0c-107">Pour sauvegarder Lync Server, utilisez les outils identifiés dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="70c0c-107">To back up Lync Server, use the tools identified in the following table.</span></span> <span data-ttu-id="70c0c-108">Toutes les commandes dont vous avez besoin pour sauvegarder Lync Server peuvent être scriptées et exécutées à distance.</span><span class="sxs-lookup"><span data-stu-id="70c0c-108">All the commands that you need to back up Lync Server can be scripted and can be run remotely.</span></span>

### <a name="tools-for-backing-up-lync-server"></a><span data-ttu-id="70c0c-109">Outils de sauvegarde de Lync Server</span><span class="sxs-lookup"><span data-stu-id="70c0c-109">Tools for Backing Up Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70c0c-110">Pour sauvegarder ces éléments, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="70c0c-110">To back up this:</span></span></th>
<th><span data-ttu-id="70c0c-111">Utilisez cet outil ou cette applet de commande :</span><span class="sxs-lookup"><span data-stu-id="70c0c-111">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70c0c-112">Données de configuration de topologie (XDS. mdf)</span><span class="sxs-lookup"><span data-stu-id="70c0c-112">Topology configuration data (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="70c0c-113">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="70c0c-113">Export-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70c0c-114">Données de service d’informations d’emplacement (E9-1-1) (LIS. mdf)</span><span class="sxs-lookup"><span data-stu-id="70c0c-114">Location information service (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="70c0c-115">Export-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="70c0c-115">Export-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70c0c-116">Données de configuration de Response Group (RgsConfig. mdf)</span><span class="sxs-lookup"><span data-stu-id="70c0c-116">Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="70c0c-117">Export-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="70c0c-117">Export-CsRgsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70c0c-118">Données utilisateur persistantes (base de données Rtcxds. mdf)</span><span class="sxs-lookup"><span data-stu-id="70c0c-118">Persistent user data (Rtcxds.mdf database)</span></span></p>
<p><span data-ttu-id="70c0c-119">ID de conférence</span><span class="sxs-lookup"><span data-stu-id="70c0c-119">Conference IDs</span></span></p></td>
<td><p><span data-ttu-id="70c0c-120">Export-CsUserData</span><span class="sxs-lookup"><span data-stu-id="70c0c-120">Export-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="70c0c-121">Base de données d’archivage (LcsLog. mdf)</span><span class="sxs-lookup"><span data-stu-id="70c0c-121">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="70c0c-122">Base de données d’enregistrement des détails des appels de surveillance (LcsCDR. mdf)</span><span class="sxs-lookup"><span data-stu-id="70c0c-122">Monitoring call detail record database (LcsCDR.mdf)</span></span></p></li>
<li><p><span data-ttu-id="70c0c-123">Surveillance de la base de données QoE (QoEMetrics. mdf)</span><span class="sxs-lookup"><span data-stu-id="70c0c-123">Monitoring QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="70c0c-124">Outil de base de données SQL Server, tel que SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="70c0c-124">SQL Server database tool, such as SQL Server Management Studio</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70c0c-125">Base de données de conversation permanente (MGC. mdf)</span><span class="sxs-lookup"><span data-stu-id="70c0c-125">Persistent Chat database (Mgc.mdf)</span></span></p></td>
<td><p><span data-ttu-id="70c0c-126">Procédures de sauvegarde SQL Server ou Export-applet cspersistentchatdata.</span><span class="sxs-lookup"><span data-stu-id="70c0c-126">SQL Server backup procedures or Export-CsPersistentChatData.</span></span> <span data-ttu-id="70c0c-127">Export-CsPersistentChatData exporte les données de conversation permanente sous forme de fichier.</span><span class="sxs-lookup"><span data-stu-id="70c0c-127">Export-CsPersistentChatData exports Persistent Chat data as a file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70c0c-128">Tous les magasins de fichiers : magasin de fichiers Lync Server, magasin de fichiers d’archivage</span><span class="sxs-lookup"><span data-stu-id="70c0c-128">All file stores: Lync Server file store, Archiving file store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="70c0c-129">Les fichiers nommés <STRONG>Meeting. active</STRONG> ne doivent pas être sauvegardés.</span><span class="sxs-lookup"><span data-stu-id="70c0c-129">Files named <STRONG>Meeting.Active</STRONG> should not be backed up.</span></span> <span data-ttu-id="70c0c-130">Ces fichiers sont en cours d’utilisation et verrouillés lors d’une réunion.</span><span class="sxs-lookup"><span data-stu-id="70c0c-130">These files are in use and locked while a meeting takes place.</span></span>


</div></td>
<td><p><span data-ttu-id="70c0c-131">Outil de gestion de système de fichiers standard, tel que Robocopy.</span><span class="sxs-lookup"><span data-stu-id="70c0c-131">Standard file system management tool, such as Robocopy.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a><span data-ttu-id="70c0c-132">Generation</span><span class="sxs-lookup"><span data-stu-id="70c0c-132">Restoration</span></span>

<span data-ttu-id="70c0c-133">Pour restaurer Lync Server, utilisez les outils dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="70c0c-133">To restore Lync Server, use the tools in the following table.</span></span> <span data-ttu-id="70c0c-134">Toutes les commandes dont vous avez besoin pour restaurer Lync Server peuvent être scriptées.</span><span class="sxs-lookup"><span data-stu-id="70c0c-134">All the commands that you need to restore Lync Server can be scripted.</span></span> <span data-ttu-id="70c0c-135">Certaines peuvent être exécutées à distance, mais d’autres doivent être exécutées localement, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="70c0c-135">Some can be run remotely, but others need to be run locally, as specified in the following table.</span></span>

### <a name="tools-for-restoring-lync-server"></a><span data-ttu-id="70c0c-136">Outils de restauration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="70c0c-136">Tools for Restoring Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70c0c-137">Pour ce faire :</span><span class="sxs-lookup"><span data-stu-id="70c0c-137">To do this:</span></span></th>
<th><span data-ttu-id="70c0c-138">Utilisez cet outil ou cette applet de commande :</span><span class="sxs-lookup"><span data-stu-id="70c0c-138">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70c0c-139">Créer un ordinateur nouveau ou propre</span><span class="sxs-lookup"><span data-stu-id="70c0c-139">Build a new or clean computer</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="70c0c-140">Logiciel d’installation du système d’exploitation Windows</span><span class="sxs-lookup"><span data-stu-id="70c0c-140">Windows operating system installation software</span></span></p></li>
<li><p><span data-ttu-id="70c0c-141">Logiciel d’installation de SQL Server</span><span class="sxs-lookup"><span data-stu-id="70c0c-141">SQL Server installation software</span></span></p></li>
<li><p><span data-ttu-id="70c0c-142">Composant logiciel enfichable Certificats de la console MMC (Microsoft Management Console), si vous restaurez des certificats avec une clé privée exportable</span><span class="sxs-lookup"><span data-stu-id="70c0c-142">Certificates Microsoft Management Console (MMC) snap-in, if restoring certificates with an exportable private key</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70c0c-143">Restaurer les données du magasin de fichiers</span><span class="sxs-lookup"><span data-stu-id="70c0c-143">Restore file store data</span></span></p></td>
<td><p><span data-ttu-id="70c0c-144">Outil de gestion de système de fichiers standard, tel que Robocopy</span><span class="sxs-lookup"><span data-stu-id="70c0c-144">Standard file system management tool, such as Robocopy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70c0c-145">Recréez les bases de données vides et définissez des autorisations pour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="70c0c-145">Recreate empty databases and set permissions for the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="70c0c-146">magasin central de gestion</span><span class="sxs-lookup"><span data-stu-id="70c0c-146">Central Management store</span></span></p></li>
<li><p><span data-ttu-id="70c0c-147">serveur principal</span><span class="sxs-lookup"><span data-stu-id="70c0c-147">Back End Server</span></span></p></li>
<li><p><span data-ttu-id="70c0c-148">Base de données de surveillance</span><span class="sxs-lookup"><span data-stu-id="70c0c-148">Monitoring database</span></span></p></li>
<li><p><span data-ttu-id="70c0c-149">Base de données d’archivage</span><span class="sxs-lookup"><span data-stu-id="70c0c-149">Archiving database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="70c0c-150">Install-CsDatabase</span><span class="sxs-lookup"><span data-stu-id="70c0c-150">Install-CsDatabase</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70c0c-151">Restaurer le pointeur des services de domaine Active Directory vers le magasin central de gestion</span><span class="sxs-lookup"><span data-stu-id="70c0c-151">Restore the Active Directory Domain Services pointer to the Central Management store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="70c0c-152">Si vous perdez le point de connexion de service à tout moment, vous pouvez réexécuter cette applet de commande.</span><span class="sxs-lookup"><span data-stu-id="70c0c-152">If you lose the service connection point at any time, you can rerun this cmdlet.</span></span>


</div></td>
<td><p><span data-ttu-id="70c0c-153">Set-CsConfigurationStoreLocation</span><span class="sxs-lookup"><span data-stu-id="70c0c-153">Set-CsConfigurationStoreLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70c0c-154">Importer la topologie, les stratégies et les paramètres de configuration dans le magasin central de gestion (XDS. mdf)</span><span class="sxs-lookup"><span data-stu-id="70c0c-154">Import the topology, policies, and configuration settings to the Central Management store (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="70c0c-155">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="70c0c-155">Import-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70c0c-156">Publier et activer la topologie</span><span class="sxs-lookup"><span data-stu-id="70c0c-156">Publish and enable the topology</span></span></p></td>
<td><p><span data-ttu-id="70c0c-157">Générateur de topologies</span><span class="sxs-lookup"><span data-stu-id="70c0c-157">Topology Builder</span></span></p>
<p><span data-ttu-id="70c0c-158">-ou-</span><span class="sxs-lookup"><span data-stu-id="70c0c-158">-or-</span></span></p>
<p><span data-ttu-id="70c0c-159">Publish-CsTopology et Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="70c0c-159">Publish-CsTopology and Enable-CsTopology</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70c0c-160">Activer la dernière topologie publiée</span><span class="sxs-lookup"><span data-stu-id="70c0c-160">Enable the last published topology</span></span></p></td>
<td><p><span data-ttu-id="70c0c-161">Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="70c0c-161">Enable-CsTopology</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70c0c-162">Réinstaller les composants Lync Server</span><span class="sxs-lookup"><span data-stu-id="70c0c-162">Reinstall Lync Server components</span></span></p></td>
<td><p><span data-ttu-id="70c0c-163">Programme d’installation de Lync Server</span><span class="sxs-lookup"><span data-stu-id="70c0c-163">Lync Server Setup</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="70c0c-164">Situé dans le dossier ou le support d’installation de Lync Server sur \setup\amd64\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="70c0c-164">Located in the Lync Server installation folder or media at \setup\amd64\Setup.exe.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70c0c-165">Restaurer les données d’informations d’emplacement (E9-1-1) (LIS. mdf)</span><span class="sxs-lookup"><span data-stu-id="70c0c-165">Restore location information (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="70c0c-166">Import-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="70c0c-166">Import-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70c0c-167">Restaurer les données utilisateur persistantes (Rtcxds. mdf)</span><span class="sxs-lookup"><span data-stu-id="70c0c-167">Restore persistent user data (Rtcxds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="70c0c-168">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="70c0c-168">Import-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70c0c-169">Restaurer les données de configuration du groupe Response Group (RgsConfig. mdf)</span><span class="sxs-lookup"><span data-stu-id="70c0c-169">Restore Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="70c0c-170">Import-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="70c0c-170">Import-CsRgsConfiguration</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="70c0c-171">Si la configuration est restaurée dans un pool nouvellement déployé sans données Response Group dans la base de données, vous devez utiliser l’option – OverwriteOwner.</span><span class="sxs-lookup"><span data-stu-id="70c0c-171">If the configuration is being restored in a newly deployed pool that has no Response Group data in the database, then you should use the –OverwriteOwner option.</span></span> <span data-ttu-id="70c0c-172">Utilisez cette option même si les données en cours de restauration se trouvent dans un pool avec le même nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="70c0c-172">Use this option even if the data being restored is in a pool with the same fully qualified domain name (FQDN).</span></span> <span data-ttu-id="70c0c-173">Dans le cas contraire, l’importation échouera, car les objets contact sont déjà présents dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="70c0c-173">Otherwise, the import will not succeed, due to the contact objects to the Response Groups already existing in Active Directory.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70c0c-174">Restaurez les bases de données suivantes :</span><span class="sxs-lookup"><span data-stu-id="70c0c-174">Restore the following databases:</span></span></p>
<ul>
<li><p><span data-ttu-id="70c0c-175">Base de données d’archivage (LcsLog. mdf)</span><span class="sxs-lookup"><span data-stu-id="70c0c-175">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="70c0c-176">Bases de données de surveillance : base de données d’enregistrements des détails des appels (LcsCDR. mdf) et base de données QoE (QoEMetrics. mdf)</span><span class="sxs-lookup"><span data-stu-id="70c0c-176">Monitoring databases: call detail record database (LcsCDR.mdf) and QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="70c0c-177">Outils de gestion de base de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="70c0c-177">SQL Server database management tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70c0c-178">Base de données de conversation permanente (MGS. mdf)</span><span class="sxs-lookup"><span data-stu-id="70c0c-178">Persistent Chat database (Mgs.mdf)</span></span></p></td>
<td><p><span data-ttu-id="70c0c-179">Procédures de restauration SQL Server ou Import-applet cspersistentchatdata.</span><span class="sxs-lookup"><span data-stu-id="70c0c-179">SQL Server restore procedures or Import-CsPersistentChatData.</span></span> <span data-ttu-id="70c0c-180">Vous pouvez utiliser Import-CsPersistentChatData avec un fichier créé par Export-applet cspersistentchatdata, et les données seront importées dans la base de données de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="70c0c-180">You can use Import-CsPersistentChatData with a file created by Export-CsPersistentChatData, and the data will be imported into the Persistent Chat database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a><span data-ttu-id="70c0c-181">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="70c0c-181">Required Permissions</span></span>

<span data-ttu-id="70c0c-182">Les utilisateurs doivent être membres du groupe **RTCUniversalServerAdmins** pour effectuer toutes les commandes décrites dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="70c0c-182">Users must be a member of the **RTCUniversalServerAdmins** group to perform all the commands described in this topic.</span></span> <span data-ttu-id="70c0c-183">La plupart des commandes de sauvegarde et de restauration ne prennent pas en charge le contrôle d’accès basé sur un rôle (RBAC).</span><span class="sxs-lookup"><span data-stu-id="70c0c-183">Most backup and restore commands do not support role-based access control (RBAC).</span></span> <span data-ttu-id="70c0c-184">Il existe deux exceptions : les cmdlets de conversation permanente Export-CsPersistentChatData et Import-applet cspersistentchatdata, qui doivent être exécutées par un utilisateur membre du groupe CsPersistentChatAdministrator.</span><span class="sxs-lookup"><span data-stu-id="70c0c-184">Two exceptions are the Persistent Chat cmdlets Export-CsPersistentChatData and Import-CsPersistentChatData, which must be run by a user who is a member of the CsPersistentChatAdministrator group.</span></span> <span data-ttu-id="70c0c-185">Pour exécuter l’Assistant Déploiement Lync Server, un utilisateur doit également être membre du groupe Administrateurs local.</span><span class="sxs-lookup"><span data-stu-id="70c0c-185">To run Lync Server Deployment Wizard, a user must also be a member of the Local Adminstrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

