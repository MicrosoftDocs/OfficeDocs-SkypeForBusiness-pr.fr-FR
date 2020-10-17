---
title: 'Lync Server 2013 : conditions requises en matière de sauvegarde et de restauration : outils et autorisations'
description: 'Lync Server 2013 : conditions requises en matière de sauvegarde et de restauration : outils et autorisations.'
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
ms.openlocfilehash: 36327d1214854586b44024f126bbd87acad6c4b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553465"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a><span data-ttu-id="fc4ac-103">Configuration requise pour la sauvegarde et la restauration dans Lync Server 2013 : outils et autorisations</span><span class="sxs-lookup"><span data-stu-id="fc4ac-103">Backup and restoration requirements in Lync Server 2013: tools and permissions</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc4ac-104">_**Dernière modification de la rubrique :** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="fc4ac-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="fc4ac-105">Cette rubrique identifie les outils que vous pouvez utiliser pour sauvegarder et restaurer Lync Server 2013, les autorisations dont vous avez besoin et si vous pouvez exécuter des commandes à distance ou localement.</span><span class="sxs-lookup"><span data-stu-id="fc4ac-105">This topic identifies the tools that you can use to back up and restore Lync Server 2013, the permissions that you need, and whether you can run commands remotely or locally.</span></span> <span data-ttu-id="fc4ac-106">Plus précisément, cette rubrique se concentre sur les outils fournis avec Lync Server pour la sauvegarde et la restauration.</span><span class="sxs-lookup"><span data-stu-id="fc4ac-106">Specifically, this topic focuses on tools that are provided with Lync Server for backup and restoration.</span></span>

<div>

## <a name="backups"></a><span data-ttu-id="fc4ac-107">Sauvegardes</span><span class="sxs-lookup"><span data-stu-id="fc4ac-107">Backups</span></span>

<span data-ttu-id="fc4ac-108">Pour sauvegarder Lync Server, utilisez les outils identifiés dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="fc4ac-108">To back up Lync Server, use the tools identified in the following table.</span></span> <span data-ttu-id="fc4ac-109">Toutes les commandes dont vous avez besoin pour sauvegarder Lync Server peuvent être scriptées et exécutées à distance.</span><span class="sxs-lookup"><span data-stu-id="fc4ac-109">All the commands that you need to back up Lync Server can be scripted and can be run remotely.</span></span>

