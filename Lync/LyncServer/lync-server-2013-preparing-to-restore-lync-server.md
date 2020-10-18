---
title: 'Lync Server 2013 : préparation de la restauration de Lync Server'
description: 'Lync Server 2013 : préparation de la restauration de Lync Server.'
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
ms.openlocfilehash: 1875a691cfb70a6a824ab19bfde3dee4d699e48a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579950"
---
# <a name="preparing-to-restore-lync-server-2013"></a><span data-ttu-id="3478f-103">Préparation de la restauration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3478f-103">Preparing to restore Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3478f-104">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="3478f-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="3478f-105">Avant de commencer la restauration des serveurs et des bases de données après une défaillance, vous devez déterminer :</span><span class="sxs-lookup"><span data-stu-id="3478f-105">Before you begin restoring servers and databases after a failure, you need to determine the following:</span></span>

  - <span data-ttu-id="3478f-106">Ce qui doit être restauré.</span><span class="sxs-lookup"><span data-stu-id="3478f-106">What needs to be restored.</span></span>

  - <span data-ttu-id="3478f-107">Le matériel, les logiciels, les données et les outils dont vous avez besoin pour la restauration.</span><span class="sxs-lookup"><span data-stu-id="3478f-107">The hardware, software, data, and tools you need for restoration.</span></span>

<div>

## <a name="determining-what-to-restore"></a><span data-ttu-id="3478f-108">Détermination des éléments à restaurer</span><span class="sxs-lookup"><span data-stu-id="3478f-108">Determining What to Restore</span></span>

<span data-ttu-id="3478f-109">Cette rubrique décrit comment restaurer les pannes Lync Server qui se produisent au niveau du serveur, du pool ou du magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="3478f-109">This topic describes how to restore Lync Server outages that occur at the server, pool, or Central Management store level.</span></span> <span data-ttu-id="3478f-110">Si le magasin central de gestion échoue, votre déploiement de Lync Server continue de fonctionner, mais vous ne pouvez pas modifier la configuration.</span><span class="sxs-lookup"><span data-stu-id="3478f-110">If the Central Management store fails, your Lync Server deployment continues to function, but you cannot make any configuration changes.</span></span> <span data-ttu-id="3478f-111">En cas de défaillance d’un serveur principal ou d’un serveur Standard Edition, le pool d’utilisateurs cesse de fonctionner.</span><span class="sxs-lookup"><span data-stu-id="3478f-111">If a Back End Server or Standard Edition server fails, the user pool stops functioning.</span></span> <span data-ttu-id="3478f-112">En cas de défaillance d’un autre serveur, l’étendue de la défaillance dépend du rôle du serveur et du fait qu’il héberge ou non une ou plusieurs bases de données.</span><span class="sxs-lookup"><span data-stu-id="3478f-112">If any other server fails, the magnitude of the failure depends on the server role the server is running and whether the server hosts one or more databases.</span></span>

