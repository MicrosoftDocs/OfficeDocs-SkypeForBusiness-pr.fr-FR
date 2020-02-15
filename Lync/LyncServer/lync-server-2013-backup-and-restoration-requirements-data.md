---
title: 'Lync Server 2013 : exigences en matière de sauvegarde et de restauration : données'
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
ms.openlocfilehash: 4688c143a16ffd7113a03172274436f7c1371694
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a><span data-ttu-id="a674a-102">Configuration requise pour la sauvegarde et la restauration dans Lync Server 2013 : données</span><span class="sxs-lookup"><span data-stu-id="a674a-102">Backup and restoration requirements in Lync Server 2013: data</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a674a-103">_**Dernière modification de la rubrique :** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="a674a-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="a674a-104">Lync Server utilise les paramètres et les informations de configuration stockés dans les bases de données, ainsi que les données stockées dans les bases de données et les magasins de fichiers.</span><span class="sxs-lookup"><span data-stu-id="a674a-104">Lync Server uses settings and configuration information that are stored in databases, and data that is stored in databases and file stores.</span></span> <span data-ttu-id="a674a-105">Cette rubrique décrit les données que vous devez sauvegarder pour pouvoir restaurer le service si votre organisation rencontre une défaillance ou une panne, et identifie également les données et les composants utilisés par Lync Server que vous devez sauvegarder séparément.</span><span class="sxs-lookup"><span data-stu-id="a674a-105">This topic describes the data that you need to back up to be able to restore service if your organization experiences a failure or outage, and also identifies the data and components used by Lync Server that you need to back up separately.</span></span>

<div>

## <a name="settings-and-configuration-requirements"></a><span data-ttu-id="a674a-106">Paramètres et configuration requis</span><span class="sxs-lookup"><span data-stu-id="a674a-106">Settings and Configuration Requirements</span></span>

<span data-ttu-id="a674a-107">Cette rubrique inclut des procédures de sauvegarde et de restauration des paramètres et des informations de configuration nécessaires pour la récupération du service Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a674a-107">This topic includes procedures for backing up and restoring the settings and configuration information that is required for recovery of Lync Server service.</span></span> <span data-ttu-id="a674a-108">Les informations de configuration se trouvent dans le magasin central de gestion ou sur une autre base de données principale ou sur un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="a674a-108">The configuration information is located in the Central Management store or on another back-end database or on Standard Edition server.</span></span>

<span data-ttu-id="a674a-109">Le tableau suivant identifie les paramètres et les informations de configuration que vous devez sauvegarder et restaurer.</span><span class="sxs-lookup"><span data-stu-id="a674a-109">The following table identifies the settings and configuration information that you need to back up and restore.</span></span>

