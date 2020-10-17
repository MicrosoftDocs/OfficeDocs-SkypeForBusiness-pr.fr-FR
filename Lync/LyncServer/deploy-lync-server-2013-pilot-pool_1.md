---
title: Déployer le pool pilote Lync Server 2013
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
ms.openlocfilehash: 3df30b2aa45fe9519d724f904e8b375bed794042
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502954"
---
# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="4feb3-102">Déployer le pool pilote Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4feb3-102">Deploy Lync Server 2013 pilot pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4feb3-103">_**Dernière modification de la rubrique :** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="4feb3-103">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="4feb3-104">L’une des premières étapes requises pour la migration vers Lync Server 2013 consiste à déployer un pool pilote.</span><span class="sxs-lookup"><span data-stu-id="4feb3-104">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="4feb3-105">Le pool pilote est l’endroit où vous testez la coexistence de Lync Server 2013 avec votre déploiement Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="4feb3-105">The pilot pool is where you test coexistence of Lync Server 2013 with your Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="4feb3-106">La coexistence est un état temporaire qui dure jusqu’à ce que vous ayez déplacé tous les utilisateurs et pools vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4feb3-106">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="4feb3-107">Lorsque vous déployez un pool pilote, vous utilisez l’Assistant Définir un nouveau pool frontal.</span><span class="sxs-lookup"><span data-stu-id="4feb3-107">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="4feb3-108">Vous devez déployer les mêmes fonctionnalités et charges de travail dans votre pool de pilotes Lync Server 2013 que vous avez dans votre pool Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="4feb3-108">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="4feb3-109">Si vous avez déployé le serveur d’archivage, le serveur de surveillance ou System Center Operations Manager pour l’archivage ou la surveillance de votre environnement Office Communications Server 2007 R2, et que vous souhaitez continuer l’archivage ou la surveillance tout au long de la migration, vous devez également déployer ces fonctionnalités dans votre environnement pilote.</span><span class="sxs-lookup"><span data-stu-id="4feb3-109">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Office Communications Server 2007 R2 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="4feb3-110">La version que vous avez déployée pour archiver ou surveiller votre environnement Office Communications Server 2007 R2 ne capture pas les données dans votre environnement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4feb3-110">The version you deployed to archive or monitor your Office Communications Server 2007 R2 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4feb3-111">La procédure qui suit traite des fonctionnalités et paramètres à considérer dans le cadre du processus de déploiement général de votre pool pilote.</span><span class="sxs-lookup"><span data-stu-id="4feb3-111">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="4feb3-112">Cette section présente uniquement les points clés dont vous devez tenir compte dans le cadre du déploiement de votre pool pilote.</span><span class="sxs-lookup"><span data-stu-id="4feb3-112">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="4feb3-113">Pour obtenir la procédure détaillée, reportez-vous au Guide de déploiement de <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="4feb3-113">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="4feb3-114">**Pour déployer un pool pilote Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="4feb3-114">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="4feb3-115">Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="4feb3-115">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="4feb3-116">Ouvrez le générateur de topologies et choisissez de créer une nouvelle topologie.</span><span class="sxs-lookup"><span data-stu-id="4feb3-116">Open Topology Builder and choose to create a new topology.</span></span>

3.  <span data-ttu-id="4feb3-117">Entrez le domaine SIP principal.</span><span class="sxs-lookup"><span data-stu-id="4feb3-117">Enter the primary SIP domain.</span></span>
    
    <span data-ttu-id="4feb3-118">![Créer une topologie, définir la page de domaine principal](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Créer une topologie, définir la page de domaine principal")</span><span class="sxs-lookup"><span data-stu-id="4feb3-118">![Create New Topology, Define primary domain page](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Create New Topology, Define primary domain page")</span></span>

4.  <span data-ttu-id="4feb3-119">Poursuivez l’exécution de l’Assistant jusqu’à ce que vous accédiez à l’Assistant **définir un nouveau pool frontal** .</span><span class="sxs-lookup"><span data-stu-id="4feb3-119">Continue completing the wizard until you reach the **Define the New Front End pool** wizard.</span></span> <span data-ttu-id="4feb3-120">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="4feb3-120">Click Next.</span></span>

