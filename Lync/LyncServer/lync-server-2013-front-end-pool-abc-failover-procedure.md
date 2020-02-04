---
title: 'Lync Server 2013 : Procédure de basculement ABC vers un pool frontal'
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
ms.openlocfilehash: edf3d12aa519ab7746ccec92998995ed463aa9be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a><span data-ttu-id="c7544-102">Procédure de basculement ABC vers un pool frontal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7544-102">Front End pool ABC failover procedure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7544-103">_**Dernière modification de la rubrique :** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="c7544-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="c7544-104">Procédez comme suit pour effectuer la procédure de basculement ABC.</span><span class="sxs-lookup"><span data-stu-id="c7544-104">Use the following steps to perform the ABC failover procedure.</span></span> <span data-ttu-id="c7544-105">Cette procédure contient une description de haut niveau de chaque étape, suivie de commandes et d’applets de commande à exécuter pour chaque étape.</span><span class="sxs-lookup"><span data-stu-id="c7544-105">This procedure contains a high-level description of each step, followed by commands and cmdlets to be run for each step.</span></span>

<span data-ttu-id="c7544-106">Pour exécuter les applets de cmdlet, ouvrez Lync Server Management Shell à l’aide de l’applet exécuter en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="c7544-106">To run the cmdlets, open a Lync Server Management Shell using Run as Administrator.</span></span>

<div>

## <a name="to-perform-an-abc-failover"></a><span data-ttu-id="c7544-107">Pour effectuer un basculement ABC</span><span class="sxs-lookup"><span data-stu-id="c7544-107">To Perform an ABC Failover</span></span>

1.  <span data-ttu-id="c7544-108">Vérifiez si le pool A est l’hôte du serveur de gestion central (CMS).</span><span class="sxs-lookup"><span data-stu-id="c7544-108">Check whether the pool A is the host for the Central Management Server (CMS).</span></span>
    
      - <span data-ttu-id="c7544-109">Exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c7544-109">Run the following cmdlet:</span></span>
        
            Get-CsService -CentralManagement
        
        <span data-ttu-id="c7544-110">Si le champ Identity du CMS actif pointe vers le nom de domaine complet (FQDN) du pool A, vous devez commencer par suivre les étapes 2 et 3 de cette procédure pour basculer d’abord sur le serveur de gestion central.</span><span class="sxs-lookup"><span data-stu-id="c7544-110">If the Identity field of the active CMS points to the fully qualified domain name (FQDN) of Pool A, then you use steps 2 and 3 of this procedure to fail over the Central Management Server first.</span></span> <span data-ttu-id="c7544-111">Dans le cas contraire, passez à l’étape 4.</span><span class="sxs-lookup"><span data-stu-id="c7544-111">Otherwise, skip to step 4.</span></span>

