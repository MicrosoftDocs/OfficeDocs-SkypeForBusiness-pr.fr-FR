---
title: Procédures de récupération d’urgence des groupes Response Group dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response group disaster recovery procedures
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48185171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f28f13d1acdbdae58b1aadd6f73871af270b7d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a><span data-ttu-id="53928-102">Procédures de récupération d’urgence des groupes Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53928-102">Response group disaster recovery procedures in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53928-103">_**Dernière modification de la rubrique:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="53928-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="53928-104">Lors de la phase de reprise après incident, les groupes de réponse résident dans plusieurs pools: dans le pool principal (non disponible) et dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="53928-104">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="53928-105">Les groupes Response dans les deux pools ont le même nom et le même propriétaire (le pool principal), mais ils ont des parents différents.</span><span class="sxs-lookup"><span data-stu-id="53928-105">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span> <span data-ttu-id="53928-106">Pendant ce temps, les cmdlets de groupe de réponse fonctionnent légèrement différemment.</span><span class="sxs-lookup"><span data-stu-id="53928-106">During this time, Response Group cmdlets work a little differently.</span></span> <span data-ttu-id="53928-107">Veillez à utiliser les paramètres comme spécifié dans la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="53928-107">Be sure to use parameters as specified in the following procedure.</span></span> <span data-ttu-id="53928-108">Pour plus d’informations sur le fonctionnement des cmdlets lors de la phase de basculement, voir l’article de blog NextHop «Lync Server 2013: récupération de [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957)Response Groups en cours de reprise après sinistre».</span><span class="sxs-lookup"><span data-stu-id="53928-108">For details about how cmdlets work during the failover phase, see NextHop blog article "Lync Server 2013: Recovering Response Groups During Disaster Recovery" at [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957).</span></span> <span data-ttu-id="53928-109">Ce blog s’applique également à la version publiée de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53928-109">This blog article also applies to the released version of Lync Server 2013.</span></span>

<span data-ttu-id="53928-110">Suivez les étapes décrites dans la procédure ci-dessous pour préparer et exécuter une reprise après sinistre pour le service Response Group de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="53928-110">Use the steps in the following procedure to prepare for and perform disaster recovery for Lync Server Response Group service.</span></span>

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a><span data-ttu-id="53928-111">Pour basculer et annuler le regroupement de réponses</span><span class="sxs-lookup"><span data-stu-id="53928-111">To fail over and fail back Response Group</span></span>

