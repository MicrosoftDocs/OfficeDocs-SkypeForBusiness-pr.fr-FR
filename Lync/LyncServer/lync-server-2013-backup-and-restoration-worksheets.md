---
title: 'Lync Server 2013 : feuilles de calcul de sauvegarde et de restauration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration worksheets
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202169(v=OCS.15)
ms:contentKeyID: 51541460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 390d6289daf8075c873e90319642f0e74b61d835
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a><span data-ttu-id="c230d-102">Sauvegarder et restaurer des feuilles de calcul pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c230d-102">Backup and restoration worksheets for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c230d-103">_**Dernière modification de la rubrique :** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="c230d-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="c230d-104">Le plan de sauvegarde et de restauration de votre organisation doit contenir des détails sur la façon dont et quand vous sauvegardez des données et des paramètres.</span><span class="sxs-lookup"><span data-stu-id="c230d-104">The backup and restoration plan for your organization should contain details about how and when you back up data and settings.</span></span> <span data-ttu-id="c230d-105">Vous pouvez utiliser les feuilles de calcul présentées ici pour documenter ces informations pour votre déploiement spécifique et pour les besoins en matière de sauvegarde et de restauration de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c230d-105">You can use the worksheets presented here to help you document this information for your specific deployment and for your organization's backup and restoration requirements.</span></span>

<span data-ttu-id="c230d-106">Utilisez les feuilles de calcul suivantes pour enregistrer les informations dont vous avez besoin pour sauvegarder et restaurer des informations de base de données, de magasin de fichiers et de paramètres pour un pool de serveurs Lync ou un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="c230d-106">Use the following worksheets to record the information that you need to back up and restore database, File Store, and settings information for a Lync Server pool or Standard Edition server.</span></span> <span data-ttu-id="c230d-107">Conservation d’une ou plusieurs copies de ces feuilles de calcul dans un emplacement sécurisé de sorte qu’elles soient facilement accessibles si vous devez restaurer Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c230d-107">Keep one or more copies of these worksheets in a secure location so that they are readily accessible if you need to restore Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c230d-108">Les feuilles de calcul de cette section couvrent uniquement les informations nécessaires pour restaurer les données et les paramètres des bases de données et serveurs Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c230d-108">The worksheets in this section cover only the information that is required to restore the data and settings of Lync Server databases and servers.</span></span> <span data-ttu-id="c230d-109">Si vous avez besoin de documenter d’autres informations de restauration, telles que les informations de réinstallation de systèmes d’exploitation et autres logiciels, utilisez les plans de déploiement de votre organisation ainsi que les plans de sauvegarde et de restauration pour répondre à ces exigences.</span><span class="sxs-lookup"><span data-stu-id="c230d-109">If you need to document other restoration information, such as the information for reinstalling operating systems and other software, use your organization's deployment plans and backup and restoration plans to address those requirements.</span></span>



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a><span data-ttu-id="c230d-110">Feuille de calcul de sauvegarde et de restauration de base de données</span><span class="sxs-lookup"><span data-stu-id="c230d-110">Database Backup and Restoration Worksheet</span></span>

<span data-ttu-id="c230d-111">Utilisez le tableau suivant pour enregistrer les informations dont vous avez besoin pour sauvegarder et restaurer des bases de données Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c230d-111">Use the following table to record the information that you need to back up and restore Lync Server databases.</span></span>

