---
title: 'Lync Server 2013: configuration requise pour la sauvegarde et la restauration: données'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Backup and restoration requirements: data'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202194(v=OCS.15)
ms:contentKeyID: 51541526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54814295343b99cb51e5827791df160dbeff2638
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a><span data-ttu-id="210b1-102">Configuration requise pour la sauvegarde et la restauration dans Lync Server 2013: données</span><span class="sxs-lookup"><span data-stu-id="210b1-102">Backup and restoration requirements in Lync Server 2013: data</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="210b1-103">_**Dernière modification de la rubrique:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="210b1-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="210b1-104">Lync Server utilise les paramètres et les informations de configuration stockées dans les bases de données et les données qui sont stockées dans les bases de données et les magasins de fichiers.</span><span class="sxs-lookup"><span data-stu-id="210b1-104">Lync Server uses settings and configuration information that are stored in databases, and data that is stored in databases and file stores.</span></span> <span data-ttu-id="210b1-105">Cette rubrique décrit les données que vous devez sauvegarder pour pouvoir restaurer le service en cas d’échec ou d’interruption de votre organisation, ainsi que les données et composants utilisés par Lync Server et dont vous avez besoin pour vous sauvegarder séparément.</span><span class="sxs-lookup"><span data-stu-id="210b1-105">This topic describes the data that you need to back up to be able to restore service if your organization experiences a failure or outage, and also identifies the data and components used by Lync Server that you need to back up separately.</span></span>

<div>

## <a name="settings-and-configuration-requirements"></a><span data-ttu-id="210b1-106">Paramètres et configuration requise</span><span class="sxs-lookup"><span data-stu-id="210b1-106">Settings and Configuration Requirements</span></span>

<span data-ttu-id="210b1-107">Cette rubrique inclut les procédures de sauvegarde et de restauration des paramètres et des informations de configuration nécessaires à la récupération du service Lync Server.</span><span class="sxs-lookup"><span data-stu-id="210b1-107">This topic includes procedures for backing up and restoring the settings and configuration information that is required for recovery of Lync Server service.</span></span> <span data-ttu-id="210b1-108">Les informations de configuration se trouvent dans le magasin de gestion central ou sur une autre base de données principale ou sur un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="210b1-108">The configuration information is located in the Central Management store or on another back-end database or on Standard Edition server.</span></span>

<span data-ttu-id="210b1-109">Le tableau suivant répertorie les paramètres et les informations de configuration nécessaires pour la sauvegarde et la restauration.</span><span class="sxs-lookup"><span data-stu-id="210b1-109">The following table identifies the settings and configuration information that you need to back up and restore.</span></span>

