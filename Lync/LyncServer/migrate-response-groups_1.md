---
title: Migrer des groupes Response Group
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c01ec246ba99d2a2f71a16179d839409e6b57b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="81807-102">Migrer des groupes Response Group</span><span class="sxs-lookup"><span data-stu-id="81807-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81807-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="81807-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="81807-104">Après avoir déplacé vos utilisateurs vers les pools Lync Server 2013, vous pouvez migrer vos groupes de réponse.</span><span class="sxs-lookup"><span data-stu-id="81807-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="81807-105">La migration de groupes de réponse inclut la copie de groupes d’agents, de files d’attente, de flux de travail et de fichiers audio, et le déplacement d’objets de contact de groupe de réponse du déploiement hérité vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81807-105">Migrating response groups includes copying agent groups, queues, workflows, and audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="81807-106">Après la migration de vos groupes de réponse hérités, les appels vers les groupes de réponse sont gérés par l’application Response Group dans le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81807-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="81807-107">Les appels de Response Groups ne sont plus gérés par le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="81807-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81807-108">Même si vous pouvez migrer des groupes de réponses avant de déplacer tous les utilisateurs vers le pool Lync Server 2013, nous vous recommandons de déplacer d’abord tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="81807-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="81807-109">En particulier, les utilisateurs qui sont agents de groupe de réponse ne disposeront pas de toutes les fonctionnalités des nouvelles fonctionnalités tant qu’ils ne seront pas déplacés vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81807-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="81807-110">Avant de migrer des groupes de réponse, vous devez avoir déployé un pool Lync Server 2013 qui inclut l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="81807-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="81807-111">L’application Response Group est installée et activée par défaut lorsque vous déployez Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="81807-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="81807-112">Vous pouvez vous assurer que l’application Response Group est installée en exécutant l’applet de demande **Get-CsService-ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="81807-112">You can ensure that the Response Group application is installed by running the **Get-CsService–ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81807-113">Vous pouvez créer des groupes de réponse Lync Server 2013 dans le pool Lync Server 2013 avant de migrer vos groupes de réponse hérités.</span><span class="sxs-lookup"><span data-stu-id="81807-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="81807-114">Pour migrer des groupes de réponse d’un pool hérité vers Lync Server 2013, exécutez l’applet de **passe Move-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="81807-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="81807-115">Pour pouvoir exécuter **Move-CsRgsConfiguration**, vous devez d’abord installer le package d’interface de compatibilité descendante WMI (Windows Management Instrumentation).</span><span class="sxs-lookup"><span data-stu-id="81807-115">Before you can run **Move-CsRgsConfiguration**, you must first install the Windows Management Instrumentation (WMI) Backward Compatibility interfaces package.</span></span> <span data-ttu-id="81807-116">Installez cette application en exécutant OCSWMIBC. msi.</span><span class="sxs-lookup"><span data-stu-id="81807-116">Install this application by running OCSWMIBC.msi.</span></span> <span data-ttu-id="81807-117">Vous pouvez trouver OCSWMIBC. msi sur le support d’installation dans le dossier d’installation.</span><span class="sxs-lookup"><span data-stu-id="81807-117">You can find OCSWMIBC.msi on the installation media in the Setup folder.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="81807-118">L’applet de passe de migration de groupe de réponse déplace la configuration de groupe de réponse pour le pool entier.</span><span class="sxs-lookup"><span data-stu-id="81807-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="81807-119">Vous ne pouvez pas sélectionner des groupes, des files d’attente ou des flux de travail spécifiques à migrer.</span><span class="sxs-lookup"><span data-stu-id="81807-119">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="81807-120">Une fois les groupes de réponse migrés, vous devez mettre à jour l’URL utilisée par les agents formels pour se connecter et se déconnecter de leurs groupes de réponse, et utiliser le panneau de configuration de Lync Server ou les applets de commande Lync Server Management Shell pour vérifier le déplacement de tous les groupes d’agents, files d’attente et flux de travail. réussi.</span><span class="sxs-lookup"><span data-stu-id="81807-120">After you migrate the response groups, you need to update the URL that formal agents use to sign into and out of their response groups, and use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="81807-121">Lors de la migration de Response Groups, les groupes de réponse Office Communications Server 2007 R2 ne sont pas supprimés.</span><span class="sxs-lookup"><span data-stu-id="81807-121">When you migrate response groups, the Office Communications Server 2007 R2 response groups are not removed.</span></span> <span data-ttu-id="81807-122">Ne supprimez pas les groupes de réponse Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="81807-122">Do not remove Office Communications Server 2007 R2 response groups.</span></span> <span data-ttu-id="81807-123">Si vous supprimez un groupe de réponses Office Communications Server 2007 R2, les groupes de réponse de Lync Server 2013 cessent de fonctionner.</span><span class="sxs-lookup"><span data-stu-id="81807-123">If you remove an Office Communications Server 2007 R2 response group, the response groups in Lync Server 2013 stop working.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="81807-124">Nous vous recommandons de ne pas supprimer les données de votre déploiement antérieur tant que vous n’avez pas désactivé le pool.</span><span class="sxs-lookup"><span data-stu-id="81807-124">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="81807-125">Par ailleurs, nous vous conseillons vivement d’exporter des groupes de réponse immédiatement après la migration.</span><span class="sxs-lookup"><span data-stu-id="81807-125">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="81807-126">Si un groupe de réponse Office Communications Server 2007 R2 est supprimé, vous pouvez restaurer vos groupes de réponse à partir de la sauvegarde pour obtenir les groupes de réponse Lync Server 2013 en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="81807-126">If an Office Communications Server 2007 R2 response group gets removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="81807-127">Lorsque vous exécutez l’applet de cmdlet **Move-CsRgsConfiguration** , les groupes d’agents, les files d’attente, les flux de travail et les fichiers audio restent dans le pool hérité à des fins de restauration.</span><span class="sxs-lookup"><span data-stu-id="81807-127">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="81807-128">Toutefois, si vous avez besoin de revenir au pool hérité, vous devez exécuter l’applet de passe **Move-CsApplicationEndpoint** pour replacer les objets de contact sur le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="81807-128">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="81807-129">Nous vous recommandons de ne pas supprimer les données du groupe de réponses du pool hérité tant que vous n’avez pas désactivé le pool.</span><span class="sxs-lookup"><span data-stu-id="81807-129">We recommend that you don't delete any response group data from the legacy pool until you decommission the pool.</span></span>



