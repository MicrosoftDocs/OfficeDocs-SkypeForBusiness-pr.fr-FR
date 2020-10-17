---
title: 'Lync Server 2013 : feuilles de calcul de sauvegarde et de restauration'
description: 'Lync Server 2013 : feuilles de calcul de sauvegarde et de restauration.'
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
ms.openlocfilehash: 1713e291ae7132cc96309fa499bd97bf7f4f5016
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552316"
---
# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a><span data-ttu-id="4eb4a-103">Feuilles de calcul de sauvegarde et de restauration pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4eb4a-103">Backup and restoration worksheets for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4eb4a-104">_**Dernière modification de la rubrique :** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="4eb4a-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="4eb4a-105">Le plan de sauvegarde et de restauration de votre organisation doit contenir des détails sur la manière et le moment de sauvegarder les données et les paramètres.</span><span class="sxs-lookup"><span data-stu-id="4eb4a-105">The backup and restoration plan for your organization should contain details about how and when you back up data and settings.</span></span> <span data-ttu-id="4eb4a-106">Vous pouvez utiliser les feuilles de calcul présentées ici pour vous aider à documenter ces informations pour votre déploiement et pour les besoins de votre organisation en matière de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="4eb4a-106">You can use the worksheets presented here to help you document this information for your specific deployment and for your organization's backup and restoration requirements.</span></span>

<span data-ttu-id="4eb4a-107">Utilisez les feuilles de calcul suivantes pour enregistrer les informations dont vous avez besoin pour sauvegarder et restaurer les informations de base de données, de magasin de fichiers et de paramètres d’un pool Lync Server ou d’un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="4eb4a-107">Use the following worksheets to record the information that you need to back up and restore database, File Store, and settings information for a Lync Server pool or Standard Edition server.</span></span> <span data-ttu-id="4eb4a-108">Conservez une ou plusieurs copies de ces feuilles de calcul dans un endroit sûr afin qu’elles soient facilement accessibles si vous devez restaurer Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4eb4a-108">Keep one or more copies of these worksheets in a secure location so that they are readily accessible if you need to restore Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4eb4a-109">Les feuilles de cette section traitent uniquement les informations requises pour restaurer les données et les paramètres des serveurs et des bases de données Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4eb4a-109">The worksheets in this section cover only the information that is required to restore the data and settings of Lync Server databases and servers.</span></span> <span data-ttu-id="4eb4a-110">Si vous devez documenter d’autres informations de restauration, telles que les informations de réinstallation des systèmes d’exploitation et d’autres logiciels, utilisez les plans de déploiement de votre organisation, ainsi que les plans de sauvegarde et de restauration pour répondre à ces exigences.</span><span class="sxs-lookup"><span data-stu-id="4eb4a-110">If you need to document other restoration information, such as the information for reinstalling operating systems and other software, use your organization's deployment plans and backup and restoration plans to address those requirements.</span></span>



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a><span data-ttu-id="4eb4a-111">Feuille de calcul de sauvegarde et de restauration de base de données</span><span class="sxs-lookup"><span data-stu-id="4eb4a-111">Database Backup and Restoration Worksheet</span></span>

<span data-ttu-id="4eb4a-112">Utilisez le tableau suivant pour enregistrer les informations dont vous avez besoin pour sauvegarder et restaurer des bases de données Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4eb4a-112">Use the following table to record the information that you need to back up and restore Lync Server databases.</span></span>

