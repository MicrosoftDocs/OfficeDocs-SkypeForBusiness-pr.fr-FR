---
title: 'Lync Server 2013 : Planification de la récupération d’urgence des groupes Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70622364349eb83ecbc171cb3d5bf894ba03d3f9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="25a7d-102">Planification de la récupération d’urgence des groupes Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25a7d-102">Planning for response group disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25a7d-103">_**Dernière modification de la rubrique:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="25a7d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="25a7d-104">Cette section décrit quelques méthodes permettant de préparer des groupes de réponse pour une reprise après sinistre et offre une vue d’ensemble du processus de reprise après sinistre.</span><span class="sxs-lookup"><span data-stu-id="25a7d-104">This section describes some ways to prepare response groups for disaster recovery and provides an overview of the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a><span data-ttu-id="25a7d-105">Préparation de la reprise après sinistre de Response Group</span><span class="sxs-lookup"><span data-stu-id="25a7d-105">Preparing for Response Group Disaster Recovery</span></span>

<span data-ttu-id="25a7d-106">Gardez les points suivants à l’esprit lorsque vous préparez et mettez en oeuvre des procédures de reprise après sinistre.</span><span class="sxs-lookup"><span data-stu-id="25a7d-106">Keep the following in mind when you prepare for and carry out disaster recovery procedures.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="25a7d-107">Dans un environnement de coexistence, seuls les groupes de réponse Lync Server 2013 sont pris en charge pour les procédures de reprise après sinistre décrites dans ce document.</span><span class="sxs-lookup"><span data-stu-id="25a7d-107">In a coexistence environment, only the Lync Server 2013 response groups are supported for the disaster recovery procedures described in this document.</span></span>