### <a name="what-to-restore"></a><span data-ttu-id="3478f-113">Éléments à restaurer</span><span class="sxs-lookup"><span data-stu-id="3478f-113">What to Restore</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3478f-114">En cas de défaillance de cet élément</span><span class="sxs-lookup"><span data-stu-id="3478f-114">If this failed</span></span></th>
<th><span data-ttu-id="3478f-115">Voir cette section :</span><span class="sxs-lookup"><span data-stu-id="3478f-115">See this section:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3478f-116">Serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="3478f-116">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="3478f-117"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restauration d’un serveur Standard Edition Server dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3478f-117"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3478f-118">magasin central de gestion</span><span class="sxs-lookup"><span data-stu-id="3478f-118">Central Management store</span></span></p></td>
<td><p><span data-ttu-id="3478f-119"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restauration du serveur qui héberge le magasin central de gestion dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3478f-119"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restoring the server hosting the Central Management store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3478f-120">Serveur principal Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="3478f-120">Enterprise Edition Back End</span></span></p></td>
<td><p><span data-ttu-id="3478f-121"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restauration d’un serveur principal Enterprise Edition dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3478f-121"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3478f-122">Serveur principal principal en miroir Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="3478f-122">Enterprise Edition Mirrored Back End Primary Server</span></span></p></td>
<td><p><span data-ttu-id="3478f-123"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restauration d’un serveur principal Enterprise Edition en miroir dans Lync Server 2013-principal</a></span><span class="sxs-lookup"><span data-stu-id="3478f-123"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3478f-124">Serveur secondaire principal en miroir Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="3478f-124">Enterprise Edition Mirrored Back End Secondary Server</span></span></p></td>
<td><p><span data-ttu-id="3478f-125"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restauration d’un serveur principal Enterprise Edition en miroir dans Lync Server 2013-Mirror</a></span><span class="sxs-lookup"><span data-stu-id="3478f-125"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3478f-126">Tout serveur Enterprise Edition exécutant un rôle serveur, tel qu’un serveur frontal, un serveur Edge, un directeur, un serveur de médiation ou un serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="3478f-126">Any Enterprise Edition server running a server role, such as a Front End Server, Edge Server, Director, Mediation Server,.or Persistent Chat Server.</span></span></p></td>
<td><p><span data-ttu-id="3478f-127"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restauration d’un serveur membre Enterprise Edition dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3478f-127"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3478f-128">Un pool Lync Server entier</span><span class="sxs-lookup"><span data-stu-id="3478f-128">An entire Lync Server pool</span></span></p></td>
<td><p><span data-ttu-id="3478f-129"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restauration d’un pool Lync Server dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3478f-129"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restoring a Lync Server pool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3478f-130">Magasin de fichiers Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="3478f-130">Enterprise Edition File Store</span></span></p></td>
<td><p><span data-ttu-id="3478f-131"><a href="lync-server-2013-restoring-a-file-store.md">Restauration d’un magasin de fichiers dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3478f-131"><a href="lync-server-2013-restoring-a-file-store.md">Restoring a file store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3478f-132">Une base de données de surveillance autonome ou une base de données d’archivage</span><span class="sxs-lookup"><span data-stu-id="3478f-132">A standalone Monitoring database or Archiving database</span></span></p></td>
<td><p><span data-ttu-id="3478f-133"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restauration des données de surveillance ou d’archivage dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3478f-133"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restoring monitoring or archiving data in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3478f-134">Une base de données de conversation permanente autonome</span><span class="sxs-lookup"><span data-stu-id="3478f-134">A stand-alone Persistent Chat database</span></span></p></td>
<td><p><span data-ttu-id="3478f-135"><a href="lync-server-2013-restoring-persistent-chat-data.md">Restauration des données de conversation permanente dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3478f-135"><a href="lync-server-2013-restoring-persistent-chat-data.md">Restoring Persistent Chat data in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a><span data-ttu-id="3478f-136">Collecte du matériel, des logiciels et des outils</span><span class="sxs-lookup"><span data-stu-id="3478f-136">Gathering Hardware, Software, and Tools</span></span>

