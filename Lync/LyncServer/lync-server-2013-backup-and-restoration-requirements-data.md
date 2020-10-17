---
title: 'Lync Server 2013 : exigences en matière de sauvegarde et de restauration : données'
description: 'Lync Server 2013 : exigences en matière de sauvegarde et de restauration : données.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: data'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202194(v=OCS.15)
ms:contentKeyID: 51541526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e135f09706d31ff3f0efa54c8687546de9fab78
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563180"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a><span data-ttu-id="85cb6-103">Configuration requise pour la sauvegarde et la restauration dans Lync Server 2013 : données</span><span class="sxs-lookup"><span data-stu-id="85cb6-103">Backup and restoration requirements in Lync Server 2013: data</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85cb6-104">_**Dernière modification de la rubrique :** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="85cb6-104">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="85cb6-105">Lync Server utilise les paramètres et les informations de configuration stockés dans les bases de données, ainsi que les données stockées dans les bases de données et les magasins de fichiers.</span><span class="sxs-lookup"><span data-stu-id="85cb6-105">Lync Server uses settings and configuration information that are stored in databases, and data that is stored in databases and file stores.</span></span> <span data-ttu-id="85cb6-106">Cette rubrique décrit les données que vous devez sauvegarder pour pouvoir restaurer le service si votre organisation rencontre une défaillance ou une panne, et identifie également les données et les composants utilisés par Lync Server que vous devez sauvegarder séparément.</span><span class="sxs-lookup"><span data-stu-id="85cb6-106">This topic describes the data that you need to back up to be able to restore service if your organization experiences a failure or outage, and also identifies the data and components used by Lync Server that you need to back up separately.</span></span>

<div>

## <a name="settings-and-configuration-requirements"></a><span data-ttu-id="85cb6-107">Paramètres et configuration requis</span><span class="sxs-lookup"><span data-stu-id="85cb6-107">Settings and Configuration Requirements</span></span>

<span data-ttu-id="85cb6-108">Cette rubrique inclut des procédures de sauvegarde et de restauration des paramètres et des informations de configuration nécessaires pour la récupération du service Lync Server.</span><span class="sxs-lookup"><span data-stu-id="85cb6-108">This topic includes procedures for backing up and restoring the settings and configuration information that is required for recovery of Lync Server service.</span></span> <span data-ttu-id="85cb6-109">Les informations de configuration se trouvent dans le magasin central de gestion ou sur une autre base de données principale ou sur un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="85cb6-109">The configuration information is located in the Central Management store or on another back-end database or on Standard Edition server.</span></span>

<span data-ttu-id="85cb6-110">Le tableau suivant identifie les paramètres et les informations de configuration que vous devez sauvegarder et restaurer.</span><span class="sxs-lookup"><span data-stu-id="85cb6-110">The following table identifies the settings and configuration information that you need to back up and restore.</span></span>

