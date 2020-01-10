---
title: Mise à niveau vers Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: 'Résumé : Découvrez comment effectuer une mise à niveau de Lync Server 2013 vers Skype entreprise Server 2015. Télécharger une version d’évaluation gratuite de Skype entreprise Server 2015 à partir du centre d’évaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverMicrosoft pour :.'
ms.openlocfilehash: d9ce950ead8b8a3a8857c53d421470a0e647ea23
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001874"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a><span data-ttu-id="367f4-104">Upgrade to Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="367f4-104">Upgrade to Skype for Business Server 2015</span></span>
 
<span data-ttu-id="367f4-105">**Résumé :** Découvrez comment effectuer une mise à niveau de Lync Server 2013 vers Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="367f4-105">**Summary:** Learn how to upgrade from Lync Server 2013 to Skype for Business Server 2015.</span></span> <span data-ttu-id="367f4-106">Télécharger une version d’évaluation gratuite de Skype entreprise Server 2015 à partir du [Centre d’évaluation Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="367f4-106">Download a free trial of Skype for Business Server 2015 from the  [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="367f4-107">Pour effectuer une mise à niveau de Lync Server 2013 vers Skype entreprise Server 2015 à l’aide du générateur de topologie Skype entreprise Server et de la nouvelle fonctionnalité de mise à niveau sur place, suivez les procédures décrites dans ce document.</span><span class="sxs-lookup"><span data-stu-id="367f4-107">Use the procedures in this document to upgrade from Lync Server 2013 to Skype for Business Server 2015 by using the Skype for Business Server Topology Builder and the new In-Place Upgrade feature.</span></span> <span data-ttu-id="367f4-108">Si vous voulez effectuer une mise à niveau à partir de Lync Server 2010 ou d’Office Communications Server 2007 R2, voir [planifier la mise à niveau vers Skype entreprise Server 2015](../plan-your-deployment/upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="367f4-108">If you want to upgrade from Lync Server 2010 or Office Communications Server 2007 R2, see [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>

> [!NOTE]
> <span data-ttu-id="367f4-109">Les mises à niveau sur place étaient disponibles dans Skype entreprise Server 2015, mais ne sont plus prises en charge dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="367f4-109">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="367f4-110">Le coexistence côte à côte est pris en charge, reportez-vous à la rubrique [migration vers Skype entreprise Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="367f4-110">Side by side coexistance is supported, see [Migration to Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>
  
## <a name="upgrade-from-lync-server-2013"></a><span data-ttu-id="367f4-111">Effectuer une mise à niveau à partir de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="367f4-111">Upgrade from Lync Server 2013</span></span>

<span data-ttu-id="367f4-112">La mise à niveau de Lync Server 2013 vers Skype entreprise Server 2015 implique l’installation de logiciels requis, en utilisant le générateur de topologie Skype entreprise Server pour mettre à niveau des bases de données de la liste, et l’utilisation de la mise à niveau sur place de Skype entreprise Server sur chaque serveurs associés au pool.</span><span class="sxs-lookup"><span data-stu-id="367f4-112">Upgrading Lync Server 2013 to Skype for Business Server 2015 involves installing prerequisite software, using the Skype for Business Server Topology Builder to upgrade databases in the pool, and using the Skype for Business Server In-Place Upgrade on each of the servers associated with the pool.</span></span> <span data-ttu-id="367f4-113">Pour procéder à la mise à niveau, passez en revue les huit étapes décrites dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="367f4-113">To complete the upgrade, go through the eight steps in this topic.</span></span>
  
### <a name="before-you-begin"></a><span data-ttu-id="367f4-114">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="367f4-114">Before you begin</span></span>

- <span data-ttu-id="367f4-115">Reportez-vous à [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="367f4-115">Review [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>
    
- <span data-ttu-id="367f4-116">Reportez-vous [à la configuration requise pour Skype entreprise server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="367f4-116">Review [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="367f4-117">[Installez la configuration requise pour Skype entreprise Server 2015](install/install-prerequisites.md) .</span><span class="sxs-lookup"><span data-stu-id="367f4-117">[Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md) .</span></span>
    
- <span data-ttu-id="367f4-118">[Installez Skype entreprise Server 2015](install/install.md) .</span><span class="sxs-lookup"><span data-stu-id="367f4-118">[Install Skype for Business Server 2015](install/install.md) .</span></span>
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a><span data-ttu-id="367f4-119">Étape 1 : Installer les outils d’administrateur et télécharger la topologie</span><span class="sxs-lookup"><span data-stu-id="367f4-119">Step 1: Install Administrator tools and download topology</span></span>

1. <span data-ttu-id="367f4-120">Connectez-vous à un ordinateur dans la topologie sur laquelle Lync OCSCore ou tout autre composant Lync n’est pas installé.</span><span class="sxs-lookup"><span data-stu-id="367f4-120">Connect to computer in the topology that does not have Lync OCSCore or any other Lync components installed.</span></span>
    
2. <span data-ttu-id="367f4-121">À partir du support d’installation de Skype entreprise Server 2015, exécutez **Setup. exe** à partir de **OCS_Volume \Setup\amd64**.</span><span class="sxs-lookup"><span data-stu-id="367f4-121">From Skype for Business Server 2015 installation media, run **Setup.exe** from **OCS_Volume\Setup\AMD64**.</span></span> 
    
3. <span data-ttu-id="367f4-122">Cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="367f4-122">Click **Install**.</span></span> 
    
4. <span data-ttu-id="367f4-123">Acceptez les termes du contrat de licence.</span><span class="sxs-lookup"><span data-stu-id="367f4-123">Accept the license agreement.</span></span>
    
5. <span data-ttu-id="367f4-124">Dans l’Assistant Déploiement, cliquez sur **Installer les outils d’administrateur**, puis suivez les étapes d’installation.</span><span class="sxs-lookup"><span data-stu-id="367f4-124">On the Deployment Wizard, click **Install Administrator tools**, and follow the steps to install.</span></span>
    
     ![Capture d’écran de l’Assistant Déploiement avec lien Installer les outils d’administrateur.](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. <span data-ttu-id="367f4-126">Dans l’écran de démarrage de Windows, ouvrez le générateur de topologie Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="367f4-126">From the Windows Start screen, open Skype for Business Server Topology Builder.</span></span>
    
7. <span data-ttu-id="367f4-127">Cliquez sur **Télécharger la topologie à partir d’un déploiement existant**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="367f4-127">Click **Download topology from existing deployment**, and click **Next**.</span></span>
    
8. <span data-ttu-id="367f4-128">Entrez un nom pour la topologie, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="367f4-128">Enter a name for the topology, and click **Save**.</span></span>
    
9. <span data-ttu-id="367f4-129">Accédez à l’emplacement où vous avez enregistré la topologie, puis effectuez une copie de la topologie.</span><span class="sxs-lookup"><span data-stu-id="367f4-129">Go to location where you saved the topology, and make a copy of the topology.</span></span>
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a><span data-ttu-id="367f4-130">Étape 2 : mise à niveau et publication de la topologie à l’aide du Générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="367f4-130">Step 2: Upgrade and publish topology using Topology Builder</span></span>

<span data-ttu-id="367f4-131">Avant de démarrer le processus de mise à niveau, tous les services doivent être exécutés pour les pools que vous envisagez de mettre à niveau.</span><span class="sxs-lookup"><span data-stu-id="367f4-131">Before you start the upgrade process, all services must be running for the pools you plan to upgrade.</span></span> <span data-ttu-id="367f4-132">Les changements de la topologie pourront ainsi être répliqués dans la base de données locale des serveurs dans le pool.</span><span class="sxs-lookup"><span data-stu-id="367f4-132">This is so the topology changes will be replicated to the local database of the servers in the pool.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="367f4-133">Enregistrez une copie de votre fichier de topologie avant la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="367f4-133">Save a copy of your topology file before you upgrade.</span></span> <span data-ttu-id="367f4-134">Après la mise à niveau, vous ne serez pas en mesure d’effectuer la mise à niveau de la topologie. > si vos services se trouvent sur le même serveur que vos bases de données, comme le service de chat permanent se trouve sur le même serveur que la base de données de chat persistante, ignorez cette étape, puis passez à l’étape 4.</span><span class="sxs-lookup"><span data-stu-id="367f4-134">After you upgrade, you will not be able to downgrade the topology.>  If your services are on the same servers as your databases, like the Persistent Chat service is on the same server as the Persistent Chat database, skip this step, and go to step 4.</span></span> <span data-ttu-id="367f4-135">Après avoir arrêté les services, exécutez le programme de mise à niveau sur place sur chaque serveur pour effectuer la mise à niveau vers les bases de données locales.</span><span class="sxs-lookup"><span data-stu-id="367f4-135">After you stop the services, run the In-Place Upgrade setup on each server to upgrade the local databases.</span></span>
  
> [!NOTE]
> <span data-ttu-id="367f4-p108">Si la topologie comporte une base de données principale mise en miroir, les bases de données principale et en miroir s’affichent **lorsque vous publiez la topologie** à l’aide du générateur de topologie. Vérifiez que toutes les bases de données sont exécutées dans la base de données principale et veillez à sélectionner la base de données principale et non la base de données miroir lors de la publication de la topologie, autrement un avertissement s’affichera après la publication de la topologie.</span><span class="sxs-lookup"><span data-stu-id="367f4-p108">If the topology has a back-end database that is mirrored then you will see both the Principal and the Mirrored databases show up **when you publish the topology** using Topology Builder. Make sure all of the databases are running on the Principal and only select the Principal, not the mirror, when publishing the topology otherwise you will see a warning after publishing the topology.</span></span>
  
<span data-ttu-id="367f4-138">Sélectionnez l’une des options ci-dessous pour mettre à niveau et publier une nouvelle topologie à l’aide du générateur de topologie 2015 de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="367f4-138">Pick one of the options below to upgrade and publish a new topology by using the Skype for Business Server 2015 Topology Builder.</span></span> <span data-ttu-id="367f4-139">Après avoir effectué ces étapes et publié la topologie mise à jour, passez à l’Étape 3 de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="367f4-139">After you complete the steps and publish the updated topology, move to Step 3 in this topic.</span></span>
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a><span data-ttu-id="367f4-140">Option 1 : Mettre à niveau un pool frontal isolé et les magasins d’archivage et de surveillance associés</span><span class="sxs-lookup"><span data-stu-id="367f4-140">Option 1: Upgrade an isolated Front End pool and associated Archiving and Monitoring stores</span></span>

<span data-ttu-id="367f4-141">Si le pool que vous mettez à niveau a une dépendance des magasins d’archivage et de surveillance, quand vous utilisez les étapes suivantes, le magasin d’archivage et de surveillance est aussi mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="367f4-141">If the pool you're upgrading has an Archiving and Monitoring store dependency, when you use the following steps, the Archiving and Monitoring store will be upgraded as well.</span></span>
  
1. <span data-ttu-id="367f4-142">Dans le générateur de topologie, cliquez avec le bouton droit sur un pool Lync Server 2013, sélectionnez **mettre à niveau vers Skype entreprise server 2015**, puis suivez les étapes.</span><span class="sxs-lookup"><span data-stu-id="367f4-142">In Topology Builder, right-click a Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Capture d’écran du menu contextuel présentant l’option de mise à niveau vers Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. <span data-ttu-id="367f4-144">Dans le générateur de topologie, cliquez sur **action** > **publier** la topologie ou la**topologie** > d' **action** > **publier.**</span><span class="sxs-lookup"><span data-stu-id="367f4-144">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
     ![Capture d’écran du menu Action avec l’option Publier la topologie dans le Générateur de topologie.](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. <span data-ttu-id="367f4-146">Au cours de la publication, choisissez d’installer une base de données dans le magasin d’archivage et de surveillance.</span><span class="sxs-lookup"><span data-stu-id="367f4-146">During publishing, choose to install a database on the Archiving and Monitoring store.</span></span>
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a><span data-ttu-id="367f4-147">Option 2 : mise à niveau de la liste frontale sans mise à niveau de l’archivage et de la surveillance</span><span class="sxs-lookup"><span data-stu-id="367f4-147">Option 2: Upgrade Front End pool without upgrading Archiving and Monitoring stores</span></span>

<span data-ttu-id="367f4-p110">Si vous utilisez les étapes suivantes, l’archivage et la surveillance pour le pool sélectionné sont désactivées. Le pool n’aura pas de magasins d’archivage et de surveillance après la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="367f4-p110">If you use the following steps, archiving and monitoring for the selected pool are disabled. The pool will not have Archiving and Monitoring stores after the upgrade.</span></span>
  
1. <span data-ttu-id="367f4-150">Dans le générateur de topologie, sélectionnez le pool Lync Server 2013 que vous voulez mettre à niveau.</span><span class="sxs-lookup"><span data-stu-id="367f4-150">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span>
    
2. <span data-ttu-id="367f4-151">Supprimez la dépendance aux magasins d’archivage et de surveillance Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="367f4-151">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="367f4-152">Accédez à \*\*\*\* > **Propriétés de modification**d’action.</span><span class="sxs-lookup"><span data-stu-id="367f4-152">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="367f4-153">Désactivez la case à cocher **Archivage**.</span><span class="sxs-lookup"><span data-stu-id="367f4-153">Clear the **Archiving** check box.</span></span>
    
     ![Capture d’écran de la boîte de dialogue Modifier les paramètres qui contient la case à cocher Archivage.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="367f4-155">Désactivez la case à cocher **Surveillance**.</span><span class="sxs-lookup"><span data-stu-id="367f4-155">Clear the **Monitoring** check box.</span></span>
    
     ![Capture d’écran de la boîte de dialogue Modifier les paramètres qui contient la case à cocher Surveillance.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="367f4-157">Cliquez avec le bouton droit sur le pool Lync Server 2013, sélectionnez **mettre à niveau vers Skype entreprise server 2015**, puis suivez les étapes.</span><span class="sxs-lookup"><span data-stu-id="367f4-157">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Capture d’écran du menu contextuel présentant l’option de mise à niveau vers Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="367f4-159">Dans le générateur de topologie, cliquez sur **action** > **publier** la topologie ou la**topologie** > d' **action** > **publier.**</span><span class="sxs-lookup"><span data-stu-id="367f4-159">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a><span data-ttu-id="367f4-160">Option 3 : mise à niveau de la réserve frontale et associée aux nouvelles boutiques Skype entreprise Server 2015 d’archivage et de surveillance</span><span class="sxs-lookup"><span data-stu-id="367f4-160">Option 3: Upgrade Front End pool and associated it to new Skype for Business Server 2015 Archiving and Monitoring stores</span></span>

<span data-ttu-id="367f4-161">Si vous utilisez les étapes suivantes, l’archivage et la surveillance s’arrêteront dans le magasin précédent et commenceront dans le nouveau magasin que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="367f4-161">If you use the following steps, archiving and monitoring will stop in the previous store and start in the new store you've created.</span></span> 
  
1. <span data-ttu-id="367f4-162">Dans le générateur de topologie, sélectionnez le pool Lync Server 2013 que vous voulez mettre à niveau.</span><span class="sxs-lookup"><span data-stu-id="367f4-162">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span> 
    
2. <span data-ttu-id="367f4-163">Supprimez la dépendance aux magasins d’archivage et de surveillance Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="367f4-163">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="367f4-164">Accédez à \*\*\*\* > **Propriétés de modification**d’action.</span><span class="sxs-lookup"><span data-stu-id="367f4-164">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="367f4-165">Désactivez la case à cocher **Archivage**.</span><span class="sxs-lookup"><span data-stu-id="367f4-165">Clear the **Archiving** check box.</span></span>
    
     ![Capture d’écran de la boîte de dialogue Modifier les paramètres qui contient la case à cocher Archivage.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="367f4-167">Désactivez la case à cocher **Surveillance**.</span><span class="sxs-lookup"><span data-stu-id="367f4-167">Clear the **Monitoring** check box.</span></span>
    
     ![Capture d’écran de la boîte de dialogue Modifier les paramètres qui contient la case à cocher Surveillance.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="367f4-169">Cliquez avec le bouton droit sur le pool Lync Server 2013, sélectionnez **mettre à niveau vers Skype entreprise server 2015**, puis suivez les étapes.</span><span class="sxs-lookup"><span data-stu-id="367f4-169">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Capture d’écran du menu contextuel présentant l’option de mise à niveau vers Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="367f4-171">Créez un nouveau magasin SQL pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="367f4-171">Create a new SQL store for Archiving.</span></span> 
    
   - <span data-ttu-id="367f4-172">Sélectionnez les propriétés de \*\*\*\* > **modification**du pool et de l’action.</span><span class="sxs-lookup"><span data-stu-id="367f4-172">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="367f4-173">Activez la case à cocher **Archivage**.</span><span class="sxs-lookup"><span data-stu-id="367f4-173">Select the **Archiving** check box.</span></span>
    
   - <span data-ttu-id="367f4-174">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="367f4-174">Click **New**.</span></span>
    
     ![Capture d’écran de la boîte de dialogue Modifier les paramètres figurant le bouton Nouveau dans la section Archivage.](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. <span data-ttu-id="367f4-176">Créez un nouveau magasin SQL pour la surveillance.</span><span class="sxs-lookup"><span data-stu-id="367f4-176">Create a new SQL store for Monitoring.</span></span> 
    
   - <span data-ttu-id="367f4-177">Sélectionnez les propriétés de \*\*\*\* > **modification**du pool et de l’action.</span><span class="sxs-lookup"><span data-stu-id="367f4-177">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="367f4-178">Activez la case à cocher **Surveillance**.</span><span class="sxs-lookup"><span data-stu-id="367f4-178">Select the **Monitoring** check box.</span></span>
    
   - <span data-ttu-id="367f4-179">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="367f4-179">Click **New**.</span></span>
    
     ![Capture d’écran de la boîte de dialogue Modifier les paramètres figurant le bouton Nouveau dans la section Surveillance.](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. <span data-ttu-id="367f4-181">Dans le générateur de topologie, cliquez sur **action** > **publier** la topologie ou la**topologie** > d' **action** > **publier.**</span><span class="sxs-lookup"><span data-stu-id="367f4-181">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
7. <span data-ttu-id="367f4-182">Au cours de la publication, choisissez d’installer la base de données dans le magasin d’archivage et de surveillance.</span><span class="sxs-lookup"><span data-stu-id="367f4-182">During publishing, choose to install the database on the new Archiving and Monitoring store.</span></span>
    
### <a name="step-3-wait-for-replication"></a><span data-ttu-id="367f4-183">Étape 3 : Attendre la réplication</span><span class="sxs-lookup"><span data-stu-id="367f4-183">Step 3: Wait for replication</span></span>

<span data-ttu-id="367f4-184">Laissez à la réplication le temps de publier la topologie mise à jour vers tous les serveurs de l’environnement.</span><span class="sxs-lookup"><span data-stu-id="367f4-184">Give replication some time to publish the updated topology to all the servers in the environment.</span></span>
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a><span data-ttu-id="367f4-185">Étape 4 : Arrêter les services dans le pool à mettre à niveau</span><span class="sxs-lookup"><span data-stu-id="367f4-185">Step 4: Stop all services in pool to be upgraded</span></span>

<span data-ttu-id="367f4-186">Sur chaque serveur qui dessert le pool que vous allez mettre à niveau, exécutez l’applet de commande suivante dans PowerShell :</span><span class="sxs-lookup"><span data-stu-id="367f4-186">On each server that is servicing the pool that you're going to upgrade, run the following cmdlet in PowerShell:</span></span>
  
```powershell
Disable-CsComputer -Scorch
```

<span data-ttu-id="367f4-187">Nous vous recommandons d’utiliser Disable-CsComputer, car il est possible que vous deviez redémarrer le serveur pendant le processus de mise à niveau sur place.</span><span class="sxs-lookup"><span data-stu-id="367f4-187">We recommend using Disable-CsComputer because you may need to reboot the server during the In-Place Upgrade process.</span></span> <span data-ttu-id="367f4-188">Si vous utilisez Stop-CsWindowsService, certains services peuvent redémarrer automatiquement après un redémarrage.</span><span class="sxs-lookup"><span data-stu-id="367f4-188">If you use Stop-CsWindowsService, some services may restart automatically after a reboot.</span></span> <span data-ttu-id="367f4-189">Cela peut entraîner l’échec de la mise à niveau sur place.</span><span class="sxs-lookup"><span data-stu-id="367f4-189">This may cause the In-Place Upgrade to fail.</span></span>
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a><span data-ttu-id="367f4-190">Étape 5 : Mettre à niveau les pools frontaux et les serveurs des pools non frontaux</span><span class="sxs-lookup"><span data-stu-id="367f4-190">Step 5: Upgrade Front End pools and non-Front End pool servers</span></span>

> [!NOTE]
>  <span data-ttu-id="367f4-191">Avant de procéder à la mise à niveau, procédez à l’installation de tous les nouveaux éléments requis pour Skype entreprise Server 2015 qui incluent : > au moins 32 Go d’espace libre avant d’effectuer une mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="367f4-191">Before upgrading please install all new prerequisites required for Skype for Business Server 2015 which include:>  At least 32GB of free space before attempting an upgrade.</span></span> <span data-ttu-id="367f4-192">Par ailleurs, assurez-vous que le lecteur est un disque local fixe, qu’il n’est pas connecté par USB ou FireWire. est mis en forme avec le système de fichiers NTFS, n’est pas compressé et ne contient pas de fichier de page. > PowerShell version 6.2.9200.0 ou une version ultérieure. > la dernière mise à jour cumulative de Lync Server 2013. > SQL Server 2012 SP1 installé. > la mise à jour suivante de Windows Server 2008 R2-[KB2533623](https://support.microsoft.com/kb/2533623) > windows server 2012-[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2 [KB2982006](https://support.microsoft.com/kb/2982006)</span><span class="sxs-lookup"><span data-stu-id="367f4-192">In addition, make sure that the drive is a fixed local drive, is not connected by USB or Firewire, is formatted with NTFS file system, is not compressed, and does not contain a page file.>  PowerShell version 6.2.9200.0 or later.>  The latest Lync Server 2013 Cumulative Update installed.>  SQL Server 2012 SP1 installed.>  The following KB's installed (installed automatically if using Microsoft Update):>  Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)>  Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)>  Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)</span></span>
  
<span data-ttu-id="367f4-193">Utilisez la mise à niveau sur place de chaque serveur pour mettre à jour la liste frontale, le pool de médiation et le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="367f4-193">Use the In-Place Upgrade on each server to update the Front End pool, Edge pool, Mediation server, and the Persistent Chat pool.</span></span>
  
1. <span data-ttu-id="367f4-194">Sur chaque serveur, exécutez **Setup. exe** à partir de **OCS_Volume \Setup\amd64** sur le support d’installation de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="367f4-194">On each server, run **Setup.exe** from **OCS_Volume\Setup\amd64** on the Skype for Business Server 2015 installation media.</span></span>
    
2. <span data-ttu-id="367f4-195">Acceptez le contrat de licence et suivez les invites de la mise à niveau sur place.</span><span class="sxs-lookup"><span data-stu-id="367f4-195">Accept the license agreement and follow the prompts for the In-Place Upgrade.</span></span>
    
3. <span data-ttu-id="367f4-196">Répétez ces étapes pour chaque serveur dans le pool frontal et sur chacun d’eux.</span><span class="sxs-lookup"><span data-stu-id="367f4-196">Repeat these steps for each server in the Front End pool and on each non-Front End pool server.</span></span>
    
> [!NOTE]
> <span data-ttu-id="367f4-197">Vous pouvez être invité à redémarrer le serveur pendant la mise à niveau sur place.</span><span class="sxs-lookup"><span data-stu-id="367f4-197">You might be prompted to reboot the server during the In-Place Upgrade.</span></span> <span data-ttu-id="367f4-198">C'est d'accord.</span><span class="sxs-lookup"><span data-stu-id="367f4-198">That's ok.</span></span> <span data-ttu-id="367f4-199">Après le redémarrage, la mise à niveau sur place reste là là où elle s’était arrêtée.</span><span class="sxs-lookup"><span data-stu-id="367f4-199">After you reboot, the In-Place Upgrade will continue from where it left off.</span></span> 
  
<span data-ttu-id="367f4-200">Lorsque la mise à niveau sur place réussit, le message suivant s’affiche.</span><span class="sxs-lookup"><span data-stu-id="367f4-200">When the In-Place Upgrade completes successfully, you see the following message.</span></span>
  
![Capture d’écran montrant que la mise à niveau sur place a réussi.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a><span data-ttu-id="367f4-202">Étape 6 : Redémarrer les services sur tous les serveurs mis à niveau</span><span class="sxs-lookup"><span data-stu-id="367f4-202">Step 6: Restart services on all upgraded servers</span></span>

> [!NOTE]
> <span data-ttu-id="367f4-203">Avant de redémarrer les services, assurez-vous que%ProgramData%\WindowsFabric n’existe pas sur tous les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="367f4-203">Before restarting the services, please make sure %ProgramData%\WindowsFabric doesn't exist on all Front End Servers.</span></span> <span data-ttu-id="367f4-204">S’il existe, supprimez-le avant de démarrer les services.</span><span class="sxs-lookup"><span data-stu-id="367f4-204">If it exists, delete it before starting the services.</span></span> 
  
- <span data-ttu-id="367f4-205">Après avoir effectué la mise à niveau de tous les serveurs dans la liste frontale, redémarrez les services en utilisant la commande PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="367f4-205">After you've upgraded all servers in the Front End pool, restart the services by using the following PowerShell command:</span></span> 
    
  ```powershell
  Start-CsPool
  ```

    > [!NOTE]
    > <span data-ttu-id="367f4-p115">Si un redémarrage système déjà en attente est nécessaire avant le lancement d’une procédure de mise à niveau sur place, la mise à niveau sur place ne vous demandera alors pas de redémarrer à la fin de l’installation. Des exceptions d’assembly seront alors levées concernant le premier serveur frontal lorsque vous tenterez de démarrer des services à l’aide de l’applet de commande Start-CSPool. Pour résoudre ces erreurs, redémarrez tous les serveurs du pool et réexécutez l’applet de commande.</span><span class="sxs-lookup"><span data-stu-id="367f4-p115">If there is already a pending system reboot needed before you start running In-Place Upgrade, then In-Place Upgrade won't ask you to reboot at the end of the installation. This will cause some assembly exceptions to be thrown against the first Front End server when you try to start services using the Start-CSPool cmdlet. To resolve these errors, reboot all of the servers in the pool and run the cmdlet again.</span></span> 
  
- <span data-ttu-id="367f4-209">Sur les serveurs du pool non frontal, redémarrez les services en utilisant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="367f4-209">On the non-Front End pool servers, restart the services by using the following command:</span></span>
    
  ```powershell
  Start-CsWindowsService
  ```

<span data-ttu-id="367f4-210">Après avoir cliqué sur **OK** sur la page de mise à niveau sur place, le rappel suivant s’affiche vous invitant à compléter le reste de l’étape.</span><span class="sxs-lookup"><span data-stu-id="367f4-210">After you click **OK** on the In-Place Upgrade page, you'll see the following reminder to complete this step.</span></span>
  
![Capture d’écran montrant les étapes qui suivent la mise à niveau sur place réussie.](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a><span data-ttu-id="367f4-212">Étape 7 : vérifier le fonctionnement de la fonctionnalité Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="367f4-212">Step 7: Verify Skype for Business functionality works</span></span>

<span data-ttu-id="367f4-213">Pour vous assurer que la mise à niveau a réussi, pour le pool qui a été mis à niveau, testez Skype entreprise pour vous assurer que le fonctionnement fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="367f4-213">To make sure the upgrade was successful, for the pool that was upgraded, test Skype for Business to make sure the functionality is working as expected.</span></span> 
  
### <a name="step-8-upgrade-secondary-pools"></a><span data-ttu-id="367f4-214">Étape 8 : Mettre à niveau les pools secondaires</span><span class="sxs-lookup"><span data-stu-id="367f4-214">Step 8: Upgrade secondary pools</span></span>

<span data-ttu-id="367f4-215">Répétez les étapes de cette rubrique pour mettre à niveau les autres pools de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="367f4-215">Repeat the steps in this topic to upgrade any additional pools that you have in your environment.</span></span>
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a><span data-ttu-id="367f4-216">Résoudre les problèmes de la mise à niveau sur place</span><span class="sxs-lookup"><span data-stu-id="367f4-216">Troubleshoot issues with the In-Place Upgrade</span></span>

<span data-ttu-id="367f4-217">Si la mise à niveau sur place échoue, un message tel que celui qui figure sur l’image suivante peut s’afficher.</span><span class="sxs-lookup"><span data-stu-id="367f4-217">If the In-Place Upgrade fails, you might see a message similar to what's in the following image.</span></span> 
  
![Capture d’écran montrant l’échec de la mise à niveau sur place à cause de la non-installation d’une mise à jour cumulative obligatoire.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
<span data-ttu-id="367f4-219">Examinez le message complet au bas de la page pour vous aider à résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="367f4-219">Review the full message at the bottom of the page to help you troubleshoot the issue.</span></span> <span data-ttu-id="367f4-220">Cliquez sur **Afficher les journaux** pour obtenir plus de détails.</span><span class="sxs-lookup"><span data-stu-id="367f4-220">Click **View logs** to get more detail.</span></span>
  
<span data-ttu-id="367f4-221">Si la mise à niveau sur place échoue pour vérifier la compatibilité de la **mise à niveau** ou **l’installation des conditions préalables manquantes**, assurez-vous que le serveur possède toutes les mises à jour de Windows Server, de LYNC Server et de SQL Server, et que tous les logiciels et rôles requis sont installés.</span><span class="sxs-lookup"><span data-stu-id="367f4-221">If the In-Place Upgrade fails on **Verifying upgrade readiness** or **Installing missing prerequisites**, make sure the server has all the latest Windows Server, Lync Server, and SQL Server updates applied, and all the required software and roles are installed.</span></span> <span data-ttu-id="367f4-222">Pour obtenir la liste des éléments requis, voir [Configuration requise pour Skype entreprise server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) et installer la configuration requise [pour skype entreprise Server 2015](install/install-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="367f4-222">For a list of what's required, see [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="367f4-223">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="367f4-223">See also</span></span>

[<span data-ttu-id="367f4-224">Plan to upgrade to Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="367f4-224">Plan to upgrade to Skype for Business Server 2015</span></span>](../plan-your-deployment/upgrade.md)
  
[<span data-ttu-id="367f4-225">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="367f4-225">Server requirements for Skype for Business Server 2015</span></span>](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="367f4-226">Installation des composants prérequis pour Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="367f4-226">Install prerequisites for Skype for Business Server 2015</span></span>](install/install-prerequisites.md)
  
[<span data-ttu-id="367f4-227">Installer Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="367f4-227">Install Skype for Business Server 2015</span></span>](install/install.md)