5.  <span data-ttu-id="4feb3-121">Entrez le nom de domaine complet du pool.</span><span class="sxs-lookup"><span data-stu-id="4feb3-121">Enter the pool FQDN.</span></span> <span data-ttu-id="4feb3-122">Lorsque vous définissez votre pool pilote, vous pouvez choisir de déployer un pool frontal Enterprise Edition ou un serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="4feb3-122">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="4feb3-123">Lync Server 2013 ne requiert pas que les fonctionnalités de pool pilote correspondent à ce qui a été déployé dans votre pool hérité.</span><span class="sxs-lookup"><span data-stu-id="4feb3-123">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="4feb3-124">Le nom de domaine complet du pool ou serveur que vous définissez pour le pool pilote doit être unique.</span><span class="sxs-lookup"><span data-stu-id="4feb3-124">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="4feb3-125">Il ne peut pas correspondre au nom du pool Office Communications Server 2007 R2 actuellement déployé, ni aux autres serveurs actuellement déployés.</span><span class="sxs-lookup"><span data-stu-id="4feb3-125">It cannot match the name of the currently deployed Office Communications Server 2007 R2 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="4feb3-126">![Définir la page nom de domaine complet du pool frontal](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Définir la page nom de domaine complet du pool frontal")</span><span class="sxs-lookup"><span data-stu-id="4feb3-126">![Define the Front End pool FQDN page](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Define the Front End pool FQDN page")</span></span>

6.  <span data-ttu-id="4feb3-127">Définissez l’ordinateur qui sera ajouté au pool.</span><span class="sxs-lookup"><span data-stu-id="4feb3-127">Define the computer that will be added to the pool.</span></span>
    
    <span data-ttu-id="4feb3-128">![Boîte de dialogue définir un nouveau pool frontal](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Boîte de dialogue définir un nouveau pool frontal")</span><span class="sxs-lookup"><span data-stu-id="4feb3-128">![Define New Front End Pool dialog](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Define New Front End Pool dialog")</span></span>

