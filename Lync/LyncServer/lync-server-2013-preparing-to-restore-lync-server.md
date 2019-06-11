---
title: 'Lync Server 2013: préparation de la restauration de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a470a338d05436be942201e6df6a864f955ac87c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-to-restore-lync-server-2013"></a><span data-ttu-id="b93ee-102">Préparation de la restauration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b93ee-102">Preparing to restore Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b93ee-103">_**Dernière modification de la rubrique:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="b93ee-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="b93ee-104">Avant de procéder à la restauration de serveurs et de bases de données après un échec, vous devez déterminer les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="b93ee-104">Before you begin restoring servers and databases after a failure, you need to determine the following:</span></span>

  - <span data-ttu-id="b93ee-105">Ce qui doit être restauré.</span><span class="sxs-lookup"><span data-stu-id="b93ee-105">What needs to be restored.</span></span>

  - <span data-ttu-id="b93ee-106">Le matériel, les logiciels, les données et les outils dont vous avez besoin pour la restauration.</span><span class="sxs-lookup"><span data-stu-id="b93ee-106">The hardware, software, data, and tools you need for restoration.</span></span>

<div>

## <a name="determining-what-to-restore"></a><span data-ttu-id="b93ee-107">Déterminer les données à restaurer</span><span class="sxs-lookup"><span data-stu-id="b93ee-107">Determining What to Restore</span></span>

<span data-ttu-id="b93ee-108">Cette rubrique décrit la restauration des pannes du serveur Lync qui se produisent au niveau du serveur, du pool ou du magasin de gestion central.</span><span class="sxs-lookup"><span data-stu-id="b93ee-108">This topic describes how to restore Lync Server outages that occur at the server, pool, or Central Management store level.</span></span> <span data-ttu-id="b93ee-109">En cas d’échec du magasin de gestion central, votre déploiement de Lync Server continue de fonctionner, mais vous ne pouvez pas apporter de modifications à la configuration.</span><span class="sxs-lookup"><span data-stu-id="b93ee-109">If the Central Management store fails, your Lync Server deployment continues to function, but you cannot make any configuration changes.</span></span> <span data-ttu-id="b93ee-110">En cas d’échec d’un serveur principal ou d’un serveur Standard Edition Server, le pool d’utilisateurs cesse de fonctionner.</span><span class="sxs-lookup"><span data-stu-id="b93ee-110">If a Back End Server or Standard Edition server fails, the user pool stops functioning.</span></span> <span data-ttu-id="b93ee-111">En cas d’échec d’un autre serveur, l’amplitude de l’échec dépend du rôle de serveur exécuté sur le serveur et de l’hébergement d’une ou plusieurs bases de données par le serveur.</span><span class="sxs-lookup"><span data-stu-id="b93ee-111">If any other server fails, the magnitude of the failure depends on the server role the server is running and whether the server hosts one or more databases.</span></span>

