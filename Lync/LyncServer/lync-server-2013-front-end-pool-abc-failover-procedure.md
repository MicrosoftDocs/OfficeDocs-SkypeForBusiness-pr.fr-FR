---
title: 'Lync Server 2013 : procédure de basculement ABC de pool frontal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool ABC failover procedure
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945635(v=OCS.15)
ms:contentKeyID: 51541486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2f3798dbe49b9da0e76810d1ea8e6619a4e9b6e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a><span data-ttu-id="32c21-102">Procédure de basculement ABC de pool frontal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32c21-102">Front End pool ABC failover procedure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32c21-103">_**Dernière modification de la rubrique :** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="32c21-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="32c21-104">Procédez comme suit pour effectuer la procédure de basculement ABC.</span><span class="sxs-lookup"><span data-stu-id="32c21-104">Use the following steps to perform the ABC failover procedure.</span></span> <span data-ttu-id="32c21-105">Cette procédure contient une description détaillée de chaque étape, suivies des commandes et des cmdlets à exécuter pour chaque étape.</span><span class="sxs-lookup"><span data-stu-id="32c21-105">This procedure contains a high-level description of each step, followed by commands and cmdlets to be run for each step.</span></span>

<span data-ttu-id="32c21-106">Pour exécuter les applets de commande, ouvrez un environnement Lync Server Management Shell à l’aide de l’applet de commande exécuter en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="32c21-106">To run the cmdlets, open a Lync Server Management Shell using Run as Administrator.</span></span>

<div>

## <a name="to-perform-an-abc-failover"></a><span data-ttu-id="32c21-107">Pour effectuer un basculement ABC</span><span class="sxs-lookup"><span data-stu-id="32c21-107">To Perform an ABC Failover</span></span>

1.  <span data-ttu-id="32c21-108">Vérifiez si le pool A est l’hôte du serveur central de gestion (CMS).</span><span class="sxs-lookup"><span data-stu-id="32c21-108">Check whether the pool A is the host for the Central Management Server (CMS).</span></span>
    
      - <span data-ttu-id="32c21-109">Exécutez la cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="32c21-109">Run the following cmdlet:</span></span>
        
            Get-CsService -CentralManagement
        
        <span data-ttu-id="32c21-110">Si le champ Identity du MCG actif pointe vers le nom de domaine complet (FQDN) du pool A, utilisez les étapes 2 et 3 de cette procédure pour faire basculer d’abord le serveur de gestion centralisée.</span><span class="sxs-lookup"><span data-stu-id="32c21-110">If the Identity field of the active CMS points to the fully qualified domain name (FQDN) of Pool A, then you use steps 2 and 3 of this procedure to fail over the Central Management Server first.</span></span> <span data-ttu-id="32c21-111">Sinon, passez à l’étape 4.</span><span class="sxs-lookup"><span data-stu-id="32c21-111">Otherwise, skip to step 4.</span></span>

