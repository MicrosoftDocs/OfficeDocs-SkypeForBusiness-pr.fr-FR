---
title: Effectuer la migration de groupes Response Group
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b25f46a492cc87c90c4b9f562c81487f9c064a10
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="22252-102">Effectuer la migration de groupes Response Group</span><span class="sxs-lookup"><span data-stu-id="22252-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22252-103">_**Dernière modification de la rubrique :** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="22252-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="22252-104">Une fois les utilisateurs déplacés vers les pools Lync Server 2013, vous pouvez migrer vos groupes Response Group.</span><span class="sxs-lookup"><span data-stu-id="22252-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="22252-105">La migration de groupes Response Group consiste à copier des groupes d’agents, des files d’attente, des flux de travail, des fichiers audio et des objets de contact de groupe Response Group à partir du déploiement hérité vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22252-105">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="22252-106">Une fois vos groupes de réponse hérités migrés, les appels vers les groupes Response Group sont gérés par l’application Response Group dans le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22252-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="22252-107">Les appels destinés aux groupes Response Group ne sont plus gérés par le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="22252-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="22252-108">Bien que vous puissiez migrer des groupes Response Group avant de déplacer tous les utilisateurs vers le pool Lync Server 2013, nous vous recommandons de déplacer tous les utilisateurs en premier.</span><span class="sxs-lookup"><span data-stu-id="22252-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="22252-109">En particulier, les utilisateurs qui sont des agents Response Group ne disposent pas de toutes les fonctionnalités des nouvelles fonctionnalités tant qu’ils ne sont pas déplacés vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22252-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="22252-110">Avant de migrer les groupes Response Group, vous devez avoir déployé un pool Lync Server 2013 qui inclut l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="22252-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="22252-111">L’application Response Group est installée et activée par défaut lorsque vous déployez voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="22252-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="22252-112">Vous pouvez vous assurer que l’application Response Group est installée en exécutant la cmdlet **Get-CsService-ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="22252-112">You can ensure that the Response Group application is installed by running the **Get-CsService –ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="22252-113">Vous pouvez créer des groupes de réponses Lync Server 2013 dans le pool Lync Server 2013 avant de migrer vos groupes de réponses hérités.</span><span class="sxs-lookup"><span data-stu-id="22252-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="22252-114">Pour migrer des groupes Response Group d’un pool hérité vers le Lync Server 2013, exécutez la cmdlet **Move-applet csrgsconfiguration** .</span><span class="sxs-lookup"><span data-stu-id="22252-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="22252-115">La cmdlet Response Group migration déplace la configuration Response Group pour l’ensemble du pool.</span><span class="sxs-lookup"><span data-stu-id="22252-115">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="22252-116">Vous ne pouvez pas sélectionner de groupes, files d’attente ou flux de travail spécifiques à migrer.</span><span class="sxs-lookup"><span data-stu-id="22252-116">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="22252-117">Après avoir migré les groupes Response Group, vous devez utiliser le panneau de configuration Lync Server ou les applets de commande Lync Server Management Shell pour vérifier que tous les groupes d’agents, files d’attente et flux de travail ont été déplacés avec succès.</span><span class="sxs-lookup"><span data-stu-id="22252-117">After you migrate the response groups, you need to use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<span data-ttu-id="22252-118">Lorsque vous migrez des groupes Response Group, les groupes Response Group de Lync Server 2010 ne sont pas supprimés.</span><span class="sxs-lookup"><span data-stu-id="22252-118">When you migrate response groups, the Lync Server 2010 response groups are not removed.</span></span> <span data-ttu-id="22252-119">Lorsque vous gérez des groupes Response Group après une migration à l’aide du panneau de configuration Lync Server ou de Lync Server Management Shell, vous pouvez voir les groupes de réponse Lync Server 2010 et les groupes Response Group Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22252-119">When you manage response groups after migration by using either Lync Server Control Panel or Lync Server Management Shell, you can see both the Lync Server 2010 response groups and the Lync Server 2013 response groups.</span></span> <span data-ttu-id="22252-120">Vous devez appliquer les mises à jour uniquement aux groupes Response Group Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22252-120">You should apply updates only to the Lync Server 2013 response groups.</span></span> <span data-ttu-id="22252-121">Les groupes Response Group de Lync Server 2010 sont conservés uniquement à des fins de restauration.</span><span class="sxs-lookup"><span data-stu-id="22252-121">The Lync Server 2010 response groups are retained only for rollback purposes.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="22252-122">Une fois la migration terminée et les nouveaux groupes Response Group créés, le panneau de configuration Lync Server et Lync Server Management Shell affichent les versions Lync Server 2010 et Lync Server 2013 de chaque groupe Response Group.</span><span class="sxs-lookup"><span data-stu-id="22252-122">After the migration has been completed and the new response groups have been created, the Lync Server Control Panel and the Lync Server Management Shell will display the Lync Server 2010 and Lync Server 2013 versions of each response group.</span></span> <span data-ttu-id="22252-123">N’utilisez pas le panneau de configuration Lync Server ni Lync Server Management Shell pour supprimer les groupes Response Group Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="22252-123">Do not use Lync Server Control Panel or Lync Server Management Shell to remove the Lync Server 2010 response groups.</span></span> <span data-ttu-id="22252-124">Si vous supprimez un, le groupe Response Group correspondant qui a été créé pendant la migration cessera de fonctionner.</span><span class="sxs-lookup"><span data-stu-id="22252-124">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="22252-125">Les groupes de réponses Lync Server 2010 sont supprimés lorsque vous désactivez le pool Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="22252-125">The Lync Server 2010 response groups will be removed when you decommission the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="22252-126">Nous vous recommandons de ne pas supprimer les données de votre déploiement précédent tant que vous n’avez pas désaffecté le pool.</span><span class="sxs-lookup"><span data-stu-id="22252-126">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="22252-127">En outre, nous vous recommandons fortement d’exporter les groupes Response Group immédiatement après la migration.</span><span class="sxs-lookup"><span data-stu-id="22252-127">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="22252-128">Si un groupe de réponse Lync Server 2010 doit être supprimé, vous pouvez restaurer vos groupes Response Group à partir de la sauvegarde pour obtenir les groupes de réponses Lync Server 2013 en cours d’exécution à nouveau.</span><span class="sxs-lookup"><span data-stu-id="22252-128">If a Lync Server 2010 response group should get removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="22252-129">Lync Server 2013 introduit une nouvelle fonctionnalité Response Group appelée **type de flux de travail**.</span><span class="sxs-lookup"><span data-stu-id="22252-129">Lync Server 2013 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="22252-130">Le **Type de flux de travail** peut être **Géré** ou **Non géré**.</span><span class="sxs-lookup"><span data-stu-id="22252-130">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="22252-131">Tous les groupes Response Group sont migrés avec le **Type de flux de travail** défini à **Non géré** et avec une liste de gestionnaires vide.</span><span class="sxs-lookup"><span data-stu-id="22252-131">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span>

