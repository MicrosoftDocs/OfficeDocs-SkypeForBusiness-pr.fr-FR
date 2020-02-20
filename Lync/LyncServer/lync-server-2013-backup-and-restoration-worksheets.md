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
ms.openlocfilehash: af90939e8034c8bf240ec04514a1a30044a14c94
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a><span data-ttu-id="b3c11-102">Feuilles de calcul de sauvegarde et de restauration pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3c11-102">Backup and restoration worksheets for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3c11-103">_**Dernière modification de la rubrique :** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="b3c11-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="b3c11-104">Le plan de sauvegarde et de restauration de votre organisation doit contenir des détails sur la manière et le moment de sauvegarder les données et les paramètres.</span><span class="sxs-lookup"><span data-stu-id="b3c11-104">The backup and restoration plan for your organization should contain details about how and when you back up data and settings.</span></span> <span data-ttu-id="b3c11-105">Vous pouvez utiliser les feuilles de calcul présentées ici pour vous aider à documenter ces informations pour votre déploiement et pour les besoins de votre organisation en matière de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="b3c11-105">You can use the worksheets presented here to help you document this information for your specific deployment and for your organization's backup and restoration requirements.</span></span>

<span data-ttu-id="b3c11-106">Utilisez les feuilles de calcul suivantes pour enregistrer les informations dont vous avez besoin pour sauvegarder et restaurer les informations de base de données, de magasin de fichiers et de paramètres d’un pool Lync Server ou d’un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="b3c11-106">Use the following worksheets to record the information that you need to back up and restore database, File Store, and settings information for a Lync Server pool or Standard Edition server.</span></span> <span data-ttu-id="b3c11-107">Conservez une ou plusieurs copies de ces feuilles de calcul dans un endroit sûr afin qu’elles soient facilement accessibles si vous devez restaurer Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3c11-107">Keep one or more copies of these worksheets in a secure location so that they are readily accessible if you need to restore Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b3c11-108">Les feuilles de cette section traitent uniquement les informations requises pour restaurer les données et les paramètres des serveurs et des bases de données Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3c11-108">The worksheets in this section cover only the information that is required to restore the data and settings of Lync Server databases and servers.</span></span> <span data-ttu-id="b3c11-109">Si vous devez documenter d’autres informations de restauration, telles que les informations de réinstallation des systèmes d’exploitation et d’autres logiciels, utilisez les plans de déploiement de votre organisation, ainsi que les plans de sauvegarde et de restauration pour répondre à ces exigences.</span><span class="sxs-lookup"><span data-stu-id="b3c11-109">If you need to document other restoration information, such as the information for reinstalling operating systems and other software, use your organization's deployment plans and backup and restoration plans to address those requirements.</span></span>



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a><span data-ttu-id="b3c11-110">Feuille de calcul de sauvegarde et de restauration de base de données</span><span class="sxs-lookup"><span data-stu-id="b3c11-110">Database Backup and Restoration Worksheet</span></span>

<span data-ttu-id="b3c11-111">Utilisez le tableau suivant pour enregistrer les informations dont vous avez besoin pour sauvegarder et restaurer des bases de données Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3c11-111">Use the following table to record the information that you need to back up and restore Lync Server databases.</span></span>

