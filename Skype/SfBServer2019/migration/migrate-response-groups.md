---
title: Migrer des groupes de réponses
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Une fois que vos utilisateurs sont déplacés vers Skype pour les pools d’entreprise Server 2019, vous pouvez migrer vos groupes Response Group. Migration de Response Group groupes comprend la copie des groupes d’agents, les files d’attente, les flux de travail, les fichiers audio et déplacer les objets de contact de Response Group à partir du déploiement hérité vers le Skype pour Business Server 2019 pool. Après avoir fait migrer vos groupes Response Group hérités, les appels vers les groupes Response Group sont gérés par l’application Response Group dans le Skype pour Business Server 2019 pool. Les appels vers les groupes Response Group sont ne sont plus gérés par le pool hérité.
ms.openlocfilehash: bdff9b96b73e925fb68b4a2f9bebb9b23edb4b56
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028018"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="3902e-106">Migrer des groupes de réponses</span><span class="sxs-lookup"><span data-stu-id="3902e-106">Migrate response groups</span></span>

<span data-ttu-id="3902e-107">Une fois que vos utilisateurs sont déplacés vers Skype pour les pools d’entreprise Server 2019, vous pouvez migrer vos groupes Response Group.</span><span class="sxs-lookup"><span data-stu-id="3902e-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="3902e-108">Migration de Response Group groupes comprend la copie des groupes d’agents, les files d’attente, les flux de travail, les fichiers audio et déplacer les objets de contact de Response Group à partir du déploiement hérité vers le Skype pour Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="3902e-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="3902e-109">Après avoir fait migrer vos groupes Response Group hérités, les appels vers les groupes Response Group sont gérés par l’application Response Group dans le Skype pour Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="3902e-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="3902e-110">Les appels vers les groupes Response Group sont ne sont plus gérés par le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="3902e-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3902e-111">Bien que vous pouvez migrer des groupes de réponses avant de déplacer tous les utilisateurs vers le Skype pour le pool d’entreprise Server 2019, nous vous recommandons de déplacer tout d’abord tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3902e-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="3902e-112">En particulier, les utilisateurs qui sont des agents response group n’auront pas toutes les fonctionnalités des nouvelles fonctionnalités jusqu'à ce qu’ils sont déplacés vers le Skype pour Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="3902e-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="3902e-113">Avant de migrer les groupes Response Group, vous devez avoir déployé un Skype pour le pool d’entreprise Server 2019 qui inclut l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="3902e-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="3902e-114">L’application Response Group est installée et activée par défaut lors du déploiement d’Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="3902e-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="3902e-115">Vous pouvez vous assurer que l’application Response Group est installée en exécutant l’applet de commande **Get-CsService-ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="3902e-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3902e-116">Vous pouvez créer nouveau Skype pour les groupes de réponse Business Server 2019 dans le Skype pour Business Server 2019 pool avant de migrer vos groupes Response Group hérités.</span><span class="sxs-lookup"><span data-stu-id="3902e-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="3902e-117">Pour migrer des groupes de réponses à partir d’un pool hérité vers le Skype pour Business Server 2019, vous exécutez l’applet de commande **Move-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="3902e-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="3902e-118">L’applet de commande de migration de Response Group déplace la configuration de Response Group pour l’intégralité du pool.</span><span class="sxs-lookup"><span data-stu-id="3902e-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="3902e-119">Vous ne pouvez pas sélectionner des groupes spécifiques, des files d’attente ou des flux de travail à migrer.</span><span class="sxs-lookup"><span data-stu-id="3902e-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="3902e-120">Après avoir migré les groupes Response Group, vous devez utiliser Skype pour le panneau de configuration serveur Business ou Skype pour les applets de commande Business Server Management Shell pour vérifier que tous les groupes d’agents, files d’attente et flux de travail déplacés avec succès.</span><span class="sxs-lookup"><span data-stu-id="3902e-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="3902e-121">Lorsque vous migrez des groupes de réponses, les groupes Response Group hérités ne sont pas supprimés.</span><span class="sxs-lookup"><span data-stu-id="3902e-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="3902e-122">Lorsque vous gérez des groupes de réponses après la migration à l’aide de deux Skype pour le panneau de configuration serveur Business ou Skype pour Business Server Management Shell, vous pouvez voir les groupes Response Group hérités et le Skype pour les groupes de réponse Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3902e-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="3902e-123">Vous devez appliquer les mises à jour uniquement à la Skype pour les groupes de réponse Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3902e-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="3902e-124">Les groupes Response Group hérités sont conservées uniquement à des fins de restauration.</span><span class="sxs-lookup"><span data-stu-id="3902e-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="3902e-125">Une fois la migration est terminée et les nouveaux groupes de réponse ont été créés, le Skype pour le panneau de configuration serveur Business et le Skype pour Business Server Management Shell affichera hérité et Skype pour les versions Business Server 2019 de chaque réponse. groupe.</span><span class="sxs-lookup"><span data-stu-id="3902e-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="3902e-126">N’utilisez pas Skype pour le panneau de configuration serveur Business ou Skype pour Business Server Management Shell pour supprimer les groupes Response Group hérités.</span><span class="sxs-lookup"><span data-stu-id="3902e-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="3902e-127">Si vous supprimez un, le groupe Response Group correspondante qui a été créé lors de la migration cessera de fonctionner.</span><span class="sxs-lookup"><span data-stu-id="3902e-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="3902e-128">Les groupes Response Group hérités seront supprimés lorsque vous mettez hors service le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="3902e-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="3902e-129">Nous vous recommandons de ne pas supprimer toutes les données de votre déploiement précédent jusqu'à ce que vous mettez hors service le pool.</span><span class="sxs-lookup"><span data-stu-id="3902e-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="3902e-130">En outre, il est vivement recommandé que vous exportez des groupes de réponses immédiatement après la migration.</span><span class="sxs-lookup"><span data-stu-id="3902e-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="3902e-131">Si un groupe Response Group hérités doit obtenir supprimé, vous pouvez ensuite restaurer vos groupes Response Group à partir de la sauvegarde pour obtenir Skype pour les groupes de réponses Business Server 2019 exécute à nouveau.</span><span class="sxs-lookup"><span data-stu-id="3902e-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="3902e-132">Skype pour Business Server 2019 présente une nouvelle fonctionnalité de Response Group appelée le **Type de flux de travail**.</span><span class="sxs-lookup"><span data-stu-id="3902e-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="3902e-133">**Type de flux de travail** peuvent être **gérés** ou **non gérés**.</span><span class="sxs-lookup"><span data-stu-id="3902e-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="3902e-134">Tous les groupes de réponse sont migrés avec le **Type de flux de travail** , la valeur **non géré** et avec une liste vide de gestionnaire.</span><span class="sxs-lookup"><span data-stu-id="3902e-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="3902e-135">Lorsque vous exécutez l’applet de commande **Move-CsRgsConfiguration** , les groupes d’agents, files d’attente, flux de travail et les fichiers audio restent dans le pool hérité à des fins de restauration.</span><span class="sxs-lookup"><span data-stu-id="3902e-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="3902e-136">Si vous n’avez pas besoin de restaurer le pool hérité, toutefois, vous devez exécuter l’applet de commande **Move-CsApplicationEndpoint** pour déplacer les objets contact retour vers le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="3902e-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="3902e-137">La procédure suivante pour migrer des configurations Response Group suppose que vous disposez d’une relation entre vos pools hérités et le Skype pour les pools d’entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3902e-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="3902e-138">Si vous prévoyez de consolider ou fractionner des pools au cours de votre déploiement et de migration, vous devez planifier le pool hérité mappe sur quels Skype pour Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="3902e-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="3902e-139">Pour migrer les configurations de Response Group</span><span class="sxs-lookup"><span data-stu-id="3902e-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="3902e-140">Ouvrez une session l’ordinateur avec un compte qui est membre du groupe RTCUniversalServerAdmins ou disposant d’autorisations et droits d’administrateur équivalents.</span><span class="sxs-lookup"><span data-stu-id="3902e-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="3902e-141">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Microsoft Skype pour Business Server 2019**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="3902e-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="3902e-142">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="3902e-142">Run:</span></span>
    
  ```
  Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
  ```

    <span data-ttu-id="3902e-143">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="3902e-143">For example:</span></span>
    
  ```
  Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
  ```

