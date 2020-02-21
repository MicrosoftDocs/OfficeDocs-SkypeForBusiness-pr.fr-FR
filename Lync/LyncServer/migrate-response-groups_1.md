---
title: Effectuer la migration de groupes Response Group
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
ms.openlocfilehash: 36b37fc6a67a1935c442edb4e2e8ef0d8812315c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="e9616-102">Effectuer la migration de groupes Response Group</span><span class="sxs-lookup"><span data-stu-id="e9616-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9616-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="e9616-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="e9616-104">Une fois les utilisateurs déplacés vers les pools Lync Server 2013, vous pouvez migrer vos groupes Response Group.</span><span class="sxs-lookup"><span data-stu-id="e9616-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="e9616-105">La migration de groupes Response Group consiste à copier des groupes d’agents, des files d’attente, des flux de travail et des fichiers audio, ainsi qu’à transférer des objets contact Response Group depuis le déploiement hérité vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9616-105">Migrating response groups includes copying agent groups, queues, workflows, and audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="e9616-106">Une fois vos groupes de réponse hérités migrés, les appels vers les groupes Response Group sont gérés par l’application Response Group dans le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9616-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="e9616-107">Les appels destinés aux groupes Response Group ne sont plus gérés par le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="e9616-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e9616-108">Bien que vous puissiez migrer des groupes Response Group avant de déplacer tous les utilisateurs vers le pool Lync Server 2013, nous vous recommandons de déplacer tous les utilisateurs en premier.</span><span class="sxs-lookup"><span data-stu-id="e9616-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="e9616-109">En particulier, les utilisateurs qui sont des agents Response Group ne disposent pas de toutes les fonctionnalités des nouvelles fonctionnalités tant qu’ils ne sont pas déplacés vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9616-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="e9616-110">Avant de migrer les groupes Response Group, vous devez avoir déployé un pool Lync Server 2013 qui inclut l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="e9616-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="e9616-111">L’application Response Group est installée et activée par défaut lorsque vous déployez voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="e9616-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="e9616-112">Vous pouvez vous assurer que l’application Response Group est installée en exécutant la cmdlet **Get-CsService-ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="e9616-112">You can ensure that the Response Group application is installed by running the **Get-CsService–ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e9616-113">Vous pouvez créer des groupes de réponses Lync Server 2013 dans le pool Lync Server 2013 avant de migrer vos groupes de réponses hérités.</span><span class="sxs-lookup"><span data-stu-id="e9616-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="e9616-114">Pour migrer des groupes Response Group d’un pool hérité vers le Lync Server 2013, exécutez la cmdlet **Move-applet csrgsconfiguration** .</span><span class="sxs-lookup"><span data-stu-id="e9616-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="e9616-115">Avant d’exécuter **Move-CsRgsConfiguration**, vous devez installer le package des interfaces de compatibilité descendante Windows Management Instrumentation (WMI).</span><span class="sxs-lookup"><span data-stu-id="e9616-115">Before you can run **Move-CsRgsConfiguration**, you must first install the Windows Management Instrumentation (WMI) Backward Compatibility interfaces package.</span></span> <span data-ttu-id="e9616-116">Installez cette application en exécutant OCSWMIBC.msi.</span><span class="sxs-lookup"><span data-stu-id="e9616-116">Install this application by running OCSWMIBC.msi.</span></span> <span data-ttu-id="e9616-117">Vous trouverez OCSWMIBC.msi sur le média d’installation, dans le dossier d’installation.</span><span class="sxs-lookup"><span data-stu-id="e9616-117">You can find OCSWMIBC.msi on the installation media in the Setup folder.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e9616-118">La cmdlet Response Group migration déplace la configuration Response Group pour l’ensemble du pool.</span><span class="sxs-lookup"><span data-stu-id="e9616-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="e9616-119">Vous ne pouvez pas sélectionner de groupes, files d’attente ou flux de travail spécifiques à migrer.</span><span class="sxs-lookup"><span data-stu-id="e9616-119">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="e9616-120">Après avoir migré les groupes Response Group, vous devez mettre à jour l’URL utilisée par les agents formels pour se connecter à leurs groupes Response Group et les déconnecter, et utiliser le panneau de configuration Lync Server ou les applets de commande Lync Server Management Shell pour vérifier que tous les groupes d’agents, files d’attente et flux de travail sont déplacés. exécuté.</span><span class="sxs-lookup"><span data-stu-id="e9616-120">After you migrate the response groups, you need to update the URL that formal agents use to sign into and out of their response groups, and use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="e9616-121">Lors de la migration de groupes Response Group, les groupes Response Group Office Communications Server 2007 R2 ne sont pas supprimés.</span><span class="sxs-lookup"><span data-stu-id="e9616-121">When you migrate response groups, the Office Communications Server 2007 R2 response groups are not removed.</span></span> <span data-ttu-id="e9616-122">Ne supprimez pas les groupes Response Group Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e9616-122">Do not remove Office Communications Server 2007 R2 response groups.</span></span> <span data-ttu-id="e9616-123">Si vous supprimez un groupe Response Group Office Communications Server 2007 R2, les groupes Response Group dans Lync Server 2013 cessent de fonctionner.</span><span class="sxs-lookup"><span data-stu-id="e9616-123">If you remove an Office Communications Server 2007 R2 response group, the response groups in Lync Server 2013 stop working.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e9616-124">Nous vous recommandons de ne pas supprimer les données de votre déploiement précédent tant que vous n’avez pas désaffecté le pool.</span><span class="sxs-lookup"><span data-stu-id="e9616-124">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="e9616-125">En outre, nous vous recommandons fortement d’exporter les groupes Response Group immédiatement après la migration.</span><span class="sxs-lookup"><span data-stu-id="e9616-125">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="e9616-126">Si un groupe Response Group Office Communications Server 2007 R2 est supprimé, vous pouvez restaurer vos groupes Response Group à partir de la sauvegarde pour obtenir les groupes de réponses Lync Server 2013 en cours d’exécution à nouveau.</span><span class="sxs-lookup"><span data-stu-id="e9616-126">If an Office Communications Server 2007 R2 response group gets removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="e9616-127">Lorsque vous exécutez l’applet de commande **Move-applet csrgsconfiguration** , les groupes d’agents, les files d’attente, les flux de travail et les fichiers audio restent dans le pool hérité à des fins de restauration.</span><span class="sxs-lookup"><span data-stu-id="e9616-127">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="e9616-128">Toutefois, si vous devez restaurer le pool hérité, vous devez exécuter la cmdlet **Move-CsApplicationEndpoint** pour déplacer les objets contact vers le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="e9616-128">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e9616-129">Nous vous recommandons de ne pas supprimer les données du groupe Response Group du pool hérité tant que vous n’avez pas désaffecté le pool.</span><span class="sxs-lookup"><span data-stu-id="e9616-129">We recommend that you don't delete any response group data from the legacy pool until you decommission the pool.</span></span>



