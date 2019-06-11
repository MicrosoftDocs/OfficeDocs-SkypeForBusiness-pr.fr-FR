---
title: Migrer des groupes Response Group
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60a5bb2b2124b84adeb6a494f6f33ce867f7d416
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="54ef5-102">Migrer des groupes Response Group</span><span class="sxs-lookup"><span data-stu-id="54ef5-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54ef5-103">_**Dernière modification de la rubrique:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="54ef5-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="54ef5-104">Après avoir déplacé vos utilisateurs vers les pools Lync Server 2013, vous pouvez migrer vos groupes de réponse.</span><span class="sxs-lookup"><span data-stu-id="54ef5-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="54ef5-105">La migration de groupes de réponse inclut la copie de groupes d’agents, de files d’attente, de flux de travail, de fichiers audio et de déplacements de groupe de réponses de l’ancien déploiement au pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54ef5-105">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="54ef5-106">Après la migration de vos groupes de réponse hérités, les appels vers les groupes de réponse sont gérés par l’application Response Group dans le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54ef5-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="54ef5-107">Les appels de Response Groups ne sont plus gérés par le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="54ef5-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="54ef5-108">Même si vous pouvez migrer des groupes de réponses avant de déplacer tous les utilisateurs vers le pool Lync Server 2013, nous vous recommandons de déplacer d’abord tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="54ef5-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="54ef5-109">En particulier, les utilisateurs qui sont agents de groupe de réponse ne disposeront pas de toutes les fonctionnalités des nouvelles fonctionnalités tant qu’ils ne seront pas déplacés vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54ef5-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="54ef5-110">Avant de migrer des groupes de réponse, vous devez avoir déployé un pool Lync Server 2013 qui inclut l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="54ef5-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="54ef5-111">L’application Response Group est installée et activée par défaut lorsque vous déployez Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="54ef5-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="54ef5-112">Vous pouvez vous assurer que l’application Response Group est installée en exécutant l’applet de demande **Get-CsService-ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="54ef5-112">You can ensure that the Response Group application is installed by running the **Get-CsService –ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="54ef5-113">Vous pouvez créer des groupes de réponse Lync Server 2013 dans le pool Lync Server 2013 avant de migrer vos groupes de réponse hérités.</span><span class="sxs-lookup"><span data-stu-id="54ef5-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="54ef5-114">Pour migrer des groupes de réponse d’un pool hérité vers Lync Server 2013, exécutez l’applet de **passe Move-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="54ef5-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="54ef5-115">L’applet de passe de migration de groupe de réponse déplace la configuration de groupe de réponse pour le pool entier.</span><span class="sxs-lookup"><span data-stu-id="54ef5-115">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="54ef5-116">Vous ne pouvez pas sélectionner des groupes, des files d’attente ou des flux de travail spécifiques à migrer.</span><span class="sxs-lookup"><span data-stu-id="54ef5-116">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="54ef5-117">Une fois les groupes de réponse migrés, vous devez utiliser le panneau de configuration de Lync Server ou les applets de commande Lync Server Management Shell pour vérifier le déplacement de tous les groupes d’agents, files d’attente et flux de travail.</span><span class="sxs-lookup"><span data-stu-id="54ef5-117">After you migrate the response groups, you need to use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<span data-ttu-id="54ef5-118">Lorsque vous migrez des groupes de réponse, les groupes de réponse Lync Server 2010 ne sont pas supprimés.</span><span class="sxs-lookup"><span data-stu-id="54ef5-118">When you migrate response groups, the Lync Server 2010 response groups are not removed.</span></span> <span data-ttu-id="54ef5-119">Lorsque vous gérez des groupes de réponses après la migration à l’aide du panneau de configuration de Lync Server ou de Lync Server Management Shell, vous pouvez voir les groupes de réponse Lync Server 2010 et les groupes de réponse Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54ef5-119">When you manage response groups after migration by using either Lync Server Control Panel or Lync Server Management Shell, you can see both the Lync Server 2010 response groups and the Lync Server 2013 response groups.</span></span> <span data-ttu-id="54ef5-120">Vous devez appliquer les mises à jour uniquement aux groupes de réponse Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54ef5-120">You should apply updates only to the Lync Server 2013 response groups.</span></span> <span data-ttu-id="54ef5-121">Les groupes de réponse Lync Server 2010 sont conservés uniquement à des fins de restauration.</span><span class="sxs-lookup"><span data-stu-id="54ef5-121">The Lync Server 2010 response groups are retained only for rollback purposes.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="54ef5-122">Une fois la migration effectuée et les nouveaux groupes de réponse créés, le panneau de configuration de Lync Server et Lync Server Management Shell affichent les versions Lync Server 2010 et Lync Server 2013 de chaque groupe de réponses.</span><span class="sxs-lookup"><span data-stu-id="54ef5-122">After the migration has been completed and the new response groups have been created, the Lync Server Control Panel and the Lync Server Management Shell will display the Lync Server 2010 and Lync Server 2013 versions of each response group.</span></span> <span data-ttu-id="54ef5-123">N’utilisez pas le panneau de configuration de Lync Server ou Lync Server Management Shell pour supprimer les groupes de réponse Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="54ef5-123">Do not use Lync Server Control Panel or Lync Server Management Shell to remove the Lync Server 2010 response groups.</span></span> <span data-ttu-id="54ef5-124">Si vous supprimez un, le groupe de réponse correspondant qui a été créé lors de la migration ne fonctionnera plus.</span><span class="sxs-lookup"><span data-stu-id="54ef5-124">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="54ef5-125">Les groupes de réponse Lync Server 2010 seront supprimés lorsque vous désaffectez le pool Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="54ef5-125">The Lync Server 2010 response groups will be removed when you decommission the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="54ef5-126">Nous vous recommandons de ne pas supprimer les données de votre déploiement antérieur tant que vous n’avez pas désactivé le pool.</span><span class="sxs-lookup"><span data-stu-id="54ef5-126">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="54ef5-127">Par ailleurs, nous vous conseillons vivement d’exporter des groupes de réponse immédiatement après la migration.</span><span class="sxs-lookup"><span data-stu-id="54ef5-127">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="54ef5-128">Si un groupe de réponse Lync Server 2010 doit être supprimé, vous pouvez restaurer vos groupes de réponse à partir de la sauvegarde pour obtenir les groupes de réponse Lync Server 2013 en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="54ef5-128">If a Lync Server 2010 response group should get removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="54ef5-129">Lync Server 2013 introduit une nouvelle fonctionnalité de groupe de réponse appelée **type de flux de travail**.</span><span class="sxs-lookup"><span data-stu-id="54ef5-129">Lync Server 2013 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="54ef5-130">Le **type de flux de travail** peut être **géré** ou **non**géré.</span><span class="sxs-lookup"><span data-stu-id="54ef5-130">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="54ef5-131">Tous les groupes de réponses sont migrés avec le **type de flux de travail** défini sur **non géré** et avec une liste de gestionnaires vide.</span><span class="sxs-lookup"><span data-stu-id="54ef5-131">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span>