### <a name="database-information-for-backup-and-restoration"></a><span data-ttu-id="b3c11-112">Informations de base de données pour la sauvegarde et la restauration</span><span class="sxs-lookup"><span data-stu-id="b3c11-112">Database Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="b3c11-113">Base de données</span><span class="sxs-lookup"><span data-stu-id="b3c11-113">Database</span></span></th>
<th><span data-ttu-id="b3c11-114">Nom de serveur (FQDN)</span><span class="sxs-lookup"><span data-stu-id="b3c11-114">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="b3c11-115">Planification de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="b3c11-115">Backup schedule</span></span></th>
<th><span data-ttu-id="b3c11-116">Outil de sauvegarde de base de données</span><span class="sxs-lookup"><span data-stu-id="b3c11-116">Database backup tool</span></span></th>
<th><span data-ttu-id="b3c11-117">Jeu de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="b3c11-117">Backup set</span></span></th>
<th><span data-ttu-id="b3c11-118">Destination de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="b3c11-118">Backup destination</span></span></th>
<th><span data-ttu-id="b3c11-119">Notes</span><span class="sxs-lookup"><span data-stu-id="b3c11-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3c11-120">Base de données RTC sur le serveur principal pour les données utilisateur</span><span class="sxs-lookup"><span data-stu-id="b3c11-120">Rtc database on Back End Server for user data</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="b3c11-121">Cmdlet <strong>Export-applet csuserdata</strong></span><span class="sxs-lookup"><span data-stu-id="b3c11-121"><strong>Export-CsUserData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="b3c11-122">Nom</span><span class="sxs-lookup"><span data-stu-id="b3c11-122">Name:</span></span></p>
<p><span data-ttu-id="b3c11-123">Pire</span><span class="sxs-lookup"><span data-stu-id="b3c11-123">Expiration:</span></span></p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3c11-124">Base de données LcsLog (nom par défaut) sur le serveur de base de données d’archivage</span><span class="sxs-lookup"><span data-stu-id="b3c11-124">LcsLog (default name) database on Archiving database server</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3c11-125">Outil de gestion SQL Server</span><span class="sxs-lookup"><span data-stu-id="b3c11-125">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="b3c11-126">Nom</span><span class="sxs-lookup"><span data-stu-id="b3c11-126">Name:</span></span></p>
<p><span data-ttu-id="b3c11-127">Pire</span><span class="sxs-lookup"><span data-stu-id="b3c11-127">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3c11-128">Base de données LcsCdr sur le serveur de base de données de surveillance pour les enregistrements des détails des appels</span><span class="sxs-lookup"><span data-stu-id="b3c11-128">LcsCdr database on Monitoring database server for call detail records (CDRs)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3c11-129">Outil de gestion SQL Server</span><span class="sxs-lookup"><span data-stu-id="b3c11-129">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="b3c11-130">Nom</span><span class="sxs-lookup"><span data-stu-id="b3c11-130">Name:</span></span></p>
<p><span data-ttu-id="b3c11-131">Pire</span><span class="sxs-lookup"><span data-stu-id="b3c11-131">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3c11-132">Base de données QoEMetrics sur le serveur de base de données de surveillance pour les données QoE (qualité de l’expérience)</span><span class="sxs-lookup"><span data-stu-id="b3c11-132">QoEMetrics database on Monitoring database server for Quality of Experience (QoE) data</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3c11-133">Outil de gestion SQL Server</span><span class="sxs-lookup"><span data-stu-id="b3c11-133">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="b3c11-134">Nom</span><span class="sxs-lookup"><span data-stu-id="b3c11-134">Name:</span></span></p>
<p><span data-ttu-id="b3c11-135">Pire</span><span class="sxs-lookup"><span data-stu-id="b3c11-135">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3c11-136">Base de données de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="b3c11-136">Persistent Chat Database</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="b3c11-137">Outil de gestion SQL Server ou cmdlet <strong>Export-applet cspersistentchatdata</strong></span><span class="sxs-lookup"><span data-stu-id="b3c11-137">SQL Server management tool or <strong>Export-CsPersistentChatData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="b3c11-138">Nom</span><span class="sxs-lookup"><span data-stu-id="b3c11-138">Name:</span></span></p>
<p><span data-ttu-id="b3c11-139">Pire</span><span class="sxs-lookup"><span data-stu-id="b3c11-139">Expiration:</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b3c11-140">Aucune sauvegarde ou restauration n’est requise pour les bases de données suivantes :</span><span class="sxs-lookup"><span data-stu-id="b3c11-140">No backup or restoration is required of the following databases:</span></span>

  - <span data-ttu-id="b3c11-141">RTCDyn.</span><span class="sxs-lookup"><span data-stu-id="b3c11-141">Rtcdyn.</span></span> <span data-ttu-id="b3c11-142">Les données utilisateur temporaires de cette base de données ne sont pas nécessaires à la restauration du service.</span><span class="sxs-lookup"><span data-stu-id="b3c11-142">The transient user data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="b3c11-143">RTCAb.</span><span class="sxs-lookup"><span data-stu-id="b3c11-143">Rtcab.</span></span> <span data-ttu-id="b3c11-144">La base de données de carnet d’adresses est recréée automatiquement à partir de la liste d’adresses globale (LAG) dans les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b3c11-144">The Address Book database is automatically recreated from the Global Address List (GAL) in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="b3c11-145">Rgsdyn.</span><span class="sxs-lookup"><span data-stu-id="b3c11-145">Rgsdyn.</span></span> <span data-ttu-id="b3c11-146">Les données de service Response Group de cette base de données ne sont pas nécessaires à la restauration du service.</span><span class="sxs-lookup"><span data-stu-id="b3c11-146">The transient Response Group service data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="b3c11-147">Cpsdyn.</span><span class="sxs-lookup"><span data-stu-id="b3c11-147">Cpsdyn.</span></span> <span data-ttu-id="b3c11-148">Les informations dynamiques pour l’application de parcage d’appel ne sont pas nécessaires à la restauration du service.</span><span class="sxs-lookup"><span data-stu-id="b3c11-148">The dynamic information for the Call Park application is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="b3c11-149">MgcComp.</span><span class="sxs-lookup"><span data-stu-id="b3c11-149">MgcComp.</span></span> <span data-ttu-id="b3c11-150">La base de données de conformité pour la conversation permanente n’est pas nécessaire pour la restauration du service.</span><span class="sxs-lookup"><span data-stu-id="b3c11-150">The compliance database for Persistent Chat is not necessary for restoration of service.</span></span>

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a><span data-ttu-id="b3c11-151">Feuille de calcul de sauvegarde et de restauration du magasin de fichiers</span><span class="sxs-lookup"><span data-stu-id="b3c11-151">File Store Backup and Restoration Worksheet</span></span>