### <a name="what-to-restore"></a><span data-ttu-id="b93ee-112">Restauration</span><span class="sxs-lookup"><span data-stu-id="b93ee-112">What to Restore</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b93ee-113">Si ce n’est pas le cas</span><span class="sxs-lookup"><span data-stu-id="b93ee-113">If this failed</span></span></th>
<th><span data-ttu-id="b93ee-114">Consultez cette section:</span><span class="sxs-lookup"><span data-stu-id="b93ee-114">See this section:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b93ee-115">serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="b93ee-115">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="b93ee-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restauration d’un serveur Standard Edition Server dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b93ee-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b93ee-117">magasin central de gestion</span><span class="sxs-lookup"><span data-stu-id="b93ee-117">Central Management store</span></span></p></td>
<td><p><span data-ttu-id="b93ee-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restauration du serveur qui héberge le magasin de gestion central dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b93ee-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restoring the server hosting the Central Management store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b93ee-119">Version back-end de l’entreprise</span><span class="sxs-lookup"><span data-stu-id="b93ee-119">Enterprise Edition Back End</span></span></p></td>
<td><p><span data-ttu-id="b93ee-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restauration d’un serveur principal Enterprise Edition dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b93ee-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b93ee-121">Serveur principal principal en miroir d’Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="b93ee-121">Enterprise Edition Mirrored Back End Primary Server</span></span></p></td>
<td><p><span data-ttu-id="b93ee-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restauration d’un serveur principal Enterprise Edition en miroir sur Lync Server 2013-principal</a></span><span class="sxs-lookup"><span data-stu-id="b93ee-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b93ee-123">Serveur secondaire de l’édition Enterprise en miroir</span><span class="sxs-lookup"><span data-stu-id="b93ee-123">Enterprise Edition Mirrored Back End Secondary Server</span></span></p></td>
<td><p><span data-ttu-id="b93ee-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restauration d’un serveur principal Enterprise Edition en miroir sur Lync Server 2013-Mirror</a></span><span class="sxs-lookup"><span data-stu-id="b93ee-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b93ee-125">Tout serveur Enterprise Edition exécutant un rôle serveur, tel qu’un serveur frontal, un serveur Edge, un directeur, un serveur de médiation, ou un serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="b93ee-125">Any Enterprise Edition server running a server role, such as a Front End Server, Edge Server, Director, Mediation Server,.or Persistent Chat Server.</span></span></p></td>
<td><p><span data-ttu-id="b93ee-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restauration d’un serveur membre Enterprise Edition dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b93ee-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b93ee-127">Ensemble d’un pool de serveurs Lync</span><span class="sxs-lookup"><span data-stu-id="b93ee-127">An entire Lync Server pool</span></span></p></td>
<td><p><span data-ttu-id="b93ee-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restauration d’un pool de serveurs Lync dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b93ee-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restoring a Lync Server pool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b93ee-129">Magasin de fichiers Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="b93ee-129">Enterprise Edition File Store</span></span></p></td>
<td><p><span data-ttu-id="b93ee-130"><a href="lync-server-2013-restoring-a-file-store.md">Restauration d’un magasin de fichiers dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b93ee-130"><a href="lync-server-2013-restoring-a-file-store.md">Restoring a file store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b93ee-131">Une base de données de surveillance autonome ou une base de données d’archivage</span><span class="sxs-lookup"><span data-stu-id="b93ee-131">A standalone Monitoring database or Archiving database</span></span></p></td>
<td><p><span data-ttu-id="b93ee-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restauration de données d’analyse ou d’archivage dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b93ee-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restoring monitoring or archiving data in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b93ee-133">Une base de données de conversation permanente autonome</span><span class="sxs-lookup"><span data-stu-id="b93ee-133">A stand-alone Persistent Chat database</span></span></p></td>
<td><p><span data-ttu-id="b93ee-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">Restauration de données de conversations permanentes dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b93ee-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">Restoring Persistent Chat data in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a><span data-ttu-id="b93ee-135">Rassemblement de matériel, de logiciels et d’outils</span><span class="sxs-lookup"><span data-stu-id="b93ee-135">Gathering Hardware, Software, and Tools</span></span>

