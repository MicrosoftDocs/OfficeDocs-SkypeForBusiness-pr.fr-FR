---
title: Déploiement du pool de pilotes Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204718(v=OCS.15)
ms:contentKeyID: 48183539
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46e6d4bd34c20038e430323b0f78ccf4f918aa62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="190a4-102">Déploiement du pool de pilotes Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="190a4-102">Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="190a4-103">_**Dernière modification de la rubrique :** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="190a4-103">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="190a4-104">L’une des premières étapes requises pour la migration vers Lync Server 2013 consiste à déployer un pool de pilotes.</span><span class="sxs-lookup"><span data-stu-id="190a4-104">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="190a4-105">Le pool de pilotes permet de tester la coexistence de Lync Server 2013 avec le déploiement d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="190a4-105">The pilot pool is where you test coexistence of Lync Server 2013 with your Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="190a4-106">La coexistence est un état temporaire qui dure jusqu’à ce que vous ayez déplacé l’ensemble des utilisateurs et des groupes vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="190a4-106">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="190a4-107">Lorsque vous déployez un pool de pilotes, vous utilisez l’Assistant définir un nouveau pool frontal.</span><span class="sxs-lookup"><span data-stu-id="190a4-107">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="190a4-108">Vous devez déployer les mêmes fonctionnalités et charges de travail dans votre pool de pilotes Lync Server 2013 que vous avez dans votre pool Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="190a4-108">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="190a4-109">Si vous avez déployé une version Server, Monitoring Server ou System Center Operations Manager pour l’archivage ou la surveillance de votre environnement Office Communications Server 2007 R2 et que vous voulez continuer à archiver ou à surveiller tout au long de la migration, vous devez Déployez également ces fonctionnalités dans votre environnement pilote.</span><span class="sxs-lookup"><span data-stu-id="190a4-109">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Office Communications Server 2007 R2 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="190a4-110">La version que vous avez déployée pour archiver ou surveiller votre environnement Office Communications Server 2007 R2 ne capture pas de données dans votre environnement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="190a4-110">The version you deployed to archive or monitor your Office Communications Server 2007 R2 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="190a4-111">La procédure suivante décrit les fonctionnalités et paramètres à envisager dans le cadre de votre processus global de déploiement de pool pilote.</span><span class="sxs-lookup"><span data-stu-id="190a4-111">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="190a4-112">Cette section présente uniquement les points clés à prendre en compte dans le cadre de votre déploiement de pool pilote.</span><span class="sxs-lookup"><span data-stu-id="190a4-112">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="190a4-113">Pour consulter la procédure détaillée, voir le Guide de déploiement de <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="190a4-113">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="190a4-114">**Pour déployer un pool de pilotes de Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="190a4-114">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="190a4-115">Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="190a4-115">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="190a4-116">Ouvrez le générateur de topologie et choisissez de créer une nouvelle topologie.</span><span class="sxs-lookup"><span data-stu-id="190a4-116">Open Topology Builder and choose to create a new topology.</span></span>

3.  <span data-ttu-id="190a4-117">Entrez le domaine SIP principal.</span><span class="sxs-lookup"><span data-stu-id="190a4-117">Enter the primary SIP domain.</span></span>
    
    <span data-ttu-id="190a4-118">![Créer une nouvelle topologie, définir la page de domaine principal](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Créer une nouvelle topologie, définir la page de domaine principal")</span><span class="sxs-lookup"><span data-stu-id="190a4-118">![Create New Topology, Define primary domain page](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Create New Topology, Define primary domain page")</span></span>

4.  <span data-ttu-id="190a4-119">Continuez à terminer l’Assistant jusqu’à atteindre l’Assistant **définir le pool frontal** .</span><span class="sxs-lookup"><span data-stu-id="190a4-119">Continue completing the wizard until you reach the **Define the New Front End pool** wizard.</span></span> <span data-ttu-id="190a4-120">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="190a4-120">Click Next.</span></span>