### <a name="settings-and-configuration-data"></a><span data-ttu-id="a674a-110">Paramètres et données de configuration</span><span class="sxs-lookup"><span data-stu-id="a674a-110">Settings and Configuration Data</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a674a-111">DataType</span><span class="sxs-lookup"><span data-stu-id="a674a-111">Type of data</span></span></th>
<th><span data-ttu-id="a674a-112">Emplacement de stockage</span><span class="sxs-lookup"><span data-stu-id="a674a-112">Where stored</span></span></th>
<th><span data-ttu-id="a674a-113">Description/quand sauvegarder</span><span class="sxs-lookup"><span data-stu-id="a674a-113">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a674a-114">Informations de configuration de la topologie</span><span class="sxs-lookup"><span data-stu-id="a674a-114">Topology configuration information</span></span></p></td>
<td><p><span data-ttu-id="a674a-115">Magasin central de gestion (base de données : XDS. mdf)</span><span class="sxs-lookup"><span data-stu-id="a674a-115">Central Management store (database: Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="a674a-116">Paramètres de topologie, de stratégie et de configuration.</span><span class="sxs-lookup"><span data-stu-id="a674a-116">Topology, policy, and configuration settings.</span></span></p>
<p><span data-ttu-id="a674a-117">Sauvegardez vos sauvegardes régulières et une fois que vous avez utilisé le panneau de configuration ou les cmdlets Lync Server pour modifier votre configuration ou vos stratégies.</span><span class="sxs-lookup"><span data-stu-id="a674a-117">Back up with your regular backups and after you use Lync Server Control Panel or cmdlets to modify your configuration or policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a674a-118">Informations d’emplacement</span><span class="sxs-lookup"><span data-stu-id="a674a-118">Location information</span></span></p></td>
<td><p><span data-ttu-id="a674a-119">Magasin central de gestion (base de données : lis. mdf)</span><span class="sxs-lookup"><span data-stu-id="a674a-119">Central Management store (database: Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="a674a-120">Informations de configuration d’Enterprise Voice Enhanced 9-1-1 (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="a674a-120">Enterprise Voice Enhanced 9-1-1 (E9-1-1) configuration information.</span></span> <span data-ttu-id="a674a-121">Ces informations sont généralement statiques.</span><span class="sxs-lookup"><span data-stu-id="a674a-121">This information is generally static.</span></span></p>
<p><span data-ttu-id="a674a-122">Sauvegardez vos sauvegardes régulières.</span><span class="sxs-lookup"><span data-stu-id="a674a-122">Back up with your regular backups.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a674a-123">Informations de configuration du groupe Response Group</span><span class="sxs-lookup"><span data-stu-id="a674a-123">Response Group configuration information</span></span></p></td>
<td><p><span data-ttu-id="a674a-124">Serveur principal ou serveur Standard Edition (base de données : RgsConfig. mdf)</span><span class="sxs-lookup"><span data-stu-id="a674a-124">Back End Server or Standard Edition server (database: RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="a674a-125">Groupes d’agents Response Group, files d’attente et flux de travail.</span><span class="sxs-lookup"><span data-stu-id="a674a-125">Response Group agent groups, queues, and workflows.</span></span></p>
<p><span data-ttu-id="a674a-126">Sauvegardez vos sauvegardes régulières et après avoir ajouté ou modifié des groupes d’agents, des files d’attente ou des flux de travail.</span><span class="sxs-lookup"><span data-stu-id="a674a-126">Back up with your regular backups and after you add or change agent groups, queues, or workflows.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a><span data-ttu-id="a674a-127">Données requises</span><span class="sxs-lookup"><span data-stu-id="a674a-127">Data Requirements</span></span>

<span data-ttu-id="a674a-128">Voici une liste des données Lync Server que vous devez sauvegarder afin de pouvoir restaurer le service Lync Server en cas de défaillance.</span><span class="sxs-lookup"><span data-stu-id="a674a-128">Here is a list of the Lync Server data that you need to back up so that you can restore Lync Server service in the event of a failure.</span></span>

<span data-ttu-id="a674a-129">Notez que certains types de données ne sont pas requis pour la récupération.</span><span class="sxs-lookup"><span data-stu-id="a674a-129">Note that some types of data are not required for recovery.</span></span> <span data-ttu-id="a674a-130">Cette rubrique ne contient pas les procédures de sauvegarde de ces types de données, notamment les suivantes :</span><span class="sxs-lookup"><span data-stu-id="a674a-130">This topic does not contain procedures for backing up these types of data, which include the following:</span></span>

  - <span data-ttu-id="a674a-131">Les données utilisateur temporaires, telles que les points de terminaison et les abonnements, les serveurs de conférence actifs et les États de conférence transitoires (base de données : RtcDyn. mdf)</span><span class="sxs-lookup"><span data-stu-id="a674a-131">Transient user data, such as endpoints and subscriptions, active conferencing servers, and transient conferencing states (database: RtcDyn.mdf)</span></span>

  - <span data-ttu-id="a674a-132">Données de carnet d’adresses (bases de données : RTCAb. mdf et Rtcab1. mdf).</span><span class="sxs-lookup"><span data-stu-id="a674a-132">Address Book data (databases: Rtcab.mdf and Rtcab1.mdf).</span></span> <span data-ttu-id="a674a-133">La base de données de carnet d’adresses est automatiquement régénérée à partir des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a674a-133">The Address Book database is regenerated automatically from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="a674a-134">Informations dynamiques pour l’application de parcage d’appel (base de données : CpsDyn. mdf)</span><span class="sxs-lookup"><span data-stu-id="a674a-134">Dynamic information for the Call Park application (database: CpsDyn.mdf)</span></span>

  - <span data-ttu-id="a674a-135">Données de groupe de réponse transitoires, telles que l’état de connexion de l’agent et les informations d’attente d’appel (base de données : RgsDyn. mdf)</span><span class="sxs-lookup"><span data-stu-id="a674a-135">Transient Response Group data, such as agent sign-in state and call waiting information (database: RgsDyn.mdf)</span></span>

  - <span data-ttu-id="a674a-136">La base de données de conformité pour la conversation permanente (base de données : MgcComp. mdf).</span><span class="sxs-lookup"><span data-stu-id="a674a-136">The compliance database for Persistent Chat (database: MgcComp.mdf).</span></span> <span data-ttu-id="a674a-137">Si la conformité de conversation permanente est activée, les informations contenues dans la base de données de conformité de conversation permanente sont transitoires tant que vous disposez d’un adaptateur configuré pour lire les informations de la base de données et les convertir dans un autre format.</span><span class="sxs-lookup"><span data-stu-id="a674a-137">If you have Persistent Chat compliance enabled, the information in the Persistent Chat Compliance database is transient as long as you have an adapter configured to read information from the database and convert it to an alternate format.</span></span> <span data-ttu-id="a674a-138">La base de données de conformité pour la conversation permanente est donc considérée comme transitoire.</span><span class="sxs-lookup"><span data-stu-id="a674a-138">Hence the compliance database for Persistent Chat is considered transient.</span></span>
    
    <span data-ttu-id="a674a-139">Lync Server 2013 le serveur de conversation permanente est fourni avec une carte XML.</span><span class="sxs-lookup"><span data-stu-id="a674a-139">Lync Server 2013 Persistent Chat Server ships with an XML adapter.</span></span> <span data-ttu-id="a674a-140">Vous pouvez également installer des adaptateurs personnalisés qui prennent ces données et les déplacer vers d’autres sources, telles que les archives hébergées sur Exchange.</span><span class="sxs-lookup"><span data-stu-id="a674a-140">You can also install custom adapters that take this data and move it to other sources, such as Exchange Hosted Archives.</span></span>

<span data-ttu-id="a674a-141">Le tableau suivant identifie les données que vous devez sauvegarder et restaurer.</span><span class="sxs-lookup"><span data-stu-id="a674a-141">The following table identifies the data that you need to back up and restore.</span></span>

### <a name="data-stored-in-databases"></a><span data-ttu-id="a674a-142">Données stockées dans des bases de données</span><span class="sxs-lookup"><span data-stu-id="a674a-142">Data Stored in Databases</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a674a-143">DataType</span><span class="sxs-lookup"><span data-stu-id="a674a-143">Type of data</span></span></th>
<th><span data-ttu-id="a674a-144">Emplacement de stockage</span><span class="sxs-lookup"><span data-stu-id="a674a-144">Where stored</span></span></th>
<th><span data-ttu-id="a674a-145">Description/quand sauvegarder</span><span class="sxs-lookup"><span data-stu-id="a674a-145">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a674a-146">Données utilisateur persistantes</span><span class="sxs-lookup"><span data-stu-id="a674a-146">Persistent user data</span></span></p></td>
<td><p><span data-ttu-id="a674a-147">Serveur principal ou serveur Standard Edition (base de données : RTCXDS. mdf)</span><span class="sxs-lookup"><span data-stu-id="a674a-147">Back End Server or Standard Edition server (database: RTCXDS.mdf)</span></span></p></td>
<td><p><span data-ttu-id="a674a-148">Les droits d’utilisateur, les listes de contacts des utilisateurs, les données du serveur ou du pool, les conférences planifiées, etc.</span><span class="sxs-lookup"><span data-stu-id="a674a-148">User rights, user Contacts lists, server or pool data, scheduled conferences, and so on.</span></span> <span data-ttu-id="a674a-149">Ces données utilisateur n’incluent pas le contenu téléchargé vers une conférence.</span><span class="sxs-lookup"><span data-stu-id="a674a-149">This user data does not include content uploaded to a conference.</span></span></p>
<p><span data-ttu-id="a674a-150">Sauvegardez vos sauvegardes régulières.</span><span class="sxs-lookup"><span data-stu-id="a674a-150">Back up with your regular backups.</span></span> <span data-ttu-id="a674a-151">Ces informations sont dynamiques, mais la perte de mises à jour n’est pas catastrophique pour Lync Server si vous devez effectuer une restauration à votre dernière sauvegarde régulière.</span><span class="sxs-lookup"><span data-stu-id="a674a-151">This information is dynamic, but the loss of updates is not catastrophic to Lync Server if you need to restore to your last regular backup.</span></span> <span data-ttu-id="a674a-152">Si les listes de contacts sont essentielles à votre organisation, vous pouvez sauvegarder ces données plus fréquemment.</span><span class="sxs-lookup"><span data-stu-id="a674a-152">If Contacts lists are critical to your organization, you can back up this data more frequently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a674a-153">Données d’archivage</span><span class="sxs-lookup"><span data-stu-id="a674a-153">Archiving data</span></span></p></td>
<td><p><span data-ttu-id="a674a-154">Base de données d’archivage (base de données : LcsLog. mdf)</span><span class="sxs-lookup"><span data-stu-id="a674a-154">Archiving database (database: LcsLog.mdf)</span></span></p>
<p><span data-ttu-id="a674a-155">Ces données peuvent être stockées sur Exchange 2013, si vous avez activé l’option d’intégration de Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="a674a-155">This data may be stored on Exchange 2013, if you have enabled the Microsoft Exchange integration option.</span></span> <span data-ttu-id="a674a-156">Dans le cas contraire, ces données sont conservées dans une base de données d’archivage Lync Server, qui peut être colocalisée avec une autre base de données Lync Server ou autonome sur un serveur de base de données distinct.</span><span class="sxs-lookup"><span data-stu-id="a674a-156">Otherwise, this data is kept in a Lync Server Archiving database, which may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="a674a-157">Messagerie instantanée et contenu de la réunion.</span><span class="sxs-lookup"><span data-stu-id="a674a-157">Instant messaging (IM) and meeting content.</span></span></p>
<p><span data-ttu-id="a674a-158">Ces données ne sont pas essentielles à Lync Server, mais elles peuvent être critiques pour votre organisation à des fins de réglementation.</span><span class="sxs-lookup"><span data-stu-id="a674a-158">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="a674a-159">Déterminez votre planification de sauvegarde en conséquence.</span><span class="sxs-lookup"><span data-stu-id="a674a-159">Determine your back up schedule accordingly.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a674a-160">Données de surveillance</span><span class="sxs-lookup"><span data-stu-id="a674a-160">Monitoring data</span></span></p></td>
<td><p><span data-ttu-id="a674a-161">Bases de données de surveillance (LcsCDR. mdf et QoeMetrics. mdf)</span><span class="sxs-lookup"><span data-stu-id="a674a-161">Monitoring databases (LcsCDR.mdf and QoeMetrics.mdf)</span></span></p>
<p><span data-ttu-id="a674a-162">Ces bases de données peuvent être colocalisées avec une autre base de données Lync Server ou autonome sur un serveur de base de données distinct.</span><span class="sxs-lookup"><span data-stu-id="a674a-162">These databases may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="a674a-163">Enregistrements des détails des appels (LcsCDR. mdf) et mesures de qualité de l’expérience (QoE) (QoeMetrics. mdf).</span><span class="sxs-lookup"><span data-stu-id="a674a-163">Call detail records (LcsCDR.mdf) and Quality of Experience (QoE) metrics (QoeMetrics.mdf).</span></span></p>
<p><span data-ttu-id="a674a-164">Les enregistrements des détails des appels sont dynamiques et peuvent être essentiels à votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="a674a-164">Call detail records are dynamic and may be critical to your business.</span></span> <span data-ttu-id="a674a-165">Déterminez votre planning de sauvegarde en prenant en compte si vous avez besoin de ces enregistrements pour des raisons de réglementation.</span><span class="sxs-lookup"><span data-stu-id="a674a-165">Determine your back up schedule by considering whether you need these records for regulatory reasons.</span></span></p>
<p><span data-ttu-id="a674a-166">Les informations sur la qualité de l’expérience sont dynamiques.</span><span class="sxs-lookup"><span data-stu-id="a674a-166">Quality of experience information is dynamic.</span></span> <span data-ttu-id="a674a-167">La perte de données QoE n’est pas essentielle pour le fonctionnement de Lync Server, mais elle peut être cruciale pour votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="a674a-167">Loss of QoE data is not critical for the operation of Lync Server, but it may be critical to your business.</span></span> <span data-ttu-id="a674a-168">Déterminez votre planning de sauvegarde en fonction de l’importance de ces informations pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a674a-168">Determine your back up schedule based on how critical this information is to your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a674a-169">Données de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="a674a-169">Persistent Chat data</span></span></p></td>
<td><p><span data-ttu-id="a674a-170">Base de données de conversation permanente (gérées. mdf).</span><span class="sxs-lookup"><span data-stu-id="a674a-170">Persistent Chat database (mgd.mdf).</span></span></p>
<p><span data-ttu-id="a674a-171">Cette base de données peut être colocalisée avec une autre base de données Lync Server ou autonome sur un serveur de base de données distinct.</span><span class="sxs-lookup"><span data-stu-id="a674a-171">This database may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="a674a-172">Les données de conversation permanente sont le contenu de conversation réel publié dans les salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="a674a-172">Persistent Chat Data is actual chat content being posted in chat rooms.</span></span> <span data-ttu-id="a674a-173">Ces données sont souvent essentielles à l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="a674a-173">This data is often business critical.</span></span></p>
<p><span data-ttu-id="a674a-174">Vous pouvez choisir d’utiliser la sauvegarde SQL Server ou exporter la base de données à l’aide de la cmdlet <strong>Export-applet cspersistentchatdata</strong> fournie dans Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a674a-174">You can choose to use SQL Server backup, or export the database by using the <strong>Export-CsPersistentChatData</strong> cmdlet that is provided in Lync Server.</span></span> <span data-ttu-id="a674a-175">Pour la récupération des données, vous pouvez importer et restaurer la base de données au point de la dernière sauvegarde complète, ce qui signifie que vous ne pouvez pas restaurer la base de données au point de défaillance.</span><span class="sxs-lookup"><span data-stu-id="a674a-175">For recovery of the data, you can import and restore the database to the point of the last full backup, which means you cannot restore the database to the point of failure.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a><span data-ttu-id="a674a-176">Exigences relatives aux données du magasin de fichiers</span><span class="sxs-lookup"><span data-stu-id="a674a-176">File Store Data Requirements</span></span>

<span data-ttu-id="a674a-177">Dans un déploiement Enterprise Edition, le magasin de fichiers Lync Server se trouve généralement sur un serveur de fichiers.</span><span class="sxs-lookup"><span data-stu-id="a674a-177">In an Enterprise Edition deployment, the Lync Server file store is typically located on a file server.</span></span> <span data-ttu-id="a674a-178">Dans un déploiement Standard Edition, le magasin de fichiers Lync Server se trouve par défaut sur le serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a674a-178">In a Standard Edition deployment, the Lync Server file store is located by default on the Standard Edition server.</span></span> <span data-ttu-id="a674a-179">En règle générale, il existe un magasin de fichiers Lync Server partagé pour un site.</span><span class="sxs-lookup"><span data-stu-id="a674a-179">Typically, there is one Lync Server file store that is shared for a site.</span></span> <span data-ttu-id="a674a-180">Le magasin de fichiers de conversation permanente utilise le même partage de fichiers que le magasin de fichiers Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a674a-180">The Persistent Chat file store uses the same file share as the Lync Server file store.</span></span>

<span data-ttu-id="a674a-181">Les emplacements de magasin de fichiers \\ \\sont\\identifiés comme nom de partage du serveur.</span><span class="sxs-lookup"><span data-stu-id="a674a-181">File store locations are identified as \\\\server\\share name.</span></span> <span data-ttu-id="a674a-182">Pour rechercher les emplacements spécifiques de vos magasins de fichiers, ouvrez le générateur de topologies et regardez dans le nœud **magasins de fichiers** .</span><span class="sxs-lookup"><span data-stu-id="a674a-182">To find the specific locations of your file stores, open Topology Builder and look in the **File stores** node.</span></span>

<span data-ttu-id="a674a-183">Le tableau suivant identifie les magasins de fichiers que vous devez sauvegarder et restaurer.</span><span class="sxs-lookup"><span data-stu-id="a674a-183">The following table identifies the file stores you need to back up and restore.</span></span>

### <a name="file-stores"></a><span data-ttu-id="a674a-184">Magasins de fichiers</span><span class="sxs-lookup"><span data-stu-id="a674a-184">File Stores</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a674a-185">DataType</span><span class="sxs-lookup"><span data-stu-id="a674a-185">Type of data</span></span></th>
<th><span data-ttu-id="a674a-186">Emplacement de stockage</span><span class="sxs-lookup"><span data-stu-id="a674a-186">Where stored</span></span></th>
<th><span data-ttu-id="a674a-187">Description/quand sauvegarder</span><span class="sxs-lookup"><span data-stu-id="a674a-187">Description / when to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a674a-188">Magasin de fichiers Lync Server</span><span class="sxs-lookup"><span data-stu-id="a674a-188">Lync Server file store</span></span></p></td>
<td><p><span data-ttu-id="a674a-189">Généralement sur un serveur de fichiers, un cluster de fichiers ou un serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="a674a-189">Typically on a file server, file cluster, or a Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="a674a-190">Contenu de réunion, métadonnées de contenu de réunion, journaux de conformité de réunion, fichiers de données d’application, fichiers de mise à jour pour les mises à jour de périphériques, fichiers audio pour les groupes Response Group, parcage d’appel et applications d’annonce, et fichiers publiés dans les salles de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="a674a-190">Meeting content, meeting content metadata, meeting compliance logs, application data files, update files for device updates, audio files for Response Group, Call Park, and Announcement applications, and files posted into Persistent Chat rooms.</span></span></p>
<p><span data-ttu-id="a674a-191">Sauvegardez vos sauvegardes régulières.</span><span class="sxs-lookup"><span data-stu-id="a674a-191">Back up with your regular backups.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a><span data-ttu-id="a674a-192">Autres exigences de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="a674a-192">Additional Backup Requirements</span></span>

<span data-ttu-id="a674a-193">Pour vous aider à restaurer les services Lync Server en cas de panne, vous devez sauvegarder les composants nécessaires qui ne font pas partie de Lync Server lui-même.</span><span class="sxs-lookup"><span data-stu-id="a674a-193">To help ensure your ability to restore Lync Server services in the event of a failure, you must back up some necessary components that are not part of Lync Server itself.</span></span> <span data-ttu-id="a674a-194">Les composants suivants ne sont pas sauvegardés ni restaurés dans le cadre du processus de sauvegarde et de restauration de Lync Server décrit dans ce document :</span><span class="sxs-lookup"><span data-stu-id="a674a-194">The following components are not backed up or restored as part of the Lync Server backup and restoration process described in this document:</span></span>

  - <span data-ttu-id="a674a-195">**Services de domaine Active Directory**   vous devez sauvegarder AD DS à l’aide des outils Active Directory en même temps que Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a674a-195">**Active Directory Domain Services**   You need to back up AD DS by using Active Directory tools at the same time that you back up Lync Server.</span></span> <span data-ttu-id="a674a-196">Il est important de maintenir AD DS synchronisé avec Lync Server, afin d’éviter les problèmes qui peuvent se produire lorsque Lync Server attend des objets contact qui ne correspondent pas à ceux dans AD DS.</span><span class="sxs-lookup"><span data-stu-id="a674a-196">It is important to keep AD DS synchronized with Lync Server, to avoid problems that can occur when Lync Server expects contact objects that do not match those in AD DS.</span></span> <span data-ttu-id="a674a-197">AD DS stocke les paramètres suivants utilisés par Lync Server :</span><span class="sxs-lookup"><span data-stu-id="a674a-197">AD DS stores the following settings which are used by Lync Server:</span></span>
    
      - <span data-ttu-id="a674a-198">URI SIP de l’utilisateur et autres paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a674a-198">User SIP URI and other user settings.</span></span>
    
      - <span data-ttu-id="a674a-199">Objets contact pour les applications telles que Response Group et le service de conférence.</span><span class="sxs-lookup"><span data-stu-id="a674a-199">Contact objects for applications such as Response Group and Conferencing Attendant.</span></span>
    
      - <span data-ttu-id="a674a-200">Pointeur vers le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="a674a-200">A pointer to the Central Management Store.</span></span>
    
      - <span data-ttu-id="a674a-201">Le compte d’authentification Kerberos (un objet ordinateur facultatif) et les groupes de sécurité Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a674a-201">Kerberos Authentication Account (an optional computer object) and Lync Server security groups.</span></span>
    
    <span data-ttu-id="a674a-202">Pour plus d’informations sur la sauvegarde et la restauration des services AD DS dans Windows Server 2008, voir « Guide pas à pas de la sauvegarde et de [http://go.microsoft.com/fwlink/p/?linkId=209105](http://go.microsoft.com/fwlink/p/?linkid=209105)la récupération AD DS » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="a674a-202">For details about backing up and restoring AD DS in Windows Server 2008, see "AD DS Backup and Recovery Step-by-Step Guide" at [http://go.microsoft.com/fwlink/p/?linkId=209105](http://go.microsoft.com/fwlink/p/?linkid=209105).</span></span>

  - <span data-ttu-id="a674a-203">**Autorité de certification et certificats**   utilisez la stratégie de votre organisation pour sauvegarder votre autorité de certification et vos certificats.</span><span class="sxs-lookup"><span data-stu-id="a674a-203">**Certification authority and certificates**   Use your organization's policy for backing up your certification authority (CA) and certificates.</span></span> <span data-ttu-id="a674a-204">Si vous utilisez des clés privées exportables, vous pouvez sauvegarder le certificat et la clé privée, puis les exporter si vous utilisez les procédures décrites dans ce document pour restaurer Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a674a-204">If you use exportable private keys, you can back up the certificate and the private key, and then export them if you use the procedures in this document to restore Lync Server.</span></span> <span data-ttu-id="a674a-205">Si vous utilisez une autorité de certification interne, vous pouvez réinscrire si vous avez besoin de restaurer Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a674a-205">If you use an internal CA, you can re-enroll if you need to restore Lync Server.</span></span> <span data-ttu-id="a674a-206">Il est important de conserver la clé privée dans un endroit sûr où elle sera disponible en cas de défaillance d’un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="a674a-206">It is important that you retain the private key in a secure location where it will be available if a computer fails.</span></span>

  - <span data-ttu-id="a674a-207">**System Center Operations Manager**   si vous utilisez Microsoft System Center Operations Manager (anciennement Microsoft Operations Manager) pour surveiller votre déploiement Lync Server, vous pouvez sauvegarder les données qu’il crée pendant qu’il analyse Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a674a-207">**System Center Operations Manager**   If you use Microsoft System Center Operations Manager (formerly Microsoft Operations Manager) to monitor your Lync Server deployment, you can optionally back up the data it creates while it is monitoring Lync Server.</span></span> <span data-ttu-id="a674a-208">Utilisez votre processus de sauvegarde SQL Server standard pour sauvegarder les fichiers System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="a674a-208">Use your standard SQL Server backup process to back up System Center Operations Manager files.</span></span> <span data-ttu-id="a674a-209">Ces fichiers ne sont pas restaurés lors de la récupération.</span><span class="sxs-lookup"><span data-stu-id="a674a-209">These files are not restored during recovery.</span></span>

  - <span data-ttu-id="a674a-210">**Configuration de la passerelle PSTN (réseau téléphonique commuté)**   si vous utilisez des appliances voix entreprise ou Survivable Branch Appliances, vous devez sauvegarder la configuration de la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="a674a-210">**Public switched telephone network (PSTN) gateway configuration**   If you use Enterprise Voice or Survivable Branch Appliances, you need to back up the PSTN gateway configuration.</span></span> <span data-ttu-id="a674a-211">Pour plus d’informations sur la sauvegarde et la restauration des configurations de passerelle PSTN, consultez votre fournisseur.</span><span class="sxs-lookup"><span data-stu-id="a674a-211">See your vendor for details about backing up and restoring PSTN gateway configurations.</span></span>

  - <span data-ttu-id="a674a-212">**Versions coexistantes de Lync Server ou Office Communications Server**   si votre déploiement Lync Server 2013 coexiste avec Lync Server 2010 ou une version antérieure d’Office Communications Server, vous ne pouvez pas utiliser les procédures décrites dans ce document pour sauvegarder ou restaurer la version antérieure.</span><span class="sxs-lookup"><span data-stu-id="a674a-212">**Coexisting versions of Lync Server or Office Communications Server**   If your Lync Server 2013 deployment coexists with Lync Server 2010 or an earlier version of Office Communications Server, you can’t use the procedures in this document for backing up or restoring the earlier version.</span></span> <span data-ttu-id="a674a-213">Au lieu de cela, vous devez utiliser les procédures de sauvegarde et de restauration documentées spécifiquement pour votre version précédente.</span><span class="sxs-lookup"><span data-stu-id="a674a-213">Instead, you must use the backup and restoration procedures documented specifically for your earlier version.</span></span> <span data-ttu-id="a674a-214">Pour plus d’informations sur la sauvegarde et la restauration de Lync Server [http://go.microsoft.com/fwlink/p/?linkId=265417](http://go.microsoft.com/fwlink/p/?linkid=265417) 2010, reportez-vous à la rubrique.</span><span class="sxs-lookup"><span data-stu-id="a674a-214">For details about backing up and restoring Lync Server 2010, see [http://go.microsoft.com/fwlink/p/?linkId=265417](http://go.microsoft.com/fwlink/p/?linkid=265417) .</span></span> <span data-ttu-id="a674a-215">Pour plus d’informations sur la sauvegarde et la restauration de Microsoft Office Communications Server 2007 [http://go.microsoft.com/fwlink/p/?linkId=168162](http://go.microsoft.com/fwlink/p/?linkid=168162)R2, reportez-vous à la rubrique.</span><span class="sxs-lookup"><span data-stu-id="a674a-215">For details about backing up and restoring Microsoft Office Communications Server 2007 R2, see [http://go.microsoft.com/fwlink/p/?linkId=168162](http://go.microsoft.com/fwlink/p/?linkid=168162).</span></span>

  - <span data-ttu-id="a674a-216">**Informations**   relatives à l’infrastructure dont vous avez besoin pour sauvegarder des informations sur votre infrastructure, telles que la configuration de votre pare-feu, la configuration de l’équilibrage de charge, la configuration des services Internet (IIS), les enregistrements DNS (Domain Name System) et les adresses IP, ainsi que la configuration du protocole DHCP (Dynamic Host Configuration Protocol).</span><span class="sxs-lookup"><span data-stu-id="a674a-216">**Infrastructure information**   You need to back up information about your infrastructure, such as your firewall configuration, load balancing configuration, Internet Information Services (IIS) configuration, Domain Name System (DNS) records and IP addresses, and Dynamic Host Configuration Protocol (DHCP) configuration.</span></span> <span data-ttu-id="a674a-217">Pour plus d’informations sur la sauvegarde de ces composants, consultez leur fournisseur respectif.</span><span class="sxs-lookup"><span data-stu-id="a674a-217">For details about backing up these components, check with their respective vendors.</span></span>

  - <span data-ttu-id="a674a-218">**Microsoft Exchange et la messagerie unifiée Exchange**   sauvegarde et restauration de Microsoft Exchange et de la messagerie unifiée Exchange, comme décrit dans la documentation de Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="a674a-218">**Microsoft Exchange and Exchange Unified Messaging (UM)**   Backup and restore Microsoft Exchange and Exchange UM as described in the Microsoft Exchange documentation.</span></span> <span data-ttu-id="a674a-219">Pour plus d’informations sur la sauvegarde et la restauration d’Exchange Server [http://go.microsoft.com/fwlink/?LinkId=285384](http://go.microsoft.com/fwlink/?linkid=285384)2013, voir.</span><span class="sxs-lookup"><span data-stu-id="a674a-219">For details about backing up and restoring Exchange Server 2013, see [http://go.microsoft.com/fwlink/?LinkId=285384](http://go.microsoft.com/fwlink/?linkid=285384).</span></span> <span data-ttu-id="a674a-220">Pour plus d’informations sur la sauvegarde et la restauration d’Exchange Server [http://go.microsoft.com/fwlink/p/?linkId=209179](http://go.microsoft.com/fwlink/p/?linkid=209179)2010, voir.</span><span class="sxs-lookup"><span data-stu-id="a674a-220">For details about backing up and restoring Exchange Server 2010, see [http://go.microsoft.com/fwlink/p/?linkId=209179](http://go.microsoft.com/fwlink/p/?linkid=209179).</span></span>
    
    <span data-ttu-id="a674a-221">Notez que Lync Server 2013 offre la possibilité de faire en sorte que les listes de contacts de l’utilisateur, les photos des utilisateurs à haute définition et les données d’archivage soient stockées dans Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="a674a-221">Note that Lync Server 2013 introduces the ability to have user contact lists, high definition user photos, and archiving data stored in Exchange 2013.</span></span> <span data-ttu-id="a674a-222">Consultez la liste suivante pour savoir comment sauvegarder ces types de données :</span><span class="sxs-lookup"><span data-stu-id="a674a-222">See the following list to see how to back up these types of data:</span></span>
    
      - <span data-ttu-id="a674a-223">Les **photos haute définition** sont sauvegardées dans le cadre de la sauvegarde Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="a674a-223">**High definition photos** are backed up as part of the Exchange Server backup.</span></span>
    
      - <span data-ttu-id="a674a-224">Le **magasin de contacts unifié** est présenté dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a674a-224">**Unified contact store** is introduced in Lync Server 2013.</span></span> <span data-ttu-id="a674a-225">Magasin de contacts unifié permet aux utilisateurs de conserver toutes leurs informations de contact dans Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="a674a-225">Unified contact store enables users to keep all their contact information in Exchange 2013.</span></span>
        
        <span data-ttu-id="a674a-226">Vous devez vous assurer que les sauvegardes sont à jour pour les utilisateurs en ce qui concerne le stockage de leurs contacts dans le magasin de contacts unifié ou sur le serveur principal Lync.</span><span class="sxs-lookup"><span data-stu-id="a674a-226">You should make sure that backups are up-to-date for users in terms of whether their user contacts are stored in the unified contact store or on the Lync Back End Server.</span></span> <span data-ttu-id="a674a-227">Les scénarios suivants montrent où la migration des contacts de l’utilisateur vers le magasin de contacts unifié peut entraîner des problèmes pour le processus de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="a674a-227">The following scenarios illustrate where migrating user contacts to the unified contact store can cause issues for the backup and restore process.</span></span>
        
        <span data-ttu-id="a674a-228">**Scénario 1 :** Les contacts de l’utilisateur sont migrés vers le magasin de contacts unifié et une restauration est effectuée à partir d’une sauvegarde Lync Server effectuée avant la migration des contacts de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a674a-228">**Scenario 1:** User contacts are migrated to the unified contact store, and a restore is performed from a Lync Server backup taken prior to the migration of user contacts.</span></span> <span data-ttu-id="a674a-229">Dans ce scénario, l’utilisateur aura un état de contacts obsolètes jusqu’à un jour jusqu’à ce que la tâche de migration Lync Server commence à migrer les contacts de l’utilisateur vers Exchange.</span><span class="sxs-lookup"><span data-stu-id="a674a-229">In this scenario, the user will have a state of outdated contacts for up to one day until Lync Server Migration Task begins migrating user contacts to Exchange.</span></span> <span data-ttu-id="a674a-230">(Notez que, étant donné que les contacts utilisateur ont déjà été migrés vers le magasin de contacts unifié, les informations de contact Exchange seront utilisées).</span><span class="sxs-lookup"><span data-stu-id="a674a-230">(Note that because the user contacts were previously migrated to the unified contact store, the Exchange contact information will be used).</span></span> <span data-ttu-id="a674a-231">Aucune intervention de l’administrateur n’est nécessaire dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="a674a-231">No administrator intervention is needed in this scenario.</span></span>
        
        <span data-ttu-id="a674a-232">**Scénario 2 :** Les contacts utilisateur étaient précédemment stockés dans le magasin de contacts unifié, puis annulés.</span><span class="sxs-lookup"><span data-stu-id="a674a-232">**Scenario 2:** User contacts were previously stored in the unified contact store, but then rolled back.</span></span> <span data-ttu-id="a674a-233">Une restauration est effectuée à partir d’une sauvegarde Lync Server effectuée lorsque les contacts de l’utilisateur ont été stockés dans le magasin de contacts unifié.</span><span class="sxs-lookup"><span data-stu-id="a674a-233">A restore is performed from a Lync Server backup taken when the user contacts were stored in the unified contact store.</span></span> <span data-ttu-id="a674a-234">Dans ce scénario, un message d’erreur `Error: Incorrect Exchange Version` de dans les journaux du client ou du serveur Lyss peut indiquer qu’il s’agit d’un problème.</span><span class="sxs-lookup"><span data-stu-id="a674a-234">In this scenario, an error message of `Error: Incorrect Exchange Version` in the client or Lyss server logs may indicate this as an issue.</span></span> <span data-ttu-id="a674a-235">L’utilisateur pourra accéder à sa liste de contacts dans Lync 2013 directement à partir d’Exchange, mais l’état du client ne correspondra pas à l’état du serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="a674a-235">The user will be able to access their contact list in Lync 2013 directly from Exchange, but client’s state will not match the Lync Server state.</span></span> <span data-ttu-id="a674a-236">Pour résoudre ce problème, un administrateur doit exécuter les applets de commande **Invoke-CsUCSRollback** pour les utilisateurs concernés.</span><span class="sxs-lookup"><span data-stu-id="a674a-236">To fix this, an administrator will need to run the **Invoke-CsUCSRollback** cmdlets for the affected users.</span></span>
    
      - <span data-ttu-id="a674a-237">Les **données d’archivage** peuvent être stockées dans Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="a674a-237">**Archiving Data** can be stored in Exchange 2013.</span></span> <span data-ttu-id="a674a-238">Ces données ne sont pas essentielles à Lync Server, mais elles peuvent être critiques pour votre organisation à des fins de réglementation.</span><span class="sxs-lookup"><span data-stu-id="a674a-238">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="a674a-239">Si les données d’archivage sont stockées dans Exchange et qu’elles sont essentielles pour votre organisation, suivez les procédures de sauvegarde et de restauration d’Exchange.</span><span class="sxs-lookup"><span data-stu-id="a674a-239">If archiving data is stored in Exchange and is critical to your organization, then follow Exchange backup and restore procedures.</span></span> <span data-ttu-id="a674a-240">Notez que les données d’archivage stockées dans Exchange ne peuvent pas être déplacées vers Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a674a-240">Note that archiving data stored in Exchange cannot be moved back to Lync Server.</span></span> <span data-ttu-id="a674a-241">De plus, il n’existe aucun moyen de déplacer des données déjà stockées dans la base de données d’archivage Lync vers Exchange.</span><span class="sxs-lookup"><span data-stu-id="a674a-241">Additionally, there is no way to move data already stored in the Lync archiving database to Exchange.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