4. <span data-ttu-id="3902e-144">Après avoir migré les groupes de réponses et les agents à la Skype pour le pool d’entreprise Server 2019, l’URL que les agents utilisent pour se connecter et se déconnecter est un Skype pour Business 2019 URL et est disponible dans le menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="3902e-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="3902e-145">Rappeler les agents à mettre à jour toutes les références, telles que des signets, vers la nouvelle URL.</span><span class="sxs-lookup"><span data-stu-id="3902e-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="3902e-146">Pour vérifier la migration de Response Group à l’aide de Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="3902e-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="3902e-147">Ouvrez une session l’ordinateur avec un compte qui est membre du groupe RTCUniversalReadOnlyAdmins ou qui est au moins un membre du rôle CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3902e-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="3902e-148">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="3902e-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="3902e-149">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer Skype pour le panneau de configuration serveur Business, voir [Open Skype pour les outils d’administration Business Server 2019](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span><span class="sxs-lookup"><span data-stu-id="3902e-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="3902e-150">Dans le volet de navigation de gauche, cliquez sur **Groupes Response Group**.</span><span class="sxs-lookup"><span data-stu-id="3902e-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="3902e-151">Sous l’onglet **flux de travail** , vérifiez que tous les flux de travail de votre environnement hérité est inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="3902e-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="3902e-152">Cliquez sur l’onglet **file d’attente** et vérifiez que toutes les files d’attente dans votre environnement hérité sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="3902e-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="3902e-153">Cliquez sur l’onglet **groupe** et vérifiez que tous les groupes d’agents de votre environnement hérité sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="3902e-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="3902e-154">Pour vérifier la migration de Response Group à l’aide de Skype pour Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="3902e-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="3902e-155">Ouvrez une session l’ordinateur avec un compte qui est membre du groupe RTCUniversalReadOnlyAdmins ou qui est au moins un membre du rôle CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3902e-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="3902e-156">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Microsoft Skype pour Business Server 2019**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="3902e-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="3902e-157">Pour plus d’informations sur les applets de commande suivantes, exécutez :</span><span class="sxs-lookup"><span data-stu-id="3902e-157">For details about the following cmdlets, run:</span></span>
    
  ```
  Get-Help <cmdlet name> -Detailed
  ```

3. <span data-ttu-id="3902e-158">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="3902e-158">Run:</span></span>
    
  ```
  Get-CsRgsAgentGroup
  ```

4. <span data-ttu-id="3902e-159">Vérifiez que tous les groupes d’agents de votre environnement hérité sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="3902e-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="3902e-160">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="3902e-160">Run:</span></span>
    
  ```
  Get-CsRgsQueue
  ```

6. <span data-ttu-id="3902e-161">Vérifiez que toutes les files d’attente dans votre environnement hérité sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="3902e-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="3902e-162">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="3902e-162">Run:</span></span>
    
  ```
  Get-CsRgsWorkflow
  ```

8. <span data-ttu-id="3902e-163">Vérifiez que tous les flux de travail de votre environnement hérité est inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="3902e-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