5.  <span data-ttu-id="190a4-121">Entrez le nom de domaine complet (FQDN) du pool.</span><span class="sxs-lookup"><span data-stu-id="190a4-121">Enter the pool FQDN.</span></span> <span data-ttu-id="190a4-122">Lors de la définition de votre pool de pilotes, vous pouvez choisir de déployer un pool frontal Enterprise Edition ou un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="190a4-122">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="190a4-123">Lync Server 2013 ne nécessite pas que les fonctionnalités de votre pool pilote correspondent aux éléments déployés dans votre pool hérité.</span><span class="sxs-lookup"><span data-stu-id="190a4-123">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="190a4-124">Le pool ou le nom de domaine complet (FQDN) du serveur que vous définissez pour le pool pilote doit être unique.</span><span class="sxs-lookup"><span data-stu-id="190a4-124">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="190a4-125">Il ne peut pas correspondre au nom du pool Office Communications Server 2007 R2 actuellement déployé ou à tout autre serveur actuellement déployé.</span><span class="sxs-lookup"><span data-stu-id="190a4-125">It cannot match the name of the currently deployed Office Communications Server 2007 R2 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="190a4-126">![Définir la page de nom de domaine complet (FQDN) du pool frontal](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Définir la page de nom de domaine complet (FQDN) du pool frontal")</span><span class="sxs-lookup"><span data-stu-id="190a4-126">![Define the Front End pool FQDN page](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Define the Front End pool FQDN page")</span></span>

6.  <span data-ttu-id="190a4-127">Définissez l’ordinateur qui sera ajouté au pool.</span><span class="sxs-lookup"><span data-stu-id="190a4-127">Define the computer that will be added to the pool.</span></span>
    
    <span data-ttu-id="190a4-128">![Boîte de dialogue définir un nouveau pool frontal](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Boîte de dialogue définir un nouveau pool frontal")</span><span class="sxs-lookup"><span data-stu-id="190a4-128">![Define New Front End Pool dialog](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Define New Front End Pool dialog")</span></span>