</div>

  - <span data-ttu-id="25a7d-108">Prévoyez une reprise après sinistre lors de la planification de la capacité.</span><span class="sxs-lookup"><span data-stu-id="25a7d-108">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="25a7d-109">Pour la capacité de reprise après sinistre, chaque pool dans un pool couplé doit être en mesure de gérer les charges de travail de tous les groupes de réponses dans les deux pools.</span><span class="sxs-lookup"><span data-stu-id="25a7d-109">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of all the response groups in both pools.</span></span> <span data-ttu-id="25a7d-110">Pour plus d’informations sur la planification de la capacité du groupe de réponse, voir [planification de la capacité pour le groupe réponse dans Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span><span class="sxs-lookup"><span data-stu-id="25a7d-110">For details about Response Group capacity planning, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span></span>

  - <span data-ttu-id="25a7d-111">Prenez des copies de sauvegarde régulières de toutes les configurations de Response Group dans tous les pools frontaux dans lesquels vous avez déployé l’application Response Group à l’aide de la procédure d’exportation décrite dans ce document.</span><span class="sxs-lookup"><span data-stu-id="25a7d-111">Take regular backup copies of all the response group configurations in all the Front End pools where you deployed the Response Group application by using the export procedure described in this document.</span></span> <span data-ttu-id="25a7d-112">Pour plus d’informations, consultez [procédures de rétablissement de sinistre de Response Group dans Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="25a7d-112">For details, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span> <span data-ttu-id="25a7d-113">Conservez les copies de sauvegarde dans un emplacement sûr.</span><span class="sxs-lookup"><span data-stu-id="25a7d-113">Keep the backup copies in a safe location.</span></span>

  - <span data-ttu-id="25a7d-114">Conservez une copie de sauvegarde séparée de tous les fichiers audio d’origine que vous avez utilisés pour l’application Response Group, y compris tous les enregistrements et fichiers musicaux en attente.</span><span class="sxs-lookup"><span data-stu-id="25a7d-114">Keep a separate backup copy of all the original audio files you used for the Response Group application, including any recordings and music-on-hold files.</span></span> <span data-ttu-id="25a7d-115">Conservez les fichiers de sauvegarde dans un emplacement sûr.</span><span class="sxs-lookup"><span data-stu-id="25a7d-115">Keep the backup files in a safe location.</span></span>

  - <span data-ttu-id="25a7d-116">Dans le cas d’une reprise après sinistre Lync Server 2013, tous les paramètres de groupe de réponse doivent avoir des noms uniques au sein de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="25a7d-116">For Lync Server 2013 disaster recovery, all Response Group settings must have unique names across your deployment.</span></span> <span data-ttu-id="25a7d-117">Cette condition s’applique aux flux de travail, files d’attente, groupes d’agents, jours fériés et heures d’activité.</span><span class="sxs-lookup"><span data-stu-id="25a7d-117">This requirement applies to workflows, queues, agent groups, holiday sets, and hours of business.</span></span> <span data-ttu-id="25a7d-118">Assurez-vous que cette obligation est remplie lorsque les pools principal et de sauvegarde sont toujours actifs et avant d’avoir besoin de démarrer une procédure de reprise.</span><span class="sxs-lookup"><span data-stu-id="25a7d-118">You should verify that this requirement is met when the primary and backup pools are still active, and before you need to initiate any failover procedure.</span></span> <span data-ttu-id="25a7d-119">Si vous rencontrez des conflits de nom lorsque vous importez des données de groupe de réponse au pool de sauvegarde, l’importation échoue.</span><span class="sxs-lookup"><span data-stu-id="25a7d-119">If you encounter name conflicts while importing response group data to the backup pool, the import fails.</span></span> <span data-ttu-id="25a7d-120">Pour achever la procédure d’importation et de basculement, vous devez résoudre les conflits de noms en renommant l’objet Response Group dans le pool de sauvegarde ou en utilisant l’applet de passe **Import-CsRgsConfiguration** avec le paramètre-ResolveNameConflicts automatiquement. Résolvez le conflit en ajoutant un numéro d’identification unique à l’objet Response Group.</span><span class="sxs-lookup"><span data-stu-id="25a7d-120">To complete the import and failover procedure, you need to resolve the name conflicts by renaming the response group object in the backup pool or by using the **Import-CsRgsConfiguration** cmdlet with the –ResolveNameConflicts parameter to automatically resolve the conflict by appending a unique identifying number to the response group object.</span></span>

  - <span data-ttu-id="25a7d-121">En règle générale, il est recommandé d’effectuer des sauvegardes journalières, mais si vous avez un volume élevé de modifications, vous souhaiterez peut-être planifier des sauvegardes plus fréquentes.</span><span class="sxs-lookup"><span data-stu-id="25a7d-121">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="25a7d-122">La quantité d’informations que vous pouvez perdre en cas de sinistre dépend de la fréquence de vos sauvegardes, ainsi que de la fréquence et du volume des modifications.</span><span class="sxs-lookup"><span data-stu-id="25a7d-122">The amount of information you can lose in the event of a disaster depends on the frequency of your backups, as well as the frequency and volume of changes.</span></span>

  - <span data-ttu-id="25a7d-123">Il est possible d’importer des groupes de réponses dans un pool de sauvegarde avant qu’une opération de secours ou de reprise ne se produise.</span><span class="sxs-lookup"><span data-stu-id="25a7d-123">It is possible to import response groups to a backup pool before a disaster or failover operation occurs.</span></span> <span data-ttu-id="25a7d-124">L’importation de groupes de réponse à l’avance réduit les temps d’arrêt, car le service du groupe de réponse du serveur Lync peut être restauré dans le pool de sauvegarde dès que les appels sont routés vers le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="25a7d-124">Importing response groups in advance reduces downtime, because the Lync Server Response Group service can be restored in the backup pool as soon as calls are routed to the backup pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="25a7d-125">L’application Response Group ne peut pas accéder aux agents hébergés dans un pool inactif jusqu’à ce que le basculement soit terminé.</span><span class="sxs-lookup"><span data-stu-id="25a7d-125">The Response Group application cannot reach any agents homed in an inactive pool until failover is complete.</span></span> <span data-ttu-id="25a7d-126">Pendant ce temps, l’application du groupe de réponse traite les appels comme s’ils ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="25a7d-126">During this time, the Response Group application processes calls as if those agents are unavailable.</span></span>

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a><span data-ttu-id="25a7d-127">Processus de récupération d’urgence de Response Group</span><span class="sxs-lookup"><span data-stu-id="25a7d-127">Response Group Disaster Recovery Process</span></span>

<span data-ttu-id="25a7d-128">Dans le cas d’un sinistre, vous pouvez récupérer des groupes de réponse en utilisant l’une des approches suivantes:</span><span class="sxs-lookup"><span data-stu-id="25a7d-128">In the event of a disaster, you can recover response groups by using either of the following recovery approaches:</span></span>

  - <span data-ttu-id="25a7d-129">Basculez vers un pool de sauvegarde, puis restaurez le pool d’origine.</span><span class="sxs-lookup"><span data-stu-id="25a7d-129">Fail over to a backup pool and then fail back to the original pool.</span></span>

  - <span data-ttu-id="25a7d-130">Basculez vers un pool de sauvegarde, créez un nouveau pool avec un nom de domaine complet différent (FQDN), puis importez les groupes de réponses dans le nouveau pool.</span><span class="sxs-lookup"><span data-stu-id="25a7d-130">Fail over to a backup pool, create a new pool with a different fully qualified domain name (FQDN), and then import the response groups to the new pool.</span></span>

<span data-ttu-id="25a7d-131">Lors de la phase de reprise après incident, les groupes de réponse résident dans plusieurs pools: dans le pool principal (non disponible) et dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="25a7d-131">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="25a7d-132">Les groupes Response dans les deux pools ont le même nom et le même propriétaire (le pool principal), mais ils ont des parents différents.</span><span class="sxs-lookup"><span data-stu-id="25a7d-132">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span>

<span data-ttu-id="25a7d-133">Lorsque vous récupérez en créant un nouveau pool avec un nom de domaine complet différent, vous devez affecter le nouveau pool en tant que propriétaire des groupes de réponses lorsque vous les importez.</span><span class="sxs-lookup"><span data-stu-id="25a7d-133">When you recover by creating a new pool with a different FQDN, you need to assign the new pool as the owner of the response groups when you import them.</span></span> <span data-ttu-id="25a7d-134">La propriété de Response Groups reste avec le pool d’origine à moins que vous ne le réactiviez explicitement à l’aide du paramètre-OverwriteOwner avec l’applet de certification **Import-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="25a7d-134">Ownership of response groups remains with the original pool unless or until you explicitly reassign ownership by using the –OverwriteOwner parameter with the **Import-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="25a7d-135">Vous devez également utiliser le paramètre – OverwriteOwner si vous reconstruisez le pool lors de la récupération (autrement dit, la base de données du groupe de réponses est vide), que vous utilisiez ou non le même nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="25a7d-135">You also need to use the –OverwriteOwner parameter if you rebuilt the pool during the recovery (that is, the Response Group database is empty), whether or not you use the same FQDN.</span></span> <span data-ttu-id="25a7d-136">Vous n’avez pas besoin d’utiliser le paramètre – OverwriteOwner si vous n’avez pas rérégénéré le pool, mais il est autorisé à utiliser ce paramètre chaque fois que vous importez les groupes de réponses vers le pool principal.</span><span class="sxs-lookup"><span data-stu-id="25a7d-136">You do not need to use the –OverwriteOwner parameter if you did not rebuild the pool, but it is permissible to use this parameter whenever you import response groups back to the primary pool.</span></span>



</div>

<span data-ttu-id="25a7d-137">Vous ne pouvez définir qu’un ensemble de paramètres de configuration de groupe de réponse au niveau de l’application par liste.</span><span class="sxs-lookup"><span data-stu-id="25a7d-137">You can define only one set of application-level Response Group configuration settings per pool.</span></span> <span data-ttu-id="25a7d-138">Il s’agit de la configuration par défaut de Music-Holding, du fichier audio de musique par défaut, de la période de grâce aux retours d’appel d’agent et de la configuration du contexte d’appel.</span><span class="sxs-lookup"><span data-stu-id="25a7d-138">These settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="25a7d-139">Pour afficher ces paramètres de configuration, exécutez l’applet **de passe Get-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="25a7d-139">To view these configuration settings, run the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="25a7d-140">Pour plus d’informations sur l’applet de connexion **Get-CsRgsConfiguration** , voir [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span><span class="sxs-lookup"><span data-stu-id="25a7d-140">For details about the **Get-CsRgsConfiguration** cmdlet, see [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span></span>

<span data-ttu-id="25a7d-141">Vous pouvez transférer ces paramètres au niveau de l’application d’un pool à un autre à l’aide de l’applet de passe **Import-CsRgsConfiguration** à l’aide du paramètre-ReplaceExistingSettings, mais cela a pour effet de remplacer les paramètres du pool de destination.</span><span class="sxs-lookup"><span data-stu-id="25a7d-141">You can transfer these application-level settings from one pool to another by using the **Import-CsRgsConfiguration** cmdlet with the –ReplaceExistingSettings parameter, but doing so overrides the settings in the destination pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="25a7d-142">Cette contrainte concernant le transfert des paramètres vers un autre pool est vraie uniquement pour les paramètres au niveau de l’application et le fichier audio par défaut de musique.</span><span class="sxs-lookup"><span data-stu-id="25a7d-142">This constraint about transferring settings to another pool is true only for the application-level settings and the default music-on-hold audio file.</span></span> <span data-ttu-id="25a7d-143">Cela ne s’applique pas aux groupes d’agents, files d’attente, flux de travail, heures d’activité et ensembles de jours fériés.</span><span class="sxs-lookup"><span data-stu-id="25a7d-143">It does not apply to agent groups, queues, workflows, business hours, and holiday sets.</span></span>



</div>

<span data-ttu-id="25a7d-144">Si vous ne voulez pas remplacer les paramètres au niveau de l’application dans le pool de sauvegarde en cours de sinistre et que le pool principal ne peut pas être récupéré, les paramètres au niveau de l’application du pool principal seront perdus.</span><span class="sxs-lookup"><span data-stu-id="25a7d-144">If you don't want to replace the application-level settings in the backup pool during a disaster and the primary pool can't be recovered, the application-level settings from the primary pool will be lost.</span></span> <span data-ttu-id="25a7d-145">Si vous avez besoin de créer un nouveau pool pour remplacer le pool principal lors de la récupération, avec le même nom de domaine complet ou un nom de domaine complet différent, vous ne pouvez pas récupérer les paramètres au niveau de l’application d’origine.</span><span class="sxs-lookup"><span data-stu-id="25a7d-145">If you need to create a new pool to replace the primary pool during recovery, either with the same FQDN or with a different FQDN, you can't recover the original application-level settings.</span></span> <span data-ttu-id="25a7d-146">Dans ce cas, vous devez configurer le nouveau pool avec ces paramètres et inclure le fichier audio de musique en attente.</span><span class="sxs-lookup"><span data-stu-id="25a7d-146">In this case, you need to configure the new pool with these settings and include the music-on-hold audio file.</span></span>

<span data-ttu-id="25a7d-147">Si vous décidez d’utiliser l’applet de cmdlet **Import-CsRgsConfiguration** pour transférer des paramètres au niveau de l’application à partir du pool principal vers le pool de sauvegarde en cours de sinistre, vous pouvez ensuite transférer les paramètres du pool de sauvegarde vers le nouveau pool lors de la récupération dans le même façon dont vous les avez transférés du pool principal vers le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="25a7d-147">If you decide to use the **Import-CsRgsConfiguration** cmdlet to transfer application-level settings from the primary pool to the backup pool during a disaster, you can then transfer the settings from the backup pool to the new pool during recovery in the same way that you transferred them from the primary pool to the backup pool.</span></span>

<span data-ttu-id="25a7d-148">Le tableau suivant est une vue d’ensemble des étapes nécessaires à la récupération de Response groups.</span><span class="sxs-lookup"><span data-stu-id="25a7d-148">The following table is an overview of the steps involved in recovering response groups.</span></span>

<span data-ttu-id="25a7d-149">Pour plus d’informations sur l’exécution de ces étapes, voir [procédures de reprise après sinistre de Response Group dans Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="25a7d-149">For details about performing these steps, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span>

### <a name="response-group-disaster-recovery-steps"></a><span data-ttu-id="25a7d-150">Étapes de la reprise après sinistre de Response Group</span><span class="sxs-lookup"><span data-stu-id="25a7d-150">Response Group Disaster Recovery Steps</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25a7d-151">Phase</span><span class="sxs-lookup"><span data-stu-id="25a7d-151">Phase</span></span></th>
<th><span data-ttu-id="25a7d-152">Étapes</span><span class="sxs-lookup"><span data-stu-id="25a7d-152">Steps</span></span></th>
<th><span data-ttu-id="25a7d-153">Groupes et rôles requis</span><span class="sxs-lookup"><span data-stu-id="25a7d-153">Required groups and roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25a7d-154">Avant interruption</span><span class="sxs-lookup"><span data-stu-id="25a7d-154">Before outage</span></span></p></td>
<td><p><span data-ttu-id="25a7d-155">D’un point de vue régulier, exécutez l’applet de demande <strong>Export-CsRgsConfiguration</strong> pour créer des copies de sauvegarde de toutes les configurations de Response Group dans tous les pools frontaux dans lesquels l’application Response Group est déployée.</span><span class="sxs-lookup"><span data-stu-id="25a7d-155">On a routine basis, run the <strong>Export-CsRgsConfiguration</strong> cmdlet to create backups of all Response Group configurations in all Front End pools where Response Group application is deployed.</span></span></p></td>
<td><p><span data-ttu-id="25a7d-156">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="25a7d-156">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="25a7d-157">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="25a7d-157">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a7d-158">Pendant la période d’interruption</span><span class="sxs-lookup"><span data-stu-id="25a7d-158">During outage</span></span></p></td>
<td><p><span data-ttu-id="25a7d-159">Exécutez l’applet de action <strong>Import-CsRgsConfiguration</strong> pour importer la configuration de service de groupe de réponses du serveur Lync</span><span class="sxs-lookup"><span data-stu-id="25a7d-159">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the backed up Lync Server Response Group service configuration from the primary pool to the backup pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="25a7d-160">Utilisez le paramètre – ReplaceExistingSettings si vous voulez remplacer les paramètres du groupe de réponses au niveau de l’application dans le pool de sauvegarde par les paramètres de la liste principale.</span><span class="sxs-lookup"><span data-stu-id="25a7d-160">Use the –ReplaceExistingSettings parameter if you want to replace application-level Response Group settings in the backup pool with the settings from the primary pool.</span></span> <span data-ttu-id="25a7d-161">Si vous ne transférez pas les paramètres au niveau de l’application du pool principal vers le pool de sauvegarde et que le pool principal ne peut pas être récupéré, vous perdrez les paramètres du pool principal.</span><span class="sxs-lookup"><span data-stu-id="25a7d-161">If you do not transfer the application-level settings from the primary pool to the backup pool, and the primary pool can't be recovered, you will lose the settings from the primary pool.</span></span>


</div></td>
<td><p><span data-ttu-id="25a7d-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="25a7d-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="25a7d-163">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="25a7d-163">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a7d-164">Après importation</span><span class="sxs-lookup"><span data-stu-id="25a7d-164">After importing</span></span></p></td>
<td><p><span data-ttu-id="25a7d-165">Exécutez les applets de contrôle de Response Group avec le paramètre – ShowAll (pour afficher tous les groupes de réponse) ou le paramètre – Owner (pour afficher uniquement les groupes de réponse importés) pour vérifier que toutes les configurations de Response Group ont été importées dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="25a7d-165">Run Response Group cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were imported to the backup pool.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="25a7d-166">Si vous n’utilisez pas le paramètre – ShowAll ou – Owner, les groupes de réponse que vous avez importés dans le pool de sauvegarde ne seront pas répertoriés dans les résultats renvoyés par les applets de requête.</span><span class="sxs-lookup"><span data-stu-id="25a7d-166">If you do not use either the –ShowAll parameter or the –Owner parameter, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>


</div>
<p><span data-ttu-id="25a7d-167">Exécutez les applets de commande suivantes:</span><span class="sxs-lookup"><span data-stu-id="25a7d-167">Run the following cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="25a7d-168"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="25a7d-168"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="25a7d-169"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="25a7d-169"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="25a7d-170"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="25a7d-170"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="25a7d-171"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="25a7d-171"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="25a7d-172"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="25a7d-172"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="25a7d-173">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="25a7d-173">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="25a7d-174">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="25a7d-174">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a7d-175">Après le basculement</span><span class="sxs-lookup"><span data-stu-id="25a7d-175">After failover</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="25a7d-176">Passez un appel de test vers un groupe de réponse importé dans le pool de sauvegarde et vérifiez que l’appel est géré correctement.</span><span class="sxs-lookup"><span data-stu-id="25a7d-176">Place a test call to a response group that was imported to the backup pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="25a7d-177">Tous les agents officiels doivent se connecter à leur groupe formel sur le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="25a7d-177">All formal agents must sign in again to their formal groups on backup pool.</span></span></p></li>
<li><p><span data-ttu-id="25a7d-178">Gérer les modifications de configuration:</span><span class="sxs-lookup"><span data-stu-id="25a7d-178">Manage configuration changes:</span></span></p>
<p><span data-ttu-id="25a7d-179">Les groupes de réponses du pool de sauvegarde, qu’ils soient importés dans le pool de sauvegarde ou qui appartiennent au pool de sauvegarde, peuvent être modifiés comme d’habitude pendant la période d’interruption.</span><span class="sxs-lookup"><span data-stu-id="25a7d-179">Response groups in the backup pool, whether imported to the backup pool or owned by the backup pool, can be modified as usual during the outage.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="25a7d-180">Vous devez utiliser Lync Server Management Shell pour gérer les groupes de réponse que vous avez importés dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="25a7d-180">You must use Lync Server Management Shell to manage the response groups that you imported to the backup pool.</span></span> <span data-ttu-id="25a7d-181">Vous ne pouvez pas utiliser le panneau de configuration de Lync Server pour gérer ces groupes de réponse alors qu’ils se trouvent dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="25a7d-181">You cannot use Lync Server Control Panel to manage these response groups while they are in the backup pool.</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="25a7d-182">S/O</span><span class="sxs-lookup"><span data-stu-id="25a7d-182">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a7d-183">Après récupération, avant la restauration automatique</span><span class="sxs-lookup"><span data-stu-id="25a7d-183">After recovery, before failback</span></span></p></td>
<td><p><span data-ttu-id="25a7d-184">Exécutez l’applet de recherche <strong>Export-CsRgsConfiguration</strong> en spécifiant le paramètre-source en tant que pool de sauvegarde et le paramètre – owner comme pool principal pour exporter les groupes de réponse appartenant au pool principal du pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="25a7d-184">Run the <strong>Export-CsRgsConfiguration</strong> cmdlet specifying the -Source parameter as the backup pool and the –Owner parameter as the primary pool to export the response groups owned by the primary pool from the backup pool.</span></span></p></td>
<td><p><span data-ttu-id="25a7d-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="25a7d-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="25a7d-186">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="25a7d-186">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a7d-187">Après la restauration automatique</span><span class="sxs-lookup"><span data-stu-id="25a7d-187">After failback</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="25a7d-188">Exécutez l’applet de passe <strong>Import-CsRgsConfiguration</strong> pour importer les groupes de réponses dans le pool principal.</span><span class="sxs-lookup"><span data-stu-id="25a7d-188">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the response groups back to the primary pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="25a7d-189">Si le pool principal ne peut pas être récupéré et que vous déployez un nouveau pool pour le remplacer, utilisez le paramètre – ReplaceExistingSettings pour transférer les paramètres au niveau de l’application du pool de sauvegarde vers le nouveau pool.</span><span class="sxs-lookup"><span data-stu-id="25a7d-189">If the primary pool can't be recovered and you deploy a new pool to replace it, use the –ReplaceExistingSettings parameter to transfer the application-level settings from the backup pool to the new pool.</span></span> <span data-ttu-id="25a7d-190">Si vous ne transférez pas les paramètres à partir du pool de sauvegarde, le nouveau pool utilisera les paramètres par défaut.</span><span class="sxs-lookup"><span data-stu-id="25a7d-190">If you do not transfer the settings from the backup pool, the new pool will use the default settings.</span></span>


</div></li>
<li><p><span data-ttu-id="25a7d-191">Exécutez les applets de commande suivantes à l’aide du paramètre – ShowAll (pour afficher tous les groupes de réponse) ou du paramètre – Owner (pour afficher uniquement les groupes de réponse importés) pour vérifier que toutes les configurations de Response Group ont été correctement importées dans le pool principal:</span><span class="sxs-lookup"><span data-stu-id="25a7d-191">Run the following cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were successfully imported back to the primary pool:</span></span></p>
<ul>
<li><p><span data-ttu-id="25a7d-192"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="25a7d-192"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="25a7d-193"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="25a7d-193"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="25a7d-194"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="25a7d-194"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="25a7d-195"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="25a7d-195"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="25a7d-196"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="25a7d-196"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="25a7d-197">Effectuez un test d’appel vers un groupe de réponse qui a été réimporté dans le pool principal, puis vérifiez que l’appel est géré correctement.</span><span class="sxs-lookup"><span data-stu-id="25a7d-197">Place a test call to a response group that was imported back to the primary pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="25a7d-198">Vous pouvez également exécuter l’applet de commande <strong>Export-CsRgsConfiguration</strong> sur le pool de sauvegarde avec le paramètre – RemoveExportedConfiguration pour supprimer les groupes de réponse appartenant au pool principal du pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="25a7d-198">Optionally, run the <strong>Export-CsRgsConfiguration</strong> cmdlet on the backup pool with the –RemoveExportedConfiguration parameter to remove the response groups owned by the primary pool from the backup pool.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="25a7d-199">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="25a7d-199">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="25a7d-200">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="25a7d-200">CsResponseGroupAdministrator</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