<span data-ttu-id="54ef5-132">Lorsque vous exécutez l’applet de cmdlet **Move-CsRgsConfiguration** , les groupes d’agents, les files d’attente, les flux de travail et les fichiers audio restent dans le pool hérité à des fins de restauration.</span><span class="sxs-lookup"><span data-stu-id="54ef5-132">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="54ef5-133">Toutefois, si vous avez besoin de revenir au pool hérité, vous devez exécuter l’applet de passe **Move-CsApplicationEndpoint** pour replacer les objets de contact sur le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="54ef5-133">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<span data-ttu-id="54ef5-134">La procédure suivante pour la migration de configurations de groupe de réponse suppose que vous disposez d’une relation un-à-un entre vos pools hérités et les pools Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54ef5-134">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="54ef5-135">Si vous envisagez de consolider ou de fractionner des listes lors de la migration et du déploiement, vous devez planifier les mappages de pool hérité par le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54ef5-135">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="54ef5-136">Pour migrer les configurations de Response Group</span><span class="sxs-lookup"><span data-stu-id="54ef5-136">To migrate Response Group configurations</span></span>

1.  <span data-ttu-id="54ef5-137">Ouvrez une session sur l’ordinateur avec un compte membre du groupe RTCUniversalServerAdmins ou disposant d’autorisations et de droits d’administrateur équivalents.</span><span class="sxs-lookup"><span data-stu-id="54ef5-137">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