2.  <span data-ttu-id="32c21-112">Basculez le CMS vers le pool B en mode de récupération d’urgence en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="32c21-112">Fail over the CMS to Pool B in disaster recovery mode by running the following cmdlet:</span></span>
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    <span data-ttu-id="32c21-113">Une fois cette opération effectué, nous vous recommandons de déplacer le MCG du pool B vers un autre pool existant pour une résilience supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="32c21-113">After you do this, we recommend that you move the CMS from pool B to another existing paired pool for extra resiliency.</span></span> <span data-ttu-id="32c21-114">Pour plus d’informations, consultez la rubrique [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..</span><span class="sxs-lookup"><span data-stu-id="32c21-114">For details, see [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..</span></span>

3.  <span data-ttu-id="32c21-115">Si le pool A contient le MCG, importez la configuration LIS du pool A dans la base de données locale de pool B (LIS. mdf).</span><span class="sxs-lookup"><span data-stu-id="32c21-115">If Pool A contains CMS, import the LIS configuration from pool A into pool B’s LIS database (Lis.mdf).</span></span> <span data-ttu-id="32c21-116">Cela ne fonctionnera que si vous avez sauvegardé les données LIS de manière régulière.</span><span class="sxs-lookup"><span data-stu-id="32c21-116">This will work only if you have been backing up LIS data on a regular basis.</span></span> <span data-ttu-id="32c21-117">Pour importer la configuration de LIS, exécutez les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="32c21-117">To import the LIS configuration, run the following cmdlets:</span></span>
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  <span data-ttu-id="32c21-118">Importez les flux de travail de service Response Group Lync Server sauvegardés du pool A dans le pool B.</span><span class="sxs-lookup"><span data-stu-id="32c21-118">Import backed-up Lync Server Response Group service workflows from pool A into pool B.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="32c21-119">Actuellement, l’applet de commande <STRONG>Import-applet csrgsconfiguration</STRONG> nécessite que les noms de file d’attente et de flux de travail du pool A soient différents des noms de file d’attente et de flux de travail sur le pool B. Si les noms ne sont pas distincts, vous obtiendrez une erreur lors de l’exécution de la cmdlet <STRONG>Import-applet csrgsconfiguration</STRONG> , et les files d’attente et les flux de travail doivent être renommés dans le pool B avant de procéder à l’applet de commande <STRONG>Import-applet csrgsconfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="32c21-119">Currently, the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet requires that the queue and workflow names on pool A are distinct from the queue and workflow names on pool B. If the names are not distinct, you will get an error when running the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet, and the queues and workflows will need to be renamed in pool B before proceeding with <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet.</span></span>

    
    </div>
    
    <span data-ttu-id="32c21-120">Vous disposez de deux options pour importer la configuration Response Group à partir du pool A vers le pool B. L’option que vous utilisez dépend si vous voulez remplacer les paramètres au niveau de l’application du pool B par les paramètres au niveau de l’application dans le pool A.</span><span class="sxs-lookup"><span data-stu-id="32c21-120">You have two options for importing the Response Group configuration from pool A to pool B. Which option you use depends on whether you want to overwrite the application-level settings of pool B with the application-level settings in pool A.</span></span>
    
      - <span data-ttu-id="32c21-121">Si vous souhaitez remplacer les paramètres du pool B, exécutez l’applet de commande **Import-applet csrgsconfiguration** avec l’option **ReplaceExistingSettings** :</span><span class="sxs-lookup"><span data-stu-id="32c21-121">If you want to overwrite the Pool B settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="32c21-122">Si vous ne souhaitez pas remplacer les paramètres du pool B, utilisez l’applet de commande **Import-applet csrgsconfiguration** sans l’option **ReplaceExistingSettings**</span><span class="sxs-lookup"><span data-stu-id="32c21-122">If you do not want to overwrite the Pool B settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="32c21-123">N’oubliez pas que si vous ne souhaitez pas remplacer les paramètres au niveau de l’application du pool de sauvegarde (pool B) par les paramètres du pool principal (pool A), les paramètres au niveau de l’application du pool A seront perdus si le pool A est perdu, car l’application Response Group peut stockez un seul ensemble de paramètres au niveau de l’application par pool.</span><span class="sxs-lookup"><span data-stu-id="32c21-123">Keep in mind that if you do not want to overwrite the application-level settings of the backup pool (pool B) with the settings of the primary pool (pool A), pool A’s application-level settings will be lost if pool A is lost, because the Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="32c21-124">Lorsque le pool C est déployé pour remplacer le pool A, les paramètres de niveau application doivent être reconfigurés, y compris le fichier audio de l’attente musicale par défaut.</span><span class="sxs-lookup"><span data-stu-id="32c21-124">When pool C is deployed to replace pool A, the application-level settings must be reconfigured, including the default music-on-hold audio file.</span></span>

    
    </div>

5.  <span data-ttu-id="32c21-125">Vérifiez que l’importation de la configuration Response Group a réussi en exécutant les cmdlets suivantes pour afficher les groupes Response Group importés.</span><span class="sxs-lookup"><span data-stu-id="32c21-125">Verify that the Response Group configuration import was successful by running the following cmdlets to display the imported response groups.</span></span> <span data-ttu-id="32c21-126">Notez que les groupes Response Group importés sont toujours détenus par le pool A.</span><span class="sxs-lookup"><span data-stu-id="32c21-126">Note that the imported response groups are still owned by pool A.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  <span data-ttu-id="32c21-127">Pour les numéros non attribués, déplacez les plages de numéros non attribués qui utilisent « annonce » comme service d’annonce sélectionné dans le pool A vers le pool B. Pour cela, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="32c21-127">For Unassigned Numbers, move the Unassigned Number ranges that are using "Announcement" as the selected announcement service from pool A to pool B. To do so:</span></span>
    
      - <span data-ttu-id="32c21-128">Recréez toutes les annonces qui ont été déployées dans le pool A sur le pool B. Si des fichiers audio ont été utilisés lors du déploiement des annonces dans le pool A, ces fichiers seront nécessaires pour recréer les annonces dans le pool B. Pour recréer les annonces dans le pool B, utilisez les cmdlets **New-CsAnnouncement** avec le pool b comme service parent.</span><span class="sxs-lookup"><span data-stu-id="32c21-128">Re-create all announcements that were deployed in pool A on pool B. If any audio files were used when deploying the announcements in pool A, these files will be needed to re-create the announcements in pool B. To re-create the announcements in pool B, use the **New-CsAnnouncement** cmdlets, with pool B as the Parent service.</span></span>
    
      - <span data-ttu-id="32c21-129">Reciblez toutes les plages de numéros non attribués ciblant une annonce dans le pool A vers les annonces nouvellement déployées dans le pool B. Exécutez l’applet de commande suivante pour chaque plage de numéros non attribué ciblant une annonce du pool A :</span><span class="sxs-lookup"><span data-stu-id="32c21-129">Retarget all the Unassigned Number ranges that are targeting an announcement in pool A to the newly deployed announcements in pool B. Run the following cmdlet for every Unassigned Number range targeting an announcement of pool A:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="32c21-130">Cette étape n’est pas obligatoire pour les plages de numéros non attribués qui utilisent « messagerie unifiée Exchange » comme service d’annonce sélectionné.</span><span class="sxs-lookup"><span data-stu-id="32c21-130">This step is not required for unassigned number ranges that use "Exchange UM" as the selected announcement service.</span></span>

    
    </div>

7.  <span data-ttu-id="32c21-131">Basculez le pool A vers le pool B en mode de récupération d’urgence (DR) en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="32c21-131">Fail over Pool A to Pool B in Disaster Recovery (DR) mode, by running the following cmdlet:</span></span>
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  <span data-ttu-id="32c21-132">Créez le pool C, mais ne démarrez aucun service sur le pool C.</span><span class="sxs-lookup"><span data-stu-id="32c21-132">Build pool C, but do not start any services on pool C.</span></span>
    
    <span data-ttu-id="32c21-133">Notez que cette étape peut être exécutée en même temps que les étapes 5 et 6.</span><span class="sxs-lookup"><span data-stu-id="32c21-133">Note that this step can be carried out concurrently with steps 5 and 6.</span></span>

9.  <span data-ttu-id="32c21-134">Forcez les utilisateurs hébergés sur le pool A à déplacer vers le pool C en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="32c21-134">Force users homed on pool A to move to pool C by running the following cmdlet:</span></span>
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    <span data-ttu-id="32c21-135">À ce stade, les utilisateurs hébergés sur le pool A commencent à subir une panne de service.</span><span class="sxs-lookup"><span data-stu-id="32c21-135">At this point, users homed on pool A will begin to experience a service outage.</span></span> <span data-ttu-id="32c21-136">Cette panne se poursuivra jusqu’à l’étape 16, à laquelle les services pointent sur le pool C.</span><span class="sxs-lookup"><span data-stu-id="32c21-136">This outage will continue until step 16, at which point services are started on pool C.</span></span>

10. <span data-ttu-id="32c21-137">Forcez l’annuaire des conférences du pool A à se déplacer vers le pool C en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="32c21-137">Force the conference directory of pool A to move to pool C by running the following cmdlet:</span></span>
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. <span data-ttu-id="32c21-138">Forcez l’objet contact du standard automatique de conférence (CAA) à passer du pool A au pool C en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="32c21-138">Force the Conference Auto Attendant (CAA) Contact Object to move from pool A to pool C by running the following cmdlet:</span></span>
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. <span data-ttu-id="32c21-139">Copiez le contenu de la Conférence du pool B vers le pool C.</span><span class="sxs-lookup"><span data-stu-id="32c21-139">Copy conference content from pool B to pool C.</span></span>

13. <span data-ttu-id="32c21-140">Exportez les données utilisateur du pool B et importez les données utilisateur dans le pool C en exécutant les cmdlets suivantes :</span><span class="sxs-lookup"><span data-stu-id="32c21-140">Export user data from pool B and import the user data into pool C by running the following cmdlets:</span></span>
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. <span data-ttu-id="32c21-141">Restaurez les données de l’application de parcage d’appel sauvegardée du pool A dans le pool C et affectez les plages d’orbites de parcage d’appel du pool A au pool C.</span><span class="sxs-lookup"><span data-stu-id="32c21-141">Restore backed-up Call Park application data from pool A into pool C and assign the Call Park orbit ranges of pool A to pool C.</span></span>
    
      - <span data-ttu-id="32c21-142">Vous pouvez réaffecter une plage d’orbites de parcage d’appel du pool A vers le pool C via le panneau de configuration Lync Server ou Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="32c21-142">You can reassign a Call Park orbit range of pool A to pool C either through the Lync Server Control Panel or the Lync Server Management Shell.</span></span> <span data-ttu-id="32c21-143">Pour Lync Server Management Shell, exécutez l’applet de commande suivante pour chaque plage d’orbites de parcage d’appel assignée au pool A (Notez que le paramètre Identity fait référence aux plages d’orbites de parcage d’appel qui appartiennent au pool A) :</span><span class="sxs-lookup"><span data-stu-id="32c21-143">For the Lync Server Management Shell, run the following cmdlet for every Call Park orbit range assigned to pool A (note that the Identity parameter refers to the Call Park Orbit Ranges that belong to pool A):</span></span>
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - <span data-ttu-id="32c21-144">Si une mise en attente musicale personnalisée a été configurée pour le parcage d’appel dans le pool A, restaurez le fichier de mise en attente musicale personnalisé du parcage d’appel dans le pool C.</span><span class="sxs-lookup"><span data-stu-id="32c21-144">If a customized music-on-hold has been configured for Call Park in pool A, restore the Call Park customized music-on-hold file in pool C.</span></span>
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        <span data-ttu-id="32c21-145">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="32c21-145">For example:</span></span>
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - <span data-ttu-id="32c21-146">Enfin, reconfigurez les paramètres de parcage d’appel sur le pool C à l’aide de la cmdlet **Set-CsCpsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="32c21-146">Finally, reconfigure the Call Park settings on pool C by using the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="32c21-147">L’application de parcage d’appel ne peut stocker qu’un seul ensemble de paramètres et un seul fichier audio de conservation de musique personnalisé par pool, et ces paramètres ne sont ni sauvegardés ni conservés en cas de sinistre.</span><span class="sxs-lookup"><span data-stu-id="32c21-147">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool, and these settings are not backed up or preserved in the event of a disaster.</span></span>

15. <span data-ttu-id="32c21-148">Si le pool du tronçon suivant pour la conversation permanente pointe vers le pool A, effectuez et publiez les modifications de topologie de sorte que le serveur du tronçon suivant pointe vers le pool C.</span><span class="sxs-lookup"><span data-stu-id="32c21-148">If the next hop pool for Persistent Chat is pointing to pool A, make and publish topology changes so that the next hop server points to pool C.</span></span>
    
      - <span data-ttu-id="32c21-149">Dans le générateur de topologies, modifiez le pool de conversation permanente de sorte qu’il pointe vers le pool C en tant que tronçon suivant.</span><span class="sxs-lookup"><span data-stu-id="32c21-149">In Topology Builder, change the Persistent Chat pool to point to Pool C as its next hop.</span></span> <span data-ttu-id="32c21-150">Pour ce faire, cliquez avec le bouton droit sur le pool de conversations permanentes, cliquez sur l’onglet **général** , puis tapez le nom du pool C dans **pool du tronçon suivant**.</span><span class="sxs-lookup"><span data-stu-id="32c21-150">To do so, right-click on the Persistent Chat pool, then click the **General** tab, and then type the name of Pool C in **Next Hop Pool**.</span></span>
    
      - <span data-ttu-id="32c21-151">Démarrez les services sur le pool C en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="32c21-151">Start services on pool C by running the following cmdlet:</span></span>
        
            Start-csWindowsService
    
    <span data-ttu-id="32c21-152">À ce stade, l’interruption du service se termine pour les utilisateurs hébergés dans le pool A.</span><span class="sxs-lookup"><span data-stu-id="32c21-152">At this point, the service outage ends for users originally homed on pool A.</span></span>

16. <span data-ttu-id="32c21-153">Exportez les flux de travail de service de groupe réponse de Lync Server depuis le pool B appartenant au pool A pour l’importer dans le pool C en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="32c21-153">Export Lync Server Response Group service workflows from pool B owned by pool A for import into pool C by running the following cmdlet:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. <span data-ttu-id="32c21-154">Importez les flux de travail de service Response Group Lync Server dans le pool C à partir du pool B.</span><span class="sxs-lookup"><span data-stu-id="32c21-154">Import Lync Server Response Group service workflows into pool C from pool B.</span></span>
    
    <span data-ttu-id="32c21-155">Deux options s’offrent à vous pour importer la configuration Response Group à partir du pool B vers le pool C. L’option que vous utilisez dépend si vous voulez remplacer les paramètres au niveau de l’application du pool C par les paramètres au niveau de l’application dans le pool B.</span><span class="sxs-lookup"><span data-stu-id="32c21-155">You have two options are for importing the Response Group configuration from pool B to pool C. Which option you use depends on whether you want to overwrite the application-level settings of pool C with the application-level settings in pool B.</span></span>
    
      - <span data-ttu-id="32c21-156">Si vous souhaitez remplacer les paramètres du pool C, exécutez l’applet de commande **Import-applet csrgsconfiguration** avec l’option **ReplaceExistingSettings** :</span><span class="sxs-lookup"><span data-stu-id="32c21-156">If you want to overwrite the Pool C settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="32c21-157">Si vous ne souhaitez pas remplacer les paramètres du pool C, utilisez l’applet de commande **Import-applet csrgsconfiguration** sans l’option **ReplaceExistingSettings**</span><span class="sxs-lookup"><span data-stu-id="32c21-157">If you do not want to overwrite the Pool C settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="32c21-158">N’oubliez pas que si vous ne souhaitez pas remplacer les paramètres au niveau de l’application du pool C par les paramètres du pool de sauvegarde (pool B), les paramètres au niveau de l’application du pool B seront perdus car l’application Response Group ne peut stocker qu’un seul ensemble de niveau application paramètres par pool.</span><span class="sxs-lookup"><span data-stu-id="32c21-158">Keep in mind that if you do not want to overwrite the application-level settings of Pool C with the settings of the backup pool (pool B), pool B’s application-level settings will be lost because the Response Group application can store only one set of application-level settings per pool.</span></span>

    
    </div>

18. <span data-ttu-id="32c21-159">Vérifiez que l’importation de la configuration Response Group a réussi en exécutant les cmdlets suivantes pour afficher les groupes Response Group qui ont été importés dans le pool C.</span><span class="sxs-lookup"><span data-stu-id="32c21-159">Verify that the Response Group configuration import was successful by running the following cmdlets to display the response groups that have been imported to Pool C.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. <span data-ttu-id="32c21-160">Lorsque la configuration importée a été vérifiée dans le pool C, supprimez les groupes Response Group appartenant au pool principal du pool B. Cela réduira le temps d’arrêt des groupes Response Group.</span><span class="sxs-lookup"><span data-stu-id="32c21-160">When the imported configuration has been verified in pool C, remove the response groups owned by the primary pool from pool B. This will minimize the downtime of the response groups.</span></span>
    
    <span data-ttu-id="32c21-161">Cette étape crée un fichier avec la configuration exportée, puis supprime le fichier du pool B.</span><span class="sxs-lookup"><span data-stu-id="32c21-161">This step creates a new file with the exported configuration, and then removes the file from pool B.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. <span data-ttu-id="32c21-162">Déplacer vers le pool C plages de numéros non attribués qui ont été déplacées du pool A vers le pool B.</span><span class="sxs-lookup"><span data-stu-id="32c21-162">Move to pool C the Unassigned Number ranges that were moved from pool A to pool B.</span></span>
    
      - <span data-ttu-id="32c21-163">Recréer dans le pool C toutes les annonces qui ont été recréées à partir du pool A dans le pool B. Si des fichiers audio ont été utilisés lors du déploiement des annonces à déplacer, vous devrez utiliser ces fichiers pour recréer les annonces dans le pool C. Pour recréer les annonces dans le pool C, utilisez les cmdlets **New-CsAnnouncement** , avec le pool c comme service parent.</span><span class="sxs-lookup"><span data-stu-id="32c21-163">Re-create in pool C all announcements that were re-created from pool A in pool B. If any audio files were used when deploying the announcements to be moved, you will need to use these files to re-create the announcements in pool C. To re-create the announcements in pool C, use the **New-CsAnnouncement** cmdlets, with pool C as the Parent service.</span></span>
    
      - <span data-ttu-id="32c21-164">Recibler vers le pool C toutes les plages de numéros non attribués qui ont été reciblées du pool A vers le pool B. Exécutez l’applet de commande suivante pour chaque plage de numéros non attribués qui doit être reciblée :</span><span class="sxs-lookup"><span data-stu-id="32c21-164">Retarget to pool C all the unassigned number ranges that were retargeted from pool A to pool B. Run the following cmdlet for every Unassigned Number range that needs to be retargeted:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - <span data-ttu-id="32c21-165">Module Supprimez du pool B les annonces qui ont été recréées dans le pool C s’ils ne sont plus utilisés dans le pool B. Pour supprimer des annonces, utilisez la cmdlet **Remove-CsAnnouncement** .</span><span class="sxs-lookup"><span data-stu-id="32c21-165">(Optional) Remove from pool B the announcements that were re-created in pool C if they are no longer in use in pool B. To remove announcements, use the **Remove-CsAnnouncement** cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="32c21-166">Cette étape n’est pas obligatoire pour les plages de numéros non attribués qui utilisent « messagerie unifiée Exchange » en tant que service d’annonce.</span><span class="sxs-lookup"><span data-stu-id="32c21-166">This step is not required for unassigned number ranges that use "Exchange UM" as the announcement service.</span></span>

        
        </div>

21. <span data-ttu-id="32c21-167">Nettoyez les données utilisateur du pool A dans le pool B en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="32c21-167">Clean up user data of pool A in pool B by running the following cmdlet:</span></span>
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. <span data-ttu-id="32c21-168">Procédez comme suit dans le générateur de topologie :</span><span class="sxs-lookup"><span data-stu-id="32c21-168">Do the following in Topology Builder:</span></span>
    
      - <span data-ttu-id="32c21-169">Découpler les pools A et B. paire B et pool C. Supprimez ensuite le pool A de la topologie et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="32c21-169">Unpair pool A and pool B. Pair pool B and pool C. Then remove Pool A from the topology and publish it.</span></span> <span data-ttu-id="32c21-170">Pour ce faire, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="32c21-170">To do so:</span></span>
        
          - <span data-ttu-id="32c21-171">Dans le générateur de topologies, cliquez avec le bouton droit sur le pool B, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="32c21-171">In Topology Builder, right-click on Pool B, and then click **Edit Properties**.</span></span>
        
          - <span data-ttu-id="32c21-172">Cliquez sur **résistance** dans le volet de gauche.</span><span class="sxs-lookup"><span data-stu-id="32c21-172">Click **Resiliency** in the left pane.</span></span>
        
          - <span data-ttu-id="32c21-173">Dans la zone située sous le **pool de sauvegarde associé**, sélectionnez Pool C. Notez que la zone de sélection du pool de sauvegarde associé affiche le pool A, car le pool B était précédemment associé à ce pool.</span><span class="sxs-lookup"><span data-stu-id="32c21-173">In the box below **Associated Backup Pool**, select Pool C. Note that the Associated Backup Pool selection box will initially display pool A, because pool B was previously associated with this pool.</span></span>
        
          - <span data-ttu-id="32c21-174">Sélectionnez **Basculement et restauration automatiques pour Voice**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="32c21-174">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
            
            <span data-ttu-id="32c21-175">Quand vous affichez les détails de ce pool, le pool associé apparaît dans le volet droit sous **Résistance**.</span><span class="sxs-lookup"><span data-stu-id="32c21-175">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span>
        
          - <span data-ttu-id="32c21-176">Dans l’arborescence de la console, cliquez avec le bouton droit sur pool A, puis cliquez sur supprimer.</span><span class="sxs-lookup"><span data-stu-id="32c21-176">In the console tree, right-click pool A, and then click Delete.</span></span>
        
          - <span data-ttu-id="32c21-177">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="32c21-177">Publish the topology.</span></span>

23. <span data-ttu-id="32c21-178">Exécutez l’application d’amorçage sur le pool C pour installer l’application de service de sauvegarde, puis démarrez l’application de service de sauvegarde en exécutant ce qui suit à partir du dossier de déploiement sur un ordinateur local dans le pool C :</span><span class="sxs-lookup"><span data-stu-id="32c21-178">Run the bootstrapping application on pool C to install the backup service application, and then start the backup service application by running the following from the deployment folder on a local machine in pool C:</span></span>
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. <span data-ttu-id="32c21-179">Redémarrez l’application de service de sauvegarde sur le pool B en exécutant les cmdlets suivantes :</span><span class="sxs-lookup"><span data-stu-id="32c21-179">Restart the backup service application on pool B by running the following cmdlets:</span></span>
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. <span data-ttu-id="32c21-180">Si le pool C est un pool Standard Edition (SE) et que le pool B a CMS, installez la base de données CMS manuellement sur le pool C en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="32c21-180">If pool C is a Standard Edition (SE) Pool and pool B has CMS, install the CMS database manually on pool C by running the following cmdlet:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. <span data-ttu-id="32c21-181">Appelez le service de sauvegarde pour synchroniser l’ancien contenu de conférence du pool B vers le pool C généré avant le jumelage de B et C, et pour synchroniser le nouveau contenu de conférence du pool C vers le pool B qui a été généré après le démarrage du pool C et avant l’Association de B et C.</span><span class="sxs-lookup"><span data-stu-id="32c21-181">Invoke the backup service to sync old conferencing content from pool B to pool C that was generated before pairing B and C together, and to sync new conferencing content from pool C to pool B that was generated after starting pool C and before B and C were paired together.</span></span> <span data-ttu-id="32c21-182">Pour cela, exécutez les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="32c21-182">To do so, run the following cmdlets:</span></span>
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. <span data-ttu-id="32c21-183">Pour chaque serveur Survivable Branch Appliance X associé au pool A :</span><span class="sxs-lookup"><span data-stu-id="32c21-183">For each Survivable Branch Appliance X associated with pool A:</span></span>
    
      - <span data-ttu-id="32c21-184">Arrêtez SBA X en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="32c21-184">Shut down SBA X by running the following cmdlet:</span></span>
        
            Stop-CsWindowsService
    
      - <span data-ttu-id="32c21-185">Créez un fichier contenant une liste d’utilisateurs hébergés sur SBA X. La liste est nécessaire lorsque les utilisateurs sont déplacés de SBA X à l’étape 30.</span><span class="sxs-lookup"><span data-stu-id="32c21-185">Create a file that contains a list of users homed on SBA X. The list will be needed when the users are moved back to SBA X in step 30.</span></span> <span data-ttu-id="32c21-186">Pour ce faire, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="32c21-186">To do so, run the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - <span data-ttu-id="32c21-187">Forcez les utilisateurs hébergés sur SBA X à se déplacer vers le pool C en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="32c21-187">Force users homed on SBA X to move to pool C by running the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - <span data-ttu-id="32c21-188">Mettez à jour les données de ces utilisateurs en exécutant d’abord les cmdlets suivantes :</span><span class="sxs-lookup"><span data-stu-id="32c21-188">Update the data of these users by first running the following cmdlets:</span></span>
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        <span data-ttu-id="32c21-189">Puis exécutez ce script :</span><span class="sxs-lookup"><span data-stu-id="32c21-189">And then run this script:</span></span>
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="32c21-190">Une panne de service se produit pour les utilisateurs hébergés sur SBA qui sont associés au pool A jusqu’à ce que ces utilisateurs soient déplacés vers le pool C.</span><span class="sxs-lookup"><span data-stu-id="32c21-190">A service outage will occur for users who are homed on SBAs that are associated with pool A until these users are moved to pool C.</span></span>

        
        </div>

28. <span data-ttu-id="32c21-191">Dans le générateur de topologies, pour chaque SBA X précédemment associé au pool A, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="32c21-191">In Topology Builder, for each SBA X previously associated with Pool A, do the following:</span></span>
    
      - <span data-ttu-id="32c21-192">Modifiez l’Association en pool C. Pour ce faire, cliquez sur le site de succursale, développez le nœud Survivable Branch Appliances ou Servers, puis cliquez sur **Survivable Branch Appliance**.</span><span class="sxs-lookup"><span data-stu-id="32c21-192">Change the association to Pool C. To do so, click the branch site, expand the Survivable Branch Appliances or Servers node, and click **Survivable Branch Appliance**.</span></span> <span data-ttu-id="32c21-193">Ensuite, sélectionnez le pool **frontal, le pool de services d’utilisateurs** auquel ce Survivable Branch appliance se connectera en tant que Pool C, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="32c21-193">Then select the **Front End pool, User Services Pool** that this Survivable Branch Appliance will connect to as Pool C, and then click **Next**.</span></span>
    
      - <span data-ttu-id="32c21-194">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="32c21-194">Publish the topology.</span></span> <span data-ttu-id="32c21-195">Pour ce faire, dans l’arborescence de la console, cliquez avec le bouton droit sur le nouveau **Survivable Branch Appliance**, cliquez sur **topologie**, puis sur **publier**.</span><span class="sxs-lookup"><span data-stu-id="32c21-195">To do so, in the console tree, right-click the new **Survivable Branch Appliance**, click **Topology**, and then click **Publish**.</span></span>

29. <span data-ttu-id="32c21-196">Pour chaque SBA X maintenant associé au pool C :</span><span class="sxs-lookup"><span data-stu-id="32c21-196">For each SBA X now associated with pool C:</span></span>
    
      - <span data-ttu-id="32c21-197">Démarrez SBA X en exécutant l’applet de commande suivante sur le Survivable Branch Appliance :</span><span class="sxs-lookup"><span data-stu-id="32c21-197">Start SBA X by running the following cmdlet on the survivable branch appliance:</span></span>
        
            Start-CsWindowsService
    
      - <span data-ttu-id="32c21-198">Déplacez les utilisateurs hébergés à l’origine sur SBA X du pool C vers SBA X en exécutant l’applet de commande suivante.</span><span class="sxs-lookup"><span data-stu-id="32c21-198">Move users who were originally homed on SBA X from pool C to SBA X by running the following cmdlet.</span></span>
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