7.  <span data-ttu-id="190a4-129">Dans la page **Sélectionner des fonctionnalités** , activez les cases à cocher des fonctionnalités que vous voulez inclure dans ce pool frontal.</span><span class="sxs-lookup"><span data-stu-id="190a4-129">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="190a4-130">Par exemple, si vous déployez uniquement les fonctionnalités de messagerie instantanée et de présence, activez la case à cocher Conférence pour autoriser la messagerie instantanée multipartie, mais pas les cases à cocher Conférence rendez-vous (RTC), voix entreprise ou contrôle d’admission des appels. comme ils représentent les fonctionnalités de voix, de vidéo et de conférence de collaboration.</span><span class="sxs-lookup"><span data-stu-id="190a4-130">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="190a4-131">Pour plus d’informations sur la sélection de fonctionnalités, voir [définir et configurer un pool frontal ou un serveur Standard Edition dans Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="190a4-131">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="190a4-132">![Page de sélection des fonctionnalités du pool frontal](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Page de sélection des fonctionnalités du pool frontal")</span><span class="sxs-lookup"><span data-stu-id="190a4-132">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

8.  <span data-ttu-id="190a4-133">Dans la page **Sélectionner des rôles de serveur colocalisés** , nous vous recommandons de Collocate le serveur de médiation dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="190a4-133">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="190a4-134">Lors de la fusion d’une topologie héritée avec Lync Server 2013, vous devez commencer par collocate le serveur de médiation Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="190a4-134">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Office Communications Server 2007 R2 Mediation Server.</span></span> <span data-ttu-id="190a4-135">Après avoir fusionné les topologies et configuré le serveur de médiation Lync Server 2013, vous pouvez décider si vous souhaitez conserver le serveur de médiation colocalisé ou le modifier en serveur autonome lorsque vous déplacez le rôle de serveur de médiation vers Lync Server 2013 par la suite dans le cadre du déploiement. temps.</span><span class="sxs-lookup"><span data-stu-id="190a4-135">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="190a4-136">![Page de rôles de serveur en liste de choix](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Page de rôles de serveur en liste de choix")</span><span class="sxs-lookup"><span data-stu-id="190a4-136">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

9.  <span data-ttu-id="190a4-137">Dans la page **associez les rôles de serveur à cette liste frontale** , pendant le déploiement du pool de pilotes, ne sélectionnez pas l’option **activer un pool Edge à utiliser par le composant multimédia de cette option de pool frontal** .</span><span class="sxs-lookup"><span data-stu-id="190a4-137">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option.</span></span> <span data-ttu-id="190a4-138">Il s’agit d’une fonctionnalité que vous allez activer et mettre en ligne dans une phase ultérieure de la migration.</span><span class="sxs-lookup"><span data-stu-id="190a4-138">This is a feature you will enable and bring online in a later phase of migration.</span></span> <span data-ttu-id="190a4-139">Laissez ce paramètre désactivé pour le moment.</span><span class="sxs-lookup"><span data-stu-id="190a4-139">Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="190a4-140">![Associer des rôles de serveur à une page de pool frontal](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associer des rôles de serveur à une page de pool frontal")</span><span class="sxs-lookup"><span data-stu-id="190a4-140">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

10. <span data-ttu-id="190a4-141">Dans la page **Sélectionner un serveur Office Web Apps** , cliquez sur **nouveau**, puis spécifiez le nom de domaine complet du serveur d’applications.</span><span class="sxs-lookup"><span data-stu-id="190a4-141">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="190a4-142">![Définir de nouvelles propriétés de nom de domaine complet Office Web Apps Server](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Définir de nouvelles propriétés de nom de domaine complet Office Web Apps Server")</span><span class="sxs-lookup"><span data-stu-id="190a4-142">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

11. <span data-ttu-id="190a4-143">Dans la page **définir la SQL Server Store d’archivage** , sélectionnez l’instance SQL Server créée précédemment pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="190a4-143">On the **Define the Archiving SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="190a4-144">![Page définir l’archivage de SQL Server Store](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Page définir l’archivage de SQL Server Store")</span><span class="sxs-lookup"><span data-stu-id="190a4-144">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

12. <span data-ttu-id="190a4-145">Dans la page **définir la gestion SQL Server Store** , sélectionnez l’instance SQL Server créée précédemment pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="190a4-145">On the **Define the Monitoring SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span> <span data-ttu-id="190a4-146">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="190a4-146">Click **Finish**.</span></span>

13. <span data-ttu-id="190a4-147">À partir du nœud supérieur du générateur de topologie, cliquez avec le bouton droit sur **Lync Server** , puis cliquez sur **modifier les propriétés.**</span><span class="sxs-lookup"><span data-stu-id="190a4-147">From the top node of Topology Builder, right click **Lync Server** and click **Edit Properties.**</span></span> <span data-ttu-id="190a4-148">Cliquez sur **URL simples**.</span><span class="sxs-lookup"><span data-stu-id="190a4-148">Click **Simple URLs**.</span></span>

14. <span data-ttu-id="190a4-149">Mettez à jour l' **URL d’accès administratif**.</span><span class="sxs-lookup"><span data-stu-id="190a4-149">Update the **Administrative access URL**.</span></span>
    
    <span data-ttu-id="190a4-150">![Modifier les propriétés, page URL simples](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Modifier les propriétés, page URL simples")</span><span class="sxs-lookup"><span data-stu-id="190a4-150">![Edit Properties, Simple URLs page](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Edit Properties, Simple URLs page")</span></span>
    
    <span data-ttu-id="190a4-151">Pour plus d’informations sur les URL simples, voir la rubrique [modifier ou configurer des URL simples dans Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="190a4-151">For additional information on Simple URLs, see the topic [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

15. <span data-ttu-id="190a4-152">Dans les **propriétés d’édition**, cliquez sur **serveur de gestion central**.</span><span class="sxs-lookup"><span data-stu-id="190a4-152">From the **Edit Properties**, click **Central Management Server**.</span></span>

16. <span data-ttu-id="190a4-153">Dans la liste déroulante, sélectionnez le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="190a4-153">From the drop-down list, select the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="190a4-154">![Modifier les propriétés, page serveur d’administration centrale](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Modifier les propriétés, page serveur d’administration centrale")</span><span class="sxs-lookup"><span data-stu-id="190a4-154">![Edit Properties, Central Management Server page](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Edit Properties, Central Management Server page")</span></span>

17. <span data-ttu-id="190a4-155">Cliquez sur OK pour fermer **la page modifier les propriétés** .</span><span class="sxs-lookup"><span data-stu-id="190a4-155">Click OK to close **the Edit Properties** page.</span></span>

18. <span data-ttu-id="190a4-156">Dans le menu **action** , cliquez sur **publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="190a4-156">From the **Action** menu, select **Publish Topology**.</span></span>

19. <span data-ttu-id="190a4-157">Lorsque le processus de publication est terminé, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="190a4-157">When the publish process has completed, click **Finish**.</span></span>

20. <span data-ttu-id="190a4-158">Lorsque vous revenez à l’Assistant Déploiement de Lync Server 2013, cliquez sur **installer ou mettre à jour le système de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="190a4-158">Returning to the Lync Server 2013 Deployment Wizard, click **Install or Update Lync Server System**.</span></span>
    
    <span data-ttu-id="190a4-159">![Assistant Déploiement de Lync Server 2013](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Assistant Déploiement de Lync Server 2013")</span><span class="sxs-lookup"><span data-stu-id="190a4-159">![Lync Server 2013 Deployment Wizard](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 Deployment Wizard")</span></span>

<span data-ttu-id="190a4-160">Pour installer une copie locale du magasin de configuration et démarrer les services requis, voir [configuration de serveurs frontaux et de listes frontales pour Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="190a4-160">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>