<span data-ttu-id="b3c11-152">Utilisez le tableau suivant pour enregistrer les informations nécessaires à la sauvegarde et à la restauration des magasins de fichiers.</span><span class="sxs-lookup"><span data-stu-id="b3c11-152">Use the following table to record the information that you need to back up and restore the File Stores.</span></span> <span data-ttu-id="b3c11-153">Les magasins de fichiers contiennent des données telles que des métadonnées de contenu de réunion, des journaux de conformité de réunion, des journaux de mise à jour pour les mises à jour de périphérique et des fichiers audio pour le groupe de réponse, le parcage d’appel et les applications d’annonce.</span><span class="sxs-lookup"><span data-stu-id="b3c11-153">File Stores contain data such as meeting content metadata, meeting compliance logs, update logs for device updates, and audio files for the Response Group, Call Park, and Announcement applications.</span></span>

### <a name="file-store-information-for-backup-and-restoration"></a><span data-ttu-id="b3c11-154">Informations sur le magasin de fichiers pour la sauvegarde et la restauration</span><span class="sxs-lookup"><span data-stu-id="b3c11-154">File Store Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="b3c11-155">Contenu</span><span class="sxs-lookup"><span data-stu-id="b3c11-155">Content</span></span></th>
<th><span data-ttu-id="b3c11-156">Nom de serveur (FQDN)</span><span class="sxs-lookup"><span data-stu-id="b3c11-156">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="b3c11-157">Planification de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="b3c11-157">Backup schedule</span></span></th>
<th><span data-ttu-id="b3c11-158">Outil de sauvegarde de système de fichiers</span><span class="sxs-lookup"><span data-stu-id="b3c11-158">File system backup tool</span></span></th>
<th><span data-ttu-id="b3c11-159">Partage de fichiers à sauvegarder \*</span><span class="sxs-lookup"><span data-stu-id="b3c11-159">File share to be backed up \*</span></span></th>
<th><span data-ttu-id="b3c11-160">Destination de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="b3c11-160">Backup destination</span></span></th>
<th><span data-ttu-id="b3c11-161">Notes</span><span class="sxs-lookup"><span data-stu-id="b3c11-161">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3c11-162">Magasin de fichiers Lync Server</span><span class="sxs-lookup"><span data-stu-id="b3c11-162">Lync Server File Store</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="b3c11-163">Outil de sauvegarde standard, tel que Robocopy</span><span class="sxs-lookup"><span data-stu-id="b3c11-163">Standard backup tool, such as Robocopy</span></span></p></td>
<td><p><span data-ttu-id="b3c11-164">Sur le serveur de fichiers pour Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="b3c11-164">On file server for Enterprise Edition.</span></span> <span data-ttu-id="b3c11-165">Sur Standard Edition, par défaut, pour le déploiement Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b3c11-165">On Standard Edition by default, for Standard Edition deployment.</span></span> <span data-ttu-id="b3c11-166">En règle générale, un par site.</span><span class="sxs-lookup"><span data-stu-id="b3c11-166">Typically, one per site.</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b3c11-167">Les fichiers nommés <strong>Meeting. active</strong> ne doivent pas être sauvegardés.</span><span class="sxs-lookup"><span data-stu-id="b3c11-167">Files named <strong>Meeting.Active</strong> should not be backed up.</span></span> <span data-ttu-id="b3c11-168">Ces fichiers sont en cours d’utilisation et sont verrouillés pendant qu’une réunion a lieu.</span><span class="sxs-lookup"><span data-stu-id="b3c11-168">These files are in use and are locked while a meeting takes place.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a><span data-ttu-id="b3c11-169">Feuille de calcul de restauration et de sauvegarde des paramètres</span><span class="sxs-lookup"><span data-stu-id="b3c11-169">Settings Backup and Restoration Worksheet</span></span>