### <a name="database-information-for-backup-and-restoration"></a><span data-ttu-id="c230d-112">Informations de base de données pour la sauvegarde et la restauration</span><span class="sxs-lookup"><span data-stu-id="c230d-112">Database Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c230d-113">Bases</span><span class="sxs-lookup"><span data-stu-id="c230d-113">Database</span></span></th>
<th><span data-ttu-id="c230d-114">Nom du serveur (FQDN)</span><span class="sxs-lookup"><span data-stu-id="c230d-114">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="c230d-115">Planning de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="c230d-115">Backup schedule</span></span></th>
<th><span data-ttu-id="c230d-116">Outil de sauvegarde de base de données</span><span class="sxs-lookup"><span data-stu-id="c230d-116">Database backup tool</span></span></th>
<th><span data-ttu-id="c230d-117">Jeu de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="c230d-117">Backup set</span></span></th>
<th><span data-ttu-id="c230d-118">Destination de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="c230d-118">Backup destination</span></span></th>
<th><span data-ttu-id="c230d-119">Remarques</span><span class="sxs-lookup"><span data-stu-id="c230d-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c230d-120">Base de données RTC sur le serveur principal pour les données utilisateur</span><span class="sxs-lookup"><span data-stu-id="c230d-120">Rtc database on Back End Server for user data</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="c230d-121">Cmdlet <strong>Export-CsUserData</strong></span><span class="sxs-lookup"><span data-stu-id="c230d-121"><strong>Export-CsUserData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="c230d-122">Nommer</span><span class="sxs-lookup"><span data-stu-id="c230d-122">Name:</span></span></p>
<p><span data-ttu-id="c230d-123">Leur</span><span class="sxs-lookup"><span data-stu-id="c230d-123">Expiration:</span></span></p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c230d-124">Base de données LcsLog (nom par défaut) sur le serveur de base de données d’archivage</span><span class="sxs-lookup"><span data-stu-id="c230d-124">LcsLog (default name) database on Archiving database server</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c230d-125">Outil de gestion SQL Server</span><span class="sxs-lookup"><span data-stu-id="c230d-125">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="c230d-126">Nommer</span><span class="sxs-lookup"><span data-stu-id="c230d-126">Name:</span></span></p>
<p><span data-ttu-id="c230d-127">Leur</span><span class="sxs-lookup"><span data-stu-id="c230d-127">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c230d-128">Base de données LcsCdr sur analyse du serveur de base de données pour les enregistrements des détails des appels (CdR)</span><span class="sxs-lookup"><span data-stu-id="c230d-128">LcsCdr database on Monitoring database server for call detail records (CDRs)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c230d-129">Outil de gestion SQL Server</span><span class="sxs-lookup"><span data-stu-id="c230d-129">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="c230d-130">Nommer</span><span class="sxs-lookup"><span data-stu-id="c230d-130">Name:</span></span></p>
<p><span data-ttu-id="c230d-131">Leur</span><span class="sxs-lookup"><span data-stu-id="c230d-131">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c230d-132">Base de données QoEMetrics sur l’analyse des données d’un serveur de base de données</span><span class="sxs-lookup"><span data-stu-id="c230d-132">QoEMetrics database on Monitoring database server for Quality of Experience (QoE) data</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c230d-133">Outil de gestion SQL Server</span><span class="sxs-lookup"><span data-stu-id="c230d-133">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="c230d-134">Nommer</span><span class="sxs-lookup"><span data-stu-id="c230d-134">Name:</span></span></p>
<p><span data-ttu-id="c230d-135">Leur</span><span class="sxs-lookup"><span data-stu-id="c230d-135">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c230d-136">Base de données de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="c230d-136">Persistent Chat Database</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="c230d-137">Outil de gestion SQL Server ou cmdlet <strong>Export-CsPersistentChatData</strong></span><span class="sxs-lookup"><span data-stu-id="c230d-137">SQL Server management tool or <strong>Export-CsPersistentChatData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="c230d-138">Nommer</span><span class="sxs-lookup"><span data-stu-id="c230d-138">Name:</span></span></p>
<p><span data-ttu-id="c230d-139">Leur</span><span class="sxs-lookup"><span data-stu-id="c230d-139">Expiration:</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c230d-140">Aucune sauvegarde ou restauration requise pour les bases de données suivantes :</span><span class="sxs-lookup"><span data-stu-id="c230d-140">No backup or restoration is required of the following databases:</span></span>

  - <span data-ttu-id="c230d-141">Rtcdyn.</span><span class="sxs-lookup"><span data-stu-id="c230d-141">Rtcdyn.</span></span> <span data-ttu-id="c230d-142">Les données utilisateur temporaires de cette base de données ne sont pas nécessaires à la restauration du service.</span><span class="sxs-lookup"><span data-stu-id="c230d-142">The transient user data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="c230d-143">Rtcab.</span><span class="sxs-lookup"><span data-stu-id="c230d-143">Rtcab.</span></span> <span data-ttu-id="c230d-144">La base de données du carnet d’adresses est recréée automatiquement à partir de la liste d’adresses globale dans les services de domaine Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="c230d-144">The Address Book database is automatically recreated from the Global Address List (GAL) in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="c230d-145">Rgsdyn.</span><span class="sxs-lookup"><span data-stu-id="c230d-145">Rgsdyn.</span></span> <span data-ttu-id="c230d-146">Il n’est pas nécessaire de restaurer les données du service de groupe de réponse temporaire dans cette base de données pour la restauration du service.</span><span class="sxs-lookup"><span data-stu-id="c230d-146">The transient Response Group service data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="c230d-147">Cpsdyn.</span><span class="sxs-lookup"><span data-stu-id="c230d-147">Cpsdyn.</span></span> <span data-ttu-id="c230d-148">Les informations dynamiques pour l’application de stationnement d’appel ne sont pas nécessaires pour la restauration du service.</span><span class="sxs-lookup"><span data-stu-id="c230d-148">The dynamic information for the Call Park application is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="c230d-149">MgcComp.</span><span class="sxs-lookup"><span data-stu-id="c230d-149">MgcComp.</span></span> <span data-ttu-id="c230d-150">La base de données de conformité pour la conversation permanente n’est pas nécessaire pour la restauration du service.</span><span class="sxs-lookup"><span data-stu-id="c230d-150">The compliance database for Persistent Chat is not necessary for restoration of service.</span></span>

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a><span data-ttu-id="c230d-151">Feuille de calcul de sauvegarde et de restauration du magasin de fichiers</span><span class="sxs-lookup"><span data-stu-id="c230d-151">File Store Backup and Restoration Worksheet</span></span>