### <a name="database-information-for-backup-and-restoration"></a><span data-ttu-id="4eb4a-113">Informations de base de données pour la sauvegarde et la restauration</span><span class="sxs-lookup"><span data-stu-id="4eb4a-113">Database Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="4eb4a-114">Database</span><span class="sxs-lookup"><span data-stu-id="4eb4a-114">Database</span></span></th>
<th><span data-ttu-id="4eb4a-115">Nom de serveur (FQDN)</span><span class="sxs-lookup"><span data-stu-id="4eb4a-115">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="4eb4a-116">Planification de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="4eb4a-116">Backup schedule</span></span></th>
<th><span data-ttu-id="4eb4a-117">Outil de sauvegarde de base de données</span><span class="sxs-lookup"><span data-stu-id="4eb4a-117">Database backup tool</span></span></th>
<th><span data-ttu-id="4eb4a-118">Jeu de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="4eb4a-118">Backup set</span></span></th>
<th><span data-ttu-id="4eb4a-119">Destination de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="4eb4a-119">Backup destination</span></span></th>
<th><span data-ttu-id="4eb4a-120">Notes</span><span class="sxs-lookup"><span data-stu-id="4eb4a-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4eb4a-121">Base de données RTC sur le serveur principal pour les données utilisateur</span><span class="sxs-lookup"><span data-stu-id="4eb4a-121">Rtc database on Back End Server for user data</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="4eb4a-122">Cmdlet <strong>Export-applet csuserdata</strong></span><span class="sxs-lookup"><span data-stu-id="4eb4a-122"><strong>Export-CsUserData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="4eb4a-123">Nom</span><span class="sxs-lookup"><span data-stu-id="4eb4a-123">Name:</span></span></p>
<p><span data-ttu-id="4eb4a-124">Pire</span><span class="sxs-lookup"><span data-stu-id="4eb4a-124">Expiration:</span></span></p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eb4a-125">Base de données LcsLog (nom par défaut) sur le serveur de base de données d’archivage</span><span class="sxs-lookup"><span data-stu-id="4eb4a-125">LcsLog (default name) database on Archiving database server</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4eb4a-126">Outil de gestion SQL Server</span><span class="sxs-lookup"><span data-stu-id="4eb4a-126">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="4eb4a-127">Nom</span><span class="sxs-lookup"><span data-stu-id="4eb4a-127">Name:</span></span></p>
<p><span data-ttu-id="4eb4a-128">Pire</span><span class="sxs-lookup"><span data-stu-id="4eb4a-128">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eb4a-129">Base de données LcsCdr sur le serveur de base de données de surveillance pour les enregistrements des détails des appels</span><span class="sxs-lookup"><span data-stu-id="4eb4a-129">LcsCdr database on Monitoring database server for call detail records (CDRs)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4eb4a-130">Outil de gestion SQL Server</span><span class="sxs-lookup"><span data-stu-id="4eb4a-130">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="4eb4a-131">Nom</span><span class="sxs-lookup"><span data-stu-id="4eb4a-131">Name:</span></span></p>
<p><span data-ttu-id="4eb4a-132">Pire</span><span class="sxs-lookup"><span data-stu-id="4eb4a-132">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eb4a-133">Base de données QoEMetrics sur le serveur de base de données de surveillance pour les données QoE (qualité de l’expérience)</span><span class="sxs-lookup"><span data-stu-id="4eb4a-133">QoEMetrics database on Monitoring database server for Quality of Experience (QoE) data</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4eb4a-134">Outil de gestion SQL Server</span><span class="sxs-lookup"><span data-stu-id="4eb4a-134">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="4eb4a-135">Nom</span><span class="sxs-lookup"><span data-stu-id="4eb4a-135">Name:</span></span></p>
<p><span data-ttu-id="4eb4a-136">Pire</span><span class="sxs-lookup"><span data-stu-id="4eb4a-136">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eb4a-137">Base de données de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="4eb4a-137">Persistent Chat Database</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="4eb4a-138">Outil de gestion SQL Server ou cmdlet <strong>Export-applet cspersistentchatdata</strong></span><span class="sxs-lookup"><span data-stu-id="4eb4a-138">SQL Server management tool or <strong>Export-CsPersistentChatData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="4eb4a-139">Nom</span><span class="sxs-lookup"><span data-stu-id="4eb4a-139">Name:</span></span></p>
<p><span data-ttu-id="4eb4a-140">Pire</span><span class="sxs-lookup"><span data-stu-id="4eb4a-140">Expiration:</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4eb4a-141">Aucune sauvegarde ou restauration n’est requise pour les bases de données suivantes :</span><span class="sxs-lookup"><span data-stu-id="4eb4a-141">No backup or restoration is required of the following databases:</span></span>

  - <span data-ttu-id="4eb4a-142">RTCDyn.</span><span class="sxs-lookup"><span data-stu-id="4eb4a-142">Rtcdyn.</span></span> <span data-ttu-id="4eb4a-143">Les données utilisateur temporaires de cette base de données ne sont pas nécessaires à la restauration du service.</span><span class="sxs-lookup"><span data-stu-id="4eb4a-143">The transient user data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="4eb4a-144">RTCAb.</span><span class="sxs-lookup"><span data-stu-id="4eb4a-144">Rtcab.</span></span> <span data-ttu-id="4eb4a-145">La base de données de carnet d’adresses est recréée automatiquement à partir de la liste d’adresses globale (LAG) dans les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4eb4a-145">The Address Book database is automatically recreated from the Global Address List (GAL) in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="4eb4a-146">Rgsdyn.</span><span class="sxs-lookup"><span data-stu-id="4eb4a-146">Rgsdyn.</span></span> <span data-ttu-id="4eb4a-147">Les données de service Response Group de cette base de données ne sont pas nécessaires à la restauration du service.</span><span class="sxs-lookup"><span data-stu-id="4eb4a-147">The transient Response Group service data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="4eb4a-148">Cpsdyn.</span><span class="sxs-lookup"><span data-stu-id="4eb4a-148">Cpsdyn.</span></span> <span data-ttu-id="4eb4a-149">Les informations dynamiques pour l’application de parcage d’appel ne sont pas nécessaires à la restauration du service.</span><span class="sxs-lookup"><span data-stu-id="4eb4a-149">The dynamic information for the Call Park application is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="4eb4a-150">MgcComp.</span><span class="sxs-lookup"><span data-stu-id="4eb4a-150">MgcComp.</span></span> <span data-ttu-id="4eb4a-151">La base de données de conformité pour la conversation permanente n’est pas nécessaire pour la restauration du service.</span><span class="sxs-lookup"><span data-stu-id="4eb4a-151">The compliance database for Persistent Chat is not necessary for restoration of service.</span></span>

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a><span data-ttu-id="4eb4a-152">Feuille de calcul de sauvegarde et de restauration du magasin de fichiers</span><span class="sxs-lookup"><span data-stu-id="4eb4a-152">File Store Backup and Restoration Worksheet</span></span>