</div>

<span data-ttu-id="e9616-130">La procédure qui suit pour la migration des configurations Response Group suppose que vous disposiez d’une relation un-à-un entre vos pools hérités et les pools Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9616-130">The procedure that follows for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="e9616-131">Si vous envisagez de consolider ou de fractionner les pools au cours de votre migration et de votre déploiement, vous devez planifier le pool hérité mappé vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9616-131">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="e9616-132">Pour migrer des configurations de groupe Response Group</span><span class="sxs-lookup"><span data-stu-id="e9616-132">To Migrate Response Group Configurations</span></span>

1.  <span data-ttu-id="e9616-133">Localisez OCSWMIBC.msi dans le dossier d’installation du support d’installation, puis installez-le.</span><span class="sxs-lookup"><span data-stu-id="e9616-133">Locate OCSWMIBC.msi in the Setup folder of the installation media and install it.</span></span>

2.  <span data-ttu-id="e9616-134">Ouvrez une session sur l’ordinateur en utilisant un compte membre du groupe RTCUniversalServerAdmins ou disposant de droits et d’autorisations d’administrateur équivalents.</span><span class="sxs-lookup"><span data-stu-id="e9616-134">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

3.  <span data-ttu-id="e9616-135">Ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e9616-135">Open the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="e9616-136">Sur la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="e9616-136">At the command line, type the following:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="e9616-137">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e9616-137">For example:</span></span>
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  <span data-ttu-id="e9616-138">Si vous avez déployé l’onglet Response Group pour Microsoft Office Communicator 2007 R2 dans votre environnement Office Communications Server 2007 R2, supprimez l’onglet du fichier Office Communicator 2007 R2 Tabs. Xml.</span><span class="sxs-lookup"><span data-stu-id="e9616-138">If you deployed the Response Group tab for Microsoft Office Communicator 2007 R2 in your Office Communications Server 2007 R2 environment, remove the tab from the Office Communicator 2007 R2 tabs.xml file.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9616-139">Les agents formels ont utilisé l’onglet Response Group pour se connecter à leurs groupes de réponses avant de pouvoir recevoir des appels.</span><span class="sxs-lookup"><span data-stu-id="e9616-139">Formal agents used the Response Group tab to sign in to their response groups before they could receive calls.</span></span> <span data-ttu-id="e9616-140">Si vous avez déployé l’onglet Response Group, vous avez choisi l’emplacement du fichier Office Communicator 2007 R2 Tabs. xml lors de son déploiement.</span><span class="sxs-lookup"><span data-stu-id="e9616-140">If you deployed the Response Group tab, you chose the location for the Office Communicator 2007 R2 tabs.xml file when you deployed it.</span></span>

    
    </div>

