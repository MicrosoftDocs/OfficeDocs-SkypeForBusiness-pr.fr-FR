---
title: Migrer des groupes Response Group
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Après le déplacement de vos utilisateurs vers les pools 2019 de Skype entreprise Server, vous pouvez migrer vos groupes de réponse. La migration de Response Groups inclut la copie de groupes d’agents, de files d’attente, de flux de travail, de fichiers audio et de déplacements de groupe de réponses de l’ancien déploiement vers le pool Skype entreprise Server 2019. Après avoir migré vos groupes de réponses héritées, les appels vers les groupes de réponse sont gérés par l’application Response Group dans le pool Skype entreprise Server 2019. Les appels de Response Groups ne sont plus gérés par le pool hérité.
ms.openlocfilehash: cba50526748ca15c04513013e484b0e279410c1e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298203"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="c6662-106">Migrer des groupes Response Group</span><span class="sxs-lookup"><span data-stu-id="c6662-106">Migrate response groups</span></span>

<span data-ttu-id="c6662-107">Après le déplacement de vos utilisateurs vers les pools 2019 de Skype entreprise Server, vous pouvez migrer vos groupes de réponse.</span><span class="sxs-lookup"><span data-stu-id="c6662-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="c6662-108">La migration de Response Groups inclut la copie de groupes d’agents, de files d’attente, de flux de travail, de fichiers audio et de déplacements de groupe de réponses de l’ancien déploiement vers le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c6662-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="c6662-109">Après avoir migré vos groupes de réponses héritées, les appels vers les groupes de réponse sont gérés par l’application Response Group dans le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c6662-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="c6662-110">Les appels de Response Groups ne sont plus gérés par le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="c6662-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c6662-111">Même si vous pouvez migrer des groupes de réponses avant de déplacer tous les utilisateurs vers le pool 2019 de Skype entreprise Server, nous vous conseillons de déplacer d’abord tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c6662-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="c6662-112">En particulier, les utilisateurs qui sont des agents de Response Group n’auront pas toutes les fonctionnalités des nouvelles fonctionnalités tant qu’ils ne seront pas déplacés vers le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c6662-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="c6662-113">Avant de migrer des groupes de réponse, vous devez avoir déployé un pool Skype entreprise Server 2019 incluant l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="c6662-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="c6662-114">L’application Response Group est installée et activée par défaut lorsque vous déployez Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="c6662-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="c6662-115">Vous pouvez vous assurer que l’application Response Group est installée en exécutant l’applet de demande **Get-CsService-ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="c6662-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c6662-116">Vous pouvez créer des groupes de réponse Skype entreprise Server 2019 dans le pool 2019 de Skype entreprise Server avant de migrer vos groupes de réponse hérités.</span><span class="sxs-lookup"><span data-stu-id="c6662-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="c6662-117">Pour migrer des groupes de réponse d’un pool hérité vers Skype entreprise Server 2019, vous exécutez l’applet de **passe Move-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="c6662-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c6662-118">L’applet de passe de migration de groupe de réponse déplace la configuration de groupe de réponse pour le pool entier.</span><span class="sxs-lookup"><span data-stu-id="c6662-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="c6662-119">Vous ne pouvez pas sélectionner des groupes, des files d’attente ou des flux de travail spécifiques à migrer.</span><span class="sxs-lookup"><span data-stu-id="c6662-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="c6662-120">Après avoir migré les groupes de réponse, vous devez utiliser le panneau de configuration Skype entreprise Server ou les applets de commande Skype entreprise Server Management Shell pour vérifier que tous les groupes d’agents, files d’attente et flux de travail sont déplacés correctement.</span><span class="sxs-lookup"><span data-stu-id="c6662-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="c6662-121">Lorsque vous migrez des groupes de réponse, les groupes de réponse hérités ne sont pas supprimés.</span><span class="sxs-lookup"><span data-stu-id="c6662-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="c6662-122">Lorsque vous gérez des groupes de réponse après une migration à l’aide du panneau de configuration Skype entreprise Server ou de l’interpréteur de commandes Skype entreprise Server Management Shell, vous pouvez voir les groupes de réponse hérités et les groupes de réponse Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c6662-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="c6662-123">Vous devez appliquer les mises à jour uniquement aux groupes de réponse Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c6662-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="c6662-124">Les groupes de réponse hérités sont conservés uniquement à des fins de restauration.</span><span class="sxs-lookup"><span data-stu-id="c6662-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="c6662-125">Une fois la migration effectuée et les nouveaux groupes de réponse créés, le panneau de configuration Skype entreprise Server et Skype entreprise Server Management Shell affichent les versions d’anciens et de Skype entreprise Server 2019 de chaque réponse. Groupe.</span><span class="sxs-lookup"><span data-stu-id="c6662-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="c6662-126">N’utilisez pas le panneau de configuration Skype entreprise Server ou Skype entreprise Server Management Shell pour supprimer les groupes de réponse hérités.</span><span class="sxs-lookup"><span data-stu-id="c6662-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="c6662-127">Si vous supprimez un, le groupe de réponse correspondant qui a été créé lors de la migration ne fonctionnera plus.</span><span class="sxs-lookup"><span data-stu-id="c6662-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="c6662-128">Les groupes de réponse hérités seront supprimés lorsque vous désaffecterez le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="c6662-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c6662-129">Nous vous recommandons de ne pas supprimer les données de votre déploiement antérieur tant que vous n’avez pas désactivé le pool.</span><span class="sxs-lookup"><span data-stu-id="c6662-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="c6662-130">Par ailleurs, nous vous conseillons vivement d’exporter des groupes de réponse immédiatement après la migration.</span><span class="sxs-lookup"><span data-stu-id="c6662-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="c6662-131">Si un groupe de réponse héritée doit être supprimé, vous pouvez restaurer vos groupes de réponse à partir de la sauvegarde pour obtenir de nouveau les groupes de réponse Skype entreprise Server 2019 en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="c6662-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="c6662-132">Skype entreprise Server 2019 introduit une nouvelle fonctionnalité de groupe de réponse appelée **type de flux de travail**.</span><span class="sxs-lookup"><span data-stu-id="c6662-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="c6662-133">Le **type de flux de travail** peut être **géré** ou **non**géré.</span><span class="sxs-lookup"><span data-stu-id="c6662-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="c6662-134">Tous les groupes de réponses sont migrés avec le **type de flux de travail** défini sur **non géré** et avec une liste de gestionnaires vide.</span><span class="sxs-lookup"><span data-stu-id="c6662-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="c6662-135">Lorsque vous exécutez l’applet de cmdlet **Move-CsRgsConfiguration** , les groupes d’agents, les files d’attente, les flux de travail et les fichiers audio restent dans le pool hérité à des fins de restauration.</span><span class="sxs-lookup"><span data-stu-id="c6662-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="c6662-136">Toutefois, si vous avez besoin de revenir au pool hérité, vous devez exécuter l’applet de passe **Move-CsApplicationEndpoint** pour replacer les objets de contact sur le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="c6662-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="c6662-137">La procédure suivante pour la migration de configurations de groupe de réponse suppose que vous disposez d’une relation un-à-un entre vos pools hérités et les pools 2019 de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c6662-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="c6662-138">Si vous envisagez de consolider ou de fractionner des listes lors de la migration et du déploiement, vous devez planifier les mappages de réserve héritée vers le pool 2019 de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c6662-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="c6662-139">Pour migrer les configurations de Response Group</span><span class="sxs-lookup"><span data-stu-id="c6662-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="c6662-140">Ouvrez une session sur l’ordinateur avec un compte membre du groupe RTCUniversalServerAdmins ou disposant d’autorisations et de droits d’administrateur équivalents.</span><span class="sxs-lookup"><span data-stu-id="c6662-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="c6662-141">Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Microsoft Skype entreprise Server 2019**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c6662-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c6662-142">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="c6662-142">Run:</span></span>
    
   ```
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="c6662-143">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="c6662-143">For example:</span></span>
    
   ```
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="c6662-144">Après avoir migré des groupes de réponses et des agents vers le pool Skype entreprise Server 2019, l’URL que les agents utilisent pour se connecter et se déconnecter est une URL de Skype entreprise Server 2019 et est disponible dans le menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="c6662-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="c6662-145">Rappelez aux agents de mettre à jour les références, comme les signets, à la nouvelle URL.</span><span class="sxs-lookup"><span data-stu-id="c6662-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c6662-146">Pour vérifier la migration du groupe de réponse à l’aide du panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="c6662-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c6662-147">Ouvrez une session sur l’ordinateur avec un compte membre du groupe RTCUniversalReadOnlyAdmins ou qui est membre du rôle CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c6662-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="c6662-148">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c6662-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="c6662-149">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Skype entreprise Server, reportez-vous à la rubrique [ouverture des outils d’administration 2019 de Skype entreprise Server](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span><span class="sxs-lookup"><span data-stu-id="c6662-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="c6662-150">Dans le volet de navigation de gauche, cliquez sur **Response Groups**.</span><span class="sxs-lookup"><span data-stu-id="c6662-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="c6662-151">Dans l’onglet **flux de travail** , assurez-vous que tous les flux de travail de votre environnement hérité sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c6662-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="c6662-152">Cliquez sur l’onglet **file d’attente** , puis vérifiez que toutes les files d’attente de votre environnement hérité sont incluses dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c6662-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="c6662-153">Cliquez sur l’onglet **groupe** , puis vérifiez que tous les groupes d’agents de votre environnement hérité sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c6662-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c6662-154">Pour vérifier la migration de groupe de réponse à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="c6662-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="c6662-155">Ouvrez une session sur l’ordinateur avec un compte membre du groupe RTCUniversalReadOnlyAdmins ou qui est membre du rôle CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c6662-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="c6662-156">Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Microsoft Skype entreprise Server 2019**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c6662-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="c6662-157">Pour plus d’informations sur les applets de commande suivantes, exécutez:</span><span class="sxs-lookup"><span data-stu-id="c6662-157">For details about the following cmdlets, run:</span></span>
    
   ```
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="c6662-158">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="c6662-158">Run:</span></span>
    
   ```
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="c6662-159">Vérifiez que tous les groupes d’agents de votre environnement hérité sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c6662-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="c6662-160">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="c6662-160">Run:</span></span>
    
   ```
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="c6662-161">Vérifiez que toutes les files d’attente dans votre environnement hérité sont incluses dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c6662-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="c6662-162">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="c6662-162">Run:</span></span>
    
   ```
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="c6662-163">Vérifiez que tous les flux de travail de votre environnement hérité sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c6662-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

