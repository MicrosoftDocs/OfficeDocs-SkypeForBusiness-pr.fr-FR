---
title: 'Lync Server 2013 : Association d’un magasin de surveillance à un pool frontal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating a monitoring store with a Front End pool
ms:assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205271(v=OCS.15)
ms:contentKeyID: 48185439
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e80c6f7482787d448709beaf98e796519860d22c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520634"
---
# <a name="associating-a-monitoring-store-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="3589e-102">Association d’un magasin de surveillance à un pool frontal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3589e-102">Associating a monitoring store with a Front End pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3589e-103">_**Dernière modification de la rubrique :** 2013-04-22_</span><span class="sxs-lookup"><span data-stu-id="3589e-103">_**Topic Last Modified:** 2013-04-22_</span></span>

<span data-ttu-id="3589e-104">Dans Microsoft Lync Server 2013, les données de surveillance peuvent uniquement être collectées sur les pools frontaux qui ont été associés à un magasin de surveillance, une tâche qui, en règle générale, définit un pool frontal dans le générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="3589e-104">In Microsoft Lync Server 2013 monitoring data can only be collected on Front End pools that have been associated with a monitoring store, a task typically carried out you define a Front End pool in Topology Builder.</span></span> <span data-ttu-id="3589e-105">Pour associer un magasin de surveillance à un nouveau pool frontal, veillez à sélectionner l’option **surveillance (enregistrement des détails des appels et enregistrement des mesures de qualité de l’expérience)** sur la page **Sélectionner des fonctionnalités** de l’Assistant définir un nouveau pool frontal.</span><span class="sxs-lookup"><span data-stu-id="3589e-105">To associate a monitoring store with a new Front End pool, make sure that you select the option **Monitoring (call detail recording and logging of quality of experience metrics)** on the **Select Features** page of the Define New Front End Pool wizard.</span></span> <span data-ttu-id="3589e-106">Notez que si vous sélectionnez cette option, vous devez également spécifier un magasin SQL pour terminer l’exécution de l’Assistant. Toutefois, il n’est pas nécessaire que ce magasin existe au moment où vous exécutez l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="3589e-106">Note that, if you select this option, you must also specify a SQL store in order to complete the wizard; however, this store does not have to exist at the time you run the wizard.</span></span> <span data-ttu-id="3589e-107">Cela signifie que vous pouvez d’abord associer un pool à un magasin de surveillance, puis configurer cette banque ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="3589e-107">That means that you can first associate a pool with a monitoring store, then later setup and configure that store.</span></span>

<span data-ttu-id="3589e-108">Vous pouvez également associer un pool frontal existant à un nouveau magasin d’analyse ou à un autre en effectuant la procédure suivante :</span><span class="sxs-lookup"><span data-stu-id="3589e-108">Alternatively, you can associate an existing Front End pool with a new or different monitoring store by completing the following procedure:</span></span>

1.  <span data-ttu-id="3589e-109">Cliquez successivement sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologies Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3589e-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="3589e-110">Dans la boîte de dialogue **Générateur de topologies**, sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3589e-110">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>

3.  <span data-ttu-id="3589e-p102">Dans la boîte de dialogue **Enregistrer sous**, entrez un nom de fichier pour votre topologie actuelle, puis cliquez sur **Enregistrer**. La topologie enregistrée peut être récupérée et republiée plus tard en cas de problèmes avec la nouvelle topologie.</span><span class="sxs-lookup"><span data-stu-id="3589e-p102">In the **Save As** dialog box, enter a file name for your current topology and then click **Save**. The saved topology can later be retrieved and re-published in case there are problems with the new topology.</span></span>

4.  <span data-ttu-id="3589e-113">Dans le générateur de topologies, développez **Lync Server 2013**, développez le nom du site contenant le pool frontal, puis cliquez sur développer les **Pools frontaux Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="3589e-113">In Topology Builder, expand **Lync Server 2013**, expand the name of the site containing the Front End pool, then click expand **Enterprise Edition Front End pools**.</span></span>

