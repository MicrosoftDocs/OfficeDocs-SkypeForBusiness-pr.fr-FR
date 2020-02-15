---
title: 'Lync Server 2013 : installation de SQL Server Reporting Services'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48184345
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e1663bad8515082603a411a42de5c98d7f70594
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a><span data-ttu-id="e6ec2-102">Installation de SQL Server Reporting Services dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6ec2-102">Installing SQL Server Reporting Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6ec2-103">_**Dernière modification de la rubrique :** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="e6ec2-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="e6ec2-104">Si vous envisagez d’utiliser les rapports de surveillance Microsoft Lync Server 2013 (pour plus d’informations, consultez la section suivante de cette documentation), vous devez d’abord installer SQL Server Reporting Services ; Reporting Services peut être installé en même temps que Microsoft SQL Server ou à tout moment après l’installation de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e6ec2-104">If you intend to use Microsoft Lync Server 2013 Monitoring Reports (see the next section of this documentation for more information) you must first install SQL Server Reporting Services; Reporting Services can be installed at the same time you install Microsoft SQL Server or any time after SQL Server has been installed.</span></span> <span data-ttu-id="e6ec2-105">Vous pouvez le faire lors de l’installation de Microsoft SQL Server ou à tout moment après l’installation de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e6ec2-105">If you have not installed SQL Server, then follow the instructions provided earlier in this documentation.</span></span> <span data-ttu-id="e6ec2-106">Si vous n’avez pas installé SQL Server, suivez les instructions fournies plus haut dans cette documentation.</span><span class="sxs-lookup"><span data-stu-id="e6ec2-106">When installing SQL Server, make sure that, on the Feature Selection page, you select Reporting Services.</span></span> <span data-ttu-id="e6ec2-107">Lorsque vous installez SQL Server, dans la page Sélection des composants, veillez à sélectionner Reporting Services pour installer SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="e6ec2-107">That will install SQL Server Reporting Services.</span></span>

<span data-ttu-id="e6ec2-108">Si vous avez déjà installé SQL Server, mais que vous n’avez pas installé SQL Server Reporting Services, vous pouvez ajouter ce composant en suivant les instructions ci-après pour SQL Server 2008 R2 ou SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="e6ec2-108">If you have already installed SQL Server but did not install SQL Server Reporting Services you can add that feature by following the appropriate set of instructions for SQL Server 2008 R2 or SQL Server 2012, as appropriate.</span></span>

<span data-ttu-id="e6ec2-109">Pour vérifier que Reporting Services a été correctement installé, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e6ec2-109">To verify that the reporting Services have been successfully installed, complete the following steps:</span></span>

1.  <span data-ttu-id="e6ec2-110">Si vous exécutez Microsoft SQL Server 2008 R2, cliquez successivement sur **Démarrer**, sur **Tous les programmes**, sur **Microsoft SQL Server 2008 R2**, sur **Outils de configuration**, puis sur **Gestionnaire de configuration de Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="e6ec2-110">If you are running Microsoft SQL Server 2008 R2, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>
    
    <span data-ttu-id="e6ec2-111">Si vous exécutez Microsoft SQL Server 2012, cliquez successivement sur **Démarrer**, sur **Tous les programmes**, sur **Microsoft SQL Server 2012**, sur **Outils de configuration**, puis sur **Gestionnaire de configuration de Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="e6ec2-111">If you are running Microsoft SQL Server 2012, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2012**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="e6ec2-p102">Dans la boîte de dialogue **Connexion relative à la configuration de Reporting Services**, vérifiez que le nom de votre serveur apparaît dans la zone **Nom du serveur** et que le nom de l’instance de SQL Server qui stocke vos données de surveillance apparaît dans la zone **Instance du serveur de rapports**. Cliquez sur **Connexion**.</span><span class="sxs-lookup"><span data-stu-id="e6ec2-p102">In the **Reporting Services Configuration Connection** dialog box, verify that the name of your server appears in the **Server Name** box and that the name of the SQL Server instance that stores your monitoring data appears in the **Report Server Instance** box. Click **Connect**.</span></span>

