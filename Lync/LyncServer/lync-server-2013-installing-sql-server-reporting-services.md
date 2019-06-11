---
title: 'Lync Server 2013: installation de SQL Server Reporting Services'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48184345
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6707cafc3a08123bd2189639704741681eb9cdd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a><span data-ttu-id="86db8-102">Installation de SQL Server Reporting Services dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86db8-102">Installing SQL Server Reporting Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86db8-103">_**Dernière modification de la rubrique:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="86db8-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="86db8-104">Si vous envisagez d’utiliser les rapports d’analyse de Microsoft Lync Server 2013 (voir la section suivante de cette documentation pour plus d’informations), vous devez d’abord installer SQL Server Reporting Services. Reporting Services peut être installé en même temps que Microsoft SQL Server ou à tout moment après l’installation de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="86db8-104">If you intend to use Microsoft Lync Server 2013 Monitoring Reports (see the next section of this documentation for more information) you must first install SQL Server Reporting Services; Reporting Services can be installed at the same time you install Microsoft SQL Server or any time after SQL Server has been installed.</span></span> <span data-ttu-id="86db8-105">Vous pouvez le faire lors de l’installation de Microsoft SQL Server ou à tout moment après l’installation de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="86db8-105">If you have not installed SQL Server, then follow the instructions provided earlier in this documentation.</span></span> <span data-ttu-id="86db8-106">Si vous n’avez pas installé SQL Server, suivez les instructions fournies plus haut dans cette documentation.</span><span class="sxs-lookup"><span data-stu-id="86db8-106">When installing SQL Server, make sure that, on the Feature Selection page, you select Reporting Services.</span></span> <span data-ttu-id="86db8-107">Lorsque vous installez SQL Server, dans la page Sélection des composants, veillez à sélectionner Reporting Services pour installer SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="86db8-107">That will install SQL Server Reporting Services.</span></span>

<span data-ttu-id="86db8-108">Si vous avez déjà installé SQL Server, mais que vous n’avez pas installé SQL Server Reporting Services, vous pouvez ajouter cette fonctionnalité en suivant les instructions appropriées pour SQL Server 2008 R2 ou SQL Server 2012, selon le cas.</span><span class="sxs-lookup"><span data-stu-id="86db8-108">If you have already installed SQL Server but did not install SQL Server Reporting Services you can add that feature by following the appropriate set of instructions for SQL Server 2008 R2 or SQL Server 2012, as appropriate.</span></span>

<span data-ttu-id="86db8-109">Pour vérifier que Reporting Services a été installé correctement, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="86db8-109">To verify that the reporting Services have been successfully installed, complete the following steps:</span></span>

1.  <span data-ttu-id="86db8-110">Si vous exécutez Microsoft SQL Server 2008 R2, cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft SQL Server 2008 R2**, sur **outils de configuration**, puis sur **Gestionnaire de configuration**de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="86db8-110">If you are running Microsoft SQL Server 2008 R2, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>
    
    <span data-ttu-id="86db8-111">Si vous exécutez Microsoft SQL Server 2012, cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft SQL Server 2012**, sur **outils de configuration**, puis sur **Gestionnaire de configuration Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="86db8-111">If you are running Microsoft SQL Server 2012, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2012**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="86db8-112">Dans la boîte de dialogue **connexion de configuration** de Reporting Services, vérifiez que le nom de votre serveur apparaît dans la zone **nom du serveur** et que le nom de l’instance SQL Server qui stocke vos données de surveillance s’affiche dans le serveur de \*\*rapports. \*\*Zone d’instance.</span><span class="sxs-lookup"><span data-stu-id="86db8-112">In the **Reporting Services Configuration Connection** dialog box, verify that the name of your server appears in the **Server Name** box and that the name of the SQL Server instance that stores your monitoring data appears in the **Report Server Instance** box.</span></span> <span data-ttu-id="86db8-113">Cliquez sur **connexion**.</span><span class="sxs-lookup"><span data-stu-id="86db8-113">Click **Connect**.</span></span>

<span data-ttu-id="86db8-114">Dans le gestionnaire de configuration de service de rapports, le volet État du serveur de rapport doit indiquer que SQL Server Reporting Services est installé et que les services de création de rapports sont en cours d’exécution: l’état du serveur de rapport doit apparaître comme **démarré** et le bouton **Démarrer** doit être grisé et indisponible.</span><span class="sxs-lookup"><span data-stu-id="86db8-114">In the Reporting Service Configuration Manager, the Report Server Status pane should show that SQL Server Reporting Services has been installed and that the Reporting Services are currently running: the Report Server Status should be shown as **Started** and the **Start** button should be grayed-out and unavailable.</span></span> <span data-ttu-id="86db8-115">Si le service de création de rapports n’est pas en cours d’exécution, cliquez sur **Démarrer** pour démarrer le service.</span><span class="sxs-lookup"><span data-stu-id="86db8-115">If the Reporting Service is not running, click **Start** in order to start the service.</span></span>

