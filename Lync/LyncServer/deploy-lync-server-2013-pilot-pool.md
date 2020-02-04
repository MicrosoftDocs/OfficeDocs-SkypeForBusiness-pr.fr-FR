---
title: Déploiement du pool de pilotes Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbe36710ab0acee23af1d8b83adece108cf86c4d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="39df0-102">Déploiement du pool de pilotes Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39df0-102">Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39df0-103">_**Dernière modification de la rubrique :** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="39df0-103">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="39df0-104">L’une des premières étapes requises pour la migration vers Lync Server 2013 consiste à déployer un pool de pilotes.</span><span class="sxs-lookup"><span data-stu-id="39df0-104">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="39df0-105">Le pool de pilotes vous permet de tester la coexistence de Lync Server 2013 avec le déploiement de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="39df0-105">The pilot pool is where you test coexistence of Lync Server 2013 with your Lync Server 2010 deployment.</span></span> <span data-ttu-id="39df0-106">La coexistence est un état temporaire qui dure jusqu’à ce que vous ayez déplacé l’ensemble des utilisateurs et des groupes vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39df0-106">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="39df0-107">Lorsque vous déployez un pool de pilotes, vous utilisez l’Assistant définir un nouveau pool frontal.</span><span class="sxs-lookup"><span data-stu-id="39df0-107">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="39df0-108">Vous devez déployer les mêmes fonctionnalités et charges de travail dans votre pool de pilotes Lync Server 2013 que vous avez dans votre pool Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="39df0-108">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Lync Server 2010 pool.</span></span> <span data-ttu-id="39df0-109">Si vous avez déployé des serveurs d’archivage, de surveillance ou de System Center Operations Manager permettant d’archiver ou de surveiller votre environnement Lync Server 2010, et que vous voulez continuer à archiver ou à surveiller tout au long de la migration, vous devez également les déployer. fonctionnalités de votre environnement pilote.</span><span class="sxs-lookup"><span data-stu-id="39df0-109">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Lync Server 2010 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="39df0-110">La version que vous avez déployée pour archiver ou surveiller votre environnement Lync Server 2010 ne capture pas de données dans votre environnement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39df0-110">The version you deployed to archive or monitor your Lync Server 2010 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="39df0-111">La procédure suivante décrit les fonctionnalités et paramètres à envisager dans le cadre de votre processus global de déploiement de pool pilote.</span><span class="sxs-lookup"><span data-stu-id="39df0-111">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="39df0-112">Cette section présente uniquement les points clés à prendre en compte dans le cadre de votre déploiement de pool pilote.</span><span class="sxs-lookup"><span data-stu-id="39df0-112">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="39df0-113">Pour consulter la procédure détaillée, voir le Guide de déploiement de <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="39df0-113">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="39df0-114">**Pour déployer un pool de pilotes de Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="39df0-114">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="39df0-115">Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="39df0-115">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="39df0-116">Développez l’arborescence jusqu’à ce que vous atteigniez **Lync Server 2013** **Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="39df0-116">Expand the tree until you reach **Lync Server 2013** **Enterprise Edition Front End pools**.</span></span>

3.  <span data-ttu-id="39df0-117">Cliquez avec le bouton droit sur **Pools frontal pour Enterprise Edition**, puis sélectionnez **nouveau pool frontal**.</span><span class="sxs-lookup"><span data-stu-id="39df0-117">Right click **Enterprise Edition Front End pools**, and select **New Front End Pool**.</span></span>
    
    <span data-ttu-id="39df0-118">![Sous-menu de sélection de pool de serveurs du concepteur topologique](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Sous-menu de sélection de pool de serveurs du concepteur topologique")</span><span class="sxs-lookup"><span data-stu-id="39df0-118">![Topology Builder Server pool selection submenu](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Topology Builder Server pool selection submenu")</span></span>

4.  <span data-ttu-id="39df0-119">Entrez le nom de domaine complet (FQDN) du pool.</span><span class="sxs-lookup"><span data-stu-id="39df0-119">Enter the pool FQDN.</span></span> <span data-ttu-id="39df0-120">Lors de la définition de votre pool de pilotes, vous pouvez choisir de déployer un pool frontal Enterprise Edition ou un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="39df0-120">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="39df0-121">Lync Server 2013 ne nécessite pas que les fonctionnalités de votre pool pilote correspondent aux éléments déployés dans votre pool hérité.</span><span class="sxs-lookup"><span data-stu-id="39df0-121">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="39df0-122">Le pool ou le nom de domaine complet (FQDN) du serveur que vous définissez pour le pool pilote doit être unique.</span><span class="sxs-lookup"><span data-stu-id="39df0-122">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="39df0-123">Il ne peut pas correspondre au nom du pool Lync Server 2010 actuellement déployé ou à tout autre serveur actuellement déployé.</span><span class="sxs-lookup"><span data-stu-id="39df0-123">It cannot match the name of the currently deployed Lync Server 2010 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="39df0-124">![Page de nom de domaine complet de l’Assistant définir le pool frontal](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Page de nom de domaine complet de l’Assistant définir le pool frontal")</span><span class="sxs-lookup"><span data-stu-id="39df0-124">![Define New Front End Pool Wizard FQDN page](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Define New Front End Pool Wizard FQDN page")</span></span>

