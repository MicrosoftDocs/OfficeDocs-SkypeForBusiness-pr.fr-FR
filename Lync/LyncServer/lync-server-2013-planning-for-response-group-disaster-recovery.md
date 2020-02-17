---
title: 'Lync Server 2013 : planification de la récupération d’urgence de Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 049e07e72efba508add2135c6b77aebed2c38954
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="19ff0-102">Planification de la récupération d’urgence de Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19ff0-102">Planning for response group disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19ff0-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="19ff0-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="19ff0-104">Cette section explique comment préparer la récupération d’urgence des groupes Response Group et présente le processus de récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="19ff0-104">This section describes some ways to prepare response groups for disaster recovery and provides an overview of the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a><span data-ttu-id="19ff0-105">Préparation de la récupération d’urgence de Response Group</span><span class="sxs-lookup"><span data-stu-id="19ff0-105">Preparing for Response Group Disaster Recovery</span></span>

<span data-ttu-id="19ff0-106">Gardez les points suivants à l’esprit lorsque vous préparez et réalisez des procédures de récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="19ff0-106">Keep the following in mind when you prepare for and carry out disaster recovery procedures.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="19ff0-107">Dans un environnement de coexistence, seuls les groupes Response Group de Lync Server 2013 sont pris en charge pour les procédures de récupération d’urgence décrites dans ce document.</span><span class="sxs-lookup"><span data-stu-id="19ff0-107">In a coexistence environment, only the Lync Server 2013 response groups are supported for the disaster recovery procedures described in this document.</span></span>



