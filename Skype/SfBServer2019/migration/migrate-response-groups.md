---
title: Migration de groupes de réponses
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Une fois vos utilisateurs déplacés vers les pools Skype Entreprise Server 2019, vous pouvez migrer vos groupes Response Groups. La migration de groupes Response Group inclut la copie des groupes d’agents, des files d’attente, des flux de travail, des fichiers audio et le déplacement d’objets contact Response Group du déploiement hérité vers le pool Skype Entreprise Server 2019. Après avoir migré vos groupes Response Group hérités, les appels aux groupes Response Group sont gérés par l’application Response Group dans le pool Skype Entreprise Server 2019. Les appels destinés aux groupes Response Group ne sont plus gérés par le pool hérité.
ms.openlocfilehash: bf4087440fb112cb1af906e1a0915531eea08456
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113270"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="a1bd3-106">Migration de groupes de réponses</span><span class="sxs-lookup"><span data-stu-id="a1bd3-106">Migrate response groups</span></span>

<span data-ttu-id="a1bd3-107">Une fois vos utilisateurs déplacés vers les pools Skype Entreprise Server 2019, vous pouvez migrer vos groupes Response Groups.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="a1bd3-108">La migration de groupes Response Group inclut la copie des groupes d’agents, des files d’attente, des flux de travail, des fichiers audio et le déplacement d’objets contact Response Group du déploiement hérité vers le pool Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="a1bd3-109">Après avoir migré vos groupes Response Group hérités, les appels aux groupes Response Group sont gérés par l’application Response Group dans le pool Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="a1bd3-110">Les appels destinés aux groupes Response Group ne sont plus gérés par le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a1bd3-111">Bien que vous pouvez migrer des groupes Response Groups avant de déplacer tous les utilisateurs vers le pool Skype Entreprise Server 2019, nous vous recommandons de déplacer tous les utilisateurs en premier.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="a1bd3-112">En particulier, les utilisateurs qui sont des agents Response Group n’auront pas toutes les fonctionnalités des nouvelles fonctionnalités tant qu’ils n’auront pas été déplacés vers le pool Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="a1bd3-113">Avant de migrer des groupes Response Group, vous devez avoir déployé un pool Skype Entreprise Server 2019 qui inclut l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="a1bd3-114">L’application Response Group est installée et activée par défaut lorsque vous déployez Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="a1bd3-115">Vous pouvez vous assurer que l’application Response Group est installée en exécutant l’cmdlet **Get-CsService -ApplicationServer.**</span><span class="sxs-lookup"><span data-stu-id="a1bd3-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a1bd3-116">Vous pouvez créer des groupes Response Groups Skype Entreprise Server 2019 dans le pool Skype Entreprise Server 2019 avant de migrer vos groupes Response Groups hérités.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="a1bd3-117">Pour migrer des groupes Response Groups d’un pool hérité vers Skype Entreprise Server 2019, vous exécutez l';cmdlet **Move-CsRgsConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="a1bd3-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a1bd3-118">L’cmdlet de migration Response Group déplace la configuration Response Group pour l’ensemble du pool.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="a1bd3-119">Vous ne pouvez pas sélectionner de groupes, files d’attente ou flux de travail spécifiques à migrer.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="a1bd3-120">Après avoir migré les groupes Response Groups, vous devez utiliser le Panneau de contrôle Skype Entreprise Server ou les cmdlets Skype Entreprise Server Management Shell pour vérifier que tous les groupes d’agents, files d’attente et flux de travail ont bien été déplacés.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="a1bd3-121">Lorsque vous migrez des groupes Response Groups, les groupes Response Groups hérités ne sont pas supprimés.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="a1bd3-122">Lorsque vous gérez des groupes Response Groups après la migration à l’aide du Panneau de contrôle Skype Entreprise Server ou de Skype Entreprise Server Management Shell, vous pouvez voir les groupes Response Groups hérités et les groupes Response Groups Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="a1bd3-123">Vous devez appliquer les mises à jour uniquement aux groupes Response Groups Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="a1bd3-124">Les groupes Response Groups hérités sont conservés uniquement à des fins de récupération.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="a1bd3-125">Une fois la migration terminée et les nouveaux groupes Response Group créés, le Panneau de contrôle Skype Entreprise Server et l’environnement de ligne de commande Skype Entreprise Server Management Shell afficheront les versions héritées et Skype Entreprise Server 2019 de chaque groupe Response Group.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="a1bd3-126">N’utilisez pas le Panneau de contrôle Skype Entreprise Server ou Skype Entreprise Server Management Shell pour supprimer les groupes Response Groups hérités.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="a1bd3-127">Si vous en supprimez un, le groupe Response Group correspondant qui a été créé lors de la migration cessera de fonctionner.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="a1bd3-128">Les groupes Response Groups hérités seront supprimés lorsque vous désaffectez le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a1bd3-129">Nous vous recommandons de ne pas supprimer les données de votre déploiement précédent tant que vous n’avez pas désaffecté le pool.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="a1bd3-130">En outre, nous vous recommandons fortement d’exporter les groupes Response Group immédiatement après la migration.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="a1bd3-131">Si un groupe Response Group hérité doit être supprimé, vous pouvez restaurer vos groupes Response Group à partir de la sauvegarde pour que les groupes Response Group Skype Entreprise Server 2019 s’exécutent à nouveau.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="a1bd3-132">Skype Entreprise Server 2019 introduit une nouvelle fonctionnalité Response Group appelée Workflow **Type**.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="a1bd3-133">Le **Type de flux de travail** peut être **Géré** ou **Non géré**.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="a1bd3-134">Tous les groupes Response Group sont migrés avec le **Type de flux de travail** défini à **Non géré** et avec une liste de gestionnaires vide.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="a1bd3-135">Lorsque vous exécutez l’cmdlet **Move-CsRgsConfiguration,** les groupes d’agents, les files d’attente, les flux de travail et les fichiers audio restent dans le pool hérité à des fins de récupération.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="a1bd3-136">Toutefois, si vous devez revenir au pool hérité, vous devez exécuter l’cmdlet **Move-CsApplicationEndpoint** pour déplacer les objets contact vers le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="a1bd3-137">La procédure suivante de migration des configurations Response Group suppose que vous avez une relation un-à-un entre vos pools hérités et les pools Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="a1bd3-138">Si vous prévoyez de consolider ou de fractionner des pools lors de votre migration et de votre déploiement, vous devez planifier le pool hérité qui est MAP avec le pool Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="a1bd3-139">Pour migrer des configurations Response Group</span><span class="sxs-lookup"><span data-stu-id="a1bd3-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="a1bd3-140">Ouvrez une session sur l’ordinateur en utilisant un compte membre du groupe RTCUniversalServerAdmins ou disposant de droits et d’autorisations d’administrateur équivalents.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="a1bd3-141">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Microsoft Skype Entreprise **Server 2019,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="a1bd3-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a1bd3-142">Exécutez :  </span><span class="sxs-lookup"><span data-stu-id="a1bd3-142">Run:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="a1bd3-143">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a1bd3-143">For example:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="a1bd3-144">Après avoir migré des groupes Response Groups et des agents vers le pool Skype Entreprise Server 2019, l’URL que les agents utilisent pour se connecter et se résier est une URL Skype Entreprise Server 2019 et est disponible dans le menu **Outils.**</span><span class="sxs-lookup"><span data-stu-id="a1bd3-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="a1bd3-145">Rappeler aux agents de mettre à jour les références, telles que les signets, à la nouvelle URL.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a1bd3-146">Pour vérifier la migration de Response Group à l’aide du Panneau de contrôle Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a1bd3-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a1bd3-147">Ouvrez une session sur l’ordinateur à l’aide d’un compte membre du groupe RTCUniversalReadOnlyAdmins ou qui soit au moins membre du rôle CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="a1bd3-148">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="a1bd3-149">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le Panneau de contrôle Skype Entreprise Server, voir [Open Skype for Business Server 2019 administrative tools](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools).</span><span class="sxs-lookup"><span data-stu-id="a1bd3-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="a1bd3-150">Dans le volet de navigation gauche, cliquez sur **Services Response Group**.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="a1bd3-151">Sous **l’onglet** Flux de travail, vérifiez que tous les flux de travail de votre environnement hérité sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="a1bd3-152">Cliquez sur **l’onglet** File d’attente et vérifiez que toutes les files d’attente de votre environnement hérité sont incluses dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="a1bd3-153">Cliquez sur **l’onglet** Groupe et vérifiez que tous les groupes d’agents de votre environnement hérité sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a1bd3-154">Pour vérifier la migration de Response Group à l’aide de Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a1bd3-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="a1bd3-155">Ouvrez une session sur l’ordinateur à l’aide d’un compte membre du groupe RTCUniversalReadOnlyAdmins ou qui soit au moins membre du rôle CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="a1bd3-156">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Microsoft Skype Entreprise **Server 2019,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="a1bd3-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="a1bd3-157">Pour plus d’informations sur les applets de commande suivantes, exécutez :</span><span class="sxs-lookup"><span data-stu-id="a1bd3-157">For details about the following cmdlets, run:</span></span>
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="a1bd3-158">Exécutez :  </span><span class="sxs-lookup"><span data-stu-id="a1bd3-158">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="a1bd3-159">Vérifiez que tous les groupes d’agents de votre environnement hérité sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="a1bd3-160">Exécutez :  </span><span class="sxs-lookup"><span data-stu-id="a1bd3-160">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="a1bd3-161">Vérifiez que toutes les files d’attente de votre environnement hérité sont incluses dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="a1bd3-162">Exécutez :  </span><span class="sxs-lookup"><span data-stu-id="a1bd3-162">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="a1bd3-163">Vérifiez que tous les flux de travail de votre environnement hérité sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a1bd3-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