### <a name="tools-for-backing-up-lync-server"></a><span data-ttu-id="fc4ac-110">Outils de sauvegarde de Lync Server</span><span class="sxs-lookup"><span data-stu-id="fc4ac-110">Tools for Backing Up Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fc4ac-111">Pour sauvegarder ces éléments, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="fc4ac-111">To back up this:</span></span></th>
<th><span data-ttu-id="fc4ac-112">Utilisez cet outil ou cette applet de commande :</span><span class="sxs-lookup"><span data-stu-id="fc4ac-112">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc4ac-113">Données de configuration de topologie (XDS. mdf)</span><span class="sxs-lookup"><span data-stu-id="fc4ac-113">Topology configuration data (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fc4ac-114">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="fc4ac-114">Export-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc4ac-115">Données de service d’informations d’emplacement (E9-1-1) (LIS. mdf)</span><span class="sxs-lookup"><span data-stu-id="fc4ac-115">Location information service (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fc4ac-116">Export-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="fc4ac-116">Export-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc4ac-117">Données de configuration de Response Group (RgsConfig. mdf)</span><span class="sxs-lookup"><span data-stu-id="fc4ac-117">Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fc4ac-118">Export-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="fc4ac-118">Export-CsRgsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc4ac-119">Données utilisateur persistantes (base de données Rtcxds. mdf)</span><span class="sxs-lookup"><span data-stu-id="fc4ac-119">Persistent user data (Rtcxds.mdf database)</span></span></p>
<p><span data-ttu-id="fc4ac-120">ID de conférence</span><span class="sxs-lookup"><span data-stu-id="fc4ac-120">Conference IDs</span></span></p></td>
<td><p><span data-ttu-id="fc4ac-121">Export-CsUserData</span><span class="sxs-lookup"><span data-stu-id="fc4ac-121">Export-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="fc4ac-122">Base de données d’archivage (LcsLog. mdf)</span><span class="sxs-lookup"><span data-stu-id="fc4ac-122">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="fc4ac-123">Base de données d’enregistrement des détails des appels de surveillance (LcsCDR. mdf)</span><span class="sxs-lookup"><span data-stu-id="fc4ac-123">Monitoring call detail record database (LcsCDR.mdf)</span></span></p></li>
<li><p><span data-ttu-id="fc4ac-124">Surveillance de la base de données QoE (QoEMetrics. mdf)</span><span class="sxs-lookup"><span data-stu-id="fc4ac-124">Monitoring QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="fc4ac-125">Outil de base de données SQL Server, tel que SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fc4ac-125">SQL Server database tool, such as SQL Server Management Studio</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc4ac-126">Base de données de conversation permanente (MGC. mdf)</span><span class="sxs-lookup"><span data-stu-id="fc4ac-126">Persistent Chat database (Mgc.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fc4ac-127">Procédures de sauvegarde SQL Server ou Export-applet cspersistentchatdata.</span><span class="sxs-lookup"><span data-stu-id="fc4ac-127">SQL Server backup procedures or Export-CsPersistentChatData.</span></span> <span data-ttu-id="fc4ac-128">Export-CsPersistentChatData exporte les données de conversation permanente sous forme de fichier.</span><span class="sxs-lookup"><span data-stu-id="fc4ac-128">Export-CsPersistentChatData exports Persistent Chat data as a file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc4ac-129">Tous les magasins de fichiers : magasin de fichiers Lync Server, magasin de fichiers d’archivage</span><span class="sxs-lookup"><span data-stu-id="fc4ac-129">All file stores: Lync Server file store, Archiving file store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="fc4ac-130">Les fichiers nommés <STRONG>Meeting. active</STRONG> ne doivent pas être sauvegardés.</span><span class="sxs-lookup"><span data-stu-id="fc4ac-130">Files named <STRONG>Meeting.Active</STRONG> should not be backed up.</span></span> <span data-ttu-id="fc4ac-131">Ces fichiers sont en cours d’utilisation et verrouillés lors d’une réunion.</span><span class="sxs-lookup"><span data-stu-id="fc4ac-131">These files are in use and locked while a meeting takes place.</span></span>


</div></td>
<td><p><span data-ttu-id="fc4ac-132">Outil de gestion de système de fichiers standard, tel que Robocopy.</span><span class="sxs-lookup"><span data-stu-id="fc4ac-132">Standard file system management tool, such as Robocopy.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a><span data-ttu-id="fc4ac-133">Generation</span><span class="sxs-lookup"><span data-stu-id="fc4ac-133">Restoration</span></span>

<span data-ttu-id="fc4ac-134">Pour restaurer Lync Server, utilisez les outils dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="fc4ac-134">To restore Lync Server, use the tools in the following table.</span></span> <span data-ttu-id="fc4ac-135">Toutes les commandes dont vous avez besoin pour restaurer Lync Server peuvent être scriptées.</span><span class="sxs-lookup"><span data-stu-id="fc4ac-135">All the commands that you need to restore Lync Server can be scripted.</span></span> <span data-ttu-id="fc4ac-136">Certaines peuvent être exécutées à distance, mais d’autres doivent être exécutées localement, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="fc4ac-136">Some can be run remotely, but others need to be run locally, as specified in the following table.</span></span>

### <a name="tools-for-restoring-lync-server"></a><span data-ttu-id="fc4ac-137">Outils de restauration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="fc4ac-137">Tools for Restoring Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fc4ac-138">Pour ce faire :</span><span class="sxs-lookup"><span data-stu-id="fc4ac-138">To do this:</span></span></th>
<th><span data-ttu-id="fc4ac-139">Utilisez cet outil ou cette applet de commande :</span><span class="sxs-lookup"><span data-stu-id="fc4ac-139">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc4ac-140">Créer un ordinateur nouveau ou propre</span><span class="sxs-lookup"><span data-stu-id="fc4ac-140">Build a new or clean computer</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="fc4ac-141">Logiciel d’installation du système d’exploitation Windows</span><span class="sxs-lookup"><span data-stu-id="fc4ac-141">Windows operating system installation software</span></span></p></li>
<li><p><span data-ttu-id="fc4ac-142">Logiciel d’installation de SQL Server</span><span class="sxs-lookup"><span data-stu-id="fc4ac-142">SQL Server installation software</span></span></p></li>
<li><p><span data-ttu-id="fc4ac-143">Composant logiciel enfichable Certificats de la console MMC (Microsoft Management Console), si vous restaurez des certificats avec une clé privée exportable</span><span class="sxs-lookup"><span data-stu-id="fc4ac-143">Certificates Microsoft Management Console (MMC) snap-in, if restoring certificates with an exportable private key</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc4ac-144">Restaurer les données du magasin de fichiers</span><span class="sxs-lookup"><span data-stu-id="fc4ac-144">Restore file store data</span></span></p></td>
<td><p><span data-ttu-id="fc4ac-145">Outil de gestion de système de fichiers standard, tel que Robocopy</span><span class="sxs-lookup"><span data-stu-id="fc4ac-145">Standard file system management tool, such as Robocopy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc4ac-146">Recréez les bases de données vides et définissez des autorisations pour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="fc4ac-146">Recreate empty databases and set permissions for the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fc4ac-147">magasin central de gestion</span><span class="sxs-lookup"><span data-stu-id="fc4ac-147">Central Management store</span></span></p></li>
<li><p><span data-ttu-id="fc4ac-148">serveur principal</span><span class="sxs-lookup"><span data-stu-id="fc4ac-148">Back End Server</span></span></p></li>
<li><p><span data-ttu-id="fc4ac-149">Base de données de surveillance</span><span class="sxs-lookup"><span data-stu-id="fc4ac-149">Monitoring database</span></span></p></li>
<li><p><span data-ttu-id="fc4ac-150">Base de données d’archivage</span><span class="sxs-lookup"><span data-stu-id="fc4ac-150">Archiving database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="fc4ac-151">Install-CsDatabase</span><span class="sxs-lookup"><span data-stu-id="fc4ac-151">Install-CsDatabase</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc4ac-152">Restaurer le pointeur des services de domaine Active Directory vers le magasin central de gestion</span><span class="sxs-lookup"><span data-stu-id="fc4ac-152">Restore the Active Directory Domain Services pointer to the Central Management store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="fc4ac-153">Si vous perdez le point de connexion de service à tout moment, vous pouvez réexécuter cette applet de commande.</span><span class="sxs-lookup"><span data-stu-id="fc4ac-153">If you lose the service connection point at any time, you can rerun this cmdlet.</span></span>


</div></td>
<td><p><span data-ttu-id="fc4ac-154">Set-CsConfigurationStoreLocation</span><span class="sxs-lookup"><span data-stu-id="fc4ac-154">Set-CsConfigurationStoreLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc4ac-155">Importer la topologie, les stratégies et les paramètres de configuration dans le magasin central de gestion (XDS. mdf)</span><span class="sxs-lookup"><span data-stu-id="fc4ac-155">Import the topology, policies, and configuration settings to the Central Management store (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fc4ac-156">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="fc4ac-156">Import-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc4ac-157">Publier et activer la topologie</span><span class="sxs-lookup"><span data-stu-id="fc4ac-157">Publish and enable the topology</span></span></p></td>
<td><p><span data-ttu-id="fc4ac-158">Générateur de topologies</span><span class="sxs-lookup"><span data-stu-id="fc4ac-158">Topology Builder</span></span></p>
<p><span data-ttu-id="fc4ac-159">-ou-</span><span class="sxs-lookup"><span data-stu-id="fc4ac-159">-or-</span></span></p>
<p><span data-ttu-id="fc4ac-160">Publish-CsTopology et Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="fc4ac-160">Publish-CsTopology and Enable-CsTopology</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc4ac-161">Activer la dernière topologie publiée</span><span class="sxs-lookup"><span data-stu-id="fc4ac-161">Enable the last published topology</span></span></p></td>
<td><p><span data-ttu-id="fc4ac-162">Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="fc4ac-162">Enable-CsTopology</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc4ac-163">Réinstaller les composants Lync Server</span><span class="sxs-lookup"><span data-stu-id="fc4ac-163">Reinstall Lync Server components</span></span></p></td>
<td><p><span data-ttu-id="fc4ac-164">Programme d’installation de Lync Server</span><span class="sxs-lookup"><span data-stu-id="fc4ac-164">Lync Server Setup</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="fc4ac-165">Situé dans le dossier ou le support d’installation de Lync Server sur \setup\amd64\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="fc4ac-165">Located in the Lync Server installation folder or media at \setup\amd64\Setup.exe.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc4ac-166">Restaurer les données d’informations d’emplacement (E9-1-1) (LIS. mdf)</span><span class="sxs-lookup"><span data-stu-id="fc4ac-166">Restore location information (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fc4ac-167">Import-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="fc4ac-167">Import-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc4ac-168">Restaurer les données utilisateur persistantes (Rtcxds. mdf)</span><span class="sxs-lookup"><span data-stu-id="fc4ac-168">Restore persistent user data (Rtcxds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fc4ac-169">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="fc4ac-169">Import-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc4ac-170">Restaurer les données de configuration du groupe Response Group (RgsConfig. mdf)</span><span class="sxs-lookup"><span data-stu-id="fc4ac-170">Restore Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fc4ac-171">Import-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="fc4ac-171">Import-CsRgsConfiguration</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="fc4ac-172">Si la configuration est restaurée dans un pool nouvellement déployé sans données Response Group dans la base de données, vous devez utiliser l’option – OverwriteOwner.</span><span class="sxs-lookup"><span data-stu-id="fc4ac-172">If the configuration is being restored in a newly deployed pool that has no Response Group data in the database, then you should use the –OverwriteOwner option.</span></span> <span data-ttu-id="fc4ac-173">Utilisez cette option même si les données en cours de restauration se trouvent dans un pool avec le même nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="fc4ac-173">Use this option even if the data being restored is in a pool with the same fully qualified domain name (FQDN).</span></span> <span data-ttu-id="fc4ac-174">Dans le cas contraire, l’importation échouera, car les objets contact sont déjà présents dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fc4ac-174">Otherwise, the import will not succeed, due to the contact objects to the Response Groups already existing in Active Directory.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc4ac-175">Restaurez les bases de données suivantes :</span><span class="sxs-lookup"><span data-stu-id="fc4ac-175">Restore the following databases:</span></span></p>
<ul>
<li><p><span data-ttu-id="fc4ac-176">Base de données d’archivage (LcsLog. mdf)</span><span class="sxs-lookup"><span data-stu-id="fc4ac-176">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="fc4ac-177">Bases de données de surveillance : base de données d’enregistrements des détails des appels (LcsCDR. mdf) et base de données QoE (QoEMetrics. mdf)</span><span class="sxs-lookup"><span data-stu-id="fc4ac-177">Monitoring databases: call detail record database (LcsCDR.mdf) and QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="fc4ac-178">Outils de gestion de base de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="fc4ac-178">SQL Server database management tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc4ac-179">Base de données de conversation permanente (MGS. mdf)</span><span class="sxs-lookup"><span data-stu-id="fc4ac-179">Persistent Chat database (Mgs.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fc4ac-180">Procédures de restauration SQL Server ou Import-applet cspersistentchatdata.</span><span class="sxs-lookup"><span data-stu-id="fc4ac-180">SQL Server restore procedures or Import-CsPersistentChatData.</span></span> <span data-ttu-id="fc4ac-181">Vous pouvez utiliser Import-CsPersistentChatData avec un fichier créé par Export-applet cspersistentchatdata, et les données seront importées dans la base de données de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="fc4ac-181">You can use Import-CsPersistentChatData with a file created by Export-CsPersistentChatData, and the data will be imported into the Persistent Chat database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a><span data-ttu-id="fc4ac-182">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="fc4ac-182">Required Permissions</span></span>

<span data-ttu-id="fc4ac-183">Les utilisateurs doivent être membres du groupe **RTCUniversalServerAdmins** pour effectuer toutes les commandes décrites dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="fc4ac-183">Users must be a member of the **RTCUniversalServerAdmins** group to perform all the commands described in this topic.</span></span> <span data-ttu-id="fc4ac-184">La plupart des commandes de sauvegarde et de restauration ne prennent pas en charge le contrôle d’accès basé sur un rôle (RBAC).</span><span class="sxs-lookup"><span data-stu-id="fc4ac-184">Most backup and restore commands do not support role-based access control (RBAC).</span></span> <span data-ttu-id="fc4ac-185">Il existe deux exceptions : les cmdlets de conversation permanente Export-CsPersistentChatData et Import-applet cspersistentchatdata, qui doivent être exécutées par un utilisateur membre du groupe CsPersistentChatAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fc4ac-185">Two exceptions are the Persistent Chat cmdlets Export-CsPersistentChatData and Import-CsPersistentChatData, which must be run by a user who is a member of the CsPersistentChatAdministrator group.</span></span> <span data-ttu-id="fc4ac-186">Pour exécuter l’Assistant Déploiement Lync Server, un utilisateur doit également être membre du groupe Administrateurs local.</span><span class="sxs-lookup"><span data-stu-id="fc4ac-186">To run Lync Server Deployment Wizard, a user must also be a member of the Local Adminstrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