<span data-ttu-id="4eb4a-153">Utilisez le tableau suivant pour enregistrer les informations nécessaires à la sauvegarde et à la restauration des magasins de fichiers.</span><span class="sxs-lookup"><span data-stu-id="4eb4a-153">Use the following table to record the information that you need to back up and restore the File Stores.</span></span> <span data-ttu-id="4eb4a-154">Les magasins de fichiers contiennent des données telles que des métadonnées de contenu de réunion, des journaux de conformité de réunion, des journaux de mise à jour pour les mises à jour de périphérique et des fichiers audio pour le groupe de réponse, le parcage d’appel et les applications d’annonce.</span><span class="sxs-lookup"><span data-stu-id="4eb4a-154">File Stores contain data such as meeting content metadata, meeting compliance logs, update logs for device updates, and audio files for the Response Group, Call Park, and Announcement applications.</span></span>

### <a name="file-store-information-for-backup-and-restoration"></a><span data-ttu-id="4eb4a-155">Informations sur le magasin de fichiers pour la sauvegarde et la restauration</span><span class="sxs-lookup"><span data-stu-id="4eb4a-155">File Store Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="4eb4a-156">Contenu</span><span class="sxs-lookup"><span data-stu-id="4eb4a-156">Content</span></span></th>
<th><span data-ttu-id="4eb4a-157">Nom de serveur (FQDN)</span><span class="sxs-lookup"><span data-stu-id="4eb4a-157">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="4eb4a-158">Planification de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="4eb4a-158">Backup schedule</span></span></th>
<th><span data-ttu-id="4eb4a-159">Outil de sauvegarde de système de fichiers</span><span class="sxs-lookup"><span data-stu-id="4eb4a-159">File system backup tool</span></span></th>
<th><span data-ttu-id="4eb4a-160">Partage de fichiers à sauvegarder \*</span><span class="sxs-lookup"><span data-stu-id="4eb4a-160">File share to be backed up \*</span></span></th>
<th><span data-ttu-id="4eb4a-161">Destination de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="4eb4a-161">Backup destination</span></span></th>
<th><span data-ttu-id="4eb4a-162">Notes</span><span class="sxs-lookup"><span data-stu-id="4eb4a-162">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4eb4a-163">Magasin de fichiers Lync Server</span><span class="sxs-lookup"><span data-stu-id="4eb4a-163">Lync Server File Store</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="4eb4a-164">Outil de sauvegarde standard, tel que Robocopy</span><span class="sxs-lookup"><span data-stu-id="4eb4a-164">Standard backup tool, such as Robocopy</span></span></p></td>
<td><p><span data-ttu-id="4eb4a-165">Sur le serveur de fichiers pour Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="4eb4a-165">On file server for Enterprise Edition.</span></span> <span data-ttu-id="4eb4a-166">Sur Standard Edition, par défaut, pour le déploiement Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="4eb4a-166">On Standard Edition by default, for Standard Edition deployment.</span></span> <span data-ttu-id="4eb4a-167">En règle générale, un par site.</span><span class="sxs-lookup"><span data-stu-id="4eb4a-167">Typically, one per site.</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4eb4a-168">Les fichiers nommés <strong>Meeting. active</strong> ne doivent pas être sauvegardés.</span><span class="sxs-lookup"><span data-stu-id="4eb4a-168">Files named <strong>Meeting.Active</strong> should not be backed up.</span></span> <span data-ttu-id="4eb4a-169">Ces fichiers sont en cours d’utilisation et sont verrouillés pendant qu’une réunion a lieu.</span><span class="sxs-lookup"><span data-stu-id="4eb4a-169">These files are in use and are locked while a meeting takes place.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a><span data-ttu-id="4eb4a-170">Feuille de calcul de restauration et de sauvegarde des paramètres</span><span class="sxs-lookup"><span data-stu-id="4eb4a-170">Settings Backup and Restoration Worksheet</span></span>