2.  <span data-ttu-id="54ef5-138">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="54ef5-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="54ef5-139">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="54ef5-139">Run:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="54ef5-140">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="54ef5-140">For example:</span></span>
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  <span data-ttu-id="54ef5-141">Après avoir migré des groupes de réponses et des agents vers le pool Lync Server 2013, l’URL utilisée par les agents pour se connecter et se déconnecter est une URL Lync Server 2013 et est disponible dans le menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="54ef5-141">After you migrate response groups and agents to the Lync Server 2013 pool, the URL that agents use to sign in and sign out is a Lync Server 2013 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="54ef5-142">Rappelez aux agents de mettre à jour les références, comme les signets, à la nouvelle URL.</span><span class="sxs-lookup"><span data-stu-id="54ef5-142">Remind agents to update any references, such as bookmarks, to the new URL.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="54ef5-143">Pour vérifier la migration du groupe de réponse à l’aide du panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="54ef5-143">To verify Response Group migration by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="54ef5-144">Ouvrez une session sur l’ordinateur avec un compte membre du groupe RTCUniversalReadOnlyAdmins ou qui est membre du rôle CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="54ef5-144">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="54ef5-145">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="54ef5-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="54ef5-146">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="54ef5-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="54ef5-147">Dans le volet de navigation de gauche, cliquez sur **Response Groups**.</span><span class="sxs-lookup"><span data-stu-id="54ef5-147">In the left navigation pane, click **Response Groups**.</span></span>

4.  <span data-ttu-id="54ef5-148">Dans l’onglet **flux de travail** , vérifiez que tous les flux de travail de votre environnement Lync Server 2010 sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="54ef5-148">On the **Workflow** tab, verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="54ef5-149">Cliquez sur l’onglet **file d’attente** pour vérifier que toutes les files d’attente de votre environnement Lync Server 2010 sont incluses dans la liste.</span><span class="sxs-lookup"><span data-stu-id="54ef5-149">Click the **Queue** tab, and verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

6.  <span data-ttu-id="54ef5-150">Cliquez sur l’onglet **groupe** , puis vérifiez que tous les groupes d’agents de votre environnement Lync Server 2010 sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="54ef5-150">Click the **Group** tab, and verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a><span data-ttu-id="54ef5-151">Pour vérifier la migration de groupe de réponse à l’aide de Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="54ef5-151">To verify Response Group migration by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="54ef5-152">Ouvrez une session sur l’ordinateur avec un compte membre du groupe RTCUniversalReadOnlyAdmins ou qui est membre du rôle CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="54ef5-152">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="54ef5-153">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="54ef5-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <span data-ttu-id="54ef5-154">Pour plus d’informations sur les applets de commande suivantes, exécutez:</span><span class="sxs-lookup"><span data-stu-id="54ef5-154">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

3.  <span data-ttu-id="54ef5-155">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="54ef5-155">Run:</span></span>
    
        Get-CsRgsAgentGroup

4.  <span data-ttu-id="54ef5-156">Vérifiez que tous les groupes d’agents de votre environnement Lync Server 2010 sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="54ef5-156">Verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="54ef5-157">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="54ef5-157">Run:</span></span>
    
        Get-CsRgsQueue

6.  <span data-ttu-id="54ef5-158">Vérifiez que toutes les files d’attente de votre environnement Lync Server 2010 figurent dans la liste.</span><span class="sxs-lookup"><span data-stu-id="54ef5-158">Verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

7.  <span data-ttu-id="54ef5-159">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="54ef5-159">Run:</span></span>
    
        Get-CsRgsWorkflow

8.  <span data-ttu-id="54ef5-160">Vérifiez que tous les flux de travail de votre environnement Lync Server 2010 sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="54ef5-160">Verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