<span data-ttu-id="e6ec2-114">Dans le gestionnaire de configuration de reporting service, le volet État du serveur de rapports doit indiquer que SQL Server Reporting Services a été installé et que Reporting Services est en cours d’exécution : l’état du serveur de rapports doit être indiqué comme étant **démarré** et le bouton **Démarrer** doit être grisé et indisponible.</span><span class="sxs-lookup"><span data-stu-id="e6ec2-114">In the Reporting Service Configuration Manager, the Report Server Status pane should show that SQL Server Reporting Services has been installed and that the Reporting Services are currently running: the Report Server Status should be shown as **Started** and the **Start** button should be grayed-out and unavailable.</span></span> <span data-ttu-id="e6ec2-115">Si Reporting Services n’est pas en cours d’exécution, cliquez sur **Démarrer** pour démarrer le service.</span><span class="sxs-lookup"><span data-stu-id="e6ec2-115">If the Reporting Service is not running, click **Start** in order to start the service.</span></span>

<span data-ttu-id="e6ec2-116">Si aucune base de données n’est répertoriée en regard de l’étiquette Nom de la base de données du serveur de rapports, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e6ec2-116">If no database is listed next to the Report Server Database Name label then do the following:</span></span>

1.  <span data-ttu-id="e6ec2-117">Dans le Gestionnaire de configuration de Reporting Services, cliquez sur **Base de données**.</span><span class="sxs-lookup"><span data-stu-id="e6ec2-117">In the Reporting Services Configuration Manager click **Database**.</span></span>

2.  <span data-ttu-id="e6ec2-118">Dans le volet Base de données du serveur de rapports, cliquez sur **Changer la base de données**.</span><span class="sxs-lookup"><span data-stu-id="e6ec2-118">In the Report Server Database pane click **Change Database**.</span></span>

3.  <span data-ttu-id="e6ec2-119">Dans le volet Action de l’Assistant de configuration de la base de données du serveur de rapports, sélectionnez **Créer une nouvelle base de données de serveur de rapports**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e6ec2-119">In the Report Server Database Configuration wizard, in the Action pane, select **Create a new report server database** and then click **Next**.</span></span>

4.  <span data-ttu-id="e6ec2-p104">Dans le volet Serveur de bases de données de l’Assistant de configuration de la base de données du serveur de rapports, vérifiez que les informations contenues dans les zones **Nom du serveur**, **Type d’authentification** et **Nom d’utilisateur** sont correctes. Cliquez sur **Tester la connexion** pour vérifier qu’une connexion peut être établie au serveur de base de données, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e6ec2-p104">In the Report Server Database Configuration wizard, in the Database Server pane, verify that the information listed in the **Server Name**, **Authentication Type**, and **Username** boxes is correct. Click **Test Connection** to verify that a connection can be made to the database server and then click **Next**.</span></span>

5.  <span data-ttu-id="e6ec2-122">Dans le volet Base de données de l’Assistant de configuration de la base de données du serveur de rapports, acceptez les valeurs par défaut pour **Nom de la base de données**, **Langue** et **Mode du serveur de rapports**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e6ec2-122">In the Report Server Database Configuration wizard, in the Database pane, accept the default values for **Database Name**, **Language**, and **Report Server Mode** and then click **Next**.</span></span>

6.  <span data-ttu-id="e6ec2-123">Dans le volet Informations d’identification de l’Assistant de configuration de la base de données du serveur de rapports, vérifiez que les informations contenues dans la liste déroulante **Nom du serveur** et dans les zones **Nom d’utilisateur** et **Mot de passe** sont correctes, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e6ec2-123">In the Report Server Database Configuration wizard, in the Credentials pane, verify that the correct information is listed in the **Authentication Type** dropdown list and the **User name** and **Password** boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="e6ec2-124">Dans le volet Résumé de l’Assistant de configuration de la base de données du serveur de rapports, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e6ec2-124">In the Report Server Database Configuration wizard, in the Summary pane, click **Next**.</span></span>

8.  <span data-ttu-id="e6ec2-125">Dans le volet État d’avancement et fin de l’Assistant de configuration de la base de données du serveur de rapports, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="e6ec2-125">In the Report Server Database Configuration wizard, in the Progress and Finish pane, click **Finish**.</span></span>

<span data-ttu-id="e6ec2-p105">Pour vérifier que les URL de Reporting Services ont bien été configurées, cliquez sur **URL du service web**. Vous devriez voir une ou plusieurs URL sous la rubrique **URL du service web Report Server**. Cliquez sur chacune de ces URL pour vérifier que vous pouvez accéder à la page d’accueil de l’installation locale de SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="e6ec2-p105">To verify that the Reporting Service URLs have been configured, click **Web Service URL**. You should see one or more URLs listed under the heading **Report Server Web Service URLs**. Click each of these URLs to verify that you can reach the home page for the local installation of SQL Server Reporting Services.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