1.  <span data-ttu-id="53928-112">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="53928-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="53928-113">Effectuez régulièrement des sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="53928-113">Routinely perform backups.</span></span> <span data-ttu-id="53928-114">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="53928-114">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="53928-115">Exemple :</span><span class="sxs-lookup"><span data-stu-id="53928-115">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  <span data-ttu-id="53928-116">Au cours d’une panne, après le basculement vers le pool de sauvegarde, importez les groupes de réponses dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="53928-116">During an outage, after failover to the backup pool, import the response groups to the backup pool.</span></span> <span data-ttu-id="53928-117">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="53928-117">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="53928-118">Si vous voulez remplacer les paramètres au niveau de l’application dans le pool de sauvegarde par les paramètres de la liste principale, incluez le paramètre – ReplaceExistingSettings.</span><span class="sxs-lookup"><span data-stu-id="53928-118">If you want to replace the application-level settings in the backup pool with the settings from the primary pool, include the –ReplaceExistingSettings parameter.</span></span> <span data-ttu-id="53928-119">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="53928-119">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="53928-120">Si vous ne souhaitez pas remplacer les paramètres dans le pool de sauvegarde et que le pool principal ne peut pas être récupéré, les paramètres du pool principal seront perdus.</span><span class="sxs-lookup"><span data-stu-id="53928-120">If you do not replace the settings in the backup pool and the primary pool can't be recovered, the primary pool settings will be lost.</span></span> <span data-ttu-id="53928-121">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">planification d’une reprise après sinistre de Response Group dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="53928-121">For details, see <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for response group disaster recovery in Lync Server 2013</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="53928-122">Vérifiez que l’importation est réussie en affichant les groupes de réponse importés.</span><span class="sxs-lookup"><span data-stu-id="53928-122">Verify that the import was successful by displaying the imported response groups.</span></span> <span data-ttu-id="53928-123">Les groupes de réponse importés sont encore possédés par le pool principal.</span><span class="sxs-lookup"><span data-stu-id="53928-123">The imported response groups are still owned by the primary pool.</span></span> <span data-ttu-id="53928-124">Procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="53928-124">Do the following:</span></span>
    
      - <span data-ttu-id="53928-125">Affichez tous les flux de travail du pool de sauvegarde dont le pool principal est possédé, puis vérifiez que tous les flux de travail de pool principal sont inclus.</span><span class="sxs-lookup"><span data-stu-id="53928-125">Display all the workflows in the backup pool that are owned by the primary pool, and verify that all the primary pool workflows are included.</span></span> <span data-ttu-id="53928-126">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="53928-126">At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="53928-127">Exemple :</span><span class="sxs-lookup"><span data-stu-id="53928-127">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - <span data-ttu-id="53928-128">Affichez toutes les files d’attente du pool de sauvegarde détenu par le pool principal, puis vérifiez que tous les files d’attente du pool principal sont incluses.</span><span class="sxs-lookup"><span data-stu-id="53928-128">Display all the queues in the backup pool that are owned by the primary pool, and verify that all the primary pool queues are included.</span></span> <span data-ttu-id="53928-129">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="53928-129">At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="53928-130">Exemple :</span><span class="sxs-lookup"><span data-stu-id="53928-130">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="53928-131">Affichez tous les groupes d’agents dans le pool de sauvegarde appartenant au pool principal, puis vérifiez que tous les groupes d’agents de pool principal sont inclus.</span><span class="sxs-lookup"><span data-stu-id="53928-131">Display all the agent groups in the backup pool that are owned by the primary pool, and verify that all the primary pool agent groups are included.</span></span> <span data-ttu-id="53928-132">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="53928-132">At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="53928-133">Exemple :</span><span class="sxs-lookup"><span data-stu-id="53928-133">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="53928-134">Affichez toutes les heures d’activité dans le pool de sauvegarde qui sont détenues par le pool principal, puis vérifiez que tous les horaires d’activité du pool principal sont inclus.</span><span class="sxs-lookup"><span data-stu-id="53928-134">Display all the hours of business in the backup pool that are owned by the primary pool, and verify that all the primary pool hours of business are included.</span></span> <span data-ttu-id="53928-135">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="53928-135">At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="53928-136">Exemple :</span><span class="sxs-lookup"><span data-stu-id="53928-136">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="53928-137">Affichez tous les jeux de jours fériés dans le pool de sauvegarde appartenant au pool principal, puis vérifiez que tous les jeux de jours de vacances du pool principal sont inclus.</span><span class="sxs-lookup"><span data-stu-id="53928-137">Display all the holiday sets in the backup pool that are owned by the primary pool, and verify that all the primary pool holiday sets are included.</span></span> <span data-ttu-id="53928-138">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="53928-138">At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="53928-139">Exemple :</span><span class="sxs-lookup"><span data-stu-id="53928-139">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    <span data-ttu-id="53928-140">Par ailleurs, vous pouvez afficher tous les groupes de réponses du pool de sauvegarde, y compris ceux appartenant au pool principal et ceux appartenant au pool de sauvegarde, à l’aide du paramètre-ShowAll à la place du paramètre – owner.</span><span class="sxs-lookup"><span data-stu-id="53928-140">Alternatively, you can display all the response groups in the backup pool, including the ones owned by the primary pool and the ones owned by the backup pool by using the –ShowAll parameter instead of the –Owner parameter.</span></span> <span data-ttu-id="53928-141">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="53928-141">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="53928-142">Vous devez utiliser le paramètre – ShowAll ou – owner.</span><span class="sxs-lookup"><span data-stu-id="53928-142">You must use either the –ShowAll parameter or the –Owner parameter.</span></span> <span data-ttu-id="53928-143">Si vous n’utilisez pas l’un de ces paramètres, les groupes de réponse que vous avez importés dans le pool de sauvegarde ne seront pas répertoriés dans les résultats renvoyés par les applets de requête.</span><span class="sxs-lookup"><span data-stu-id="53928-143">If you do not use either of these parameters, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>

    
    </div>