<span data-ttu-id="4eb4a-171">Utilisez le tableau suivant pour enregistrer les informations dont vous avez besoin pour sauvegarder et restaurer les paramètres.</span><span class="sxs-lookup"><span data-stu-id="4eb4a-171">Use the following table to record the information that you need to back up and restore settings.</span></span>

### <a name="settings-information-for-backup-and-restoration"></a><span data-ttu-id="4eb4a-172">Informations sur les paramètres de sauvegarde et de restauration</span><span class="sxs-lookup"><span data-stu-id="4eb4a-172">Settings Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="4eb4a-173">Database</span><span class="sxs-lookup"><span data-stu-id="4eb4a-173">Database</span></span></th>
<th><span data-ttu-id="4eb4a-174">Nom de serveur (FQDN)</span><span class="sxs-lookup"><span data-stu-id="4eb4a-174">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="4eb4a-175">Planification de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="4eb4a-175">Backup schedule</span></span></th>
<th><span data-ttu-id="4eb4a-176">Outil de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="4eb4a-176">Backup tool</span></span></th>
<th><span data-ttu-id="4eb4a-177">Nom du fichier de configuration (. Xml)</span><span class="sxs-lookup"><span data-stu-id="4eb4a-177">Configuration file (.xml) name</span></span></th>
<th><span data-ttu-id="4eb4a-178">Emplacement de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="4eb4a-178">Backup location</span></span></th>
<th><span data-ttu-id="4eb4a-179">Notes</span><span class="sxs-lookup"><span data-stu-id="4eb4a-179">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4eb4a-180">Base de données XDS dans le magasin central de gestion pour la configuration de la topologie (Global)</span><span class="sxs-lookup"><span data-stu-id="4eb4a-180">Xds database in Central Management store for topology configuration (global)</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="4eb4a-181">Cmdlet <strong>Export-CsConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="4eb4a-181"><strong>Export-CsConfiguration</strong> cmdlet</span></span></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eb4a-182">Base de données lis dans le magasin central de gestion pour les informations d’emplacement E9-1-1 (Global)</span><span class="sxs-lookup"><span data-stu-id="4eb4a-182">Lis database in Central Management store for E9-1-1 location information (global)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4eb4a-183">Cmdlet <strong>Export-CsLisConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="4eb4a-183"><strong>Export-CsLisConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eb4a-184">Base de données RgsConfig sur le serveur principal pour la configuration Response Group (pool)</span><span class="sxs-lookup"><span data-stu-id="4eb4a-184">RgsConfig database on Back End Server for Response Group configuration (pool)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4eb4a-185">Cmdlet <strong>Export-applet csrgsconfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="4eb4a-185"><strong>Export-CsRgsConfiguration</strong> cmdlet</span></span></p></td>
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