<span data-ttu-id="c230d-152">Utilisez le tableau suivant pour enregistrer les informations dont vous avez besoin pour sauvegarder et restaurer les magasins de fichiers.</span><span class="sxs-lookup"><span data-stu-id="c230d-152">Use the following table to record the information that you need to back up and restore the File Stores.</span></span> <span data-ttu-id="c230d-153">Les magasins de fichiers contiennent des données telles que les métadonnées de contenu de la réunion, les journaux de mise à jour des mises à jour pour les mises à jour de l’appareil et les fichiers audio pour le groupe de réponse, le parc d’appels et les applications d’annonce.</span><span class="sxs-lookup"><span data-stu-id="c230d-153">File Stores contain data such as meeting content metadata, meeting compliance logs, update logs for device updates, and audio files for the Response Group, Call Park, and Announcement applications.</span></span>

### <a name="file-store-information-for-backup-and-restoration"></a><span data-ttu-id="c230d-154">Informations de stockage de fichiers pour la sauvegarde et la restauration</span><span class="sxs-lookup"><span data-stu-id="c230d-154">File Store Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c230d-155">Contenu</span><span class="sxs-lookup"><span data-stu-id="c230d-155">Content</span></span></th>
<th><span data-ttu-id="c230d-156">Nom du serveur (FQDN)</span><span class="sxs-lookup"><span data-stu-id="c230d-156">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="c230d-157">Planning de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="c230d-157">Backup schedule</span></span></th>
<th><span data-ttu-id="c230d-158">Outil de sauvegarde du système de fichiers</span><span class="sxs-lookup"><span data-stu-id="c230d-158">File system backup tool</span></span></th>
<th><span data-ttu-id="c230d-159">Partage de fichiers à sauvegarder \*</span><span class="sxs-lookup"><span data-stu-id="c230d-159">File share to be backed up \*</span></span></th>
<th><span data-ttu-id="c230d-160">Destination de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="c230d-160">Backup destination</span></span></th>
<th><span data-ttu-id="c230d-161">Remarques</span><span class="sxs-lookup"><span data-stu-id="c230d-161">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c230d-162">Magasin de fichiers de Lync Server</span><span class="sxs-lookup"><span data-stu-id="c230d-162">Lync Server File Store</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="c230d-163">Outil de sauvegarde standard, tel que Robocopy</span><span class="sxs-lookup"><span data-stu-id="c230d-163">Standard backup tool, such as Robocopy</span></span></p></td>
<td><p><span data-ttu-id="c230d-164">Sur le serveur de fichiers Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="c230d-164">On file server for Enterprise Edition.</span></span> <span data-ttu-id="c230d-165">Sur l’édition standard par défaut, pour le déploiement Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c230d-165">On Standard Edition by default, for Standard Edition deployment.</span></span> <span data-ttu-id="c230d-166">En règle générale, un par site.</span><span class="sxs-lookup"><span data-stu-id="c230d-166">Typically, one per site.</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c230d-167">Les fichiers nommés <strong>réunion. actif</strong> ne doivent pas être sauvegardés.</span><span class="sxs-lookup"><span data-stu-id="c230d-167">Files named <strong>Meeting.Active</strong> should not be backed up.</span></span> <span data-ttu-id="c230d-168">Ces fichiers sont utilisés et sont verrouillés lors d’une réunion.</span><span class="sxs-lookup"><span data-stu-id="c230d-168">These files are in use and are locked while a meeting takes place.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a><span data-ttu-id="c230d-169">Sauvegarder les paramètres et la feuille de calcul de restauration</span><span class="sxs-lookup"><span data-stu-id="c230d-169">Settings Backup and Restoration Worksheet</span></span>

