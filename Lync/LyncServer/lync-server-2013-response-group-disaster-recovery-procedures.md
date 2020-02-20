---
title: Procédures de récupération d’urgence de groupe Response Group Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group disaster recovery procedures
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48185171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ecd074254243629bbb3a6dc732b11a93cfebbe7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a><span data-ttu-id="622e3-102">Procédures de récupération d’urgence des groupes Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="622e3-102">Response group disaster recovery procedures in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="622e3-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="622e3-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="622e3-104">Pendant la phase de basculement de la récupération d’urgence, les groupes Response Group résident dans plusieurs pools : dans le pool principal (qui n’est pas disponible) et dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="622e3-104">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="622e3-105">Les groupes Response Group des deux pools portent le même nom et ont le même propriétaire (le pool principal), mais ils ont des parents différents.</span><span class="sxs-lookup"><span data-stu-id="622e3-105">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span> <span data-ttu-id="622e3-106">Pendant ce temps, les cmdlets Response Group fonctionnent un peu différemment.</span><span class="sxs-lookup"><span data-stu-id="622e3-106">During this time, Response Group cmdlets work a little differently.</span></span> <span data-ttu-id="622e3-107">Veillez à utiliser les paramètres comme spécifié dans la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="622e3-107">Be sure to use parameters as specified in the following procedure.</span></span> <span data-ttu-id="622e3-108">Pour plus d’informations sur le fonctionnement des cmdlets pendant la phase de basculement, voir l’article du blog NextHop « Lync Server 2013 : Recovering [https://go.microsoft.com/fwlink/p/?LinkId=263957](https://go.microsoft.com/fwlink/p/?linkid=263957)Response Groups during Disaster Recovery » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="622e3-108">For details about how cmdlets work during the failover phase, see NextHop blog article "Lync Server 2013: Recovering Response Groups During Disaster Recovery" at [https://go.microsoft.com/fwlink/p/?LinkId=263957](https://go.microsoft.com/fwlink/p/?linkid=263957).</span></span> <span data-ttu-id="622e3-109">Cet article du blog s’applique également à la version finale de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="622e3-109">This blog article also applies to the released version of Lync Server 2013.</span></span>

<span data-ttu-id="622e3-110">Suivez les étapes de la procédure ci-dessous pour préparer et effectuer une récupération d’urgence pour le service de groupe Response Group Lync Server.</span><span class="sxs-lookup"><span data-stu-id="622e3-110">Use the steps in the following procedure to prepare for and perform disaster recovery for Lync Server Response Group service.</span></span>

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a><span data-ttu-id="622e3-111">Pour basculer et restaurer un groupe Response Group</span><span class="sxs-lookup"><span data-stu-id="622e3-111">To fail over and fail back Response Group</span></span>

1.  <span data-ttu-id="622e3-112">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="622e3-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="622e3-p102">Effectuez régulièrement des sauvegardes. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="622e3-p102">Routinely perform backups. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="622e3-115">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="622e3-115">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  <span data-ttu-id="622e3-p103">Pendant une panne, après le basculement vers le pool de sauvegarde, importez les groupes Response Group sur le pool de sauvegarde. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="622e3-p103">During an outage, after failover to the backup pool, import the response groups to the backup pool. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="622e3-p104">Si vous voulez remplacer les paramètres de niveau application du pool de sauvegarde par les paramètres du pool principal, incluez le paramètre –ReplaceExistingSettings. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="622e3-p104">If you want to replace the application-level settings in the backup pool with the settings from the primary pool, include the –ReplaceExistingSettings parameter. For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="622e3-120">Si vous ne remplacez pas les paramètres du pool de sauvegarde et que le pool principal ne peut pas être récupéré, les paramètres du pool principal seront perdus.</span><span class="sxs-lookup"><span data-stu-id="622e3-120">If you do not replace the settings in the backup pool and the primary pool can't be recovered, the primary pool settings will be lost.</span></span> <span data-ttu-id="622e3-121">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for Response Group Disaster Recovery in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="622e3-121">For details, see <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for response group disaster recovery in Lync Server 2013</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="622e3-p106">Vérifiez que l’importation a réussi en affichant les groupes Response Group importés. Ces groupes appartiennent toujours au pool principal. Procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="622e3-p106">Verify that the import was successful by displaying the imported response groups. The imported response groups are still owned by the primary pool. Do the following:</span></span>
    
      - <span data-ttu-id="622e3-p107">Affichez tous les flux de travail du pool de sauvegarde qui appartiennent au pool principal, et vérifiez que tous les flux de travail du pool principal sont inclus. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="622e3-p107">Display all the workflows in the backup pool that are owned by the primary pool, and verify that all the primary pool workflows are included. At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="622e3-127">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="622e3-127">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - <span data-ttu-id="622e3-p108">Affichez toutes les files d’attente du pool de sauvegarde qui appartiennent au pool principal, et vérifiez que toutes les files d’attente du pool principal sont incluses. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="622e3-p108">Display all the queues in the backup pool that are owned by the primary pool, and verify that all the primary pool queues are included. At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="622e3-130">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="622e3-130">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="622e3-p109">Affichez tous les groupes d’agents du pool de sauvegarde qui appartiennent au pool principal, et vérifiez que tous les groupes d’agents du pool principal sont inclus. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="622e3-p109">Display all the agent groups in the backup pool that are owned by the primary pool, and verify that all the primary pool agent groups are included. At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="622e3-133">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="622e3-133">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="622e3-p110">Affichez toutes les heures d’ouverture du pool de sauvegarde qui appartiennent au pool principal, et vérifiez que toutes les heures d’ouverture du pool principal sont incluses. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="622e3-p110">Display all the hours of business in the backup pool that are owned by the primary pool, and verify that all the primary pool hours of business are included. At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="622e3-136">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="622e3-136">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="622e3-p111">Affichez toutes les périodes de congé du pool de sauvegarde qui appartiennent au pool principal, et vérifiez que toutes les périodes de congé du pool principal sont incluses. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="622e3-p111">Display all the holiday sets in the backup pool that are owned by the primary pool, and verify that all the primary pool holiday sets are included. At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="622e3-139">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="622e3-139">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    <span data-ttu-id="622e3-p112">Vous pouvez également afficher tous les groupes Response Group du pool de sauvegarde, y compris ceux appartenant au pool principal et ceux appartenant au pool de sauvegarde, en utilisant du paramètre –ShowAll au lieu du paramètre –Owner. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="622e3-p112">Alternatively, you can display all the response groups in the backup pool, including the ones owned by the primary pool and the ones owned by the backup pool by using the –ShowAll parameter instead of the –Owner parameter. For example:</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="622e3-p113">Vous devez utiliser le paramètre –ShowAll ou le paramètre –Owner. Si vous n’utilisez aucun de ces paramètres, les groupes Response Group que vous avez importés dans le pool de sauvegarde ne seront pas répertoriés dans les résultats retournés par les applets de commande.</span><span class="sxs-lookup"><span data-stu-id="622e3-p113">You must use either the –ShowAll parameter or the –Owner parameter. If you do not use either of these parameters, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>

    
    </div>

5.  <span data-ttu-id="622e3-144">Vérifiez que l’importation a réussi en passant un appel à un groupe Response Group importé et en vérifiant que l’appel est correctement géré.</span><span class="sxs-lookup"><span data-stu-id="622e3-144">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="622e3-145">Demandez aux agents qui sont membres de groupes d’agents formels de se connecter à leurs groupes d’agents dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="622e3-145">Request agents who are members of formal agent groups to sign in to their agent groups in the backup pool.</span></span>

7.  <span data-ttu-id="622e3-146">Gérez et modifiez les groupes Response Group importés comme d’habitude.</span><span class="sxs-lookup"><span data-stu-id="622e3-146">Manage and modify the imported response groups as usual.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="622e3-147">Lorsque les groupes Response Group se trouvent dans le pool de sauvegarde, vous devez utiliser Lync Server Management Shell pour les gérer.</span><span class="sxs-lookup"><span data-stu-id="622e3-147">While the response groups are in the backup pool, you need to use Lync Server Management Shell to manage them.</span></span> <span data-ttu-id="622e3-148">Vous ne pouvez pas utiliser le panneau de configuration Lync Server pour gérer les groupes Response Group que vous avez importés dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="622e3-148">You cannot use Lync Server Control Panel to manage the response groups that you imported to the backup pool.</span></span>

    
    </div>

8.  <span data-ttu-id="622e3-p115">Une fois le pool principal restauré et la restauration automatique terminée, exportez les groupes Response Group du pool principal qui ont été importés dans le pool de sauvegarde. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="622e3-p115">After the primary pool is restored and failback is complete, export the primary pool response groups that were imported to the backup pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  <span data-ttu-id="622e3-p116">Importez à nouveau les groupes Response Group dans le pool principal. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="622e3-p116">Import the response groups back to the primary pool. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    <span data-ttu-id="622e3-153">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="622e3-153">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="622e3-p117">Si vous reconstruisez un pool pendant la récupération, que ce soit avec le même nom de domaine complet (FQDN) ou avec un nom FQDN différent, vous devez utiliser le paramètre –OverwriteOwner. Généralement, vous pouvez toujours utiliser le paramètre –OverwriteOwner lorsque vous importez à nouveau des groupes Response Group dans le pool principal.</span><span class="sxs-lookup"><span data-stu-id="622e3-p117">If you rebuild a pool during recovery, whether with the same or a different fully qualified domain name (FQDN), you need to use the –OverwriteOwner parameter. As a rule of thumb, you can always use the –OverwriteOwner parameter when you import response groups back to the primary pool.</span></span>

    
    </div>
    
    <span data-ttu-id="622e3-p118">Si vous avez déployé un nouveau pool (avec le même nom FQDN ou avec un nom différent) pour remplacer le pool principal, et que vous voulez utiliser les paramètres de niveau application du pool de sauvegarde du nouveau pool, incluez le paramètre –ReplaceExistingSettings. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="622e3-p118">If you deployed a new pool (with the same or a different FQDN) to replace the primary pool, and you want to use the application-level settings from the backup pool for the new pool, include the –ReplaceExistingSettings parameter. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    <span data-ttu-id="622e3-158">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="622e3-158">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="622e3-159">Si vous ne voulez pas remplacer les paramètres de niveau application et le fichier audio d’attente musicale par défaut du nouveau pool par les paramètres du pool de sauvegarde, le nouveau pool utilise les paramètres de niveau application par défaut.</span><span class="sxs-lookup"><span data-stu-id="622e3-159">If you don't want to replace the application-level settings and default music-on-hold audio file for the new pool with the settings from the backup pool, the new pool will use the default application-level settings.</span></span>

    
    </div>

10. <span data-ttu-id="622e3-p119">Vérifiez que la nouvelle importation dans le pool principal a réussi en affichant la configuration des groupes Response Group importés. Procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="622e3-p119">Verify that the import back to the primary pool was successful by displaying the imported response group configuration. Do the following:</span></span>
    
      - <span data-ttu-id="622e3-p120">Affichez tous les flux de travail du pool principal, et vérifiez que tous les flux de travail importés sont inclus. Sur la ligne de commande, tapez :
</span><span class="sxs-lookup"><span data-stu-id="622e3-p120">Display all the workflows in the primary pool, and verify that all the imported workflows are included. At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="622e3-164">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="622e3-164">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="622e3-p121">Affichez toutes les files d’attente du pool principal, et vérifiez que toutes les files d’attente importées sont incluses. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="622e3-p121">Display all the queues in the primary pool, and verify that all the imported queues are included. At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="622e3-167">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="622e3-167">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="622e3-p122">Affichez tous les groupes d’agents du pool principal, et vérifiez que tous les groupes d’agents importés sont inclus. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="622e3-p122">Display all the agent groups in the primary pool, and verify that all the imported agent groups are included. At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="622e3-170">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="622e3-170">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="622e3-p123">Affichez toutes les heures d’ouverture du pool principal, et vérifiez que toutes les heures d’ouverture importées sont incluses. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="622e3-p123">Display all the hours of business in the primary pool, and verify that all the imported hours of business are included. At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="622e3-173">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="622e3-173">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="622e3-p124">Affichez toutes les périodes de congé du pool principal, et vérifiez que toutes les périodes de congé importées sont incluses. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="622e3-p124">Display all the holiday sets in the primary pool, and verify that all the imported holiday sets are included. At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="622e3-176">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="622e3-176">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. <span data-ttu-id="622e3-177">Vérifiez que l’importation a réussi en passant un appel à un groupe Response Group importé et en vérifiant que l’appel est correctement géré.</span><span class="sxs-lookup"><span data-stu-id="622e3-177">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

12. <span data-ttu-id="622e3-p125">Supprimez éventuellement du pool de sauvegarde les groupes Response Group appartenant au pool principal. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="622e3-p125">Optionally, remove the response groups owned by the primary pool from the backup pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    <span data-ttu-id="622e3-180">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="622e3-180">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="622e3-181">Cette étape crée un fichier avec la configuration exportée, puis le supprime du pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="622e3-181">This step creates a new file with the exported configuration, and then removes it from the backup pool.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