<span data-ttu-id="22252-132">Lorsque vous exécutez l’applet de commande **Move-applet csrgsconfiguration** , les groupes d’agents, les files d’attente, les flux de travail et les fichiers audio restent dans le pool hérité à des fins de restauration.</span><span class="sxs-lookup"><span data-stu-id="22252-132">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="22252-133">Toutefois, si vous devez restaurer le pool hérité, vous devez exécuter la cmdlet **Move-CsApplicationEndpoint** pour déplacer les objets contact vers le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="22252-133">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<span data-ttu-id="22252-134">La procédure suivante pour migrer des configurations de groupe Response Group suppose que vous avez une relation un-à-un entre vos pools hérités et les pools Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22252-134">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="22252-135">Si vous envisagez de consolider ou de fractionner les pools au cours de votre migration et de votre déploiement, vous devez planifier le pool hérité mappé vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22252-135">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="22252-136">Pour migrer des configurations de groupe Response Group</span><span class="sxs-lookup"><span data-stu-id="22252-136">To migrate Response Group configurations</span></span>

1.  <span data-ttu-id="22252-137">Ouvrez une session sur l’ordinateur en utilisant un compte membre du groupe RTCUniversalServerAdmins ou disposant de droits et d’autorisations d’administrateur équivalents.</span><span class="sxs-lookup"><span data-stu-id="22252-137">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