<span data-ttu-id="c230d-170">Utilisez le tableau suivant pour enregistrer les informations dont vous avez besoin pour sauvegarder et restaurer les paramètres.</span><span class="sxs-lookup"><span data-stu-id="c230d-170">Use the following table to record the information that you need to back up and restore settings.</span></span>

### <a name="settings-information-for-backup-and-restoration"></a><span data-ttu-id="c230d-171">Informations de paramètres pour la sauvegarde et la restauration</span><span class="sxs-lookup"><span data-stu-id="c230d-171">Settings Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c230d-172">Bases</span><span class="sxs-lookup"><span data-stu-id="c230d-172">Database</span></span></th>
<th><span data-ttu-id="c230d-173">Nom du serveur (FQDN)</span><span class="sxs-lookup"><span data-stu-id="c230d-173">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="c230d-174">Planning de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="c230d-174">Backup schedule</span></span></th>
<th><span data-ttu-id="c230d-175">Outil de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="c230d-175">Backup tool</span></span></th>
<th><span data-ttu-id="c230d-176">Nom du fichier de configuration (. Xml)</span><span class="sxs-lookup"><span data-stu-id="c230d-176">Configuration file (.xml) name</span></span></th>
<th><span data-ttu-id="c230d-177">Emplacement de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="c230d-177">Backup location</span></span></th>
<th><span data-ttu-id="c230d-178">Remarques</span><span class="sxs-lookup"><span data-stu-id="c230d-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c230d-179">Base de données XDS dans le magasin central de gestion pour la configuration de la topologie (globale)</span><span class="sxs-lookup"><span data-stu-id="c230d-179">Xds database in Central Management store for topology configuration (global)</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="c230d-180">Cmdlet <strong>Export-CsConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="c230d-180"><strong>Export-CsConfiguration</strong> cmdlet</span></span></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c230d-181">Base de données lis dans le magasin central de gestion pour E9-1-1 informations d’emplacement (Global)</span><span class="sxs-lookup"><span data-stu-id="c230d-181">Lis database in Central Management store for E9-1-1 location information (global)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c230d-182">Cmdlet <strong>Export-CsLisConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="c230d-182"><strong>Export-CsLisConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c230d-183">Base de données RgsConfig du serveur principal pour la configuration de Response Group (pool)</span><span class="sxs-lookup"><span data-stu-id="c230d-183">RgsConfig database on Back End Server for Response Group configuration (pool)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c230d-184">Cmdlet <strong>Export-CsRgsConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="c230d-184"><strong>Export-CsRgsConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