<span data-ttu-id="b93ee-136">Lorsque vous restaurez un serveur, vous devez commencer avec un nouvel ordinateur ou nettoyer.</span><span class="sxs-lookup"><span data-stu-id="b93ee-136">When you restore a server, you need to start with a new or clean computer.</span></span> <span data-ttu-id="b93ee-137">Par ailleurs, vous devez disposer des éléments matériels et logiciels suivants:</span><span class="sxs-lookup"><span data-stu-id="b93ee-137">Additionally, you must have the following hardware and software available:</span></span>

  - <span data-ttu-id="b93ee-138">Serveur propre ou nouveau avec le même nom de domaine complet (FQDN) que le serveur qui a échoué.</span><span class="sxs-lookup"><span data-stu-id="b93ee-138">A clean or new server with the same fully qualified domain name (FQDN) as the server that failed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b93ee-139">Lorsque vous installez le système d’exploitation, assurez-vous de ne pas supprimer le compte d’ordinateur dans les services de domaine Active Directory (AD FS) et vérifiez que les autorisations de groupe associées au compte sont conservées.</span><span class="sxs-lookup"><span data-stu-id="b93ee-139">When you install the operating system, make sure that you do not delete the computer account in Active Directory Domain Services, and verify that the group permissions for the account are retained.</span></span>

    
    </div>

  - <span data-ttu-id="b93ee-140">Programme d’installation du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="b93ee-140">Installation software for the operating system.</span></span> <span data-ttu-id="b93ee-141">Pour installer le système d’exploitation, utilisez les procédures et configurations de déploiement de serveur établies par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b93ee-141">To install the operating system, use the server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="b93ee-142">Pour restaurer le service, vous devez disposer de ces procédures et de vos exigences relatives à la configuration.</span><span class="sxs-lookup"><span data-stu-id="b93ee-142">You should have these procedures and configuration requirements available when you restore service.</span></span>

  - <span data-ttu-id="b93ee-143">Programme d’installation de SQL Server 2012 ou SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="b93ee-143">Installation software for SQL Server 2012 or SQL Server 2008 R2.</span></span> <span data-ttu-id="b93ee-144">Pour installer un serveur de base de données, utilisez la version appropriée de SQL Server, ainsi que les procédures et configurations de déploiement du serveur de base de données établies par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b93ee-144">To install a database server, use the appropriate version of SQL Server and the database server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="b93ee-145">Pour restaurer le service, vous devez disposer de ces procédures et de vos exigences relatives à la configuration.</span><span class="sxs-lookup"><span data-stu-id="b93ee-145">You should have these procedures and configuration requirements available when you restore service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b93ee-146">L’Assistant Déploiement de Lync Server installe automatiquement SQL Server 2012 Express sur chaque serveur Standard Edition et sur n’importe quel autre serveur Lync Server lors de l’installation d’un magasin de configuration local, sauf si vous avez préinstallé SQL Server 2012 ou SQL Server 2008 R2 sur serveur.</span><span class="sxs-lookup"><span data-stu-id="b93ee-146">The Lync Server Deployment Wizard automatically installs SQL Server 2012 Express on each Standard Edition server and on any other Lync Server server when a local configuration store is installed, unless you have preinstalled SQL Server 2012 or SQL Server 2008 R2 on the server.</span></span>

    
    </div>

  - <span data-ttu-id="b93ee-147">Logiciel pour la capture d’images système.</span><span class="sxs-lookup"><span data-stu-id="b93ee-147">Software for taking system images.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="b93ee-148">Nous vous conseillons de prendre une copie d’image du système après l’installation du système d’exploitation et de SQL Server, et avant de commencer la restauration, afin que vous puissiez utiliser cette image comme point de restauration en cas de problème de restauration.</span><span class="sxs-lookup"><span data-stu-id="b93ee-148">We recommend that you take an image copy of the system after you install the operating system and SQL Server, and before you start restoration, so that you can use this image as a rollback point in case something goes wrong during restoration.</span></span>

    
    </div>

  - <span data-ttu-id="b93ee-149">Programme d’installation de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b93ee-149">Lync Server 2013 installation software.</span></span> <span data-ttu-id="b93ee-150">L’Assistant Déploiement de Lync Server se trouve dans le dossier d’installation ou le média \\de\\Lync\\Server lors de l’installation de l’application. exe.</span><span class="sxs-lookup"><span data-stu-id="b93ee-150">The Lync Server Deployment Wizard is located in the Lync Server installation folder or media at \\setup\\amd64\\Setup.exe.</span></span>

<span data-ttu-id="b93ee-151">Lors de la restauration, vous devez utiliser les outils suivants:</span><span class="sxs-lookup"><span data-stu-id="b93ee-151">During restoration, you use the following tools:</span></span>

  - <span data-ttu-id="b93ee-152">Cmdlets Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="b93ee-152">Lync Server Management Shell cmdlets</span></span>

  - <span data-ttu-id="b93ee-153">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="b93ee-153">Import-CsUserData</span></span>

  - <span data-ttu-id="b93ee-154">Outils de restauration de dossiers Windows</span><span class="sxs-lookup"><span data-stu-id="b93ee-154">Tools for restoring Windows folders</span></span>

  - <span data-ttu-id="b93ee-155">Générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="b93ee-155">Topology Builder</span></span>

  - <span data-ttu-id="b93ee-156">Utilitaires de base de données SQL Server tels que SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b93ee-156">SQL Server database utilities, such as SQL Server Management Studio</span></span>