5.  <span data-ttu-id="39df0-125">Dans la page **Sélectionner des fonctionnalités** , activez les cases à cocher des fonctionnalités que vous voulez inclure dans ce pool frontal.</span><span class="sxs-lookup"><span data-stu-id="39df0-125">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="39df0-126">Par exemple, si vous déployez uniquement les fonctionnalités de messagerie instantanée et de présence, activez la case à cocher Conférence pour autoriser la messagerie instantanée multipartie, mais pas les cases à cocher Conférence rendez-vous (RTC), voix entreprise ou contrôle d’admission des appels. comme ils représentent les fonctionnalités de voix, de vidéo et de conférence de collaboration.</span><span class="sxs-lookup"><span data-stu-id="39df0-126">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="39df0-127">Pour plus d’informations sur la sélection de fonctionnalités, voir [définir et configurer un pool frontal ou un serveur Standard Edition dans Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="39df0-127">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="39df0-128">![Page de sélection des fonctionnalités du pool frontal](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Page de sélection des fonctionnalités du pool frontal")</span><span class="sxs-lookup"><span data-stu-id="39df0-128">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

6.  <span data-ttu-id="39df0-129">Dans la page **Sélectionner des rôles de serveur colocalisés** , nous vous recommandons de Collocate le serveur de médiation dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39df0-129">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="39df0-130">Lors de la fusion d’une topologie héritée avec Lync Server 2013, vous devez commencer par collocate le serveur de médiation Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="39df0-130">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Lync Server 2010 Mediation Server.</span></span> <span data-ttu-id="39df0-131">Après avoir fusionné les topologies et configuré le serveur de médiation Lync Server 2013, vous pouvez décider si vous souhaitez conserver le serveur de médiation colocalisé ou le modifier en serveur autonome lorsque vous déplacez le rôle de serveur de médiation vers Lync Server 2013 par la suite dans le cadre du déploiement. temps.</span><span class="sxs-lookup"><span data-stu-id="39df0-131">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="39df0-132">![Page de rôles de serveur en liste de choix](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Page de rôles de serveur en liste de choix")</span><span class="sxs-lookup"><span data-stu-id="39df0-132">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

7.  <span data-ttu-id="39df0-133">Dans la page **associez les rôles de serveur à cette liste frontale** , pendant le déploiement du pool de pilotes, ne sélectionnez pas l’option **activer un pool Edge à utiliser par le composant multimédia de cette option de pool frontal** .</span><span class="sxs-lookup"><span data-stu-id="39df0-133">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option.</span></span> <span data-ttu-id="39df0-134">Il s’agit d’une fonctionnalité que vous allez activer et mettre en ligne dans une phase ultérieure de la migration.</span><span class="sxs-lookup"><span data-stu-id="39df0-134">This is a feature you will enable and bring online in a later phase of migration.</span></span> <span data-ttu-id="39df0-135">Laissez ce paramètre désactivé pour le moment.</span><span class="sxs-lookup"><span data-stu-id="39df0-135">Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="39df0-136">![Associer des rôles de serveur à une page de pool frontal](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associer des rôles de serveur à une page de pool frontal")</span><span class="sxs-lookup"><span data-stu-id="39df0-136">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

8.  <span data-ttu-id="39df0-137">Dans la page **Sélectionner un serveur Office Web Apps** , cliquez sur **nouveau**, puis spécifiez le nom de domaine complet du serveur d’applications.</span><span class="sxs-lookup"><span data-stu-id="39df0-137">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="39df0-138">![Définir de nouvelles propriétés de nom de domaine complet Office Web Apps Server](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Définir de nouvelles propriétés de nom de domaine complet Office Web Apps Server")</span><span class="sxs-lookup"><span data-stu-id="39df0-138">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

9.  <span data-ttu-id="39df0-139">Dans la page **définir la banque SQL Server** , lors de la définition de la banque SQL Server pour l’archivage et la surveillance de Lync Server, sélectionnez l’instance SQL Server créée précédemment pour lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39df0-139">On the **Define the Archiving SQL Server store** page, when defining the SQL Server store for both Lync Server Archiving and Monitoring, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="39df0-140">![Page définir l’archivage de SQL Server Store](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Page définir l’archivage de SQL Server Store")</span><span class="sxs-lookup"><span data-stu-id="39df0-140">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

10. <span data-ttu-id="39df0-141">Pour publier votre topologie, cliquez avec le bouton droit sur le nœud du **serveur Lync** , puis cliquez sur **publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="39df0-141">To publish your topology, right-click the **Lync Server** node, and then click **Publish Topology**.</span></span>
    
    <span data-ttu-id="39df0-142">![Générateur de topologie présentant une topologie configurée](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Générateur de topologie présentant une topologie configurée")</span><span class="sxs-lookup"><span data-stu-id="39df0-142">![Topology Builder displaying a configured topology](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Topology Builder displaying a configured topology")</span></span>

11. <span data-ttu-id="39df0-143">Lorsque le processus de publication est terminé, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="39df0-143">When the publish process has completed, click **Finish**.</span></span>

<span data-ttu-id="39df0-144">Pour installer une copie locale du magasin de configuration et démarrer les services requis, voir [configuration de serveurs frontaux et de listes frontales pour Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="39df0-144">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>