### <a name="settings-and-configuration-data"></a><span data-ttu-id="85cb6-111">Paramètres et données de configuration</span><span class="sxs-lookup"><span data-stu-id="85cb6-111">Settings and Configuration Data</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85cb6-112">DataType</span><span class="sxs-lookup"><span data-stu-id="85cb6-112">Type of data</span></span></th>
<th><span data-ttu-id="85cb6-113">Emplacement de stockage</span><span class="sxs-lookup"><span data-stu-id="85cb6-113">Where stored</span></span></th>
<th><span data-ttu-id="85cb6-114">Description/quand sauvegarder</span><span class="sxs-lookup"><span data-stu-id="85cb6-114">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85cb6-115">Informations de configuration de la topologie</span><span class="sxs-lookup"><span data-stu-id="85cb6-115">Topology configuration information</span></span></p></td>
<td><p><span data-ttu-id="85cb6-116">Magasin central de gestion (base de données : XDS. mdf)</span><span class="sxs-lookup"><span data-stu-id="85cb6-116">Central Management store (database: Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="85cb6-117">Paramètres de topologie, de stratégie et de configuration.</span><span class="sxs-lookup"><span data-stu-id="85cb6-117">Topology, policy, and configuration settings.</span></span></p>
<p><span data-ttu-id="85cb6-118">Sauvegardez vos sauvegardes régulières et une fois que vous avez utilisé le panneau de configuration ou les cmdlets Lync Server pour modifier votre configuration ou vos stratégies.</span><span class="sxs-lookup"><span data-stu-id="85cb6-118">Back up with your regular backups and after you use Lync Server Control Panel or cmdlets to modify your configuration or policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85cb6-119">Informations d’emplacement</span><span class="sxs-lookup"><span data-stu-id="85cb6-119">Location information</span></span></p></td>
<td><p><span data-ttu-id="85cb6-120">Magasin central de gestion (base de données : lis. mdf)</span><span class="sxs-lookup"><span data-stu-id="85cb6-120">Central Management store (database: Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="85cb6-121">Informations de configuration d’Enterprise Voice Enhanced 9-1-1 (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="85cb6-121">Enterprise Voice Enhanced 9-1-1 (E9-1-1) configuration information.</span></span> <span data-ttu-id="85cb6-122">Ces informations sont généralement statiques.</span><span class="sxs-lookup"><span data-stu-id="85cb6-122">This information is generally static.</span></span></p>
<p><span data-ttu-id="85cb6-123">Sauvegardez vos sauvegardes régulières.</span><span class="sxs-lookup"><span data-stu-id="85cb6-123">Back up with your regular backups.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85cb6-124">Informations de configuration du groupe Response Group</span><span class="sxs-lookup"><span data-stu-id="85cb6-124">Response Group configuration information</span></span></p></td>
<td><p><span data-ttu-id="85cb6-125">Serveur principal ou serveur Standard Edition (base de données : RgsConfig. mdf)</span><span class="sxs-lookup"><span data-stu-id="85cb6-125">Back End Server or Standard Edition server (database: RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="85cb6-126">Groupes d’agents Response Group, files d’attente et flux de travail.</span><span class="sxs-lookup"><span data-stu-id="85cb6-126">Response Group agent groups, queues, and workflows.</span></span></p>
<p><span data-ttu-id="85cb6-127">Sauvegardez vos sauvegardes régulières et après avoir ajouté ou modifié des groupes d’agents, des files d’attente ou des flux de travail.</span><span class="sxs-lookup"><span data-stu-id="85cb6-127">Back up with your regular backups and after you add or change agent groups, queues, or workflows.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a><span data-ttu-id="85cb6-128">Données requises</span><span class="sxs-lookup"><span data-stu-id="85cb6-128">Data Requirements</span></span>

<span data-ttu-id="85cb6-129">Voici une liste des données Lync Server que vous devez sauvegarder afin de pouvoir restaurer le service Lync Server en cas de défaillance.</span><span class="sxs-lookup"><span data-stu-id="85cb6-129">Here is a list of the Lync Server data that you need to back up so that you can restore Lync Server service in the event of a failure.</span></span>

<span data-ttu-id="85cb6-130">Notez que certains types de données ne sont pas requis pour la récupération.</span><span class="sxs-lookup"><span data-stu-id="85cb6-130">Note that some types of data are not required for recovery.</span></span> <span data-ttu-id="85cb6-131">Cette rubrique ne contient pas les procédures de sauvegarde de ces types de données, notamment les suivantes :</span><span class="sxs-lookup"><span data-stu-id="85cb6-131">This topic does not contain procedures for backing up these types of data, which include the following:</span></span>

  - <span data-ttu-id="85cb6-132">Les données utilisateur temporaires, telles que les points de terminaison et les abonnements, les serveurs de conférence actifs et les États de conférence transitoires (base de données : RtcDyn. mdf)</span><span class="sxs-lookup"><span data-stu-id="85cb6-132">Transient user data, such as endpoints and subscriptions, active conferencing servers, and transient conferencing states (database: RtcDyn.mdf)</span></span>

  - <span data-ttu-id="85cb6-133">Données de carnet d’adresses (bases de données : RTCAb. mdf et Rtcab1. mdf).</span><span class="sxs-lookup"><span data-stu-id="85cb6-133">Address Book data (databases: Rtcab.mdf and Rtcab1.mdf).</span></span> <span data-ttu-id="85cb6-134">La base de données de carnet d’adresses est automatiquement régénérée à partir des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="85cb6-134">The Address Book database is regenerated automatically from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="85cb6-135">Informations dynamiques pour l’application de parcage d’appel (base de données : CpsDyn. mdf)</span><span class="sxs-lookup"><span data-stu-id="85cb6-135">Dynamic information for the Call Park application (database: CpsDyn.mdf)</span></span>

  - <span data-ttu-id="85cb6-136">Données de groupe de réponse transitoires, telles que l’état de connexion de l’agent et les informations d’attente d’appel (base de données : RgsDyn. mdf)</span><span class="sxs-lookup"><span data-stu-id="85cb6-136">Transient Response Group data, such as agent sign-in state and call waiting information (database: RgsDyn.mdf)</span></span>

  - <span data-ttu-id="85cb6-137">La base de données de conformité pour la conversation permanente (base de données : MgcComp. mdf).</span><span class="sxs-lookup"><span data-stu-id="85cb6-137">The compliance database for Persistent Chat (database: MgcComp.mdf).</span></span> <span data-ttu-id="85cb6-138">Si la conformité de conversation permanente est activée, les informations contenues dans la base de données de conformité de conversation permanente sont transitoires tant que vous disposez d’un adaptateur configuré pour lire les informations de la base de données et les convertir dans un autre format.</span><span class="sxs-lookup"><span data-stu-id="85cb6-138">If you have Persistent Chat compliance enabled, the information in the Persistent Chat Compliance database is transient as long as you have an adapter configured to read information from the database and convert it to an alternate format.</span></span> <span data-ttu-id="85cb6-139">La base de données de conformité pour la conversation permanente est donc considérée comme transitoire.</span><span class="sxs-lookup"><span data-stu-id="85cb6-139">Hence the compliance database for Persistent Chat is considered transient.</span></span>
    
    <span data-ttu-id="85cb6-140">Lync Server 2013 le serveur de conversation permanente est fourni avec une carte XML.</span><span class="sxs-lookup"><span data-stu-id="85cb6-140">Lync Server 2013 Persistent Chat Server ships with an XML adapter.</span></span> <span data-ttu-id="85cb6-141">Vous pouvez également installer des adaptateurs personnalisés qui prennent ces données et les déplacer vers d’autres sources, telles que les archives hébergées sur Exchange.</span><span class="sxs-lookup"><span data-stu-id="85cb6-141">You can also install custom adapters that take this data and move it to other sources, such as Exchange Hosted Archives.</span></span>

<span data-ttu-id="85cb6-142">Le tableau suivant identifie les données que vous devez sauvegarder et restaurer.</span><span class="sxs-lookup"><span data-stu-id="85cb6-142">The following table identifies the data that you need to back up and restore.</span></span>

### <a name="data-stored-in-databases"></a><span data-ttu-id="85cb6-143">Données stockées dans des bases de données</span><span class="sxs-lookup"><span data-stu-id="85cb6-143">Data Stored in Databases</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85cb6-144">DataType</span><span class="sxs-lookup"><span data-stu-id="85cb6-144">Type of data</span></span></th>
<th><span data-ttu-id="85cb6-145">Emplacement de stockage</span><span class="sxs-lookup"><span data-stu-id="85cb6-145">Where stored</span></span></th>
<th><span data-ttu-id="85cb6-146">Description/quand sauvegarder</span><span class="sxs-lookup"><span data-stu-id="85cb6-146">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85cb6-147">Données utilisateur persistantes</span><span class="sxs-lookup"><span data-stu-id="85cb6-147">Persistent user data</span></span></p></td>
<td><p><span data-ttu-id="85cb6-148">Serveur principal ou serveur Standard Edition (base de données : RTCXDS. mdf)</span><span class="sxs-lookup"><span data-stu-id="85cb6-148">Back End Server or Standard Edition server (database: RTCXDS.mdf)</span></span></p></td>
<td><p><span data-ttu-id="85cb6-149">Les droits d’utilisateur, les listes de contacts des utilisateurs, les données du serveur ou du pool, les conférences planifiées, etc.</span><span class="sxs-lookup"><span data-stu-id="85cb6-149">User rights, user Contacts lists, server or pool data, scheduled conferences, and so on.</span></span> <span data-ttu-id="85cb6-150">Ces données utilisateur n’incluent pas le contenu téléchargé vers une conférence.</span><span class="sxs-lookup"><span data-stu-id="85cb6-150">This user data does not include content uploaded to a conference.</span></span></p>
<p><span data-ttu-id="85cb6-151">Sauvegardez vos sauvegardes régulières.</span><span class="sxs-lookup"><span data-stu-id="85cb6-151">Back up with your regular backups.</span></span> <span data-ttu-id="85cb6-152">Ces informations sont dynamiques, mais la perte de mises à jour n’est pas catastrophique pour Lync Server si vous devez effectuer une restauration à votre dernière sauvegarde régulière.</span><span class="sxs-lookup"><span data-stu-id="85cb6-152">This information is dynamic, but the loss of updates is not catastrophic to Lync Server if you need to restore to your last regular backup.</span></span> <span data-ttu-id="85cb6-153">Si les listes de contacts sont essentielles à votre organisation, vous pouvez sauvegarder ces données plus fréquemment.</span><span class="sxs-lookup"><span data-stu-id="85cb6-153">If Contacts lists are critical to your organization, you can back up this data more frequently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85cb6-154">Données d’archivage</span><span class="sxs-lookup"><span data-stu-id="85cb6-154">Archiving data</span></span></p></td>
<td><p><span data-ttu-id="85cb6-155">Base de données d’archivage (base de données : LcsLog. mdf)</span><span class="sxs-lookup"><span data-stu-id="85cb6-155">Archiving database (database: LcsLog.mdf)</span></span></p>
<p><span data-ttu-id="85cb6-156">Ces données peuvent être stockées sur Exchange 2013, si vous avez activé l’option d’intégration de Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="85cb6-156">This data may be stored on Exchange 2013, if you have enabled the Microsoft Exchange integration option.</span></span> <span data-ttu-id="85cb6-157">Dans le cas contraire, ces données sont conservées dans une base de données d’archivage Lync Server, qui peut être colocalisée avec une autre base de données Lync Server ou autonome sur un serveur de base de données distinct.</span><span class="sxs-lookup"><span data-stu-id="85cb6-157">Otherwise, this data is kept in a Lync Server Archiving database, which may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="85cb6-158">Messagerie instantanée et contenu de la réunion.</span><span class="sxs-lookup"><span data-stu-id="85cb6-158">Instant messaging (IM) and meeting content.</span></span></p>
<p><span data-ttu-id="85cb6-159">Ces données ne sont pas essentielles à Lync Server, mais elles peuvent être critiques pour votre organisation à des fins de réglementation.</span><span class="sxs-lookup"><span data-stu-id="85cb6-159">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="85cb6-160">Déterminez votre planification de sauvegarde en conséquence.</span><span class="sxs-lookup"><span data-stu-id="85cb6-160">Determine your back up schedule accordingly.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85cb6-161">Données de surveillance</span><span class="sxs-lookup"><span data-stu-id="85cb6-161">Monitoring data</span></span></p></td>
<td><p><span data-ttu-id="85cb6-162">Bases de données de surveillance (LcsCDR. mdf et QoeMetrics. mdf)</span><span class="sxs-lookup"><span data-stu-id="85cb6-162">Monitoring databases (LcsCDR.mdf and QoeMetrics.mdf)</span></span></p>
<p><span data-ttu-id="85cb6-163">Ces bases de données peuvent être colocalisées avec une autre base de données Lync Server ou autonome sur un serveur de base de données distinct.</span><span class="sxs-lookup"><span data-stu-id="85cb6-163">These databases may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="85cb6-164">Enregistrements des détails des appels (LcsCDR. mdf) et mesures de qualité de l’expérience (QoE) (QoeMetrics. mdf).</span><span class="sxs-lookup"><span data-stu-id="85cb6-164">Call detail records (LcsCDR.mdf) and Quality of Experience (QoE) metrics (QoeMetrics.mdf).</span></span></p>
<p><span data-ttu-id="85cb6-165">Les enregistrements des détails des appels sont dynamiques et peuvent être essentiels à votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="85cb6-165">Call detail records are dynamic and may be critical to your business.</span></span> <span data-ttu-id="85cb6-166">Déterminez votre planning de sauvegarde en prenant en compte si vous avez besoin de ces enregistrements pour des raisons de réglementation.</span><span class="sxs-lookup"><span data-stu-id="85cb6-166">Determine your back up schedule by considering whether you need these records for regulatory reasons.</span></span></p>
<p><span data-ttu-id="85cb6-167">Les informations sur la qualité de l’expérience sont dynamiques.</span><span class="sxs-lookup"><span data-stu-id="85cb6-167">Quality of experience information is dynamic.</span></span> <span data-ttu-id="85cb6-168">La perte de données QoE n’est pas essentielle pour le fonctionnement de Lync Server, mais elle peut être cruciale pour votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="85cb6-168">Loss of QoE data is not critical for the operation of Lync Server, but it may be critical to your business.</span></span> <span data-ttu-id="85cb6-169">Déterminez votre planning de sauvegarde en fonction de l’importance de ces informations pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="85cb6-169">Determine your back up schedule based on how critical this information is to your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85cb6-170">Données de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="85cb6-170">Persistent Chat data</span></span></p></td>
<td><p><span data-ttu-id="85cb6-171">Base de données de conversation permanente (gérées. mdf).</span><span class="sxs-lookup"><span data-stu-id="85cb6-171">Persistent Chat database (mgd.mdf).</span></span></p>
<p><span data-ttu-id="85cb6-172">Cette base de données peut être colocalisée avec une autre base de données Lync Server ou autonome sur un serveur de base de données distinct.</span><span class="sxs-lookup"><span data-stu-id="85cb6-172">This database may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="85cb6-173">Les données de conversation permanente sont le contenu de conversation réel publié dans les salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="85cb6-173">Persistent Chat Data is actual chat content being posted in chat rooms.</span></span> <span data-ttu-id="85cb6-174">Ces données sont souvent essentielles à l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="85cb6-174">This data is often business critical.</span></span></p>
<p><span data-ttu-id="85cb6-175">Vous pouvez choisir d’utiliser la sauvegarde SQL Server ou exporter la base de données à l’aide de la cmdlet <strong>Export-applet cspersistentchatdata</strong> fournie dans Lync Server.</span><span class="sxs-lookup"><span data-stu-id="85cb6-175">You can choose to use SQL Server backup, or export the database by using the <strong>Export-CsPersistentChatData</strong> cmdlet that is provided in Lync Server.</span></span> <span data-ttu-id="85cb6-176">Pour la récupération des données, vous pouvez importer et restaurer la base de données au point de la dernière sauvegarde complète, ce qui signifie que vous ne pouvez pas restaurer la base de données au point de défaillance.</span><span class="sxs-lookup"><span data-stu-id="85cb6-176">For recovery of the data, you can import and restore the database to the point of the last full backup, which means you cannot restore the database to the point of failure.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a><span data-ttu-id="85cb6-177">Exigences relatives aux données du magasin de fichiers</span><span class="sxs-lookup"><span data-stu-id="85cb6-177">File Store Data Requirements</span></span>

<span data-ttu-id="85cb6-178">Dans un déploiement Enterprise Edition, le magasin de fichiers Lync Server se trouve généralement sur un serveur de fichiers.</span><span class="sxs-lookup"><span data-stu-id="85cb6-178">In an Enterprise Edition deployment, the Lync Server file store is typically located on a file server.</span></span> <span data-ttu-id="85cb6-179">Dans un déploiement Standard Edition, le magasin de fichiers Lync Server se trouve par défaut sur le serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="85cb6-179">In a Standard Edition deployment, the Lync Server file store is located by default on the Standard Edition server.</span></span> <span data-ttu-id="85cb6-180">En règle générale, il existe un magasin de fichiers Lync Server partagé pour un site.</span><span class="sxs-lookup"><span data-stu-id="85cb6-180">Typically, there is one Lync Server file store that is shared for a site.</span></span> <span data-ttu-id="85cb6-181">Le magasin de fichiers de conversation permanente utilise le même partage de fichiers que le magasin de fichiers Lync Server.</span><span class="sxs-lookup"><span data-stu-id="85cb6-181">The Persistent Chat file store uses the same file share as the Lync Server file store.</span></span>

<span data-ttu-id="85cb6-182">Les emplacements de magasin de fichiers sont identifiés comme \\ \\ nom de partage du serveur \\ .</span><span class="sxs-lookup"><span data-stu-id="85cb6-182">File store locations are identified as \\\\server\\share name.</span></span> <span data-ttu-id="85cb6-183">Pour rechercher les emplacements spécifiques de vos magasins de fichiers, ouvrez le générateur de topologies et regardez dans le nœud **magasins de fichiers** .</span><span class="sxs-lookup"><span data-stu-id="85cb6-183">To find the specific locations of your file stores, open Topology Builder and look in the **File stores** node.</span></span>

<span data-ttu-id="85cb6-184">Le tableau suivant identifie les magasins de fichiers que vous devez sauvegarder et restaurer.</span><span class="sxs-lookup"><span data-stu-id="85cb6-184">The following table identifies the file stores you need to back up and restore.</span></span>

### <a name="file-stores"></a><span data-ttu-id="85cb6-185">Magasins de fichiers</span><span class="sxs-lookup"><span data-stu-id="85cb6-185">File Stores</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85cb6-186">DataType</span><span class="sxs-lookup"><span data-stu-id="85cb6-186">Type of data</span></span></th>
<th><span data-ttu-id="85cb6-187">Emplacement de stockage</span><span class="sxs-lookup"><span data-stu-id="85cb6-187">Where stored</span></span></th>
<th><span data-ttu-id="85cb6-188">Description/quand sauvegarder</span><span class="sxs-lookup"><span data-stu-id="85cb6-188">Description / when to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85cb6-189">Magasin de fichiers Lync Server</span><span class="sxs-lookup"><span data-stu-id="85cb6-189">Lync Server file store</span></span></p></td>
<td><p><span data-ttu-id="85cb6-190">Généralement sur un serveur de fichiers, un cluster de fichiers ou un serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="85cb6-190">Typically on a file server, file cluster, or a Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="85cb6-191">Contenu de réunion, métadonnées de contenu de réunion, journaux de conformité de réunion, fichiers de données d’application, fichiers de mise à jour pour les mises à jour de périphériques, fichiers audio pour les groupes Response Group, parcage d’appel et applications d’annonce, et fichiers publiés dans les salles de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="85cb6-191">Meeting content, meeting content metadata, meeting compliance logs, application data files, update files for device updates, audio files for Response Group, Call Park, and Announcement applications, and files posted into Persistent Chat rooms.</span></span></p>
<p><span data-ttu-id="85cb6-192">Sauvegardez vos sauvegardes régulières.</span><span class="sxs-lookup"><span data-stu-id="85cb6-192">Back up with your regular backups.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a><span data-ttu-id="85cb6-193">Autres exigences de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="85cb6-193">Additional Backup Requirements</span></span>

<span data-ttu-id="85cb6-194">Pour vous aider à restaurer les services Lync Server en cas de panne, vous devez sauvegarder les composants nécessaires qui ne font pas partie de Lync Server lui-même.</span><span class="sxs-lookup"><span data-stu-id="85cb6-194">To help ensure your ability to restore Lync Server services in the event of a failure, you must back up some necessary components that are not part of Lync Server itself.</span></span> <span data-ttu-id="85cb6-195">Les composants suivants ne sont pas sauvegardés ni restaurés dans le cadre du processus de sauvegarde et de restauration de Lync Server décrit dans ce document :</span><span class="sxs-lookup"><span data-stu-id="85cb6-195">The following components are not backed up or restored as part of the Lync Server backup and restoration process described in this document:</span></span>

  - <span data-ttu-id="85cb6-196">Services de domaine **Active Directory**     Vous devez sauvegarder AD DS à l’aide des outils Active Directory en même temps que Lync Server.</span><span class="sxs-lookup"><span data-stu-id="85cb6-196">**Active Directory Domain Services**   You need to back up AD DS by using Active Directory tools at the same time that you back up Lync Server.</span></span> <span data-ttu-id="85cb6-197">Il est important de maintenir AD DS synchronisé avec Lync Server, afin d’éviter les problèmes qui peuvent se produire lorsque Lync Server attend des objets contact qui ne correspondent pas à ceux dans AD DS.</span><span class="sxs-lookup"><span data-stu-id="85cb6-197">It is important to keep AD DS synchronized with Lync Server, to avoid problems that can occur when Lync Server expects contact objects that do not match those in AD DS.</span></span> <span data-ttu-id="85cb6-198">AD DS stocke les paramètres suivants utilisés par Lync Server :</span><span class="sxs-lookup"><span data-stu-id="85cb6-198">AD DS stores the following settings which are used by Lync Server:</span></span>
    
      - <span data-ttu-id="85cb6-199">URI SIP de l’utilisateur et autres paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="85cb6-199">User SIP URI and other user settings.</span></span>
    
      - <span data-ttu-id="85cb6-200">Objets contact pour les applications telles que Response Group et le service de conférence.</span><span class="sxs-lookup"><span data-stu-id="85cb6-200">Contact objects for applications such as Response Group and Conferencing Attendant.</span></span>
    
      - <span data-ttu-id="85cb6-201">Pointeur vers le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="85cb6-201">A pointer to the Central Management Store.</span></span>
    
      - <span data-ttu-id="85cb6-202">Le compte d’authentification Kerberos (un objet ordinateur facultatif) et les groupes de sécurité Lync Server.</span><span class="sxs-lookup"><span data-stu-id="85cb6-202">Kerberos Authentication Account (an optional computer object) and Lync Server security groups.</span></span>
    
    <span data-ttu-id="85cb6-203">Pour plus d’informations sur la sauvegarde et la restauration des services AD DS dans Windows Server 2008, voir « Guide pas à pas de la sauvegarde et de la récupération AD DS » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105) .</span><span class="sxs-lookup"><span data-stu-id="85cb6-203">For details about backing up and restoring AD DS in Windows Server 2008, see "AD DS Backup and Recovery Step-by-Step Guide" at [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105).</span></span>

  - <span data-ttu-id="85cb6-204">**Autorité de certification et certificats**     Utilisez la stratégie de votre organisation pour sauvegarder votre autorité de certification (CA) et vos certificats.</span><span class="sxs-lookup"><span data-stu-id="85cb6-204">**Certification authority and certificates**   Use your organization's policy for backing up your certification authority (CA) and certificates.</span></span> <span data-ttu-id="85cb6-205">Si vous utilisez des clés privées exportables, vous pouvez sauvegarder le certificat et la clé privée, puis les exporter si vous utilisez les procédures décrites dans ce document pour restaurer Lync Server.</span><span class="sxs-lookup"><span data-stu-id="85cb6-205">If you use exportable private keys, you can back up the certificate and the private key, and then export them if you use the procedures in this document to restore Lync Server.</span></span> <span data-ttu-id="85cb6-206">Si vous utilisez une autorité de certification interne, vous pouvez réinscrire si vous avez besoin de restaurer Lync Server.</span><span class="sxs-lookup"><span data-stu-id="85cb6-206">If you use an internal CA, you can re-enroll if you need to restore Lync Server.</span></span> <span data-ttu-id="85cb6-207">Il est important de conserver la clé privée dans un endroit sûr où elle sera disponible en cas de défaillance d’un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="85cb6-207">It is important that you retain the private key in a secure location where it will be available if a computer fails.</span></span>

  - <span data-ttu-id="85cb6-208">**System Center Operations Manager**     Si vous utilisez Microsoft System Center Operations Manager (anciennement Microsoft Operations Manager) pour surveiller votre déploiement Lync Server, vous pouvez sauvegarder les données qu’il crée pendant qu’il analyse Lync Server.</span><span class="sxs-lookup"><span data-stu-id="85cb6-208">**System Center Operations Manager**   If you use Microsoft System Center Operations Manager (formerly Microsoft Operations Manager) to monitor your Lync Server deployment, you can optionally back up the data it creates while it is monitoring Lync Server.</span></span> <span data-ttu-id="85cb6-209">Utilisez votre processus de sauvegarde SQL Server standard pour sauvegarder les fichiers System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="85cb6-209">Use your standard SQL Server backup process to back up System Center Operations Manager files.</span></span> <span data-ttu-id="85cb6-210">Ces fichiers ne sont pas restaurés lors de la récupération.</span><span class="sxs-lookup"><span data-stu-id="85cb6-210">These files are not restored during recovery.</span></span>

  - <span data-ttu-id="85cb6-211">Configuration de la **passerelle PSTN (réseau téléphonique commuté)**     Si vous utilisez des appliances voix entreprise ou Survivable Branch Appliances, vous devez sauvegarder la configuration de la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="85cb6-211">**Public switched telephone network (PSTN) gateway configuration**   If you use Enterprise Voice or Survivable Branch Appliances, you need to back up the PSTN gateway configuration.</span></span> <span data-ttu-id="85cb6-212">Pour plus d’informations sur la sauvegarde et la restauration des configurations de passerelle PSTN, consultez votre fournisseur.</span><span class="sxs-lookup"><span data-stu-id="85cb6-212">See your vendor for details about backing up and restoring PSTN gateway configurations.</span></span>

  - <span data-ttu-id="85cb6-213">**Versions coexistantes de Lync Server ou Office Communications Server**     Si votre déploiement Lync Server 2013 coexiste avec Lync Server 2010 ou une version antérieure d’Office Communications Server, vous ne pouvez pas utiliser les procédures décrites dans ce document pour sauvegarder ou restaurer la version antérieure.</span><span class="sxs-lookup"><span data-stu-id="85cb6-213">**Coexisting versions of Lync Server or Office Communications Server**   If your Lync Server 2013 deployment coexists with Lync Server 2010 or an earlier version of Office Communications Server, you can’t use the procedures in this document for backing up or restoring the earlier version.</span></span> <span data-ttu-id="85cb6-214">Au lieu de cela, vous devez utiliser les procédures de sauvegarde et de restauration documentées spécifiquement pour votre version précédente.</span><span class="sxs-lookup"><span data-stu-id="85cb6-214">Instead, you must use the backup and restoration procedures documented specifically for your earlier version.</span></span> <span data-ttu-id="85cb6-215">Pour plus d’informations sur la sauvegarde et la restauration de Lync Server 2010, reportez-vous à la rubrique [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) .</span><span class="sxs-lookup"><span data-stu-id="85cb6-215">For details about backing up and restoring Lync Server 2010, see [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) .</span></span> <span data-ttu-id="85cb6-216">Pour plus d’informations sur la sauvegarde et la restauration de Microsoft Office Communications Server 2007 R2, reportez-vous à la rubrique [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162) .</span><span class="sxs-lookup"><span data-stu-id="85cb6-216">For details about backing up and restoring Microsoft Office Communications Server 2007 R2, see [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162).</span></span>

  - <span data-ttu-id="85cb6-217">**Informations sur**     l’infrastructure Vous devez sauvegarder les informations relatives à votre infrastructure, telles que la configuration de votre pare-feu, la configuration de l’équilibrage de charge, la configuration des services Internet (IIS), les enregistrements DNS (Domain Name System) et les adresses IP, ainsi que la configuration du protocole DHCP (Dynamic Host Configuration Protocol).</span><span class="sxs-lookup"><span data-stu-id="85cb6-217">**Infrastructure information**   You need to back up information about your infrastructure, such as your firewall configuration, load balancing configuration, Internet Information Services (IIS) configuration, Domain Name System (DNS) records and IP addresses, and Dynamic Host Configuration Protocol (DHCP) configuration.</span></span> <span data-ttu-id="85cb6-218">Pour plus d’informations sur la sauvegarde de ces composants, consultez leur fournisseur respectif.</span><span class="sxs-lookup"><span data-stu-id="85cb6-218">For details about backing up these components, check with their respective vendors.</span></span>

  - <span data-ttu-id="85cb6-219">**Microsoft Exchange et messagerie unifiée Exchange (MU)**     Sauvegarde et restauration de Microsoft Exchange et de la messagerie unifiée Exchange, comme décrit dans la documentation de Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="85cb6-219">**Microsoft Exchange and Exchange Unified Messaging (UM)**   Backup and restore Microsoft Exchange and Exchange UM as described in the Microsoft Exchange documentation.</span></span> <span data-ttu-id="85cb6-220">Pour plus d’informations sur la sauvegarde et la restauration d’Exchange Server 2013, voir [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384) .</span><span class="sxs-lookup"><span data-stu-id="85cb6-220">For details about backing up and restoring Exchange Server 2013, see [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384).</span></span> <span data-ttu-id="85cb6-221">Pour plus d’informations sur la sauvegarde et la restauration d’Exchange Server 2010, voir [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179) .</span><span class="sxs-lookup"><span data-stu-id="85cb6-221">For details about backing up and restoring Exchange Server 2010, see [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179).</span></span>
    
    <span data-ttu-id="85cb6-222">Notez que Lync Server 2013 offre la possibilité de faire en sorte que les listes de contacts de l’utilisateur, les photos des utilisateurs à haute définition et les données d’archivage soient stockées dans Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="85cb6-222">Note that Lync Server 2013 introduces the ability to have user contact lists, high definition user photos, and archiving data stored in Exchange 2013.</span></span> <span data-ttu-id="85cb6-223">Consultez la liste suivante pour savoir comment sauvegarder ces types de données :</span><span class="sxs-lookup"><span data-stu-id="85cb6-223">See the following list to see how to back up these types of data:</span></span>
    
      - <span data-ttu-id="85cb6-224">Les **photos haute définition** sont sauvegardées dans le cadre de la sauvegarde Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="85cb6-224">**High definition photos** are backed up as part of the Exchange Server backup.</span></span>
    
      - <span data-ttu-id="85cb6-225">Le **magasin de contacts unifié** est présenté dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85cb6-225">**Unified contact store** is introduced in Lync Server 2013.</span></span> <span data-ttu-id="85cb6-226">Magasin de contacts unifié permet aux utilisateurs de conserver toutes leurs informations de contact dans Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="85cb6-226">Unified contact store enables users to keep all their contact information in Exchange 2013.</span></span>
        
        <span data-ttu-id="85cb6-227">Vous devez vous assurer que les sauvegardes sont à jour pour les utilisateurs en ce qui concerne le stockage de leurs contacts dans le magasin de contacts unifié ou sur le serveur principal Lync.</span><span class="sxs-lookup"><span data-stu-id="85cb6-227">You should make sure that backups are up-to-date for users in terms of whether their user contacts are stored in the unified contact store or on the Lync Back End Server.</span></span> <span data-ttu-id="85cb6-228">Les scénarios suivants montrent où la migration des contacts de l’utilisateur vers le magasin de contacts unifié peut entraîner des problèmes pour le processus de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="85cb6-228">The following scenarios illustrate where migrating user contacts to the unified contact store can cause issues for the backup and restore process.</span></span>
        
        <span data-ttu-id="85cb6-229">**Scénario 1 :** Les contacts de l’utilisateur sont migrés vers le magasin de contacts unifié et une restauration est effectuée à partir d’une sauvegarde Lync Server effectuée avant la migration des contacts de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="85cb6-229">**Scenario 1:** User contacts are migrated to the unified contact store, and a restore is performed from a Lync Server backup taken prior to the migration of user contacts.</span></span> <span data-ttu-id="85cb6-230">Dans ce scénario, l’utilisateur aura un état de contacts obsolètes jusqu’à un jour jusqu’à ce que la tâche de migration Lync Server commence à migrer les contacts de l’utilisateur vers Exchange.</span><span class="sxs-lookup"><span data-stu-id="85cb6-230">In this scenario, the user will have a state of outdated contacts for up to one day until Lync Server Migration Task begins migrating user contacts to Exchange.</span></span> <span data-ttu-id="85cb6-231">(Notez que, étant donné que les contacts utilisateur ont déjà été migrés vers le magasin de contacts unifié, les informations de contact Exchange seront utilisées).</span><span class="sxs-lookup"><span data-stu-id="85cb6-231">(Note that because the user contacts were previously migrated to the unified contact store, the Exchange contact information will be used).</span></span> <span data-ttu-id="85cb6-232">Aucune intervention de l’administrateur n’est nécessaire dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="85cb6-232">No administrator intervention is needed in this scenario.</span></span>
        
        <span data-ttu-id="85cb6-233">**Scénario 2 :** Les contacts utilisateur étaient précédemment stockés dans le magasin de contacts unifié, puis annulés.</span><span class="sxs-lookup"><span data-stu-id="85cb6-233">**Scenario 2:** User contacts were previously stored in the unified contact store, but then rolled back.</span></span> <span data-ttu-id="85cb6-234">Une restauration est effectuée à partir d’une sauvegarde Lync Server effectuée lorsque les contacts de l’utilisateur ont été stockés dans le magasin de contacts unifié.</span><span class="sxs-lookup"><span data-stu-id="85cb6-234">A restore is performed from a Lync Server backup taken when the user contacts were stored in the unified contact store.</span></span> <span data-ttu-id="85cb6-235">Dans ce scénario, un message d’erreur de `Error: Incorrect Exchange Version` dans les journaux du client ou du serveur Lyss peut indiquer qu’il s’agit d’un problème.</span><span class="sxs-lookup"><span data-stu-id="85cb6-235">In this scenario, an error message of `Error: Incorrect Exchange Version` in the client or Lyss server logs may indicate this as an issue.</span></span> <span data-ttu-id="85cb6-236">L’utilisateur pourra accéder à sa liste de contacts dans Lync 2013 directement à partir d’Exchange, mais l’état du client ne correspondra pas à l’état du serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="85cb6-236">The user will be able to access their contact list in Lync 2013 directly from Exchange, but client’s state will not match the Lync Server state.</span></span> <span data-ttu-id="85cb6-237">Pour résoudre ce problème, un administrateur doit exécuter les applets de commande **Invoke-CsUCSRollback** pour les utilisateurs concernés.</span><span class="sxs-lookup"><span data-stu-id="85cb6-237">To fix this, an administrator will need to run the **Invoke-CsUCSRollback** cmdlets for the affected users.</span></span>
    
      - <span data-ttu-id="85cb6-238">Les **données d’archivage** peuvent être stockées dans Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="85cb6-238">**Archiving Data** can be stored in Exchange 2013.</span></span> <span data-ttu-id="85cb6-239">Ces données ne sont pas essentielles à Lync Server, mais elles peuvent être critiques pour votre organisation à des fins de réglementation.</span><span class="sxs-lookup"><span data-stu-id="85cb6-239">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="85cb6-240">Si les données d’archivage sont stockées dans Exchange et qu’elles sont essentielles pour votre organisation, suivez les procédures de sauvegarde et de restauration d’Exchange.</span><span class="sxs-lookup"><span data-stu-id="85cb6-240">If archiving data is stored in Exchange and is critical to your organization, then follow Exchange backup and restore procedures.</span></span> <span data-ttu-id="85cb6-241">Notez que les données d’archivage stockées dans Exchange ne peuvent pas être déplacées vers Lync Server.</span><span class="sxs-lookup"><span data-stu-id="85cb6-241">Note that archiving data stored in Exchange cannot be moved back to Lync Server.</span></span> <span data-ttu-id="85cb6-242">De plus, il n’existe aucun moyen de déplacer des données déjà stockées dans la base de données d’archivage Lync vers Exchange.</span><span class="sxs-lookup"><span data-stu-id="85cb6-242">Additionally, there is no way to move data already stored in the Lync archiving database to Exchange.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