<span data-ttu-id="86db8-116">Si aucune base de données n’est répertoriée en regard de l’étiquette de nom de la base de données du serveur de rapports, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="86db8-116">If no database is listed next to the Report Server Database Name label then do the following:</span></span>

1.  <span data-ttu-id="86db8-117">Dans le gestionnaire de configuration Reporting Services, cliquez sur **base de données**.</span><span class="sxs-lookup"><span data-stu-id="86db8-117">In the Reporting Services Configuration Manager click **Database**.</span></span>

2.  <span data-ttu-id="86db8-118">Dans le volet base de données du serveur de rapport, cliquez sur **modifier la base de données**.</span><span class="sxs-lookup"><span data-stu-id="86db8-118">In the Report Server Database pane click **Change Database**.</span></span>

3.  <span data-ttu-id="86db8-119">Dans l’Assistant Configuration de la base de données serveur de rapports, dans le volet action, sélectionnez **créer une nouvelle base de données serveur de rapports** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="86db8-119">In the Report Server Database Configuration wizard, in the Action pane, select **Create a new report server database** and then click **Next**.</span></span>

4.  <span data-ttu-id="86db8-120">Dans l’Assistant Configuration de la base de données serveur de rapports, dans le volet serveur de base de données, vérifiez que les informations répertoriées dans les zones **nom du serveur**, **type d’authentification**et **nom d’utilisateur** sont correctes.</span><span class="sxs-lookup"><span data-stu-id="86db8-120">In the Report Server Database Configuration wizard, in the Database Server pane, verify that the information listed in the **Server Name**, **Authentication Type**, and **Username** boxes is correct.</span></span> <span data-ttu-id="86db8-121">Cliquez sur **tester la connexion** pour vérifier qu’aucune connexion ne peut être établie avec le serveur de base de données, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="86db8-121">Click **Test Connection** to verify that a connection can be made to the database server and then click **Next**.</span></span>

5.  <span data-ttu-id="86db8-122">Dans l’Assistant Configuration de la base de données du serveur de rapports, dans le volet base de données, acceptez les valeurs par défaut pour **nom de la base de données**, **langue**et **mode serveur du rapport** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="86db8-122">In the Report Server Database Configuration wizard, in the Database pane, accept the default values for **Database Name**, **Language**, and **Report Server Mode** and then click **Next**.</span></span>

6.  <span data-ttu-id="86db8-123">Dans l’Assistant Configuration de la base de données du serveur de rapports, dans le volet informations d’identification, vérifiez que les informations appropriées apparaissent dans la liste déroulante **type d’authentification** et dans les zones **nom d’utilisateur** et **mot de passe** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="86db8-123">In the Report Server Database Configuration wizard, in the Credentials pane, verify that the correct information is listed in the **Authentication Type** dropdown list and the **User name** and **Password** boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="86db8-124">Dans l’Assistant Configuration de la base de données serveur de rapports, dans le volet Résumé, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="86db8-124">In the Report Server Database Configuration wizard, in the Summary pane, click **Next**.</span></span>

8.  <span data-ttu-id="86db8-125">Dans l’Assistant Configuration de la base de données serveur de rapports, dans le volet progression et fin, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="86db8-125">In the Report Server Database Configuration wizard, in the Progress and Finish pane, click **Finish**.</span></span>

<span data-ttu-id="86db8-126">Pour vérifier que les URL du service de création de rapports ont été configurées, cliquez sur **URL du service Web**.</span><span class="sxs-lookup"><span data-stu-id="86db8-126">To verify that the Reporting Service URLs have been configured, click **Web Service URL**.</span></span> <span data-ttu-id="86db8-127">Une ou plusieurs URL sont indiquées sous les **URL du service Web de rapport**de titre Server.</span><span class="sxs-lookup"><span data-stu-id="86db8-127">You should see one or more URLs listed under the heading **Report Server Web Service URLs**.</span></span> <span data-ttu-id="86db8-128">Cliquez sur chacune de ces URL pour vérifier que vous pouvez accéder à la page d’accueil de l’installation locale de SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="86db8-128">Click each of these URLs to verify that you can reach the home page for the local installation of SQL Server Reporting Services.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