5.  <span data-ttu-id="3589e-114">Cliquez avec le bouton droit sur le nom du pool à associer au magasin d’analyse, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="3589e-114">Right-click the name of the pool to be associated with the monitoring store and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="3589e-p103">Dans la boîte de dialogue **Modifier les propriétés**, sous l’onglet **Général**, sélectionnez l’option **Surveillance (mesures CDR et QoE)**, puis sélectionnez une base de données SQL Server existante dans la liste déroulante **Magasin d’analyse SQL Server**. (Vous pouvez également cliquer sur **Nouveau** pour associer le pool à un nouveau magasin de bases de données.) Si vous décidez d’utiliser un nouveau magasin de bases de données, dans la boîte de dialogue **Définir un nouveau magasin SQL**, entrez le nom de domaine complet de l’ordinateur SQL Server dans la zone **Nom de domaine complet du serveur SQL Server**. Si vous choisissez d’utiliser l’instance SQL Server par défaut pour ce magasin, sélectionnez **Instance par défaut**, sinon, sélectionnez **Instance nommée**, puis entrez le nom de l’instance dans la zone **Instance nommée**.</span><span class="sxs-lookup"><span data-stu-id="3589e-p103">In the **Edit Properties** dialog box, on the **General** tab, select the option **Monitoring (CDR and QoE metrics)** and then select an existing SQL Server database from the **Monitoring SQL Server store** dropdown list. (Or, click **New** to associate the pool with a new database store.) If you choose to use a new database store then, in the **Define New SQL Store** dialog box, enter the fully qualified domain name of the SQL Server computer in the **Sql Server FQDN** box. If you want to use the default SQL Server instance for that store select **Default Instance**; otherwise select **Named Instance** and enter the instance name in the **Named Instance** box.</span></span>
    
    <span data-ttu-id="3589e-p104">La boîte de dialogue **Modifier les propriétés** vous permet également de créer un miroir SQL pour votre base de données d’analyse (un miroir SQL vous permet de conserver deux copies de votre base de données d’analyse : une copie est stockée sur l’ordinateur du magasin d’analyse et l’autre copie sur l’ordinateur du miroir SQL). Pour activer la mise en miroir, sélectionnez **Cette instance SQL est dans une relation de mise en miroir**, puis entrez le numéro du port pour le serveur miroir dans la zone **Numéro de port pour la mise en miroir**.</span><span class="sxs-lookup"><span data-stu-id="3589e-p104">The **Edit Properties** dialog box also gives you the option of creating a SQL mirror for your monitoring database (a SQL mirror enables you to maintain two copies of your monitoring database, one copy stored on the monitoring store computer and the other on the SQL mirror computer). To enable mirroring, select T**his SQL instance is in mirroring relation** and enter the port number for the mirror server in the **Mirroring port number** box.</span></span>

7.  <span data-ttu-id="3589e-120">Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3589e-120">In the **Edit Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="3589e-p105">Après avoir associé le magasin d’analyse au pool frontal, vous devez publier la nouvelle topologie pour que les modifications prennent effet. Pour publier votre nouvelle topologie, effectuez les étapes suivantes dans le générateur de topologies :</span><span class="sxs-lookup"><span data-stu-id="3589e-p105">After associating the monitoring store with a Front End pool you must publish the new topology before the changes take effect. To publish your new topology, complete the following steps in Topology Builder:</span></span>

1.  <span data-ttu-id="3589e-123">Cliquez sur **Action**, pointez sur **Topologie**, puis cliquez sur **Publier**.</span><span class="sxs-lookup"><span data-stu-id="3589e-123">Click **Action**, point to **Topology**, and then click **Publish**.</span></span>

2.  <span data-ttu-id="3589e-124">Dans l’Assistant Publication de topologie, dans la page **Publier la topologie**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="3589e-124">In the Publish Topology wizard, on the **Publish the topology** page, click **Next**.</span></span>

3.  <span data-ttu-id="3589e-125">Dans la page **Assistant Publication terminé**, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="3589e-125">On the **Publishing wizard complete** page, click **Finish**.</span></span>

<span data-ttu-id="3589e-126">Après avoir publié la topologie, vous pouvez installer la base de données d’analyse sur l’ordinateur qui va héberger le magasin d’analyse.</span><span class="sxs-lookup"><span data-stu-id="3589e-126">After the topology has been published you can then install the monitoring database on the computer that will host the monitoring store.</span></span> <span data-ttu-id="3589e-127">La base de données de surveillance peut être installée à l’aide de Lync Server Management Shell et de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3589e-127">The monitoring database can be installed by using the Lync Server Management Shell and Windows PowerShell.</span></span> <span data-ttu-id="3589e-128">Pour installer la base de données localement (autrement dit, pour installer la base de données sur le même ordinateur que celui sur lequel vous exécutez Lync Server Management Shell), démarrez Management Shell sur l’ordinateur approprié, puis tapez la commande suivante et appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="3589e-128">To install the database locally (that is, to install the database on the same computer where you are running the Lync Server Management Shell), start the Management Shell on the appropriate computer, then type in the following command and press ENTER:</span></span>

    Install-CsDatabase -LocalDatabases