</div>

<span data-ttu-id="81807-130">La procédure suivante pour la migration de configurations de groupe de réponse suppose que vous disposez d’une relation un-à-un entre vos pools hérités et les pools Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81807-130">The procedure that follows for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="81807-131">Si vous envisagez de consolider ou de fractionner des listes lors de la migration et du déploiement, vous devez planifier les mappages de pool hérité par le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81807-131">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="81807-132">Pour migrer les configurations de Response Group</span><span class="sxs-lookup"><span data-stu-id="81807-132">To Migrate Response Group Configurations</span></span>

1.  <span data-ttu-id="81807-133">Recherchez OCSWMIBC. msi dans le dossier de configuration du support d’installation, puis installez-le.</span><span class="sxs-lookup"><span data-stu-id="81807-133">Locate OCSWMIBC.msi in the Setup folder of the installation media and install it.</span></span>

2.  <span data-ttu-id="81807-134">Ouvrez une session sur l’ordinateur avec un compte membre du groupe RTCUniversalServerAdmins ou disposant d’autorisations et de droits d’administrateur équivalents.</span><span class="sxs-lookup"><span data-stu-id="81807-134">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

3.  <span data-ttu-id="81807-135">Ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="81807-135">Open the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="81807-136">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="81807-136">At the command line, type the following:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="81807-137">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="81807-137">For example:</span></span>
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  <span data-ttu-id="81807-138">Si vous avez déployé l’onglet Response Group pour Microsoft Office Communicator 2007 R2 dans votre environnement Office Communications Server 2007 R2, supprimez l’onglet du fichier Office Communicator 2007 R2 Tabs. Xml.</span><span class="sxs-lookup"><span data-stu-id="81807-138">If you deployed the Response Group tab for Microsoft Office Communicator 2007 R2 in your Office Communications Server 2007 R2 environment, remove the tab from the Office Communicator 2007 R2 tabs.xml file.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="81807-139">Les agents officiels ont utilisé l’onglet Response Group pour se connecter à leurs groupes de réponse avant de recevoir des appels.</span><span class="sxs-lookup"><span data-stu-id="81807-139">Formal agents used the Response Group tab to sign in to their response groups before they could receive calls.</span></span> <span data-ttu-id="81807-140">Si vous avez déployé l’onglet Response Group, vous avez choisi l’emplacement du fichier Office Communicator 2007 R2. xml lors de son déploiement.</span><span class="sxs-lookup"><span data-stu-id="81807-140">If you deployed the Response Group tab, you chose the location for the Office Communicator 2007 R2 tabs.xml file when you deployed it.</span></span>

    
    </div>