</div>

  - <span data-ttu-id="19ff0-108">Planifiez la récupération d’urgence lorsque vous effectuez votre planification de capacité.</span><span class="sxs-lookup"><span data-stu-id="19ff0-108">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="19ff0-109">Pour la capacité de la récupération d’urgence, chaque pool d’un pool jumelé doit être capable de gérer les charges de travail de tous les groupes Response Group dans les deux pools.</span><span class="sxs-lookup"><span data-stu-id="19ff0-109">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of all the response groups in both pools.</span></span> <span data-ttu-id="19ff0-110">Pour plus d’informations sur la planification de la capacité des groupes Response Group, voir [Capacity Planning for Response Group dans Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span><span class="sxs-lookup"><span data-stu-id="19ff0-110">For details about Response Group capacity planning, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span></span>

  - <span data-ttu-id="19ff0-111">Effectuez des copies de sauvegarde régulières de toutes les configurations de groupes Response Group dans tous les pools frontaux où vous avez déployé l’application Response Group à l’aide de la procédure d’exportation décrite dans ce document.</span><span class="sxs-lookup"><span data-stu-id="19ff0-111">Take regular backup copies of all the response group configurations in all the Front End pools where you deployed the Response Group application by using the export procedure described in this document.</span></span> <span data-ttu-id="19ff0-112">Pour plus d’informations, voir [Response Group Disaster Recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="19ff0-112">For details, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span> <span data-ttu-id="19ff0-113">Conservez les copies de sauvegarde en lieu sûr.</span><span class="sxs-lookup"><span data-stu-id="19ff0-113">Keep the backup copies in a safe location.</span></span>

  - <span data-ttu-id="19ff0-114">Conservez une copie de sauvegarde distincte de tous les fichiers audio d’origine utilisés pour l’application Response Group, y compris les enregistrements et les fichiers de conservation de la musique.</span><span class="sxs-lookup"><span data-stu-id="19ff0-114">Keep a separate backup copy of all the original audio files you used for the Response Group application, including any recordings and music-on-hold files.</span></span> <span data-ttu-id="19ff0-115">Conservez les fichiers de sauvegarde en lieu sûr.</span><span class="sxs-lookup"><span data-stu-id="19ff0-115">Keep the backup files in a safe location.</span></span>

  - <span data-ttu-id="19ff0-116">Pour la récupération d’urgence Lync Server 2013, tous les paramètres Response Group doivent avoir des noms uniques dans l’ensemble de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="19ff0-116">For Lync Server 2013 disaster recovery, all Response Group settings must have unique names across your deployment.</span></span> <span data-ttu-id="19ff0-117">Cette exigence s’applique aux flux de travail, files d’attente, groupes d’agents, groupes de congés et heures ouvrées.</span><span class="sxs-lookup"><span data-stu-id="19ff0-117">This requirement applies to workflows, queues, agent groups, holiday sets, and hours of business.</span></span> <span data-ttu-id="19ff0-118">Vous devez vérifier que cette exigence est remplie alors que le pool principal et le pool de sauvegarde sont encore actifs et avant de devoir initier la procédure de basculement.</span><span class="sxs-lookup"><span data-stu-id="19ff0-118">You should verify that this requirement is met when the primary and backup pools are still active, and before you need to initiate any failover procedure.</span></span> <span data-ttu-id="19ff0-119">Si vous rencontrez des conflits de noms lors de l’importation des données Response Group dans le pool de sauvegarde, l’importation échoue.</span><span class="sxs-lookup"><span data-stu-id="19ff0-119">If you encounter name conflicts while importing response group data to the backup pool, the import fails.</span></span> <span data-ttu-id="19ff0-120">Pour réaliser l’importation et la procédure de basculement, vous devez résoudre les conflits de noms en renommant l’objet Response Group dans le pool de sauvegarde ou en utilisant l’applet de commande **Import-CsRgsConfiguration** avec le paramètre –ResolveNameConflicts pour résoudre automatiquement le conflit en ajoutant un numéro unique d’identification à l’objet Response Group.</span><span class="sxs-lookup"><span data-stu-id="19ff0-120">To complete the import and failover procedure, you need to resolve the name conflicts by renaming the response group object in the backup pool or by using the **Import-CsRgsConfiguration** cmdlet with the –ResolveNameConflicts parameter to automatically resolve the conflict by appending a unique identifying number to the response group object.</span></span>

  - <span data-ttu-id="19ff0-p105">En règle générale, nous vous recommandons d’effectuer des sauvegardes quotidiennes, mais si le volume de vos changements est élevé, vous pouvez planifier des sauvegardes plus fréquentes. La quantité d’informations que vous risquez de perdre en cas d’incident dépend de la fréquence de vos sauvegardes, ainsi que de la fréquence et du volume des changements.</span><span class="sxs-lookup"><span data-stu-id="19ff0-p105">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups. The amount of information you can lose in the event of a disaster depends on the frequency of your backups, as well as the frequency and volume of changes.</span></span>

  - <span data-ttu-id="19ff0-123">Il est possible d’importer des groupes Response Group dans un pool de sauvegarde avant qu’un incident ou qu’une opération de basculement ne se produise.</span><span class="sxs-lookup"><span data-stu-id="19ff0-123">It is possible to import response groups to a backup pool before a disaster or failover operation occurs.</span></span> <span data-ttu-id="19ff0-124">L’importation de groupes Response Group à l’avance réduit le temps d’arrêt, car le service de groupe Response Group Lync Server peut être restauré dans le pool de sauvegarde dès que les appels sont routés vers le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="19ff0-124">Importing response groups in advance reduces downtime, because the Lync Server Response Group service can be restored in the backup pool as soon as calls are routed to the backup pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="19ff0-125">L’application Response Group ne peut pas atteindre les agents hébergés dans un pool inactif tant que le basculement n’est pas terminé.</span><span class="sxs-lookup"><span data-stu-id="19ff0-125">The Response Group application cannot reach any agents homed in an inactive pool until failover is complete.</span></span> <span data-ttu-id="19ff0-126">Pendant ce temps, l’application Response Group traite les appels comme si ces agents sont indisponibles.</span><span class="sxs-lookup"><span data-stu-id="19ff0-126">During this time, the Response Group application processes calls as if those agents are unavailable.</span></span>

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a><span data-ttu-id="19ff0-127">Processus de récupération d’urgence de Response Group</span><span class="sxs-lookup"><span data-stu-id="19ff0-127">Response Group Disaster Recovery Process</span></span>

<span data-ttu-id="19ff0-128">En cas d’incident, vous pouvez récupérer les groupes Response Group en suivant l’une des approches suivantes :</span><span class="sxs-lookup"><span data-stu-id="19ff0-128">In the event of a disaster, you can recover response groups by using either of the following recovery approaches:</span></span>

  - <span data-ttu-id="19ff0-129">Basculez sur un pool de sauvegarde, puis rebasculez sur le pool d’origine.</span><span class="sxs-lookup"><span data-stu-id="19ff0-129">Fail over to a backup pool and then fail back to the original pool.</span></span>

  - <span data-ttu-id="19ff0-130">Basculez sur un pool de sauvegarde, créez un nouveau pool avec un nom de domaine complet (FQDN) différent, puis importez les groupes Response Group dans le nouveau pool.</span><span class="sxs-lookup"><span data-stu-id="19ff0-130">Fail over to a backup pool, create a new pool with a different fully qualified domain name (FQDN), and then import the response groups to the new pool.</span></span>

<span data-ttu-id="19ff0-p108">Au cours de la phase de basculement de la récupération d’urgence, les groupes Response Group se trouvent dans plusieurs pools : dans le pool principal (qui est indisponible) et dans le pool de sauvegarde. Les groupes Response Group dans les deux pools portent le même nom et ont le même propriétaire (le pool principal), mais ils ont des parents différents.</span><span class="sxs-lookup"><span data-stu-id="19ff0-p108">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool. The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span>

<span data-ttu-id="19ff0-133">Lorsque vous effectuez la récupération en créant un nouveau pool avec un nom de domaine complet FQDN différent, vous devez affecter le nouveau pool comme propriétaire des groupes Response Group lorsque vous les importez.</span><span class="sxs-lookup"><span data-stu-id="19ff0-133">When you recover by creating a new pool with a different FQDN, you need to assign the new pool as the owner of the response groups when you import them.</span></span> <span data-ttu-id="19ff0-134">La propriété des groupes Response Group demeure avec le pool d’origine jusqu’à ce que vous réaffectiez explicitement la propriété à l’aide du paramètre –OverwriteOwner avec l’applet de commande **Import-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="19ff0-134">Ownership of response groups remains with the original pool unless or until you explicitly reassign ownership by using the –OverwriteOwner parameter with the **Import-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="19ff0-135">Vous devez également utiliser le paramètre – OverwriteOwner si vous avez recréé le pool pendant la récupération (autrement dit, la base de données du groupe Response Group est vide), que vous utilisiez ou non le même nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="19ff0-135">You also need to use the –OverwriteOwner parameter if you rebuilt the pool during the recovery (that is, the Response Group database is empty), whether or not you use the same FQDN.</span></span> <span data-ttu-id="19ff0-136">Vous n’avez pas besoin d’utiliser le paramètre –OverwriteOwner si vous n’avez pas créé le pool, mais il est permis d’utiliser ce paramètre lorsque vous réimportez les groupes Response Group dans le pool principal.</span><span class="sxs-lookup"><span data-stu-id="19ff0-136">You do not need to use the –OverwriteOwner parameter if you did not rebuild the pool, but it is permissible to use this parameter whenever you import response groups back to the primary pool.</span></span>



</div>

<span data-ttu-id="19ff0-137">Vous ne pouvez définir qu’un seul ensemble de paramètres de configuration de groupe Response Group par pool.</span><span class="sxs-lookup"><span data-stu-id="19ff0-137">You can define only one set of application-level Response Group configuration settings per pool.</span></span> <span data-ttu-id="19ff0-138">Ces paramètres incluent la configuration de la mise en attente musicale par défaut, le fichier audio de mise en attente musicale par défaut, la période de grâce de reprise d’appel parqué de l’agent et la configuration du contexte de l’appel.</span><span class="sxs-lookup"><span data-stu-id="19ff0-138">These settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="19ff0-139">Pour afficher ces paramètres de configuration, exécutez l’applet de commande **Get-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="19ff0-139">To view these configuration settings, run the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="19ff0-140">Pour plus d’informations sur la cmdlet **Get-applet csrgsconfiguration** , voir [Get-applet csrgsconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span><span class="sxs-lookup"><span data-stu-id="19ff0-140">For details about the **Get-CsRgsConfiguration** cmdlet, see [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span></span>

<span data-ttu-id="19ff0-141">Vous pouvez transférer ces paramètres de niveau application d’un pool à un autre à l’aide de l’applet de commande **Import-CsRgsConfiguration** avec le paramètre –ReplaceExistingSettings, mais cette opération remplace les paramètres du pool de destination.</span><span class="sxs-lookup"><span data-stu-id="19ff0-141">You can transfer these application-level settings from one pool to another by using the **Import-CsRgsConfiguration** cmdlet with the –ReplaceExistingSettings parameter, but doing so overrides the settings in the destination pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="19ff0-p112">Cette contrainte concernant le transfert des paramètres vers un autre pool est vraie uniquement pour les paramètres de niveau application et pour le fichier audio de mise en attente musicale par défaut. Elle ne s’applique pas aux groupes d’agents, aux files d’attente, aux flux de travail, aux heures ouvrées ni aux groupes de congés.</span><span class="sxs-lookup"><span data-stu-id="19ff0-p112">This constraint about transferring settings to another pool is true only for the application-level settings and the default music-on-hold audio file. It does not apply to agent groups, queues, workflows, business hours, and holiday sets.</span></span>



</div>

<span data-ttu-id="19ff0-p113">Si vous ne souhaitez pas remplacer les paramètres de niveau application dans le pool de sauvegarde en cas d’incident et que le pool principal ne peut pas être récupéré, les paramètres de niveau application du pool principal seront perdus. Si vous devez créer un nouveau pool pour remplacer le pool principal au cours de la récupération, soit avec le même nom de domaine complet FQDN, soit avec un nom de domaine complet FQDN différent, vous ne pouvez pas récupérer les paramètres de niveau application d’origine. Dans ce cas, vous devez configurer le nouveau pool avec ces paramètres et inclure le fichier audio de mise en attente musicale.</span><span class="sxs-lookup"><span data-stu-id="19ff0-p113">If you don't want to replace the application-level settings in the backup pool during a disaster and the primary pool can't be recovered, the application-level settings from the primary pool will be lost. If you need to create a new pool to replace the primary pool during recovery, either with the same FQDN or with a different FQDN, you can't recover the original application-level settings. In this case, you need to configure the new pool with these settings and include the music-on-hold audio file.</span></span>

<span data-ttu-id="19ff0-147">Si vous décidez d’utiliser l’applet de commande **Import-CsRgsConfiguration** pour transférer les paramètres de niveau application du pool principal vers le pool de sauvegarde en cas d’incident, vous pouvez dans ce cas transférer les paramètres du pool de sauvegarde vers le nouveau pool au cours de la récupération de la même manière que vous les avez transférés du pool principal vers le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="19ff0-147">If you decide to use the **Import-CsRgsConfiguration** cmdlet to transfer application-level settings from the primary pool to the backup pool during a disaster, you can then transfer the settings from the backup pool to the new pool during recovery in the same way that you transferred them from the primary pool to the backup pool.</span></span>

<span data-ttu-id="19ff0-148">Le tableau suivant présente les étapes requises pour récupérer les groupes Response Group.</span><span class="sxs-lookup"><span data-stu-id="19ff0-148">The following table is an overview of the steps involved in recovering response groups.</span></span>

<span data-ttu-id="19ff0-149">Pour plus d’informations sur l’exécution de ces étapes, voir [Response Group Disaster Recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="19ff0-149">For details about performing these steps, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span>

### <a name="response-group-disaster-recovery-steps"></a><span data-ttu-id="19ff0-150">Étapes de récupération d’urgence de Response Group</span><span class="sxs-lookup"><span data-stu-id="19ff0-150">Response Group Disaster Recovery Steps</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="19ff0-151">Phase</span><span class="sxs-lookup"><span data-stu-id="19ff0-151">Phase</span></span></th>
<th><span data-ttu-id="19ff0-152">Étapes</span><span class="sxs-lookup"><span data-stu-id="19ff0-152">Steps</span></span></th>
<th><span data-ttu-id="19ff0-153">Groupes et rôles requis</span><span class="sxs-lookup"><span data-stu-id="19ff0-153">Required groups and roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19ff0-154">Avant une panne</span><span class="sxs-lookup"><span data-stu-id="19ff0-154">Before outage</span></span></p></td>
<td><p><span data-ttu-id="19ff0-155">Sur une base de routine, exécutez l’applet de commande <strong>Export-applet csrgsconfiguration</strong> pour créer des sauvegardes de toutes les configurations Response Group dans tous les pools frontaux où l’application Response Group est déployée.</span><span class="sxs-lookup"><span data-stu-id="19ff0-155">On a routine basis, run the <strong>Export-CsRgsConfiguration</strong> cmdlet to create backups of all Response Group configurations in all Front End pools where Response Group application is deployed.</span></span></p></td>
<td><p><span data-ttu-id="19ff0-156">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="19ff0-156">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="19ff0-157">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="19ff0-157">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19ff0-158">Pendant une panne</span><span class="sxs-lookup"><span data-stu-id="19ff0-158">During outage</span></span></p></td>
<td><p><span data-ttu-id="19ff0-159">Exécutez la cmdlet <strong>Import-applet csrgsconfiguration</strong> pour importer la configuration du service de groupe Response Group Lync Server sauvegardé depuis le pool principal vers le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="19ff0-159">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the backed up Lync Server Response Group service configuration from the primary pool to the backup pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="19ff0-160">Utilisez le paramètre – ReplaceExistingSettings si vous souhaitez remplacer les paramètres de groupe Response Group au niveau de l’application dans le pool de sauvegarde par les paramètres du pool principal.</span><span class="sxs-lookup"><span data-stu-id="19ff0-160">Use the –ReplaceExistingSettings parameter if you want to replace application-level Response Group settings in the backup pool with the settings from the primary pool.</span></span> <span data-ttu-id="19ff0-161">Si vous ne transférez pas les paramètres de niveau application du pool principal vers le pool de sauvegarde, et si le pool principal ne peut pas être récupéré, vous perdrez les paramètres du pool principal.</span><span class="sxs-lookup"><span data-stu-id="19ff0-161">If you do not transfer the application-level settings from the primary pool to the backup pool, and the primary pool can't be recovered, you will lose the settings from the primary pool.</span></span>


</div></td>
<td><p><span data-ttu-id="19ff0-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="19ff0-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="19ff0-163">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="19ff0-163">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19ff0-164">Après l’importation</span><span class="sxs-lookup"><span data-stu-id="19ff0-164">After importing</span></span></p></td>
<td><p><span data-ttu-id="19ff0-165">Exécutez les applets de commande Response Group avec le paramètre – ShowAll, (pour afficher tous les groupes Response Group) ou le paramètre – Owner (pour afficher uniquement les groupes Response Group importés) afin de vérifier que toutes les configurations Response Group ont été importées dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="19ff0-165">Run Response Group cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were imported to the backup pool.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="19ff0-166">Si vous n’utilisez ni le paramètre –ShowAll, ni le paramètre –Owner, les groupes Response Group que vous avez importés dans le pool de sauvegarde ne seront pas répertoriés dans les résultats renvoyés par les applets de commande.</span><span class="sxs-lookup"><span data-stu-id="19ff0-166">If you do not use either the –ShowAll parameter or the –Owner parameter, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>


</div>
<p><span data-ttu-id="19ff0-167">Exécutez les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="19ff0-167">Run the following cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="19ff0-168"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="19ff0-168"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="19ff0-169"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="19ff0-169"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="19ff0-170"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="19ff0-170"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="19ff0-171"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="19ff0-171"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="19ff0-172"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="19ff0-172"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="19ff0-173">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="19ff0-173">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="19ff0-174">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="19ff0-174">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19ff0-175">Après un basculement</span><span class="sxs-lookup"><span data-stu-id="19ff0-175">After failover</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="19ff0-176">Effectuez un test d’appel vers un groupe Response Group qui a été importé dans le pool de sauvegarde et vérifiez que l’appel est géré correctement.</span><span class="sxs-lookup"><span data-stu-id="19ff0-176">Place a test call to a response group that was imported to the backup pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="19ff0-177">Tous les agents formels doivent se reconnecter à leurs groupes formels dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="19ff0-177">All formal agents must sign in again to their formal groups on backup pool.</span></span></p></li>
<li><p><span data-ttu-id="19ff0-178">Gérer les changements de configuration :</span><span class="sxs-lookup"><span data-stu-id="19ff0-178">Manage configuration changes:</span></span></p>
<p><span data-ttu-id="19ff0-179">Les groupes Response Group dans le pool de sauvegarde, qu’ils soient importés dans le pool de sauvegarde ou qu’ils soient la propriété du pool de sauvegarde, peuvent être modifiés comme d’habitude pendant la panne.</span><span class="sxs-lookup"><span data-stu-id="19ff0-179">Response groups in the backup pool, whether imported to the backup pool or owned by the backup pool, can be modified as usual during the outage.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="19ff0-180">Vous devez utiliser Lync Server Management Shell pour gérer les groupes Response Group que vous avez importés dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="19ff0-180">You must use Lync Server Management Shell to manage the response groups that you imported to the backup pool.</span></span> <span data-ttu-id="19ff0-181">Vous ne pouvez pas utiliser le panneau de configuration Lync Server pour gérer ces groupes Response Group pendant qu’ils se trouvent dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="19ff0-181">You cannot use Lync Server Control Panel to manage these response groups while they are in the backup pool.</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="19ff0-182">S/O</span><span class="sxs-lookup"><span data-stu-id="19ff0-182">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19ff0-183">Après une récupération, avant une restauration</span><span class="sxs-lookup"><span data-stu-id="19ff0-183">After recovery, before failback</span></span></p></td>
<td><p><span data-ttu-id="19ff0-184">Exécutez l’applet de commande <strong>Export-CsRgsConfiguration</strong> en spécifiant le paramètre -Source comme pool de sauvegarde et le paramètre –Owner comme pool principal pour exporter les groupes Response Group détenus par le pool principal à partir du pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="19ff0-184">Run the <strong>Export-CsRgsConfiguration</strong> cmdlet specifying the -Source parameter as the backup pool and the –Owner parameter as the primary pool to export the response groups owned by the primary pool from the backup pool.</span></span></p></td>
<td><p><span data-ttu-id="19ff0-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="19ff0-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="19ff0-186">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="19ff0-186">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19ff0-187">Après une restauration</span><span class="sxs-lookup"><span data-stu-id="19ff0-187">After failback</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="19ff0-188">Exécutez l’applet de commande <strong>Import-CsRgsConfiguration</strong> pour réimporter les groupes Response Group dans le pool principal.</span><span class="sxs-lookup"><span data-stu-id="19ff0-188">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the response groups back to the primary pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="19ff0-p116">Si le pool principal ne peut pas être récupéré et que vous déployez un nouveau pool pour le remplacer, utilisez le paramètre –ReplaceExistingSettings pour transférer les paramètres de niveau application du pool de sauvegarde vers le nouveau pool. Si vous ne souhaitez pas transférer les paramètres du pool de sauvegarde, le nouveau pool utilisera les paramètres par défaut.</span><span class="sxs-lookup"><span data-stu-id="19ff0-p116">If the primary pool can't be recovered and you deploy a new pool to replace it, use the –ReplaceExistingSettings parameter to transfer the application-level settings from the backup pool to the new pool. If you do not transfer the settings from the backup pool, the new pool will use the default settings.</span></span>


</div></li>
<li><p><span data-ttu-id="19ff0-191">Exécutez les applets de commande suivantes avec le paramètre –ShowAll (pour afficher tous les groupes Response Group) ou avec le paramètre –Owner (pour afficher uniquement les groupes Response Group importés) afin de vérifier que toutes les configurations Response Group ont été réimportées dans le pool principal :</span><span class="sxs-lookup"><span data-stu-id="19ff0-191">Run the following cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were successfully imported back to the primary pool:</span></span></p>
<ul>
<li><p><span data-ttu-id="19ff0-192"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="19ff0-192"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="19ff0-193"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="19ff0-193"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="19ff0-194"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="19ff0-194"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="19ff0-195"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="19ff0-195"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="19ff0-196"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="19ff0-196"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="19ff0-197">Effectuez un test d’appel vers un groupe Response Group qui a été réimporté dans le pool principal et vérifiez que l’appel est géré correctement.</span><span class="sxs-lookup"><span data-stu-id="19ff0-197">Place a test call to a response group that was imported back to the primary pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="19ff0-198">Vous pouvez également exécuter l’applet de commande <strong>Export-CsRgsConfiguration</strong> dans le pool de sauvegarde avec le paramètre –RemoveExportedConfiguration pour supprimer du pool de sauvegarde les groupes Response Group détenus par le pool principal.</span><span class="sxs-lookup"><span data-stu-id="19ff0-198">Optionally, run the <strong>Export-CsRgsConfiguration</strong> cmdlet on the backup pool with the –RemoveExportedConfiguration parameter to remove the response groups owned by the primary pool from the backup pool.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="19ff0-199">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="19ff0-199">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="19ff0-200">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="19ff0-200">CsResponseGroupAdministrator</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