7.  <span data-ttu-id="4feb3-129">Dans la page **Sélectionner les fonctionnalités**, activez les cases à cocher correspondant aux fonctionnalités souhaitées pour ce pool frontal.</span><span class="sxs-lookup"><span data-stu-id="4feb3-129">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="4feb3-130">Par exemple, si vous déployez uniquement les fonctionnalités de messagerie instantanée et de présence, activez la case à cocher Conférence pour autoriser la messagerie instantanée à plusieurs, mais n’activez pas les cases à cocher Conférence rendez-vous (PSTN), Voix Entreprise ou Contrôle d’admission des appels, car elles représentent les fonctionnalités de voix, de vidéo et de conférence collaborative.</span><span class="sxs-lookup"><span data-stu-id="4feb3-130">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="4feb3-131">Pour plus d’informations sur la sélection des fonctionnalités, reportez-vous à la rubrique [define and Configure a front end pool or Standard Edition Server in Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="4feb3-131">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="4feb3-132">![Page Sélectionner les fonctionnalités du pool frontal](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Page Sélectionner les fonctionnalités du pool frontal")</span><span class="sxs-lookup"><span data-stu-id="4feb3-132">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

8.  <span data-ttu-id="4feb3-133">Sur la page **Sélectionner des rôles serveur colocalisés** , nous vous recommandons de colocaliser le serveur de médiation dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4feb3-133">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="4feb3-134">Lors de la fusion d’une topologie héritée avec Lync Server 2013, nous vous recommandons de commencer par colocaliser le serveur de médiation Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="4feb3-134">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Office Communications Server 2007 R2 Mediation Server.</span></span> <span data-ttu-id="4feb3-135">Après avoir fusionné les topologies et configuré le serveur de médiation Lync Server 2013, vous pouvez décider s’il faut conserver le serveur de médiation colocalisé, ou le remplacer par un serveur autonome lorsque vous déplacez le rôle de serveur de médiation vers Lync Server 2013 plus loin dans le processus de déploiement.</span><span class="sxs-lookup"><span data-stu-id="4feb3-135">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="4feb3-136">![Page pool frontal-sélection de rôles serveur colocalisés](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Page pool frontal-sélection de rôles serveur colocalisés")</span><span class="sxs-lookup"><span data-stu-id="4feb3-136">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

9.  <span data-ttu-id="4feb3-p109">Dans la page **Rôles serveur associés à ce pool frontal**, lors du déploiement du pool pilote, ne sélectionnez pas l’option **Activer un pool Edge à utiliser avec le composant média de ce pool frontal**. Il s’agit d’une fonctionnalité que vous activerez et mettrez en ligne lors d’une phase ultérieure de la migration. Laissez ce paramètre désactivé pour le moment.</span><span class="sxs-lookup"><span data-stu-id="4feb3-p109">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option. This is a feature you will enable and bring online in a later phase of migration. Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="4feb3-140">![Rôles serveur associés avec page de pool frontal](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Rôles serveur associés avec page de pool frontal")</span><span class="sxs-lookup"><span data-stu-id="4feb3-140">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

10. <span data-ttu-id="4feb3-141">Dans la page **Sélectionner un serveur Office Web Apps**, cliquez sur **Nouveau**, puis indiquez le nom de domaine complet du serveur d’applications.</span><span class="sxs-lookup"><span data-stu-id="4feb3-141">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="4feb3-142">![Définir de nouvelles propriétés de nom de domaine complet Office Web Apps Server](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Définir de nouvelles propriétés de nom de domaine complet Office Web Apps Server")</span><span class="sxs-lookup"><span data-stu-id="4feb3-142">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

11. <span data-ttu-id="4feb3-143">Sur la page **définir le magasin SQL Server d’archivage** , sélectionnez l’instance SQL Server créée précédemment pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4feb3-143">On the **Define the Archiving SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="4feb3-144">![Page définir le magasin SQL Server d’archivage](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Page définir le magasin SQL Server d’archivage")</span><span class="sxs-lookup"><span data-stu-id="4feb3-144">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

12. <span data-ttu-id="4feb3-145">Sur la page **définir le magasin SQL Server de surveillance** , sélectionnez l’instance SQL Server créée précédemment pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4feb3-145">On the **Define the Monitoring SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span> <span data-ttu-id="4feb3-146">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="4feb3-146">Click **Finish**.</span></span>

13. <span data-ttu-id="4feb3-147">À partir du nœud supérieur du générateur de topologie, cliquez avec le bouton droit sur **Lync Server** et cliquez sur **modifier les propriétés.**</span><span class="sxs-lookup"><span data-stu-id="4feb3-147">From the top node of Topology Builder, right click **Lync Server** and click **Edit Properties.**</span></span> <span data-ttu-id="4feb3-148">Cliquez sur **URL simples**.</span><span class="sxs-lookup"><span data-stu-id="4feb3-148">Click **Simple URLs**.</span></span>

14. <span data-ttu-id="4feb3-149">Mettez à jour l' **URL d’accès administratif**.</span><span class="sxs-lookup"><span data-stu-id="4feb3-149">Update the **Administrative access URL**.</span></span>
    
    <span data-ttu-id="4feb3-150">![Modifier les propriétés, page URL simples](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Modifier les propriétés, page URL simples")</span><span class="sxs-lookup"><span data-stu-id="4feb3-150">![Edit Properties, Simple URLs page](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Edit Properties, Simple URLs page")</span></span>
    
    <span data-ttu-id="4feb3-151">Pour plus d’informations sur les URL simples, voir la rubrique [modifier ou configurer des URL simples dans Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="4feb3-151">For additional information on Simple URLs, see the topic [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

15. <span data-ttu-id="4feb3-152">Dans le **modifier les propriétés**, cliquez sur **serveur de gestion centralisée**.</span><span class="sxs-lookup"><span data-stu-id="4feb3-152">From the **Edit Properties**, click **Central Management Server**.</span></span>

16. <span data-ttu-id="4feb3-153">Dans la liste déroulante, sélectionnez le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4feb3-153">From the drop-down list, select the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="4feb3-154">![Modifier les propriétés, page serveur de gestion centralisée](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Modifier les propriétés, page serveur de gestion centralisée")</span><span class="sxs-lookup"><span data-stu-id="4feb3-154">![Edit Properties, Central Management Server page](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Edit Properties, Central Management Server page")</span></span>

17. <span data-ttu-id="4feb3-155">Cliquez sur OK pour fermer **la page modifier les propriétés** .</span><span class="sxs-lookup"><span data-stu-id="4feb3-155">Click OK to close **the Edit Properties** page.</span></span>

18. <span data-ttu-id="4feb3-156">Dans le menu **action** , sélectionnez **publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="4feb3-156">From the **Action** menu, select **Publish Topology**.</span></span>

19. <span data-ttu-id="4feb3-157">Au terme du processus, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="4feb3-157">When the publish process has completed, click **Finish**.</span></span>

20. <span data-ttu-id="4feb3-158">En revenant à l’Assistant Déploiement de Lync Server 2013, cliquez sur **installer ou mettre à jour le système Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4feb3-158">Returning to the Lync Server 2013 Deployment Wizard, click **Install or Update Lync Server System**.</span></span>
    
    <span data-ttu-id="4feb3-159">![Assistant Déploiement de Lync Server 2013](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Assistant Déploiement de Lync Server 2013")</span><span class="sxs-lookup"><span data-stu-id="4feb3-159">![Lync Server 2013 Deployment Wizard](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 Deployment Wizard")</span></span>

<span data-ttu-id="4feb3-160">Pour installer une copie locale du magasin de configuration et démarrer les services requis, voir [Setting Up Front End Servers and front end pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="4feb3-160">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>