### <a name="settings-and-configuration-data"></a><span data-ttu-id="210b1-110">Paramètres et données de configuration</span><span class="sxs-lookup"><span data-stu-id="210b1-110">Settings and Configuration Data</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="210b1-111">Type de données</span><span class="sxs-lookup"><span data-stu-id="210b1-111">Type of data</span></span></th>
<th><span data-ttu-id="210b1-112">Emplacement de stockage</span><span class="sxs-lookup"><span data-stu-id="210b1-112">Where stored</span></span></th>
<th><span data-ttu-id="210b1-113">Description/moment de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="210b1-113">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="210b1-114">Informations de configuration de la topologie</span><span class="sxs-lookup"><span data-stu-id="210b1-114">Topology configuration information</span></span></p></td>
<td><p><span data-ttu-id="210b1-115">Magasin de gestion centralisée (base de données: XDS. mdf)</span><span class="sxs-lookup"><span data-stu-id="210b1-115">Central Management store (database: Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="210b1-116">Paramètres de topologie, de stratégie et de configuration.</span><span class="sxs-lookup"><span data-stu-id="210b1-116">Topology, policy, and configuration settings.</span></span></p>
<p><span data-ttu-id="210b1-117">Sauvegardez vos sauvegardes régulières et après avoir utilisé le panneau de configuration ou les applets de commande Lync Server pour modifier votre configuration ou vos stratégies.</span><span class="sxs-lookup"><span data-stu-id="210b1-117">Back up with your regular backups and after you use Lync Server Control Panel or cmdlets to modify your configuration or policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="210b1-118">Informations d’emplacement</span><span class="sxs-lookup"><span data-stu-id="210b1-118">Location information</span></span></p></td>
<td><p><span data-ttu-id="210b1-119">Magasin de gestion centralisée (base de données: lis. mdf)</span><span class="sxs-lookup"><span data-stu-id="210b1-119">Central Management store (database: Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="210b1-120">Informations de configuration de 9-1-1 voix entreprise améliorée (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="210b1-120">Enterprise Voice Enhanced 9-1-1 (E9-1-1) configuration information.</span></span> <span data-ttu-id="210b1-121">Ces informations sont généralement statiques.</span><span class="sxs-lookup"><span data-stu-id="210b1-121">This information is generally static.</span></span></p>
<p><span data-ttu-id="210b1-122">Sauvegardez vos sauvegardes régulières.</span><span class="sxs-lookup"><span data-stu-id="210b1-122">Back up with your regular backups.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="210b1-123">Informations de configuration du groupe de réponse</span><span class="sxs-lookup"><span data-stu-id="210b1-123">Response Group configuration information</span></span></p></td>
<td><p><span data-ttu-id="210b1-124">Serveur principal ou Standard Edition Server (base de données: RgsConfig. mdf)</span><span class="sxs-lookup"><span data-stu-id="210b1-124">Back End Server or Standard Edition server (database: RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="210b1-125">Response Group Group agent, files d’attente et flux de travail.</span><span class="sxs-lookup"><span data-stu-id="210b1-125">Response Group agent groups, queues, and workflows.</span></span></p>
<p><span data-ttu-id="210b1-126">Sauvegardez vos sauvegardes régulières et après avoir ajouté ou modifié des groupes d’agents, des files d’attente ou des flux de travail.</span><span class="sxs-lookup"><span data-stu-id="210b1-126">Back up with your regular backups and after you add or change agent groups, queues, or workflows.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a><span data-ttu-id="210b1-127">Exigences en matière de données</span><span class="sxs-lookup"><span data-stu-id="210b1-127">Data Requirements</span></span>

<span data-ttu-id="210b1-128">Vous trouverez ci-dessous la liste des données du serveur Lync dont vous avez besoin pour vous permettre de restaurer le service Lync Server en cas d’échec.</span><span class="sxs-lookup"><span data-stu-id="210b1-128">Here is a list of the Lync Server data that you need to back up so that you can restore Lync Server service in the event of a failure.</span></span>

<span data-ttu-id="210b1-129">Notez que certains types de données ne sont pas nécessaires pour la récupération.</span><span class="sxs-lookup"><span data-stu-id="210b1-129">Note that some types of data are not required for recovery.</span></span> <span data-ttu-id="210b1-130">Cette rubrique ne contient pas de procédures pour la sauvegarde de ces types de données, notamment les suivantes:</span><span class="sxs-lookup"><span data-stu-id="210b1-130">This topic does not contain procedures for backing up these types of data, which include the following:</span></span>

  - <span data-ttu-id="210b1-131">Des données utilisateur temporaires, telles que des points de terminaison et des abonnements, des serveurs de conférence actifs et des États de conférence temporaire (base de données: RtcDyn. mdf);</span><span class="sxs-lookup"><span data-stu-id="210b1-131">Transient user data, such as endpoints and subscriptions, active conferencing servers, and transient conferencing states (database: RtcDyn.mdf)</span></span>

  - <span data-ttu-id="210b1-132">Données du carnet d’adresses (bases de données: RTCAb. mdf et Rtcab1. mdf).</span><span class="sxs-lookup"><span data-stu-id="210b1-132">Address Book data (databases: Rtcab.mdf and Rtcab1.mdf).</span></span> <span data-ttu-id="210b1-133">La base de données du carnet d’adresses est automatiquement générée à partir des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="210b1-133">The Address Book database is regenerated automatically from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="210b1-134">Informations dynamiques pour l’application de parc d’appels (base de données: CpsDyn. mdf)</span><span class="sxs-lookup"><span data-stu-id="210b1-134">Dynamic information for the Call Park application (database: CpsDyn.mdf)</span></span>

  - <span data-ttu-id="210b1-135">Données de groupe de réponse passagère, telles que l’état de connexion d’un agent et les informations d’attente d’appel (base de données: RgsDyn. mdf)</span><span class="sxs-lookup"><span data-stu-id="210b1-135">Transient Response Group data, such as agent sign-in state and call waiting information (database: RgsDyn.mdf)</span></span>

  - <span data-ttu-id="210b1-136">La base de données de conformité pour les discussions permanentes (base de données: MgcComp. mdf).</span><span class="sxs-lookup"><span data-stu-id="210b1-136">The compliance database for Persistent Chat (database: MgcComp.mdf).</span></span> <span data-ttu-id="210b1-137">Si la conformité des conversations permanentes est activée, les informations contenues dans la base de données de compatibilité des conversations permanentes sont temporaires tant qu’un adaptateur est configuré pour lire des informations de la base de données et le convertir dans un autre format.</span><span class="sxs-lookup"><span data-stu-id="210b1-137">If you have Persistent Chat compliance enabled, the information in the Persistent Chat Compliance database is transient as long as you have an adapter configured to read information from the database and convert it to an alternate format.</span></span> <span data-ttu-id="210b1-138">Par conséquent, la base de données de conformité d’une conversation permanente est considérée comme temporaire.</span><span class="sxs-lookup"><span data-stu-id="210b1-138">Hence the compliance database for Persistent Chat is considered transient.</span></span>
    
    <span data-ttu-id="210b1-139">Lync Server 2013 permanent Chat Server est fourni avec un adaptateur XML.</span><span class="sxs-lookup"><span data-stu-id="210b1-139">Lync Server 2013 Persistent Chat Server ships with an XML adapter.</span></span> <span data-ttu-id="210b1-140">Vous pouvez également installer des adaptateurs personnalisés qui prennent ces données et les déplacer vers d’autres sources, telles que des archives hébergées d’Exchange.</span><span class="sxs-lookup"><span data-stu-id="210b1-140">You can also install custom adapters that take this data and move it to other sources, such as Exchange Hosted Archives.</span></span>

<span data-ttu-id="210b1-141">Le tableau suivant identifie les données que vous devez sauvegarder et restaurer.</span><span class="sxs-lookup"><span data-stu-id="210b1-141">The following table identifies the data that you need to back up and restore.</span></span>

### <a name="data-stored-in-databases"></a><span data-ttu-id="210b1-142">Données stockées dans des bases de données</span><span class="sxs-lookup"><span data-stu-id="210b1-142">Data Stored in Databases</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="210b1-143">Type de données</span><span class="sxs-lookup"><span data-stu-id="210b1-143">Type of data</span></span></th>
<th><span data-ttu-id="210b1-144">Emplacement de stockage</span><span class="sxs-lookup"><span data-stu-id="210b1-144">Where stored</span></span></th>
<th><span data-ttu-id="210b1-145">Description/moment de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="210b1-145">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="210b1-146">Données utilisateur persistantes</span><span class="sxs-lookup"><span data-stu-id="210b1-146">Persistent user data</span></span></p></td>
<td><p><span data-ttu-id="210b1-147">Serveur principal ou Standard Edition Server (base de données: RTCXDS. mdf)</span><span class="sxs-lookup"><span data-stu-id="210b1-147">Back End Server or Standard Edition server (database: RTCXDS.mdf)</span></span></p></td>
<td><p><span data-ttu-id="210b1-148">Droits d’utilisateur, listes des contacts utilisateur, données du serveur ou du pool, conférences planifiées, etc.</span><span class="sxs-lookup"><span data-stu-id="210b1-148">User rights, user Contacts lists, server or pool data, scheduled conferences, and so on.</span></span> <span data-ttu-id="210b1-149">Les données utilisateur n’incluent pas le contenu chargé dans une conférence.</span><span class="sxs-lookup"><span data-stu-id="210b1-149">This user data does not include content uploaded to a conference.</span></span></p>
<p><span data-ttu-id="210b1-150">Sauvegardez vos sauvegardes régulières.</span><span class="sxs-lookup"><span data-stu-id="210b1-150">Back up with your regular backups.</span></span> <span data-ttu-id="210b1-151">Ces informations sont dynamiques, mais la perte des mises à jour n’est pas irrémédiablement apportée à Lync Server si vous avez besoin de procéder à la restauration de votre dernière sauvegarde normale.</span><span class="sxs-lookup"><span data-stu-id="210b1-151">This information is dynamic, but the loss of updates is not catastrophic to Lync Server if you need to restore to your last regular backup.</span></span> <span data-ttu-id="210b1-152">Si les listes de contacts sont essentielles pour votre organisation, vous pouvez sauvegarder ces données plus fréquemment.</span><span class="sxs-lookup"><span data-stu-id="210b1-152">If Contacts lists are critical to your organization, you can back up this data more frequently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="210b1-153">Archivage de données</span><span class="sxs-lookup"><span data-stu-id="210b1-153">Archiving data</span></span></p></td>
<td><p><span data-ttu-id="210b1-154">Archivage de la base de données (base de données: LcsLog. mdf)</span><span class="sxs-lookup"><span data-stu-id="210b1-154">Archiving database (database: LcsLog.mdf)</span></span></p>
<p><span data-ttu-id="210b1-155">Ces données peuvent être stockées sur Exchange 2013, si vous avez activé l’option d’intégration de Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="210b1-155">This data may be stored on Exchange 2013, if you have enabled the Microsoft Exchange integration option.</span></span> <span data-ttu-id="210b1-156">Dans le cas contraire, il s’agit d’une base de données d’archivage Lync Server, qui peut être colocalisée avec une autre base de données Lync Server ou autonome sur un serveur de base de données distinct.</span><span class="sxs-lookup"><span data-stu-id="210b1-156">Otherwise, this data is kept in a Lync Server Archiving database, which may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="210b1-157">Messagerie instantanée et contenu de la réunion.</span><span class="sxs-lookup"><span data-stu-id="210b1-157">Instant messaging (IM) and meeting content.</span></span></p>
<p><span data-ttu-id="210b1-158">Cette information n’est pas essentielle pour Lync Server, mais elle peut être essentielle pour les fins réglementaires de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="210b1-158">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="210b1-159">Déterminez votre planning de sauvegarde en conséquence.</span><span class="sxs-lookup"><span data-stu-id="210b1-159">Determine your back up schedule accordingly.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="210b1-160">Surveiller les données</span><span class="sxs-lookup"><span data-stu-id="210b1-160">Monitoring data</span></span></p></td>
<td><p><span data-ttu-id="210b1-161">Surveiller des bases de données (LcsCDR. mdf et QoeMetrics. mdf)</span><span class="sxs-lookup"><span data-stu-id="210b1-161">Monitoring databases (LcsCDR.mdf and QoeMetrics.mdf)</span></span></p>
<p><span data-ttu-id="210b1-162">Ces bases de données risquent d’être colocalisées avec une autre base de données Lync Server ou autonome sur un serveur de base de données distinct.</span><span class="sxs-lookup"><span data-stu-id="210b1-162">These databases may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="210b1-163">Les enregistrements des détails des appels (LcsCDR. mdf) et la qualité de l’expertise (QoE) (QoeMetrics. mdf).</span><span class="sxs-lookup"><span data-stu-id="210b1-163">Call detail records (LcsCDR.mdf) and Quality of Experience (QoE) metrics (QoeMetrics.mdf).</span></span></p>
<p><span data-ttu-id="210b1-164">Les enregistrements des détails des appels sont dynamiques et peuvent être importants pour votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="210b1-164">Call detail records are dynamic and may be critical to your business.</span></span> <span data-ttu-id="210b1-165">Déterminez votre planning de sauvegarde en tenant compte de l’utilisation de ces enregistrements pour des raisons réglementaires.</span><span class="sxs-lookup"><span data-stu-id="210b1-165">Determine your back up schedule by considering whether you need these records for regulatory reasons.</span></span></p>
<p><span data-ttu-id="210b1-166">Les informations sur la qualité de l’expérimentation sont dynamiques.</span><span class="sxs-lookup"><span data-stu-id="210b1-166">Quality of experience information is dynamic.</span></span> <span data-ttu-id="210b1-167">La perte de données QoE n’est pas essentielle pour l’opération de Lync Server, mais elle peut être essentielle pour votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="210b1-167">Loss of QoE data is not critical for the operation of Lync Server, but it may be critical to your business.</span></span> <span data-ttu-id="210b1-168">Déterminez votre planning de sauvegarde en fonction de la façon dont ces informations sont importantes pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="210b1-168">Determine your back up schedule based on how critical this information is to your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="210b1-169">Données de chat permanent</span><span class="sxs-lookup"><span data-stu-id="210b1-169">Persistent Chat data</span></span></p></td>
<td><p><span data-ttu-id="210b1-170">Base de données de chat permanent (MGD. mdf).</span><span class="sxs-lookup"><span data-stu-id="210b1-170">Persistent Chat database (mgd.mdf).</span></span></p>
<p><span data-ttu-id="210b1-171">Cette base de données est susceptible d’être colocalisée avec une autre base de données Lync Server ou indépendante sur un serveur de base de données distinct.</span><span class="sxs-lookup"><span data-stu-id="210b1-171">This database may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="210b1-172">Les données de conversation permanente sont des messages de discussion en cours de publication dans des salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="210b1-172">Persistent Chat Data is actual chat content being posted in chat rooms.</span></span> <span data-ttu-id="210b1-173">Il s’agit souvent de données critiques pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="210b1-173">This data is often business critical.</span></span></p>
<p><span data-ttu-id="210b1-174">Vous pouvez choisir d’utiliser la sauvegarde SQL Server ou exporter la base de données à l’aide de l’applet de passe <strong>Export-CsPersistentChatData</strong> fournie dans Lync Server.</span><span class="sxs-lookup"><span data-stu-id="210b1-174">You can choose to use SQL Server backup, or export the database by using the <strong>Export-CsPersistentChatData</strong> cmdlet that is provided in Lync Server.</span></span> <span data-ttu-id="210b1-175">Pour la récupération des données, vous pouvez importer et restaurer la base de données à l’emplacement de la dernière sauvegarde complète, ce qui signifie que vous ne pouvez pas restaurer la base de données vers le point de défaillance.</span><span class="sxs-lookup"><span data-stu-id="210b1-175">For recovery of the data, you can import and restore the database to the point of the last full backup, which means you cannot restore the database to the point of failure.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a><span data-ttu-id="210b1-176">Exigences relatives aux données du magasin de fichiers</span><span class="sxs-lookup"><span data-stu-id="210b1-176">File Store Data Requirements</span></span>

<span data-ttu-id="210b1-177">Dans un déploiement Enterprise Edition, le magasin de fichiers de Lync Server se trouve généralement sur un serveur de fichiers.</span><span class="sxs-lookup"><span data-stu-id="210b1-177">In an Enterprise Edition deployment, the Lync Server file store is typically located on a file server.</span></span> <span data-ttu-id="210b1-178">Dans un déploiement Standard Edition, le magasin de fichiers de Lync Server se trouve par défaut sur le serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="210b1-178">In a Standard Edition deployment, the Lync Server file store is located by default on the Standard Edition server.</span></span> <span data-ttu-id="210b1-179">En règle générale, il existe un magasin de fichiers Lync Server partagé pour un site.</span><span class="sxs-lookup"><span data-stu-id="210b1-179">Typically, there is one Lync Server file store that is shared for a site.</span></span> <span data-ttu-id="210b1-180">Le magasin de fichiers permanents chat utilise le même partage de fichiers que le magasin de fichiers du serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="210b1-180">The Persistent Chat file store uses the same file share as the Lync Server file store.</span></span>

<span data-ttu-id="210b1-181">Les emplacements du magasin de fichiers \\ \\sont\\identifiés par le nom de partage du serveur.</span><span class="sxs-lookup"><span data-stu-id="210b1-181">File store locations are identified as \\\\server\\share name.</span></span> <span data-ttu-id="210b1-182">Pour trouver les emplacements spécifiques de vos magasins de fichiers, ouvrez le générateur de topologie et recherchez dans le nœud **magasins de fichiers** .</span><span class="sxs-lookup"><span data-stu-id="210b1-182">To find the specific locations of your file stores, open Topology Builder and look in the **File stores** node.</span></span>

<span data-ttu-id="210b1-183">Le tableau suivant identifie les banques de fichiers que vous devez sauvegarder et restaurer.</span><span class="sxs-lookup"><span data-stu-id="210b1-183">The following table identifies the file stores you need to back up and restore.</span></span>

### <a name="file-stores"></a><span data-ttu-id="210b1-184">Magasins de fichiers</span><span class="sxs-lookup"><span data-stu-id="210b1-184">File Stores</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="210b1-185">Type de données</span><span class="sxs-lookup"><span data-stu-id="210b1-185">Type of data</span></span></th>
<th><span data-ttu-id="210b1-186">Emplacement de stockage</span><span class="sxs-lookup"><span data-stu-id="210b1-186">Where stored</span></span></th>
<th><span data-ttu-id="210b1-187">Description/moment de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="210b1-187">Description / when to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="210b1-188">Magasin de fichiers de Lync Server</span><span class="sxs-lookup"><span data-stu-id="210b1-188">Lync Server file store</span></span></p></td>
<td><p><span data-ttu-id="210b1-189">Généralement sur un serveur de fichiers, un groupe de fichiers ou un serveur Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="210b1-189">Typically on a file server, file cluster, or a Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="210b1-190">Le contenu de la réunion, les métadonnées de contenu de la réunion, les journaux de conformité des réunions, les fichiers de données d’application, les fichiers de mise à jour des mises à jour de périphériques, les fichiers audio pour les réunions de groupe de réponse</span><span class="sxs-lookup"><span data-stu-id="210b1-190">Meeting content, meeting content metadata, meeting compliance logs, application data files, update files for device updates, audio files for Response Group, Call Park, and Announcement applications, and files posted into Persistent Chat rooms.</span></span></p>
<p><span data-ttu-id="210b1-191">Sauvegardez vos sauvegardes régulières.</span><span class="sxs-lookup"><span data-stu-id="210b1-191">Back up with your regular backups.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a><span data-ttu-id="210b1-192">Exigences de sauvegarde supplémentaires</span><span class="sxs-lookup"><span data-stu-id="210b1-192">Additional Backup Requirements</span></span>

<span data-ttu-id="210b1-193">Pour vous aider à garantir la possibilité de restaurer les services Lync Server en cas d’échec, vous devez sauvegarder les composants nécessaires qui ne font pas partie de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="210b1-193">To help ensure your ability to restore Lync Server services in the event of a failure, you must back up some necessary components that are not part of Lync Server itself.</span></span> <span data-ttu-id="210b1-194">Les composants suivants ne sont pas sauvegardés ou restaurés dans le cadre du processus de sauvegarde et de restauration de Lync Server décrits dans ce document:</span><span class="sxs-lookup"><span data-stu-id="210b1-194">The following components are not backed up or restored as part of the Lync Server backup and restoration process described in this document:</span></span>

  - <span data-ttu-id="210b1-195">**Services de domaine Active Directory**   vous devez sauvegarder les services de domaine Active Directory (AD DS) en utilisant les outils Active Directory en même temps que la sauvegarde de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="210b1-195">**Active Directory Domain Services**   You need to back up AD DS by using Active Directory tools at the same time that you back up Lync Server.</span></span> <span data-ttu-id="210b1-196">Il est important de maintenir la synchronisation AD DS sur Lync Server, afin d’éviter les problèmes qui peuvent survenir lorsque Lync Server attend des objets de contact qui ne correspondent pas à ceux d’AD DS.</span><span class="sxs-lookup"><span data-stu-id="210b1-196">It is important to keep AD DS synchronized with Lync Server, to avoid problems that can occur when Lync Server expects contact objects that do not match those in AD DS.</span></span> <span data-ttu-id="210b1-197">AD DS stocke les paramètres suivants qui sont utilisés par Lync Server:</span><span class="sxs-lookup"><span data-stu-id="210b1-197">AD DS stores the following settings which are used by Lync Server:</span></span>
    
      - <span data-ttu-id="210b1-198">URI SIP utilisateur et autres paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="210b1-198">User SIP URI and other user settings.</span></span>
    
      - <span data-ttu-id="210b1-199">Objets de contact pour des applications telles que Response Group et attendant.</span><span class="sxs-lookup"><span data-stu-id="210b1-199">Contact objects for applications such as Response Group and Conferencing Attendant.</span></span>
    
      - <span data-ttu-id="210b1-200">Pointeur vers le magasin de gestion central.</span><span class="sxs-lookup"><span data-stu-id="210b1-200">A pointer to the Central Management Store.</span></span>
    
      - <span data-ttu-id="210b1-201">Compte d’authentification Kerberos (objet ordinateur facultatif) et groupes de sécurité Lync Server.</span><span class="sxs-lookup"><span data-stu-id="210b1-201">Kerberos Authentication Account (an optional computer object) and Lync Server security groups.</span></span>
    
    <span data-ttu-id="210b1-202">Pour plus d’informations sur l’utilisation de la fonction de sauvegarde et de restauration des services AD DS dans Windows Server 2008, voir le guide étape par étape [http://go.microsoft.com/fwlink/p/?linkId=209105](http://go.microsoft.com/fwlink/p/?linkid=209105)de sauvegarde et récupération AD DS à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="210b1-202">For details about backing up and restoring AD DS in Windows Server 2008, see "AD DS Backup and Recovery Step-by-Step Guide" at [http://go.microsoft.com/fwlink/p/?linkId=209105](http://go.microsoft.com/fwlink/p/?linkid=209105).</span></span>

  - <span data-ttu-id="210b1-203">**Autorités de certification et certificats**   utilisez la stratégie de votre organisation pour sauvegarder votre autorité de certification et vos certificats.</span><span class="sxs-lookup"><span data-stu-id="210b1-203">**Certification authority and certificates**   Use your organization's policy for backing up your certification authority (CA) and certificates.</span></span> <span data-ttu-id="210b1-204">Si vous utilisez des clés privées exportables, vous pouvez sauvegarder le certificat et la clé privée, puis les exporter si vous suivez les procédures décrites dans ce document pour restaurer Lync Server.</span><span class="sxs-lookup"><span data-stu-id="210b1-204">If you use exportable private keys, you can back up the certificate and the private key, and then export them if you use the procedures in this document to restore Lync Server.</span></span> <span data-ttu-id="210b1-205">Si vous utilisez une autorité de certification interne, vous pouvez procéder de nouveau à l’inscription si vous avez besoin de restaurer Lync Server.</span><span class="sxs-lookup"><span data-stu-id="210b1-205">If you use an internal CA, you can re-enroll if you need to restore Lync Server.</span></span> <span data-ttu-id="210b1-206">Il est important que vous conserviez la clé privée à un emplacement sécurisé pour qu’elle soit disponible en cas d’échec d’un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="210b1-206">It is important that you retain the private key in a secure location where it will be available if a computer fails.</span></span>

  - <span data-ttu-id="210b1-207">**System Center Operations Manager**   si vous utilisez Microsoft System Center Operations Manager (auparavant Microsoft Operations Manager) pour contrôler votre déploiement de Lync Server, vous pouvez sauvegarder les données qu’il crée lors de l’analyse de Lync Serveurs.</span><span class="sxs-lookup"><span data-stu-id="210b1-207">**System Center Operations Manager**   If you use Microsoft System Center Operations Manager (formerly Microsoft Operations Manager) to monitor your Lync Server deployment, you can optionally back up the data it creates while it is monitoring Lync Server.</span></span> <span data-ttu-id="210b1-208">Utilisez votre processus de sauvegarde SQL Server standard pour sauvegarder les fichiers System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="210b1-208">Use your standard SQL Server backup process to back up System Center Operations Manager files.</span></span> <span data-ttu-id="210b1-209">Ces fichiers ne sont pas restaurés lors de la récupération.</span><span class="sxs-lookup"><span data-stu-id="210b1-209">These files are not restored during recovery.</span></span>

  - <span data-ttu-id="210b1-210">**Configuration de la passerelle de réseau téléphonique commuté (PSTN)**   si vous utilisez des appareils de succursale voix entreprise ou survivables, vous devez sauvegarder la configuration de la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="210b1-210">**Public switched telephone network (PSTN) gateway configuration**   If you use Enterprise Voice or Survivable Branch Appliances, you need to back up the PSTN gateway configuration.</span></span> <span data-ttu-id="210b1-211">Pour plus d’informations sur la sauvegarde et la restauration des configurations de passerelle RTC, consultez votre fournisseur.</span><span class="sxs-lookup"><span data-stu-id="210b1-211">See your vendor for details about backing up and restoring PSTN gateway configurations.</span></span>

  - <span data-ttu-id="210b1-212">**Versions et coexistence de Lync Server ou d’Office Communications Server**   si votre déploiement Lync Server 2013 est le même que celui de Lync Server 2010 ou une version antérieure d’Office Communications Server, vous ne pouvez pas utiliser les procédures décrites dans ce document pour la sauvegarde ou en restaurant une version antérieure.</span><span class="sxs-lookup"><span data-stu-id="210b1-212">**Coexisting versions of Lync Server or Office Communications Server**   If your Lync Server 2013 deployment coexists with Lync Server 2010 or an earlier version of Office Communications Server, you can’t use the procedures in this document for backing up or restoring the earlier version.</span></span> <span data-ttu-id="210b1-213">À la place, vous devez utiliser les procédures de sauvegarde et de restauration indiquées spécifiquement pour votre version antérieure.</span><span class="sxs-lookup"><span data-stu-id="210b1-213">Instead, you must use the backup and restoration procedures documented specifically for your earlier version.</span></span> <span data-ttu-id="210b1-214">Pour plus d’informations sur la sauvegarde et la restauration de Lync Server [http://go.microsoft.com/fwlink/p/?linkId=265417](http://go.microsoft.com/fwlink/p/?linkid=265417) 2010, voir.</span><span class="sxs-lookup"><span data-stu-id="210b1-214">For details about backing up and restoring Lync Server 2010, see [http://go.microsoft.com/fwlink/p/?linkId=265417](http://go.microsoft.com/fwlink/p/?linkid=265417) .</span></span> <span data-ttu-id="210b1-215">Pour plus d’informations sur la sauvegarde et la restauration de Microsoft Office Communications Server 2007 [http://go.microsoft.com/fwlink/p/?linkId=168162](http://go.microsoft.com/fwlink/p/?linkid=168162)R2, voir.</span><span class="sxs-lookup"><span data-stu-id="210b1-215">For details about backing up and restoring Microsoft Office Communications Server 2007 R2, see [http://go.microsoft.com/fwlink/p/?linkId=168162](http://go.microsoft.com/fwlink/p/?linkid=168162).</span></span>

  - <span data-ttu-id="210b1-216">**Informations d’infrastructure**   vous devez sauvegarder des informations relatives à votre infrastructure, telles que la configuration de votre pare-feu, la configuration de l’équilibrage de charge, la configuration d’Internet Information Services (IIS), les enregistrements DNS (Domain Name System) et Les adresses IP et la configuration DHCP (Dynamic Host Configuration Protocol).</span><span class="sxs-lookup"><span data-stu-id="210b1-216">**Infrastructure information**   You need to back up information about your infrastructure, such as your firewall configuration, load balancing configuration, Internet Information Services (IIS) configuration, Domain Name System (DNS) records and IP addresses, and Dynamic Host Configuration Protocol (DHCP) configuration.</span></span> <span data-ttu-id="210b1-217">Pour plus d’informations sur la sauvegarde de ces composants, contactez leurs fournisseurs respectifs.</span><span class="sxs-lookup"><span data-stu-id="210b1-217">For details about backing up these components, check with their respective vendors.</span></span>

  - <span data-ttu-id="210b1-218">**Microsoft Exchange et Exchange Unified Messaging (um)**   sauvegarde et restauration de Microsoft Exchange et Exchange um comme décrit dans la documentation Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="210b1-218">**Microsoft Exchange and Exchange Unified Messaging (UM)**   Backup and restore Microsoft Exchange and Exchange UM as described in the Microsoft Exchange documentation.</span></span> <span data-ttu-id="210b1-219">Pour plus d’informations sur la sauvegarde et la restauration d’Exchange Server [http://go.microsoft.com/fwlink/?LinkId=285384](http://go.microsoft.com/fwlink/?linkid=285384)2013, voir.</span><span class="sxs-lookup"><span data-stu-id="210b1-219">For details about backing up and restoring Exchange Server 2013, see [http://go.microsoft.com/fwlink/?LinkId=285384](http://go.microsoft.com/fwlink/?linkid=285384).</span></span> <span data-ttu-id="210b1-220">Pour plus d’informations sur la sauvegarde et la restauration d’Exchange Server [http://go.microsoft.com/fwlink/p/?linkId=209179](http://go.microsoft.com/fwlink/p/?linkid=209179)2010, voir.</span><span class="sxs-lookup"><span data-stu-id="210b1-220">For details about backing up and restoring Exchange Server 2010, see [http://go.microsoft.com/fwlink/p/?linkId=209179](http://go.microsoft.com/fwlink/p/?linkid=209179).</span></span>
    
    <span data-ttu-id="210b1-221">Notez que Lync Server 2013 offre la possibilité d’utiliser les listes de contacts de l’utilisateur, les photos haute définition et les données d’archivage stockées dans Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="210b1-221">Note that Lync Server 2013 introduces the ability to have user contact lists, high definition user photos, and archiving data stored in Exchange 2013.</span></span> <span data-ttu-id="210b1-222">Pour plus d’informations sur la sauvegarde de ces types de données, consultez la liste suivante:</span><span class="sxs-lookup"><span data-stu-id="210b1-222">See the following list to see how to back up these types of data:</span></span>
    
      - <span data-ttu-id="210b1-223">Les **photos haute définition** sont sauvegardées dans le cadre de la sauvegarde du serveur Exchange.</span><span class="sxs-lookup"><span data-stu-id="210b1-223">**High definition photos** are backed up as part of the Exchange Server backup.</span></span>
    
      - <span data-ttu-id="210b1-224">Le **magasin de contacts unifié** est présenté dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="210b1-224">**Unified contact store** is introduced in Lync Server 2013.</span></span> <span data-ttu-id="210b1-225">Un magasin de contacts unifié permet aux utilisateurs de conserver toutes leurs informations de contact dans Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="210b1-225">Unified contact store enables users to keep all their contact information in Exchange 2013.</span></span>
        
        <span data-ttu-id="210b1-226">Assurez-vous que les sauvegardes sont à jour pour les utilisateurs en termes de stockage ou de gestion des contacts de l’utilisateur dans le magasin de contacts unifié ou sur le serveur principal Lync.</span><span class="sxs-lookup"><span data-stu-id="210b1-226">You should make sure that backups are up-to-date for users in terms of whether their user contacts are stored in the unified contact store or on the Lync Back End Server.</span></span> <span data-ttu-id="210b1-227">Les scénarios suivants vous montrent où la migration de contacts utilisateur vers le magasin de contacts unifié peut provoquer des problèmes pour le processus de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="210b1-227">The following scenarios illustrate where migrating user contacts to the unified contact store can cause issues for the backup and restore process.</span></span>
        
        <span data-ttu-id="210b1-228">**Scénario 1:** Les contacts des utilisateurs sont déplacés vers le magasin de contacts unifié, et une restauration est effectuée à partir d’une sauvegarde de serveur Lync prélevée avant la migration des contacts utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="210b1-228">**Scenario 1:** User contacts are migrated to the unified contact store, and a restore is performed from a Lync Server backup taken prior to the migration of user contacts.</span></span> <span data-ttu-id="210b1-229">Dans ce scénario, l’utilisateur aura un état de contacts obsolètes jusqu’à un jour jusqu’à ce que la tâche de migration de Lync Server commence à migrer les contacts de l’utilisateur vers Exchange.</span><span class="sxs-lookup"><span data-stu-id="210b1-229">In this scenario, the user will have a state of outdated contacts for up to one day until Lync Server Migration Task begins migrating user contacts to Exchange.</span></span> <span data-ttu-id="210b1-230">(Notez que, dans la mesure où les contacts de l’utilisateur ont été précédemment transférés dans le magasin de contacts unifié, les informations de contact Exchange seront utilisées).</span><span class="sxs-lookup"><span data-stu-id="210b1-230">(Note that because the user contacts were previously migrated to the unified contact store, the Exchange contact information will be used).</span></span> <span data-ttu-id="210b1-231">Ce scénario ne nécessite aucune intervention de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="210b1-231">No administrator intervention is needed in this scenario.</span></span>
        
        <span data-ttu-id="210b1-232">**Scénario 2:** Les contacts des utilisateurs étaient auparavant stockés dans le magasin de contacts unifié, puis restaurés.</span><span class="sxs-lookup"><span data-stu-id="210b1-232">**Scenario 2:** User contacts were previously stored in the unified contact store, but then rolled back.</span></span> <span data-ttu-id="210b1-233">Une restauration est effectuée à partir d’une sauvegarde de serveur Lync effectuée lorsque les contacts de l’utilisateur ont été stockés dans le magasin de contacts unifié.</span><span class="sxs-lookup"><span data-stu-id="210b1-233">A restore is performed from a Lync Server backup taken when the user contacts were stored in the unified contact store.</span></span> <span data-ttu-id="210b1-234">Dans ce scénario, un message d’erreur `Error: Incorrect Exchange Version` figurant dans les journaux du client ou du serveur Lyss est susceptible de signaler un problème.</span><span class="sxs-lookup"><span data-stu-id="210b1-234">In this scenario, an error message of `Error: Incorrect Exchange Version` in the client or Lyss server logs may indicate this as an issue.</span></span> <span data-ttu-id="210b1-235">L’utilisateur sera en mesure d’accéder à sa liste de contacts dans Lync 2013 directement à partir d’Exchange, mais l’état du client ne correspond pas à l’état du serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="210b1-235">The user will be able to access their contact list in Lync 2013 directly from Exchange, but client’s state will not match the Lync Server state.</span></span> <span data-ttu-id="210b1-236">Pour résoudre ce problème, un administrateur doit exécuter les applets de cmdlet **Invoke-CsUCSRollback** pour les utilisateurs concernés.</span><span class="sxs-lookup"><span data-stu-id="210b1-236">To fix this, an administrator will need to run the **Invoke-CsUCSRollback** cmdlets for the affected users.</span></span>
    
      - <span data-ttu-id="210b1-237">Les **données** d’archivage peuvent être stockées dans Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="210b1-237">**Archiving Data** can be stored in Exchange 2013.</span></span> <span data-ttu-id="210b1-238">Cette information n’est pas essentielle pour Lync Server, mais elle peut être essentielle pour les fins réglementaires de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="210b1-238">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="210b1-239">Si les données d’archivage sont stockées dans Exchange et sont importantes pour votre organisation, suivez les procédures de sauvegarde et de restauration d’Exchange.</span><span class="sxs-lookup"><span data-stu-id="210b1-239">If archiving data is stored in Exchange and is critical to your organization, then follow Exchange backup and restore procedures.</span></span> <span data-ttu-id="210b1-240">Notez que les données d’archivage stockées dans Exchange ne peuvent pas être replacées sur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="210b1-240">Note that archiving data stored in Exchange cannot be moved back to Lync Server.</span></span> <span data-ttu-id="210b1-241">Par ailleurs, il est impossible de déplacer des données déjà stockées dans la base de données d’archivage Lync vers Exchange.</span><span class="sxs-lookup"><span data-stu-id="210b1-241">Additionally, there is no way to move data already stored in the Lync archiving database to Exchange.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