6.  <span data-ttu-id="e9616-141">Fournissez aux utilisateurs l’URL mise à jour dont les agents ont besoin pour se connecter ou se déconnecter de leurs groupes de réponses.</span><span class="sxs-lookup"><span data-stu-id="e9616-141">Provide users with the updated URL that agents need to sign into and out of their response groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9616-142">L’URL est généralement https://webpoolFQDN/RgsClients/Tab.aspx, où webpoolfqdn représente est le nom de domaine complet (FQDN) du pool de sites Web associé au pool que vous venez de migrer vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9616-142">The URL is typically https://webpoolFQDN/RgsClients/Tab.aspx, where webpoolFQDN is the fully qualified domain name (FQDN) of the web pool that is associated with the pool that you just migrated to Lync Server 2013.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9616-143">Cette étape n’est pas nécessaire après la mise à niveau des utilisateurs vers Lync 2013 car l’URL est disponible à partir du menu <STRONG>Outils</STRONG> dans Lync.</span><span class="sxs-lookup"><span data-stu-id="e9616-143">This step is not required after users upgrade to Lync 2013 because the URL is available from the <STRONG>Tools</STRONG> menu in Lync.</span></span>

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="e9616-144">Pour vérifier la migration de groupes Response Group à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="e9616-144">To Verify Response Group Migration by Using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e9616-145">Ouvrez le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e9616-145">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="e9616-146">Dans le volet de navigation gauche, cliquez sur **Services Response Group**.</span><span class="sxs-lookup"><span data-stu-id="e9616-146">In the left navigation pane, click **Response Groups**.</span></span>

3.  <span data-ttu-id="e9616-147">Sous l’onglet **flux de travail** , vérifiez que tous les flux de travail de votre environnement Office Communications Server 2007 R2 sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e9616-147">On the **Workflow** tab, verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="e9616-148">Cliquez sur l’onglet **file d’attente** , puis vérifiez que toutes les files d’attente de votre environnement Office Communications Server 2007 R2 sont incluses dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e9616-148">Click the **Queue** tab, and verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

5.  <span data-ttu-id="e9616-149">Cliquez sur l’onglet **groupe** , puis vérifiez que tous les groupes d’agents de votre environnement Office Communications Server 2007 R2 sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e9616-149">Click the **Group** tab, and verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a><span data-ttu-id="e9616-150">Pour vérifier la migration de groupes Response Group à l’aide d’applets de commande</span><span class="sxs-lookup"><span data-stu-id="e9616-150">To Verify Response Group Migration by Using Cmdlets</span></span>

1.  <span data-ttu-id="e9616-151">Ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e9616-151">Open the Lync Server Management Shell.</span></span>
    
    <span data-ttu-id="e9616-152">Pour plus d’informations sur les applets de commande suivantes, exécutez :</span><span class="sxs-lookup"><span data-stu-id="e9616-152">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

2.  <span data-ttu-id="e9616-153">Sur la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="e9616-153">At the command line, type the following:</span></span>
    
        Get-CsRgsAgentGroup

3.  <span data-ttu-id="e9616-154">Vérifiez que tous les groupes d’agents de votre environnement Office Communications Server 2007 R2 sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e9616-154">Verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="e9616-155">Dans la ligne de commande, tapez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="e9616-155">At the command line, type the following:</span></span>
    
        Get-CsRgsQueue

5.  <span data-ttu-id="e9616-156">Vérifiez que toutes les files d’attente de votre environnement Office Communications Server 2007 R2 sont incluses dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e9616-156">Verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

6.  <span data-ttu-id="e9616-157">Dans la ligne de commande, tapez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="e9616-157">At the command line, type the following:</span></span>
    
        Get-CsRgsWorkflow

7.  <span data-ttu-id="e9616-158">Vérifiez que tous les flux de travail de votre environnement Office Communications Server 2007 R2 sont inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e9616-158">Verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