</div>

<div>

## <a name="preparing-to-restore-a-server"></a><span data-ttu-id="b93ee-157">Préparation de la restauration d’un serveur</span><span class="sxs-lookup"><span data-stu-id="b93ee-157">Preparing to Restore a Server</span></span>

<span data-ttu-id="b93ee-158">Avant de restaurer le serveur, vous devez effectuer les étapes suivantes:</span><span class="sxs-lookup"><span data-stu-id="b93ee-158">Before you restore the server, you must perform the following steps:</span></span>

1.  <span data-ttu-id="b93ee-159">Installez le système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="b93ee-159">Install the operating system.</span></span>

2.  <span data-ttu-id="b93ee-160">S’il s’agit d’un serveur principal, installez SQL Server 2012 ou SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="b93ee-160">If the server is a Back End Server, install SQL Server 2012 or SQL Server 2008 R2.</span></span>

3.  <span data-ttu-id="b93ee-161">Restaurez ou réinscrivez vos certificats.</span><span class="sxs-lookup"><span data-stu-id="b93ee-161">Restore or reenroll your certificates.</span></span> <span data-ttu-id="b93ee-162">Pour plus d’informations sur les certificats, voir «exigences de sauvegarde supplémentaires» dans [les exigences de sauvegarde et de restauration dans Lync Server 2013: données](lync-server-2013-backup-and-restoration-requirements-data.md).</span><span class="sxs-lookup"><span data-stu-id="b93ee-162">For details about certificates, see "Additional Backup Requirements" in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

4.  <span data-ttu-id="b93ee-163">Prenez une photo du système avant de commencer la restauration à utiliser comme point de restauration, en cas de problème de restauration.</span><span class="sxs-lookup"><span data-stu-id="b93ee-163">Take an image of the system before starting restoration to use as a rollback point, in case something goes wrong during restoration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b93ee-164">L’Assistant Déploiement de Lync Server et les applets de commande décrits dans les procédures décrites dans cette rubrique, ainsi que les rubriques connexes, définissent toutes les listes de contrôle d’accès (ACL) requises.</span><span class="sxs-lookup"><span data-stu-id="b93ee-164">The Lync Server Deployment Wizard and cmdlets described in the procedures in this topic, and related topics, set all required access control lists (ACLs).</span></span>



</div>

<span data-ttu-id="b93ee-165">Vérifiez que le matériel et le logiciel dont vous avez besoin pour les composants que vous envisagez de restaurer sont disponibles avant de commencer la restauration.</span><span class="sxs-lookup"><span data-stu-id="b93ee-165">Verify that the hardware and the software that you need for the components that you plan to restore are available before you start restoration.</span></span> <span data-ttu-id="b93ee-166">Après avoir installé le système d’exploitation et SQL Server, la plupart des étapes de la procédure de restauration suivantes peuvent être exécutées à distance.</span><span class="sxs-lookup"><span data-stu-id="b93ee-166">After you install the operating system and SQL Server, most of the steps in the following restoration procedures can be run remotely.</span></span> <span data-ttu-id="b93ee-167">Les exceptions sont indiquées dans les procédures.</span><span class="sxs-lookup"><span data-stu-id="b93ee-167">The exceptions are noted in the procedures.</span></span>

<span data-ttu-id="b93ee-168">Pour plus d’informations, reportez-vous au plan de sauvegarde et de restauration de votre organisation ainsi qu’aux informations de votre dernière sauvegarde, telles que les informations figurant dans les feuilles de calcul de ce document (pour plus d’informations, reportez-vous à la rubrique [sauvegarde et restauration de feuilles de calcul pour Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)). disponible avant de commencer la restauration.</span><span class="sxs-lookup"><span data-stu-id="b93ee-168">You should also have your organization's backup and restoration plan and the information from your last backup, such as the information in the worksheets in this document (for details, see [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), available before you begin restoration.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