<span data-ttu-id="3478f-137">Lorsque vous restaurez un serveur, vous devez démarrer avec un ordinateur nouveau ou propre.</span><span class="sxs-lookup"><span data-stu-id="3478f-137">When you restore a server, you need to start with a new or clean computer.</span></span> <span data-ttu-id="3478f-138">De plus, vous devez disposer des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="3478f-138">Additionally, you must have the following hardware and software available:</span></span>

  - <span data-ttu-id="3478f-139">Un nouveau serveur ayant le même nom de domaine complet que le serveur ayant subi une défaillance.</span><span class="sxs-lookup"><span data-stu-id="3478f-139">A clean or new server with the same fully qualified domain name (FQDN) as the server that failed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3478f-140">Lorsque vous installez le système d’exploitation, veillez à ne pas supprimer le compte d’ordinateur dans les services de domaine Active Directory et à vérifier que les autorisations de groupe pour le compte sont conservées.</span><span class="sxs-lookup"><span data-stu-id="3478f-140">When you install the operating system, make sure that you do not delete the computer account in Active Directory Domain Services, and verify that the group permissions for the account are retained.</span></span>

    
    </div>

  - <span data-ttu-id="3478f-141">Logiciel d’installation pour le système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="3478f-141">Installation software for the operating system.</span></span> <span data-ttu-id="3478f-142">Pour installer le système d’exploitation, utilisez les configurations et procédures de déploiement de serveur établies par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3478f-142">To install the operating system, use the server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="3478f-143">Ces procédures et conditions de configuration doivent être disponibles lorsque vous restaurez le service.</span><span class="sxs-lookup"><span data-stu-id="3478f-143">You should have these procedures and configuration requirements available when you restore service.</span></span>

  - <span data-ttu-id="3478f-144">Logiciel d’installation pour SQL Server 2012 ou SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="3478f-144">Installation software for SQL Server 2012 or SQL Server 2008 R2.</span></span> <span data-ttu-id="3478f-145">Pour installer un serveur de bases de données, utilisez la version appropriée de SQL Server et les procédures et configurations de déploiement de serveur de bases de données établies par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3478f-145">To install a database server, use the appropriate version of SQL Server and the database server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="3478f-146">Ces procédures et conditions de configuration doivent être disponibles lorsque vous restaurez le service.</span><span class="sxs-lookup"><span data-stu-id="3478f-146">You should have these procedures and configuration requirements available when you restore service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3478f-147">L’Assistant Déploiement de Lync Server installe automatiquement SQL Server 2012 Express sur chaque serveur Standard Edition et sur tout autre serveur Lync Server lors de l’installation d’un magasin de configurations local, sauf si vous avez préinstallé SQL Server 2012 ou SQL Server 2008 R2 sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="3478f-147">The Lync Server Deployment Wizard automatically installs SQL Server 2012 Express on each Standard Edition server and on any other Lync Server server when a local configuration store is installed, unless you have preinstalled SQL Server 2012 or SQL Server 2008 R2 on the server.</span></span>

    
    </div>

  - <span data-ttu-id="3478f-148">Logiciels de prise d’images système</span><span class="sxs-lookup"><span data-stu-id="3478f-148">Software for taking system images.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="3478f-149">Nous vous recommandons de prendre une copie de l’image du système après avoir installé le système d’exploitation et SQL Server, et avant de commencer la restauration, afin que vous puissiez utiliser cette image comme point de restauration en cas de problème lors de la restauration.</span><span class="sxs-lookup"><span data-stu-id="3478f-149">We recommend that you take an image copy of the system after you install the operating system and SQL Server, and before you start restoration, so that you can use this image as a rollback point in case something goes wrong during restoration.</span></span>

    
    </div>

  - <span data-ttu-id="3478f-150">Logiciel d’installation Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3478f-150">Lync Server 2013 installation software.</span></span> <span data-ttu-id="3478f-151">L’Assistant Déploiement de Lync Server se trouve dans le dossier ou le support d’installation de Lync Server lors de l' \\ installation de \\ amd64 \\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="3478f-151">The Lync Server Deployment Wizard is located in the Lync Server installation folder or media at \\setup\\amd64\\Setup.exe.</span></span>

<span data-ttu-id="3478f-152">Durant la restauration, vous utilisez les outils suivants :</span><span class="sxs-lookup"><span data-stu-id="3478f-152">During restoration, you use the following tools:</span></span>

  - <span data-ttu-id="3478f-153">Applets de commande Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="3478f-153">Lync Server Management Shell cmdlets</span></span>

  - <span data-ttu-id="3478f-154">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="3478f-154">Import-CsUserData</span></span>

  - <span data-ttu-id="3478f-155">Outils de restauration des dossiers Windows</span><span class="sxs-lookup"><span data-stu-id="3478f-155">Tools for restoring Windows folders</span></span>

  - <span data-ttu-id="3478f-156">Générateur de topologies</span><span class="sxs-lookup"><span data-stu-id="3478f-156">Topology Builder</span></span>

  - <span data-ttu-id="3478f-157">Utilitaires de bases de données SQL Server, tels que SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3478f-157">SQL Server database utilities, such as SQL Server Management Studio</span></span>

