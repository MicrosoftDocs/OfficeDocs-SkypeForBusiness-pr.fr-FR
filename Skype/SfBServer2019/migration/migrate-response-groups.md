---
title: Effectuer la migration de groupes Response Group
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Une fois les utilisateurs déplacés vers les pools Skype entreprise Server 2019, vous pouvez migrer vos groupes Response Group. La migration de groupes Response Group consiste à copier des groupes d’agents, des files d’attente, des flux de travail, des fichiers audio et des objets de contact de groupe Response Group à partir du déploiement hérité vers le pool Skype entreprise Server 2019. Une fois vos groupes de réponse hérités migrés, les appels vers les groupes Response Group sont gérés par l’application Response Group dans le pool Skype entreprise Server 2019. Les appels destinés aux groupes Response Group ne sont plus gérés par le pool hérité.
ms.openlocfilehash: 2d439462fa103cc16fd7ae70b79364be7d79803a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42016105"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="c2f7c-106">Effectuer la migration de groupes Response Group</span><span class="sxs-lookup"><span data-stu-id="c2f7c-106">Migrate response groups</span></span>

<span data-ttu-id="c2f7c-107">Une fois les utilisateurs déplacés vers les pools Skype entreprise Server 2019, vous pouvez migrer vos groupes Response Group.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="c2f7c-108">La migration de groupes Response Group consiste à copier des groupes d’agents, des files d’attente, des flux de travail, des fichiers audio et des objets de contact de groupe Response Group à partir du déploiement hérité vers le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="c2f7c-109">Une fois vos groupes de réponse hérités migrés, les appels vers les groupes Response Group sont gérés par l’application Response Group dans le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="c2f7c-110">Les appels destinés aux groupes Response Group ne sont plus gérés par le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c2f7c-111">Bien que vous puissiez migrer des groupes Response Group avant de déplacer tous les utilisateurs vers le pool Skype entreprise Server 2019, nous vous recommandons de déplacer tous les utilisateurs en premier.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="c2f7c-112">En particulier, les utilisateurs qui sont des agents Response Group ne disposent pas de toutes les fonctionnalités des nouvelles fonctionnalités tant qu’ils ne sont pas déplacés vers le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="c2f7c-113">Avant de migrer les groupes Response Group, vous devez avoir déployé un pool Skype entreprise Server 2019 qui inclut l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="c2f7c-114">L’application Response Group est installée et activée par défaut lorsque vous déployez voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="c2f7c-115">Vous pouvez vous assurer que l’application Response Group est installée en exécutant la cmdlet **Get-CsService-ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="c2f7c-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c2f7c-116">Vous pouvez créer des groupes de réponses Skype entreprise Server 2019 dans le pool de Skype entreprise Server 2019 avant de migrer vos groupes de réponse hérités.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="c2f7c-117">Pour migrer des groupes Response Group d’un pool hérité vers Skype entreprise Server 2019, exécutez l’applet de commande **Move-applet csrgsconfiguration** .</span><span class="sxs-lookup"><span data-stu-id="c2f7c-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c2f7c-118">La cmdlet Response Group migration déplace la configuration Response Group pour l’ensemble du pool.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="c2f7c-119">Vous ne pouvez pas sélectionner de groupes, files d’attente ou flux de travail spécifiques à migrer.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="c2f7c-120">Après avoir migré les groupes Response Group, vous devez utiliser le panneau de configuration de Skype entreprise Server ou les applets de commande Skype entreprise Server Management Shell pour vérifier que tous les groupes d’agents, files d’attente et flux de travail ont été déplacés avec succès.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="c2f7c-121">Lorsque vous migrez des groupes Response Group, les groupes Response Group hérités ne sont pas supprimés.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="c2f7c-122">Lorsque vous gérez des groupes Response Group après une migration à l’aide du panneau de configuration de Skype entreprise ou de Skype entreprise Server Management Shell, vous pouvez voir les groupes Response Group hérités et Skype entreprise Server 2019 Response groups.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="c2f7c-123">Vous devez appliquer les mises à jour uniquement aux groupes Response Group de Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="c2f7c-124">Les groupes Response Group hérités ne sont conservés qu’à des fins de restauration.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="c2f7c-125">Une fois que la migration est terminée et que les nouveaux groupes Response Group ont été créés, le panneau de configuration Skype entreprise Server et Skype entreprise Server Management Shell afficheront les versions héritées et Skype entreprise Server 2019 de chaque réponse. Communauté.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="c2f7c-126">N’utilisez pas le panneau de configuration Skype entreprise Server ou Skype entreprise Server Management Shell pour supprimer les groupes Response Group hérités.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="c2f7c-127">Si vous supprimez un, le groupe Response Group correspondant qui a été créé pendant la migration cessera de fonctionner.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="c2f7c-128">Les groupes Response Group hérités sont supprimés lorsque vous désactivez le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c2f7c-129">Nous vous recommandons de ne pas supprimer les données de votre déploiement précédent tant que vous n’avez pas désaffecté le pool.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="c2f7c-130">En outre, nous vous recommandons fortement d’exporter les groupes Response Group immédiatement après la migration.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="c2f7c-131">Si un groupe Response Group hérité doit être supprimé, vous pouvez restaurer vos groupes Response Group à partir de la sauvegarde pour obtenir les groupes de réponse Skype entreprise Server 2019 en cours d’exécution à nouveau.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="c2f7c-132">Skype entreprise Server 2019 introduit une nouvelle fonctionnalité Response Group appelée **type de flux de travail**.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="c2f7c-133">Le **Type de flux de travail** peut être **Géré** ou **Non géré**.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="c2f7c-134">Tous les groupes Response Group sont migrés avec le **Type de flux de travail** défini à **Non géré** et avec une liste de gestionnaires vide.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="c2f7c-135">Lorsque vous exécutez l’applet de commande **Move-applet csrgsconfiguration** , les groupes d’agents, les files d’attente, les flux de travail et les fichiers audio restent dans le pool hérité à des fins de restauration.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="c2f7c-136">Toutefois, si vous devez restaurer le pool hérité, vous devez exécuter la cmdlet **Move-CsApplicationEndpoint** pour déplacer les objets contact vers le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="c2f7c-137">La procédure suivante pour migrer des configurations de groupe Response Group suppose que vous avez une relation un-à-un entre vos pools hérités et les pools de Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="c2f7c-138">Si vous envisagez de consolider ou de fractionner les pools lors de la migration et du déploiement, vous devez planifier le pool hérité mappé vers le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="c2f7c-139">Pour migrer des configurations de groupe Response Group</span><span class="sxs-lookup"><span data-stu-id="c2f7c-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="c2f7c-140">Ouvrez une session sur l’ordinateur en utilisant un compte membre du groupe RTCUniversalServerAdmins ou disposant de droits et d’autorisations d’administrateur équivalents.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="c2f7c-141">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Skype entreprise Server 2019**, puis sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c2f7c-142">Générer</span><span class="sxs-lookup"><span data-stu-id="c2f7c-142">Run:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="c2f7c-143">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="c2f7c-143">For example:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="c2f7c-144">Une fois que vous avez migré les groupes Response Group et les agents vers le pool Skype entreprise Server 2019, l’URL que les agents utilisent pour se connecter et se déconnecter est une URL de Skype entreprise Server 2019 et est disponible dans le menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="c2f7c-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="c2f7c-145">Rappelez aux agents de mettre à jour les références, telles que les signets, vers la nouvelle URL.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c2f7c-146">Pour vérifier la migration de groupes Response Group à l’aide du panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="c2f7c-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c2f7c-147">Ouvrez une session sur l’ordinateur à l’aide d’un compte membre du groupe RTCUniversalReadOnlyAdmins ou qui soit au moins membre du rôle CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="c2f7c-148">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="c2f7c-149">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Skype entreprise Server, voir [Open Skype for Business server 2019 administrative Tools](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx).</span><span class="sxs-lookup"><span data-stu-id="c2f7c-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="c2f7c-150">Dans le volet de navigation gauche, cliquez sur **Services Response Group**.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="c2f7c-151">Sous l’onglet **flux de travail** , vérifiez que tous les flux de travail de votre environnement hérité sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="c2f7c-152">Cliquez sur l’onglet **file d’attente** , puis vérifiez que toutes les files d’attente de votre environnement hérité sont incluses dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="c2f7c-153">Cliquez sur l’onglet **groupe** , puis vérifiez que tous les groupes d’agents de votre environnement hérité sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c2f7c-154">Pour vérifier la migration de groupes Response Group à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="c2f7c-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="c2f7c-155">Ouvrez une session sur l’ordinateur à l’aide d’un compte membre du groupe RTCUniversalReadOnlyAdmins ou qui soit au moins membre du rôle CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="c2f7c-156">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Skype entreprise Server 2019**, puis sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="c2f7c-157">Pour plus d’informations sur les applets de commande suivantes, exécutez :</span><span class="sxs-lookup"><span data-stu-id="c2f7c-157">For details about the following cmdlets, run:</span></span>
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="c2f7c-158">Générer</span><span class="sxs-lookup"><span data-stu-id="c2f7c-158">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="c2f7c-159">Vérifiez que tous les groupes d’agents de votre environnement hérité sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="c2f7c-160">Générer</span><span class="sxs-lookup"><span data-stu-id="c2f7c-160">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="c2f7c-161">Vérifiez que toutes les files d’attente de votre environnement hérité sont incluses dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="c2f7c-162">Générer</span><span class="sxs-lookup"><span data-stu-id="c2f7c-162">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="c2f7c-163">Vérifiez que tous les flux de travail de votre environnement hérité sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c2f7c-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