5.  <span data-ttu-id="53928-144">Vérifiez que l’importation est réussie en effectuant un appel vers un groupe de réponse importé et en vérifiant que l’appel est correctement géré.</span><span class="sxs-lookup"><span data-stu-id="53928-144">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="53928-145">Demandez aux agents membres de groupes d’agents formels de se connecter à leurs groupes d’agents dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="53928-145">Request agents who are members of formal agent groups to sign in to their agent groups in the backup pool.</span></span>

7.  <span data-ttu-id="53928-146">Gestion et modification des groupes de réponse importés comme d’habitude.</span><span class="sxs-lookup"><span data-stu-id="53928-146">Manage and modify the imported response groups as usual.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="53928-147">Lorsque les groupes de réponse figurent dans le pool de sauvegarde, vous devez utiliser Lync Server Management Shell pour les gérer.</span><span class="sxs-lookup"><span data-stu-id="53928-147">While the response groups are in the backup pool, you need to use Lync Server Management Shell to manage them.</span></span> <span data-ttu-id="53928-148">Vous ne pouvez pas utiliser le panneau de configuration de Lync Server pour gérer les groupes de réponse que vous avez importés dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="53928-148">You cannot use Lync Server Control Panel to manage the response groups that you imported to the backup pool.</span></span>

    
    </div>

8.  <span data-ttu-id="53928-149">Lorsque le pool principal est restauré et que le retour arrière est terminé, exportez les groupes de réponses de la liste principale qui ont été importés dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="53928-149">After the primary pool is restored and failback is complete, export the primary pool response groups that were imported to the backup pool.</span></span> <span data-ttu-id="53928-150">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="53928-150">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  <span data-ttu-id="53928-151">Importez les groupes de réponse dans le pool principal.</span><span class="sxs-lookup"><span data-stu-id="53928-151">Import the response groups back to the primary pool.</span></span> <span data-ttu-id="53928-152">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="53928-152">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    <span data-ttu-id="53928-153">Exemple :</span><span class="sxs-lookup"><span data-stu-id="53928-153">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="53928-154">Si vous reconstruisez un pool lors de la récupération, qu’il s’agisse d’un nom de domaine complet, ou d’un nom de domaine complet différent, vous devez utiliser le paramètre – OverwriteOwner.</span><span class="sxs-lookup"><span data-stu-id="53928-154">If you rebuild a pool during recovery, whether with the same or a different fully qualified domain name (FQDN), you need to use the –OverwriteOwner parameter.</span></span> <span data-ttu-id="53928-155">En règle générale, vous pouvez toujours utiliser le paramètre – OverwriteOwner lorsque vous importez des groupes de réponses vers le pool principal.</span><span class="sxs-lookup"><span data-stu-id="53928-155">As a rule of thumb, you can always use the –OverwriteOwner parameter when you import response groups back to the primary pool.</span></span>

    
    </div>
    
    <span data-ttu-id="53928-156">Si vous avez déployé un nouveau pool (avec le même nom ou un nom de domaine complet différent) pour remplacer le pool principal et que vous souhaitez utiliser les paramètres au niveau de l’application du pool de sauvegarde pour le nouveau pool, incluez le paramètre – ReplaceExistingSettings.</span><span class="sxs-lookup"><span data-stu-id="53928-156">If you deployed a new pool (with the same or a different FQDN) to replace the primary pool, and you want to use the application-level settings from the backup pool for the new pool, include the –ReplaceExistingSettings parameter.</span></span> <span data-ttu-id="53928-157">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="53928-157">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    <span data-ttu-id="53928-158">Exemple :</span><span class="sxs-lookup"><span data-stu-id="53928-158">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="53928-159">Si vous ne voulez pas remplacer les paramètres au niveau de l’application et le fichier audio en attente par défaut de musique pour le nouveau pool avec les paramètres du pool de sauvegarde, le nouveau pool utilisera les paramètres de niveau application par défaut.</span><span class="sxs-lookup"><span data-stu-id="53928-159">If you don't want to replace the application-level settings and default music-on-hold audio file for the new pool with the settings from the backup pool, the new pool will use the default application-level settings.</span></span>

    
    </div>