<span data-ttu-id="3589e-129">Lorsque vous exécutez la commande précédente, Install-CsDatabase lira la topologie Lync Server actuelle, déterminez les bases de données qui doivent être installées sur l’ordinateur local, puis installez et configurez automatiquement chacune de ces bases de données.</span><span class="sxs-lookup"><span data-stu-id="3589e-129">When you run the preceding command, Install-CsDatabase will read the current Lync Server topology, determine which databases need to be installed on the local computer, and then automatically install and configure each of those databases.</span></span>

<span data-ttu-id="3589e-130">Pour installer la base de données sur un ordinateur distant (c’est-à-dire, un ordinateur autre que l’ordinateur sur lequel Management Shell est exécuté), vous devez inclure au moins deux paramètres : les paramètres ConfiguredDatabases et SqlServerFqdn.</span><span class="sxs-lookup"><span data-stu-id="3589e-130">To install the database on a remote computer (that is, a computer other than the computer where the Management Shell is running) you must include at least two parameters: the ConfiguredDatabases parameter and the SqlServerFqdn parameter.</span></span> <span data-ttu-id="3589e-131">Ces paramètres indiquent à l’applet de commande Install-CsDatabase d’extraire la topologie Lync Server, puis d’installer et de configurer les bases de données requises sur l’ordinateur spécifié par le paramètre SqlServerFqdn.</span><span class="sxs-lookup"><span data-stu-id="3589e-131">These parameters tell the Install-CsDatabase cmdlet to retrieve the Lync Server topology and then install and configure the required databases on the computer specified by the SqlServerFqdn parameter.</span></span> <span data-ttu-id="3589e-132">Le paramètre SqlServerFqdn doit utiliser une valeur représentant le nom de domaine complet de l’ordinateur sur lequel les bases de données doivent être installées.</span><span class="sxs-lookup"><span data-stu-id="3589e-132">The SqlServerFqdn parameter must use a parameter value representing the fully qualified domain name of the computer where the databases are to be installed.</span></span>

<span data-ttu-id="3589e-133">Par exemple, cette commande permet d’installer la base de données d’analyse sur l’ordinateur atl-sql-001.litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="3589e-133">For example, this command installs the monitoring database on the computer atl-sql-001.litwareinc.com:</span></span>

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

<span data-ttu-id="3589e-134">Vous pouvez également installer la base de données de surveillance en exécutant l’Assistant Déploiement de Lync Server sur l’ordinateur qui hébergera le magasin de surveillance.</span><span class="sxs-lookup"><span data-stu-id="3589e-134">Alternatively, you can install the monitoring database by running the Lync Server Deployment Wizard on the computer that will host the monitoring store.</span></span> <span data-ttu-id="3589e-135">Pour ce faire, ouvrez une session sur l’ordinateur approprié, puis effectuez la procédure suivante :</span><span class="sxs-lookup"><span data-stu-id="3589e-135">To do this, log on to the appropriate computer and complete the following procedure:</span></span>

1.  <span data-ttu-id="3589e-136">Cliquez successivement sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Assistant Déploiement Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3589e-136">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="3589e-137">Dans l’Assistant Déploiement, cliquez sur **Installer ou mettre à jour le système Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3589e-137">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="3589e-138">Dans la page **Déployer**, sous **Étape 2 : installer ou supprimer des composants Lync Server**, cliquez sur **Réexécuter**.</span><span class="sxs-lookup"><span data-stu-id="3589e-138">On the **Deploy** page, under **Step 2: Setup or Remove Lync Server Components**, click **Run Again**.</span></span>

4.  <span data-ttu-id="3589e-139">Dans l’Assistant Installation des composants Lync Server, dans la page **Installer les composants Lync Server**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="3589e-139">In the Setup Lync Server components wizard, on the **Setup Lync Server components** page, click **Next**.</span></span>

5.  <span data-ttu-id="3589e-140">Sur la page **spécifier le chemin d’accès à MSI** , tapez le chemin d’accès au fichier Ocscore.msi (un fichier inclus avec votre support d’installation Lync Server), puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="3589e-140">On the **Specify path to MSIs** page, type the path to the file Ocscore.msi (a file included with your Lync Server installation media) and then click **Next**.</span></span>

6.  <span data-ttu-id="3589e-141">Dans la page de **Exécution de commandes**, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="3589e-141">On the **Executing Commands** page, click **Finish**.</span></span>

<span data-ttu-id="3589e-142">Pour vous assurer que tous les services Lync Server requis ont été démarrés, cliquez sur **exécuter** sous le titre **étape 4 : démarrer les services** dans la page **déployer** .</span><span class="sxs-lookup"><span data-stu-id="3589e-142">To ensure that all the required Lync Server services have started, click **Run** under the heading **Step 4: Start Services** on the **Deploy** page</span></span>

</div>

<span> </span>

</div>

</div>

</div>