2.  <span data-ttu-id="22252-138">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="22252-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="22252-139">Générer</span><span class="sxs-lookup"><span data-stu-id="22252-139">Run:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="22252-140">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="22252-140">For example:</span></span>
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  <span data-ttu-id="22252-141">Une fois que vous avez migré les groupes Response Group et les agents vers le pool Lync Server 2013, l’URL que les agents utilisent pour se connecter et se déconnecter est une URL Lync Server 2013 et est disponible dans le menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="22252-141">After you migrate response groups and agents to the Lync Server 2013 pool, the URL that agents use to sign in and sign out is a Lync Server 2013 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="22252-142">Rappelez aux agents de mettre à jour les références, telles que les signets, vers la nouvelle URL.</span><span class="sxs-lookup"><span data-stu-id="22252-142">Remind agents to update any references, such as bookmarks, to the new URL.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="22252-143">Pour vérifier la migration de Response Group à l’aide du Panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="22252-143">To verify Response Group migration by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="22252-144">Ouvrez une session sur l’ordinateur à l’aide d’un compte membre du groupe RTCUniversalReadOnlyAdmins ou qui soit au moins membre du rôle CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="22252-144">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="22252-145">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22252-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="22252-146">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="22252-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="22252-147">Dans le volet de navigation gauche, cliquez sur **Services Response Group**.</span><span class="sxs-lookup"><span data-stu-id="22252-147">In the left navigation pane, click **Response Groups**.</span></span>

4.  <span data-ttu-id="22252-148">Sous l’onglet **flux de travail** , vérifiez que tous les flux de travail de votre environnement Lync Server 2010 sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="22252-148">On the **Workflow** tab, verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="22252-149">Cliquez sur l’onglet **file d’attente** , puis vérifiez que toutes les files d’attente de votre environnement Lync Server 2010 sont incluses dans la liste.</span><span class="sxs-lookup"><span data-stu-id="22252-149">Click the **Queue** tab, and verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

6.  <span data-ttu-id="22252-150">Cliquez sur l’onglet **groupe** , puis vérifiez que tous les groupes d’agents de votre environnement Lync Server 2010 sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="22252-150">Click the **Group** tab, and verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a><span data-ttu-id="22252-151">Pour vérifier la migration de groupes Response Group à l’aide de Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="22252-151">To verify Response Group migration by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="22252-152">Ouvrez une session sur l’ordinateur à l’aide d’un compte membre du groupe RTCUniversalReadOnlyAdmins ou qui soit au moins membre du rôle CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="22252-152">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="22252-153">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="22252-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <span data-ttu-id="22252-154">Pour plus d’informations sur les applets de commande suivantes, exécutez :</span><span class="sxs-lookup"><span data-stu-id="22252-154">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

3.  <span data-ttu-id="22252-155">Générer</span><span class="sxs-lookup"><span data-stu-id="22252-155">Run:</span></span>
    
        Get-CsRgsAgentGroup

4.  <span data-ttu-id="22252-156">Vérifiez que tous les groupes d’agents de votre environnement Lync Server 2010 sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="22252-156">Verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="22252-157">Générer</span><span class="sxs-lookup"><span data-stu-id="22252-157">Run:</span></span>
    
        Get-CsRgsQueue

6.  <span data-ttu-id="22252-158">Vérifiez que toutes les files d’attente de votre environnement Lync Server 2010 sont incluses dans la liste.</span><span class="sxs-lookup"><span data-stu-id="22252-158">Verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

7.  <span data-ttu-id="22252-159">Générer</span><span class="sxs-lookup"><span data-stu-id="22252-159">Run:</span></span>
    
        Get-CsRgsWorkflow

8.  <span data-ttu-id="22252-160">Vérifiez que tous les flux de travail de votre environnement Lync Server 2010 sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="22252-160">Verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