10. <span data-ttu-id="53928-160">Assurez-vous que l’importation du pool principal est réussie en affichant la configuration de groupe de réponse importée.</span><span class="sxs-lookup"><span data-stu-id="53928-160">Verify that the import back to the primary pool was successful by displaying the imported response group configuration.</span></span> <span data-ttu-id="53928-161">Procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="53928-161">Do the following:</span></span>
    
      - <span data-ttu-id="53928-162">Affichez tous les flux de travail dans la liste principale, puis vérifiez que tous les flux de travail importés sont inclus.</span><span class="sxs-lookup"><span data-stu-id="53928-162">Display all the workflows in the primary pool, and verify that all the imported workflows are included.</span></span> <span data-ttu-id="53928-163">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="53928-163">At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="53928-164">Exemple :</span><span class="sxs-lookup"><span data-stu-id="53928-164">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="53928-165">Affichez toutes les files d’attente dans la liste principale, puis vérifiez que toutes les files d’attente importées sont incluses.</span><span class="sxs-lookup"><span data-stu-id="53928-165">Display all the queues in the primary pool, and verify that all the imported queues are included.</span></span> <span data-ttu-id="53928-166">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="53928-166">At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="53928-167">Exemple :</span><span class="sxs-lookup"><span data-stu-id="53928-167">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="53928-168">Affichez tous les groupes d’agents dans la liste principale des agents et vérifiez que tous les groupes d’agents importés sont inclus.</span><span class="sxs-lookup"><span data-stu-id="53928-168">Display all the agent groups in the primary pool, and verify that all the imported agent groups are included.</span></span> <span data-ttu-id="53928-169">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="53928-169">At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="53928-170">Exemple :</span><span class="sxs-lookup"><span data-stu-id="53928-170">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="53928-171">Affichez toutes les heures d’activité dans la liste principale, puis vérifiez que toutes les heures d’activité importées sont incluses.</span><span class="sxs-lookup"><span data-stu-id="53928-171">Display all the hours of business in the primary pool, and verify that all the imported hours of business are included.</span></span> <span data-ttu-id="53928-172">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="53928-172">At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="53928-173">Exemple :</span><span class="sxs-lookup"><span data-stu-id="53928-173">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="53928-174">Affichez tous les ensembles de jours fériés dans la liste principale, puis vérifiez que tous les jeux de jours de vacances importés sont inclus.</span><span class="sxs-lookup"><span data-stu-id="53928-174">Display all the holiday sets in the primary pool, and verify that all the imported holiday sets are included.</span></span> <span data-ttu-id="53928-175">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="53928-175">At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="53928-176">Exemple :</span><span class="sxs-lookup"><span data-stu-id="53928-176">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. <span data-ttu-id="53928-177">Vérifiez que l’importation est réussie en effectuant un appel vers un groupe de réponse importé et en vérifiant que l’appel est correctement géré.</span><span class="sxs-lookup"><span data-stu-id="53928-177">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

12. <span data-ttu-id="53928-178">Vous pouvez également supprimer les groupes de réponse appartenant au pool principal du pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="53928-178">Optionally, remove the response groups owned by the primary pool from the backup pool.</span></span> <span data-ttu-id="53928-179">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="53928-179">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    <span data-ttu-id="53928-180">Exemple :</span><span class="sxs-lookup"><span data-stu-id="53928-180">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="53928-181">Cette étape permet de créer un fichier avec la configuration exportée, puis de le supprimer du pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="53928-181">This step creates a new file with the exported configuration, and then removes it from the backup pool.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