</div>

<div>

## <a name="preparing-to-restore-a-server"></a><span data-ttu-id="3478f-158">Préparation à la restauration d’un serveur</span><span class="sxs-lookup"><span data-stu-id="3478f-158">Preparing to Restore a Server</span></span>

<span data-ttu-id="3478f-159">Avant de restaurer le serveur, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="3478f-159">Before you restore the server, you must perform the following steps:</span></span>

1.  <span data-ttu-id="3478f-160">Installez le système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="3478f-160">Install the operating system.</span></span>

2.  <span data-ttu-id="3478f-161">Si le serveur est un serveur principal, installez SQL Server 2012 ou SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="3478f-161">If the server is a Back End Server, install SQL Server 2012 or SQL Server 2008 R2.</span></span>

3.  <span data-ttu-id="3478f-162">Restaurez ou réinscrivez vos certificats.</span><span class="sxs-lookup"><span data-stu-id="3478f-162">Restore or reenroll your certificates.</span></span> <span data-ttu-id="3478f-163">Pour plus d’informations sur les certificats, voir « conditions de sauvegarde supplémentaires » dans Configuration de la [sauvegarde et de la restauration dans Lync Server 2013 : Data](lync-server-2013-backup-and-restoration-requirements-data.md).</span><span class="sxs-lookup"><span data-stu-id="3478f-163">For details about certificates, see "Additional Backup Requirements" in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

4.  <span data-ttu-id="3478f-164">Prenez une image du système avant de commencer la restauration afin de l’utiliser comme point de restauration, en cas de problème lors de la restauration.</span><span class="sxs-lookup"><span data-stu-id="3478f-164">Take an image of the system before starting restoration to use as a rollback point, in case something goes wrong during restoration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3478f-165">L’Assistant Déploiement Lync Server et les cmdlets décrits dans les procédures de cette rubrique, ainsi que les rubriques connexes, définissent toutes les listes de contrôle d’accès (ACL) requises.</span><span class="sxs-lookup"><span data-stu-id="3478f-165">The Lync Server Deployment Wizard and cmdlets described in the procedures in this topic, and related topics, set all required access control lists (ACLs).</span></span>



</div>

<span data-ttu-id="3478f-166">Vérifiez que le matériel et le logiciel dont vous avez besoin pour les composants que vous prévoyez de restaurer sont disponibles avant de commencer la restauration.</span><span class="sxs-lookup"><span data-stu-id="3478f-166">Verify that the hardware and the software that you need for the components that you plan to restore are available before you start restoration.</span></span> <span data-ttu-id="3478f-167">Une fois que vous avez installé le système d’exploitation et SQL Server, la plupart des étapes des procédures de restauration suivantes peuvent être effectuées à distance.</span><span class="sxs-lookup"><span data-stu-id="3478f-167">After you install the operating system and SQL Server, most of the steps in the following restoration procedures can be run remotely.</span></span> <span data-ttu-id="3478f-168">Les exceptions sont notées dans les procédures.</span><span class="sxs-lookup"><span data-stu-id="3478f-168">The exceptions are noted in the procedures.</span></span>

<span data-ttu-id="3478f-169">Vous devez également avoir le plan de sauvegarde et de restauration de votre organisation, ainsi que les informations de votre dernière sauvegarde, telles que les informations contenues dans les feuilles de calcul de ce document (pour plus de détails, voir [Backup and Restoring Worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), disponible avant de commencer la restauration.</span><span class="sxs-lookup"><span data-stu-id="3478f-169">You should also have your organization's backup and restoration plan and the information from your last backup, such as the information in the worksheets in this document (for details, see [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), available before you begin restoration.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