6.  <span data-ttu-id="81807-141">Fournir aux utilisateurs l’URL mise à jour indiquant que les agents doivent se connecter et se déconnecter de leurs groupes de réponse.</span><span class="sxs-lookup"><span data-stu-id="81807-141">Provide users with the updated URL that agents need to sign into and out of their response groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="81807-142">En général https://webpoolFQDN/RgsClients/Tab.aspx, l’URL est le nom de domaine complet (FQDN) du pool Web associé au pool que vous venez de migrer vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81807-142">The URL is typically https://webpoolFQDN/RgsClients/Tab.aspx, where webpoolFQDN is the fully qualified domain name (FQDN) of the web pool that is associated with the pool that you just migrated to Lync Server 2013.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="81807-143">Cette étape n’est pas nécessaire lorsque les utilisateurs effectuent la mise à niveau vers Lync 2013, car l’URL est disponible dans le menu <STRONG>Outils</STRONG> de Lync.</span><span class="sxs-lookup"><span data-stu-id="81807-143">This step is not required after users upgrade to Lync 2013 because the URL is available from the <STRONG>Tools</STRONG> menu in Lync.</span></span>

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="81807-144">Pour vérifier la migration du groupe de réponse à l’aide du panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="81807-144">To Verify Response Group Migration by Using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="81807-145">Ouvrez le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="81807-145">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="81807-146">Dans le volet de navigation de gauche, cliquez sur **Response Groups**.</span><span class="sxs-lookup"><span data-stu-id="81807-146">In the left navigation pane, click **Response Groups**.</span></span>

3.  <span data-ttu-id="81807-147">Dans l’onglet **flux de travail** , vérifiez que tous les flux de travail de votre environnement Office Communications Server 2007 R2 sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="81807-147">On the **Workflow** tab, verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="81807-148">Cliquez sur l’onglet **file d’attente** pour vérifier que toutes les files d’attente de votre environnement Office Communications Server 2007 R2 sont incluses dans la liste.</span><span class="sxs-lookup"><span data-stu-id="81807-148">Click the **Queue** tab, and verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

5.  <span data-ttu-id="81807-149">Cliquez sur l’onglet **groupe** , puis vérifiez que tous les groupes d’agents de votre environnement Office Communications Server 2007 R2 sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="81807-149">Click the **Group** tab, and verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a><span data-ttu-id="81807-150">Pour vérifier la migration de groupe de réponse à l’aide de cmdlets</span><span class="sxs-lookup"><span data-stu-id="81807-150">To Verify Response Group Migration by Using Cmdlets</span></span>

1.  <span data-ttu-id="81807-151">Ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="81807-151">Open the Lync Server Management Shell.</span></span>
    
    <span data-ttu-id="81807-152">Pour plus d’informations sur les applets de commande suivantes, exécutez :</span><span class="sxs-lookup"><span data-stu-id="81807-152">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

2.  <span data-ttu-id="81807-153">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="81807-153">At the command line, type the following:</span></span>
    
        Get-CsRgsAgentGroup

3.  <span data-ttu-id="81807-154">Vérifiez que tous les groupes d’agents de votre environnement Office Communications Server 2007 R2 sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="81807-154">Verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="81807-155">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="81807-155">At the command line, type the following:</span></span>
    
        Get-CsRgsQueue

5.  <span data-ttu-id="81807-156">Vérifiez que toutes les files d’attente de votre environnement Office Communications Server 2007 R2 sont incluses dans la liste.</span><span class="sxs-lookup"><span data-stu-id="81807-156">Verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

6.  <span data-ttu-id="81807-157">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="81807-157">At the command line, type the following:</span></span>
    
        Get-CsRgsWorkflow

7.  <span data-ttu-id="81807-158">Vérifiez que tous les flux de travail de votre environnement Office Communications Server 2007 R2 sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="81807-158">Verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