2.  <span data-ttu-id="c7544-112">Basculez le CMS vers le pool B en mode de récupération d’urgence en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c7544-112">Fail over the CMS to Pool B in disaster recovery mode by running the following cmdlet:</span></span>
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    <span data-ttu-id="c7544-113">Après cela, nous vous recommandons de déplacer le MCG du pool B vers un autre pool couplé existant pour une résilience supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="c7544-113">After you do this, we recommend that you move the CMS from pool B to another existing paired pool for extra resiliency.</span></span> <span data-ttu-id="c7544-114">Pour plus d’informations, reportez-vous à [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..</span><span class="sxs-lookup"><span data-stu-id="c7544-114">For details, see [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..</span></span>

3.  <span data-ttu-id="c7544-115">Si le regroupement A contient le MCG, importez la configuration de LIS de la liste de la base de données LIS de pool A (LIS. mdf).</span><span class="sxs-lookup"><span data-stu-id="c7544-115">If Pool A contains CMS, import the LIS configuration from pool A into pool B’s LIS database (Lis.mdf).</span></span> <span data-ttu-id="c7544-116">Cela ne fonctionnera que si vous sauvegardez vos données LIS de façon régulière.</span><span class="sxs-lookup"><span data-stu-id="c7544-116">This will work only if you have been backing up LIS data on a regular basis.</span></span> <span data-ttu-id="c7544-117">Pour importer la configuration de LIS, exécutez les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="c7544-117">To import the LIS configuration, run the following cmdlets:</span></span>
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  <span data-ttu-id="c7544-118">Importez des flux de travail de service de groupe de réponse de groupe avec le regroupement A dans le pool B.</span><span class="sxs-lookup"><span data-stu-id="c7544-118">Import backed-up Lync Server Response Group service workflows from pool A into pool B.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c7544-119">Pour l’instant, l’applet de demande <STRONG>Import-CsRgsConfiguration</STRONG> nécessite que les noms de files d’attente et de flux de travail du pool A sont différents des noms de file d’attente et de flux de travail du pool B. Si les noms ne sont pas distincts, vous obtiendrez une erreur lors de l’exécution de l’applet <STRONG>de cmdlet Import-CsRgsConfiguration</STRONG> , et les files d’attente et les flux de travail devront être renommées dans le pool B avant de procéder à l’applet de passe <STRONG>Import-CsRgsConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="c7544-119">Currently, the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet requires that the queue and workflow names on pool A are distinct from the queue and workflow names on pool B. If the names are not distinct, you will get an error when running the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet, and the queues and workflows will need to be renamed in pool B before proceeding with <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet.</span></span>

    
    </div>
    
    <span data-ttu-id="c7544-120">Deux options s’offrent à vous pour importer la configuration du groupe de réponses du pool A à la liste B. L’option utilisée varie selon que vous voulez remplacer les paramètres au niveau de l’application du pool B par les paramètres au niveau de l’application dans le groupe A.</span><span class="sxs-lookup"><span data-stu-id="c7544-120">You have two options for importing the Response Group configuration from pool A to pool B. Which option you use depends on whether you want to overwrite the application-level settings of pool B with the application-level settings in pool A.</span></span>
    
      - <span data-ttu-id="c7544-121">Si vous voulez remplacer les paramètres du pool B, exécutez l’applet de commande **Import-CsRgsConfiguration** avec l’option **ReplaceExistingSettings** :</span><span class="sxs-lookup"><span data-stu-id="c7544-121">If you want to overwrite the Pool B settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="c7544-122">Si vous ne voulez pas remplacer les paramètres du pool B, utilisez l’applet de commande **Import-CsRgsConfiguration** sans l’option **ReplaceExistingSettings** .</span><span class="sxs-lookup"><span data-stu-id="c7544-122">If you do not want to overwrite the Pool B settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="c7544-123">Rappelez-vous que si vous ne voulez pas remplacer les paramètres au niveau de l’application du pool de sauvegarde (pool B) avec les paramètres du pool principal (pool A), les paramètres au niveau de l’application de regroupement seront perdus si le pool A est perdu, car l’application de groupe de réponse peut ne stockez qu’un ensemble de paramètres au niveau de l’application par liste.</span><span class="sxs-lookup"><span data-stu-id="c7544-123">Keep in mind that if you do not want to overwrite the application-level settings of the backup pool (pool B) with the settings of the primary pool (pool A), pool A’s application-level settings will be lost if pool A is lost, because the Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="c7544-124">Lorsque le pool C est déployé pour remplacer le pool A, les paramètres au niveau de l’application doivent être reconfigurés, y compris le fichier audio par défaut de musique.</span><span class="sxs-lookup"><span data-stu-id="c7544-124">When pool C is deployed to replace pool A, the application-level settings must be reconfigured, including the default music-on-hold audio file.</span></span>

    
    </div>

5.  <span data-ttu-id="c7544-125">Vérifiez que l’importation de la configuration du groupe de réponse a réussi en exécutant les applets de commande suivantes pour afficher les groupes de réponse importés.</span><span class="sxs-lookup"><span data-stu-id="c7544-125">Verify that the Response Group configuration import was successful by running the following cmdlets to display the imported response groups.</span></span> <span data-ttu-id="c7544-126">Notez que les groupes de réponse importés sont encore possédés par le groupe A.</span><span class="sxs-lookup"><span data-stu-id="c7544-126">Note that the imported response groups are still owned by pool A.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  <span data-ttu-id="c7544-127">Pour les numéros non attribués, déplacez les plages de numéros non affectées qui utilisent « annonce » en tant que service d’annonce sélectionné du pool A à pool B. Pour cela, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c7544-127">For Unassigned Numbers, move the Unassigned Number ranges that are using "Announcement" as the selected announcement service from pool A to pool B. To do so:</span></span>
    
      - <span data-ttu-id="c7544-128">Recréez toutes les annonces qui ont été déployées dans le pool A du pool B. Si des fichiers audio étaient utilisés lors du déploiement des annonces dans le pool A, ces fichiers seront nécessaires pour recréer les annonces dans le pool B. Pour recréer les annonces dans le pool B, utilisez les applets de nouvelle applet de **CsAnnouncement** , avec le pool b en tant que service parent.</span><span class="sxs-lookup"><span data-stu-id="c7544-128">Re-create all announcements that were deployed in pool A on pool B. If any audio files were used when deploying the announcements in pool A, these files will be needed to re-create the announcements in pool B. To re-create the announcements in pool B, use the **New-CsAnnouncement** cmdlets, with pool B as the Parent service.</span></span>
    
      - <span data-ttu-id="c7544-129">Reciblez toutes les plages de numéros non attribués ciblant une annonce dans le pool A aux nouvelles annonces déployées dans le pool B. Exécutez l’applet de commande suivante pour chaque plage de numéros non attribués ciblant une annonce de groupe A :</span><span class="sxs-lookup"><span data-stu-id="c7544-129">Retarget all the Unassigned Number ranges that are targeting an announcement in pool A to the newly deployed announcements in pool B. Run the following cmdlet for every Unassigned Number range targeting an announcement of pool A:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c7544-130">Cette étape n’est pas requise pour les plages de nombres non affectées qui utilisent le service d’annonce « Exchange UM ».</span><span class="sxs-lookup"><span data-stu-id="c7544-130">This step is not required for unassigned number ranges that use "Exchange UM" as the selected announcement service.</span></span>

    
    </div>

7.  <span data-ttu-id="c7544-131">Basculez le pool A vers le pool B en mode de reprise après sinistre (DR) en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c7544-131">Fail over Pool A to Pool B in Disaster Recovery (DR) mode, by running the following cmdlet:</span></span>
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  <span data-ttu-id="c7544-132">Pool de génération C, mais ne démarrez aucun service sur le pool C.</span><span class="sxs-lookup"><span data-stu-id="c7544-132">Build pool C, but do not start any services on pool C.</span></span>
    
    <span data-ttu-id="c7544-133">Notez que cette étape peut être effectuée en même temps que les étapes 5 et 6.</span><span class="sxs-lookup"><span data-stu-id="c7544-133">Note that this step can be carried out concurrently with steps 5 and 6.</span></span>

9.  <span data-ttu-id="c7544-134">Faites en sorte que les utilisateurs hébergés sur le pool A puissent accéder au pool C en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c7544-134">Force users homed on pool A to move to pool C by running the following cmdlet:</span></span>
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    <span data-ttu-id="c7544-135">À ce stade, les utilisateurs hébergés sur le pool A commenceront à utiliser une panne de service.</span><span class="sxs-lookup"><span data-stu-id="c7544-135">At this point, users homed on pool A will begin to experience a service outage.</span></span> <span data-ttu-id="c7544-136">Cette interruption continuera jusqu’à l’étape 16, à partir de laquelle les services de pointage sont démarrés sur le pool C.</span><span class="sxs-lookup"><span data-stu-id="c7544-136">This outage will continue until step 16, at which point services are started on pool C.</span></span>

10. <span data-ttu-id="c7544-137">Forcez le répertoire de conférences du groupe A à déplacer vers le pool C en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c7544-137">Force the conference directory of pool A to move to pool C by running the following cmdlet:</span></span>
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. <span data-ttu-id="c7544-138">Forcez l’objet de contact de la Conférence automatique (CAA) à passer du pool A au pool C en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c7544-138">Force the Conference Auto Attendant (CAA) Contact Object to move from pool A to pool C by running the following cmdlet:</span></span>
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. <span data-ttu-id="c7544-139">Copier le contenu d’une conférence du pool B vers le pool C.</span><span class="sxs-lookup"><span data-stu-id="c7544-139">Copy conference content from pool B to pool C.</span></span>

13. <span data-ttu-id="c7544-140">Exportez les données utilisateur à partir du pool B et importez les données utilisateur dans le pool C en exécutant les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="c7544-140">Export user data from pool B and import the user data into pool C by running the following cmdlets:</span></span>
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. <span data-ttu-id="c7544-141">Restaurez les données d’application du parc d’appels sauvegardés à partir du pool A dans le pool C et attribuez-leur les plages d’orbites du pool A au pool C.</span><span class="sxs-lookup"><span data-stu-id="c7544-141">Restore backed-up Call Park application data from pool A into pool C and assign the Call Park orbit ranges of pool A to pool C.</span></span>
    
      - <span data-ttu-id="c7544-142">Vous pouvez réattribuer une plage d’orbites du pool A au pool C à l’aide du panneau de configuration de Lync Server ou de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c7544-142">You can reassign a Call Park orbit range of pool A to pool C either through the Lync Server Control Panel or the Lync Server Management Shell.</span></span> <span data-ttu-id="c7544-143">Pour Lync Server Management Shell, exécutez l’applet de commande suivante pour chaque plage d’orbite de parc d’appels affectée au pool A (Notez que le paramètre Identity fait référence à des plages d’orbite de parking qui appartiennent au pool A) :</span><span class="sxs-lookup"><span data-stu-id="c7544-143">For the Lync Server Management Shell, run the following cmdlet for every Call Park orbit range assigned to pool A (note that the Identity parameter refers to the Call Park Orbit Ranges that belong to pool A):</span></span>
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - <span data-ttu-id="c7544-144">Si un morceau de musique personnalisé a été configuré pour le parc d’appels dans le pool A, restaurez le parc d’appels personnalisé musique en attente dans le pool C.</span><span class="sxs-lookup"><span data-stu-id="c7544-144">If a customized music-on-hold has been configured for Call Park in pool A, restore the Call Park customized music-on-hold file in pool C.</span></span>
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        <span data-ttu-id="c7544-145">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="c7544-145">For example:</span></span>
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - <span data-ttu-id="c7544-146">Pour finir, reconfigurez les paramètres de parc d’appels sur le pool C à l’aide de l’applet de la cmdlet **Set-CsCpsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="c7544-146">Finally, reconfigure the Call Park settings on pool C by using the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="c7544-147">L’application de parc d’appels ne peut stocker qu’un seul ensemble de paramètres et un fichier audio en attente personnalisé par liste, et ces paramètres ne sont pas sauvegardés ou conservés en cas de sinistre.</span><span class="sxs-lookup"><span data-stu-id="c7544-147">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool, and these settings are not backed up or preserved in the event of a disaster.</span></span>

15. <span data-ttu-id="c7544-148">Si le pool de prochains tronçons pour une conversation permanente pointe vers le regroupement A, effectuez et publiez les modifications de topologie de telle sorte que le serveur du tronçon suivant pointe vers le pool C.</span><span class="sxs-lookup"><span data-stu-id="c7544-148">If the next hop pool for Persistent Chat is pointing to pool A, make and publish topology changes so that the next hop server points to pool C.</span></span>
    
      - <span data-ttu-id="c7544-149">Dans le générateur de topologie, modifiez le pool de conversation permanente de manière à ce qu’il pointe vers le pool C comme tronçon suivant.</span><span class="sxs-lookup"><span data-stu-id="c7544-149">In Topology Builder, change the Persistent Chat pool to point to Pool C as its next hop.</span></span> <span data-ttu-id="c7544-150">Pour ce faire, cliquez avec le bouton droit de la touche dans la liste de conversations permanentes, cliquez sur l’onglet **général** , puis tapez le nom du pool C dans le **pool de sauts suivant**.</span><span class="sxs-lookup"><span data-stu-id="c7544-150">To do so, right-click on the Persistent Chat pool, then click the **General** tab, and then type the name of Pool C in **Next Hop Pool**.</span></span>
    
      - <span data-ttu-id="c7544-151">Démarrez les services sur le pool C en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c7544-151">Start services on pool C by running the following cmdlet:</span></span>
        
            Start-csWindowsService
    
    <span data-ttu-id="c7544-152">À ce stade, l’interruption du service se termine pour les utilisateurs initialement hébergés sur le pool A.</span><span class="sxs-lookup"><span data-stu-id="c7544-152">At this point, the service outage ends for users originally homed on pool A.</span></span>

16. <span data-ttu-id="c7544-153">Exportez les flux de travail du service de groupe de réponse de Lync Server du pool B possédé par le pool A pour l’importation dans le pool C en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c7544-153">Export Lync Server Response Group service workflows from pool B owned by pool A for import into pool C by running the following cmdlet:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. <span data-ttu-id="c7544-154">Importez les flux de travail du service de groupe de réponse de Lync Server dans le pool C du pool B.</span><span class="sxs-lookup"><span data-stu-id="c7544-154">Import Lync Server Response Group service workflows into pool C from pool B.</span></span>
    
    <span data-ttu-id="c7544-155">Deux options s’offrent à vous pour importer la configuration de groupe de réponses du pool B au pool C. L’option utilisée varie selon que vous voulez remplacer les paramètres au niveau de l’application du pool C par les paramètres au niveau de l’application dans le pool B.</span><span class="sxs-lookup"><span data-stu-id="c7544-155">You have two options are for importing the Response Group configuration from pool B to pool C. Which option you use depends on whether you want to overwrite the application-level settings of pool C with the application-level settings in pool B.</span></span>
    
      - <span data-ttu-id="c7544-156">Si vous voulez remplacer les paramètres C du pool, exécutez l’applet de commande **Import-CsRgsConfiguration** avec l’option **ReplaceExistingSettings** :</span><span class="sxs-lookup"><span data-stu-id="c7544-156">If you want to overwrite the Pool C settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="c7544-157">Si vous ne voulez pas remplacer les paramètres C du pool, utilisez l’applet de commande **Import-CsRgsConfiguration** sans l’option **ReplaceExistingSettings** .</span><span class="sxs-lookup"><span data-stu-id="c7544-157">If you do not want to overwrite the Pool C settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="c7544-158">Gardez à l’esprit que si vous ne voulez pas remplacer les paramètres au niveau de l’application du pool C avec les paramètres du pool de sauvegarde (pool B), les paramètres au niveau de l’application du pool B seront perdus, car l’application du groupe de réponse ne peut stocker qu’un seul ensemble de niveau application. paramètres par liste.</span><span class="sxs-lookup"><span data-stu-id="c7544-158">Keep in mind that if you do not want to overwrite the application-level settings of Pool C with the settings of the backup pool (pool B), pool B’s application-level settings will be lost because the Response Group application can store only one set of application-level settings per pool.</span></span>

    
    </div>

18. <span data-ttu-id="c7544-159">Vérifiez que l’importation de la configuration du groupe de réponse a été réussie en exécutant les applets de commande suivants pour afficher les groupes de réponse ayant été importés dans le pool C.</span><span class="sxs-lookup"><span data-stu-id="c7544-159">Verify that the Response Group configuration import was successful by running the following cmdlets to display the response groups that have been imported to Pool C.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. <span data-ttu-id="c7544-160">Lorsque la configuration importée a été vérifiée dans le pool C, supprimez les groupes de réponse appartenant au pool principal du pool B. Cela permet de réduire les temps d’arrêt des groupes de réponse.</span><span class="sxs-lookup"><span data-stu-id="c7544-160">When the imported configuration has been verified in pool C, remove the response groups owned by the primary pool from pool B. This will minimize the downtime of the response groups.</span></span>
    
    <span data-ttu-id="c7544-161">Cette étape permet de créer un fichier avec la configuration exportée, puis de supprimer le fichier du pool B.</span><span class="sxs-lookup"><span data-stu-id="c7544-161">This step creates a new file with the exported configuration, and then removes the file from pool B.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. <span data-ttu-id="c7544-162">Déplacer vers le groupe C les plages de numéros non affectées qui ont été déplacées du pool A au pool B.</span><span class="sxs-lookup"><span data-stu-id="c7544-162">Move to pool C the Unassigned Number ranges that were moved from pool A to pool B.</span></span>
    
      - <span data-ttu-id="c7544-163">Recréer dans le pool C toutes les annonces qui ont été recréées à partir du pool A dans le pool B. Si des fichiers audio étaient utilisés lors du déploiement des annonces à déplacer, vous devrez utiliser ces fichiers pour recréer les annonces dans le pool C. Pour recréer les annonces dans le pool C, utilisez les applets de nouvelle applet de **nouvelle-CsAnnouncement** , avec le service parent du pool c.</span><span class="sxs-lookup"><span data-stu-id="c7544-163">Re-create in pool C all announcements that were re-created from pool A in pool B. If any audio files were used when deploying the announcements to be moved, you will need to use these files to re-create the announcements in pool C. To re-create the announcements in pool C, use the **New-CsAnnouncement** cmdlets, with pool C as the Parent service.</span></span>
    
      - <span data-ttu-id="c7544-164">Reciblez le pool C toutes les plages de numéros non attribuées qui ont été reciblées du pool A vers le pool B. Exécutez l’applet de commande suivante pour chaque plage de nombres non affectée qui doit être reciblée :</span><span class="sxs-lookup"><span data-stu-id="c7544-164">Retarget to pool C all the unassigned number ranges that were retargeted from pool A to pool B. Run the following cmdlet for every Unassigned Number range that needs to be retargeted:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - <span data-ttu-id="c7544-165">Facultatif Supprimer du groupe B les annonces qui ont été recréées dans le pool C, si elles ne sont plus utilisées dans le pool B. Pour supprimer des annonces, utilisez l’applet de passe **Remove-CsAnnouncement** .</span><span class="sxs-lookup"><span data-stu-id="c7544-165">(Optional) Remove from pool B the announcements that were re-created in pool C if they are no longer in use in pool B. To remove announcements, use the **Remove-CsAnnouncement** cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c7544-166">Cette étape n’est pas requise pour les plages de nombres non affectées qui utilisent le service d’annonce « UM Exchange ».</span><span class="sxs-lookup"><span data-stu-id="c7544-166">This step is not required for unassigned number ranges that use "Exchange UM" as the announcement service.</span></span>

        
        </div>

21. <span data-ttu-id="c7544-167">Nettoyez les données utilisateur du pool A dans le pool B en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c7544-167">Clean up user data of pool A in pool B by running the following cmdlet:</span></span>
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. <span data-ttu-id="c7544-168">Procédez comme suit dans le générateur de topologie :</span><span class="sxs-lookup"><span data-stu-id="c7544-168">Do the following in Topology Builder:</span></span>
    
      - <span data-ttu-id="c7544-169">Découpler le pool A et le pool B Supprimez ensuite le regroupement A de la topologie et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="c7544-169">Unpair pool A and pool B. Pair pool B and pool C. Then remove Pool A from the topology and publish it.</span></span> <span data-ttu-id="c7544-170">Pour ce faire :</span><span class="sxs-lookup"><span data-stu-id="c7544-170">To do so:</span></span>
        
          - <span data-ttu-id="c7544-171">Dans le générateur de topologie, cliquez avec le bouton droit sur le pool B, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c7544-171">In Topology Builder, right-click on Pool B, and then click **Edit Properties**.</span></span>
        
          - <span data-ttu-id="c7544-172">Cliquez sur **résilience** dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="c7544-172">Click **Resiliency** in the left pane.</span></span>
        
          - <span data-ttu-id="c7544-173">Dans la zone située en dessous de **pool de sauvegarde associé**, sélectionnez Pool C. Notez que la zone de sélection de pool de sauvegarde associée affiche le pool a pour la première fois, car le pool B a été précédemment associé au pool.</span><span class="sxs-lookup"><span data-stu-id="c7544-173">In the box below **Associated Backup Pool**, select Pool C. Note that the Associated Backup Pool selection box will initially display pool A, because pool B was previously associated with this pool.</span></span>
        
          - <span data-ttu-id="c7544-174">Sélectionnez **Basculement et restauration automatiques pour Voice**, puis cliquez sur \*\*OK \*\*.</span><span class="sxs-lookup"><span data-stu-id="c7544-174">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
            
            <span data-ttu-id="c7544-175">Quand vous affichez les détails de ce pool, le pool associé s’affiche dans le volet droit sous **Résistance**. </span><span class="sxs-lookup"><span data-stu-id="c7544-175">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span>
        
          - <span data-ttu-id="c7544-176">Dans l’arborescence de la console, cliquez avec le bouton droit sur l’ensemble de la liste, puis cliquez sur supprimer.</span><span class="sxs-lookup"><span data-stu-id="c7544-176">In the console tree, right-click pool A, and then click Delete.</span></span>
        
          - <span data-ttu-id="c7544-177">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="c7544-177">Publish the topology.</span></span>

23. <span data-ttu-id="c7544-178">Exécutez l’application de démarrage sur le pool C pour installer l’application de service de sauvegarde, puis démarrez l’application de service de sauvegarde en exécutant la commande suivante à partir du dossier de déploiement sur un ordinateur local dans le pool C :</span><span class="sxs-lookup"><span data-stu-id="c7544-178">Run the bootstrapping application on pool C to install the backup service application, and then start the backup service application by running the following from the deployment folder on a local machine in pool C:</span></span>
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. <span data-ttu-id="c7544-179">Redémarrez l’application de service de sauvegarde sur le pool B en exécutant les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="c7544-179">Restart the backup service application on pool B by running the following cmdlets:</span></span>
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. <span data-ttu-id="c7544-180">S’il s’agit d’un pool standard édition (SE) et du pool B de CMS, installez la base de données CMS manuellement sur le pool C en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c7544-180">If pool C is a Standard Edition (SE) Pool and pool B has CMS, install the CMS database manually on pool C by running the following cmdlet:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. <span data-ttu-id="c7544-181">Invoquez le service de sauvegarde pour synchroniser les anciens contenus de conférences du pool B vers le pool C qui a été généré avant de jumeler les paires B et C, et pour synchroniser le nouveau contenu de conférences du pool C vers le pool B qui a été généré après le démarrage du pool C et avant le jumelage entre B et C.</span><span class="sxs-lookup"><span data-stu-id="c7544-181">Invoke the backup service to sync old conferencing content from pool B to pool C that was generated before pairing B and C together, and to sync new conferencing content from pool C to pool B that was generated after starting pool C and before B and C were paired together.</span></span> <span data-ttu-id="c7544-182">Pour cela, exécutez les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="c7544-182">To do so, run the following cmdlets:</span></span>
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. <span data-ttu-id="c7544-183">Pour chaque appareil de branchement Survivable X associé au pool A :</span><span class="sxs-lookup"><span data-stu-id="c7544-183">For each Survivable Branch Appliance X associated with pool A:</span></span>
    
      - <span data-ttu-id="c7544-184">Arrêtez l’argument SBA X en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c7544-184">Shut down SBA X by running the following cmdlet:</span></span>
        
            Stop-CsWindowsService
    
      - <span data-ttu-id="c7544-185">Créez un fichier contenant une liste d’utilisateurs hébergés sur SBA X. La liste sera nécessaire lorsque les utilisateurs seront redirigés vers SBA X à l’étape 30.</span><span class="sxs-lookup"><span data-stu-id="c7544-185">Create a file that contains a list of users homed on SBA X. The list will be needed when the users are moved back to SBA X in step 30.</span></span> <span data-ttu-id="c7544-186">Pour cela, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c7544-186">To do so, run the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - <span data-ttu-id="c7544-187">Faites en sorte que les utilisateurs hébergés sur SBA X soient déplacés vers le pool C en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c7544-187">Force users homed on SBA X to move to pool C by running the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - <span data-ttu-id="c7544-188">Mettez à jour les données de ces utilisateurs en exécutant d’abord les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="c7544-188">Update the data of these users by first running the following cmdlets:</span></span>
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        <span data-ttu-id="c7544-189">Puis exécutez le script suivant :</span><span class="sxs-lookup"><span data-stu-id="c7544-189">And then run this script:</span></span>
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c7544-190">Une panne de service survient pour les utilisateurs qui sont hébergés sur SBAs qui sont associés au pool A jusqu’à ce que ces utilisateurs soient déplacés vers le pool C.</span><span class="sxs-lookup"><span data-stu-id="c7544-190">A service outage will occur for users who are homed on SBAs that are associated with pool A until these users are moved to pool C.</span></span>

        
        </div>

28. <span data-ttu-id="c7544-191">Dans le générateur de topologie, pour chaque SBA X précédemment associé au pool A, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c7544-191">In Topology Builder, for each SBA X previously associated with Pool A, do the following:</span></span>
    
      - <span data-ttu-id="c7544-192">Remplacez l’Association par le pool C. Pour cela, cliquez sur le site de la succursale, développez le nœud périphériques et périphériques Survivables, puis cliquez sur **appareil de branchement Survivable**.</span><span class="sxs-lookup"><span data-stu-id="c7544-192">Change the association to Pool C. To do so, click the branch site, expand the Survivable Branch Appliances or Servers node, and click **Survivable Branch Appliance**.</span></span> <span data-ttu-id="c7544-193">Sélectionnez ensuite le pool **frontal, le pool de services d’utilisateurs** auquel cette application de branche Survivable sera connectée en tant que Pool C, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="c7544-193">Then select the **Front End pool, User Services Pool** that this Survivable Branch Appliance will connect to as Pool C, and then click **Next**.</span></span>
    
      - <span data-ttu-id="c7544-194">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="c7544-194">Publish the topology.</span></span> <span data-ttu-id="c7544-195">Pour ce faire, dans l’arborescence de la console, cliquez avec le bouton droit sur la nouvelle **application branche Survivable**, cliquez sur **Topology**, puis sur **publier**.</span><span class="sxs-lookup"><span data-stu-id="c7544-195">To do so, in the console tree, right-click the new **Survivable Branch Appliance**, click **Topology**, and then click **Publish**.</span></span>

29. <span data-ttu-id="c7544-196">Pour chaque SBA X désormais associé au pool C :</span><span class="sxs-lookup"><span data-stu-id="c7544-196">For each SBA X now associated with pool C:</span></span>
    
      - <span data-ttu-id="c7544-197">Démarrez SBA X en exécutant l’applet de commande suivante sur l’unité de commande Survivable :</span><span class="sxs-lookup"><span data-stu-id="c7544-197">Start SBA X by running the following cmdlet on the survivable branch appliance:</span></span>
        
            Start-CsWindowsService
    
      - <span data-ttu-id="c7544-198">Déplacez les utilisateurs initialement hébergés sur SBA X du pool C à SBA X en exécutant l’applet de commande suivante.</span><span class="sxs-lookup"><span data-stu-id="c7544-198">Move users who were originally homed on SBA X from pool C to SBA X by running the following cmdlet.</span></span>
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