<span data-ttu-id="b3c11-170">Utilisez le tableau suivant pour enregistrer les informations dont vous avez besoin pour sauvegarder et restaurer les paramètres.</span><span class="sxs-lookup"><span data-stu-id="b3c11-170">Use the following table to record the information that you need to back up and restore settings.</span></span>

### <a name="settings-information-for-backup-and-restoration"></a><span data-ttu-id="b3c11-171">Informations sur les paramètres de sauvegarde et de restauration</span><span class="sxs-lookup"><span data-stu-id="b3c11-171">Settings Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="b3c11-172">Base de données</span><span class="sxs-lookup"><span data-stu-id="b3c11-172">Database</span></span></th>
<th><span data-ttu-id="b3c11-173">Nom de serveur (FQDN)</span><span class="sxs-lookup"><span data-stu-id="b3c11-173">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="b3c11-174">Planification de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="b3c11-174">Backup schedule</span></span></th>
<th><span data-ttu-id="b3c11-175">Outil de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="b3c11-175">Backup tool</span></span></th>
<th><span data-ttu-id="b3c11-176">Nom du fichier de configuration (. Xml)</span><span class="sxs-lookup"><span data-stu-id="b3c11-176">Configuration file (.xml) name</span></span></th>
<th><span data-ttu-id="b3c11-177">Emplacement de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="b3c11-177">Backup location</span></span></th>
<th><span data-ttu-id="b3c11-178">Notes</span><span class="sxs-lookup"><span data-stu-id="b3c11-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3c11-179">Base de données XDS dans le magasin central de gestion pour la configuration de la topologie (Global)</span><span class="sxs-lookup"><span data-stu-id="b3c11-179">Xds database in Central Management store for topology configuration (global)</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="b3c11-180">Cmdlet <strong>Export-CsConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="b3c11-180"><strong>Export-CsConfiguration</strong> cmdlet</span></span></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3c11-181">Base de données lis dans le magasin central de gestion pour les informations d’emplacement E9-1-1 (Global)</span><span class="sxs-lookup"><span data-stu-id="b3c11-181">Lis database in Central Management store for E9-1-1 location information (global)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3c11-182">Cmdlet <strong>Export-CsLisConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="b3c11-182"><strong>Export-CsLisConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3c11-183">Base de données RgsConfig sur le serveur principal pour la configuration Response Group (pool)</span><span class="sxs-lookup"><span data-stu-id="b3c11-183">RgsConfig database on Back End Server for Response Group configuration (pool)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3c11-184">Cmdlet <strong>Export-applet csrgsconfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="b3c11-184"><strong>Export-CsRgsConfiguration</strong> cmdlet</span></span></p></td>
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

