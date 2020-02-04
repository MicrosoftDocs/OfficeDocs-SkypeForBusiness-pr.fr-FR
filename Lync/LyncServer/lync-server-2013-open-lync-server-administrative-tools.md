---
title: 'Lync Server 2013 : ouvrir les outils d’administration de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Open Lync Server administrative tools
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195741(v=OCS.15)
ms:contentKeyID: 48184778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f3c1b2eec210b22bc45a27c9635507c7ad83553
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="open-lync-server-2013-administrative-tools"></a><span data-ttu-id="df800-102">Ouvrez les outils d’administration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df800-102">Open Lync Server 2013 administrative tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df800-103">_**Dernière modification de la rubrique :** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="df800-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="df800-104">Vous pouvez utiliser les procédures décrites dans cette rubrique pour ouvrir les outils d’administration pour déployer, configurer ou dépanner votre topologie Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df800-104">You can use the procedures in this topic to open administrative tools to deploy, configure, or troubleshoot your Lync Server 2013 topology.</span></span>

  - <span data-ttu-id="df800-105">Assistant Déploiement</span><span class="sxs-lookup"><span data-stu-id="df800-105">Deployment Wizard</span></span>

  - <span data-ttu-id="df800-106">Générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="df800-106">Topology Builder</span></span>

  - <span data-ttu-id="df800-107">Panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="df800-107">Lync Server Control Panel</span></span>

  - <span data-ttu-id="df800-108">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="df800-108">Lync Server Management Shell</span></span>

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a><span data-ttu-id="df800-109">Assistant Déploiement</span><span class="sxs-lookup"><span data-stu-id="df800-109">Deployment Wizard</span></span>

<span data-ttu-id="df800-110">Suivez la procédure ci-dessous pour démarrer l’Assistant déploiement en local afin d’ajouter ou de supprimer des fichiers de composants Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df800-110">Use the following procedure to start the Deployment Wizard locally to add or remove Lync Server 2013 component files.</span></span>

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a><span data-ttu-id="df800-111">Pour démarrer l’Assistant Déploiement de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df800-111">To start Lync Server 2013 Deployment Wizard</span></span>

1.  <span data-ttu-id="df800-112">Ouvrez une session sur l’ordinateur sur lequel est installé l’Assistant Déploiement de Lync Server en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="df800-112">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="df800-113">Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Assistant Déploiement de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="df800-113">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a><span data-ttu-id="df800-114">Générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="df800-114">Topology Builder</span></span>

<span data-ttu-id="df800-115">Utilisez la procédure suivante pour ouvrir le générateur de topologie et définir les serveurs que vous voulez déployer dans votre topologie Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df800-115">Use the following procedure to open the Topology Builder to define the servers that you want to deploy in your Lync Server 2013 topology.</span></span>

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a><span data-ttu-id="df800-116">Pour ouvrir le générateur de topologie Lync Server 2013 et concevoir la topologie</span><span class="sxs-lookup"><span data-stu-id="df800-116">To open Lync Server 2013 Topology Builder to design the topology</span></span>

1.  <span data-ttu-id="df800-117">Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="df800-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="df800-118">Vous pouvez définir une topologie à l’aide d’un compte membre du groupe utilisateurs locaux, mais pour lire, publier ou activer une topologie, qui est requise pour installer Lync Server 2013 sur un serveur, vous devez utiliser un compte membre du groupe administrateurs de domaine et du RTCUniv. ersalServerAdmins et qui dispose des autorisations de contrôle total (en lecture, écriture et modification) sur le partage de fichiers que vous allez utiliser pour le stockage des fichiers d’archivage, afin que le générateur de topologie puisse configurer la liste de contrôle d’accès discrétionnaire (DACL) requise. ou un compte disposant de droits d’utilisateur équivalents.</span><span class="sxs-lookup"><span data-stu-id="df800-118">You can define a topology by using an account that is a member of the local Users group, but to read, publish, or enable a topology, which is required to install Lync Server 2013 on a server, you must use an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group, and that has full control permissions (that is, read, write, and modify) on the file share that you are going to use for the archiving file store so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent user rights.</span></span>

    
    </div>

2.  <span data-ttu-id="df800-119">Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="df800-119">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a><span data-ttu-id="df800-120">Panneau de configuration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df800-120">Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="df800-121">Utilisez l’une des procédures suivantes pour ouvrir le panneau de configuration de Lync Server 2013 pour gérer la configuration des serveurs, utilisateurs, clients et appareils de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="df800-121">Use one of the following procedures to open Lync Server 2013 Control Panel to manage the configuration of servers, users, clients, and devices in your environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="df800-122">Vous pouvez utiliser un compte d’utilisateur affecté au rôle CsAdministrator pour effectuer une tâche dans le panneau de configuration de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df800-122">You can use a user account that is assigned to the CsAdministrator role to perform any task in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="df800-123">Vous pouvez utiliser d’autres rôles pour vous connecter à Lync Server 2013 panneau de configuration afin d’effectuer des tâches d’administration spécifiques en fonction de la tâche que vous devez effectuer.</span><span class="sxs-lookup"><span data-stu-id="df800-123">You can use other roles to log on to Lync Server 2013 Control Panel to perform specific administration tasks, dependent on the task you need to perform.</span></span> <span data-ttu-id="df800-124">Par exemple, vous pouvez utiliser CSArchivingAdministrator pour gérer l’archivage dans Lync Server 2013 Control Panel.</span><span class="sxs-lookup"><span data-stu-id="df800-124">For example, you can use CSArchivingAdministrator to administer Archiving in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="df800-125">Pour plus d’informations sur les rôles, voir <A href="lync-server-2013-planning-for-role-based-access-control.md">planifier le contrôle d’accès basé sur les rôles dans Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="df800-125">For details about roles, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="df800-126">Pour plus d’informations sur les rôles que vous pouvez utiliser pour effectuer une tâche spécifique, voir la documentation relative à la tâche.</span><span class="sxs-lookup"><span data-stu-id="df800-126">For details about the roles that you can use to perform a specific task, see the documentation for the task.</span></span>



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a><span data-ttu-id="df800-127">Pour ouvrir le panneau de configuration Lync Server 2013 à partir de n’importe quel ordinateur dans le pare-feu de votre organisation</span><span class="sxs-lookup"><span data-stu-id="df800-127">To open Lync Server 2013 Control Panel from any computer inside your organization’s firewall</span></span>

1.  <span data-ttu-id="df800-128">À partir d’un compte d’utilisateur affecté au rôle CsAdministrator ou à un autre rôle disposant de droits d’utilisateur et d’autorisations appropriés pour la tâche à exécuter, connectez-vous à n’importe quel ordinateur dans votre déploiement interne avec une résolution d’écran minimale de 1024 x 768.</span><span class="sxs-lookup"><span data-stu-id="df800-128">From a user account that is assigned to the CsAdministrator role or other role that has appropriate user rights and permissions for the task to be performed, log on to any computer in your internal deployment with a minimum screen resolution of 1024 x 768.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="df800-129">Si vous avez configuré une adresse URL (Uniform Resource Locator) d’administration, vous pouvez accéder au panneau de configuration de Lync Server 2013 à partir d’un navigateur Internet qui s’exécute sur n’importe quel ordinateur au sein du pare-feu de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="df800-129">If you have configured an administration simple uniform resource locator (URL), you can access Lync Server 2013 Control Panel from an Internet browser that is running on any computer within your organization’s firewall.</span></span> <span data-ttu-id="df800-130">Pour plus d’informations sur la configuration de l’URL simple d’administration, voir <A href="lync-server-2013-planning-for-simple-urls.md">planification d’URL simples dans Lync server 2013</A> dans la documentation de planification et <A href="lync-server-2013-edit-or-configure-simple-urls.md">modifier ou configurer des URL simples dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="df800-130">For details about configuring the administration simple URL, see <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A> in the Planning documentation and <A href="lync-server-2013-edit-or-configure-simple-urls.md">Edit or configure simple URLs in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

2.  <span data-ttu-id="df800-131">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration configurée pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="df800-131">Open a browser window, and then enter the Admin URL configured for your organization.</span></span>

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a><span data-ttu-id="df800-132">Pour ouvrir le panneau de configuration de Lync Server 2013 sur un ordinateur exécutant Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df800-132">To open Lync Server 2013 Control Panel on a computer running Lync Server 2013</span></span>

1.  <span data-ttu-id="df800-133">À partir d’un compte d’utilisateur qui est membre du rôle CsAdministrator ou d’un autre rôle disposant de droits d’utilisateur et d’autorisations appropriés pour la tâche à exécuter, connectez-vous à un ordinateur sur lequel vous avez installé Lync Server 2013 ou, au minimum, Lync Server 2013 administration outils ive.</span><span class="sxs-lookup"><span data-stu-id="df800-133">From a user account that is a member of the CsAdministrator role or other role that has appropriate user rights and permissions for the task to be performed, log on to a computer on which you have installed Lync Server 2013 or, at a minimum, the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="df800-134">Pour configurer les paramètres, l’ordinateur doit avoir une résolution d’écran d’au moins 1024 x 768.</span><span class="sxs-lookup"><span data-stu-id="df800-134">To configure settings, the computer must have a minimum screen resolution of 1024 x 768.</span></span>

2.  <span data-ttu-id="df800-135">Démarrez le panneau de configuration de Lync Server 2013 : cliquez sur **Démarrer**, sur **tous les programmes**, pointez sur **Outils d’administration**, sur **Microsoft Lync Server 2013**, puis cliquez sur **Lync Server 2013 Control Panel**.</span><span class="sxs-lookup"><span data-stu-id="df800-135">Start Lync Server 2013 Control Panel: Click **Start**, click **All Programs**, point to **Administrative Tools**, point to **Microsoft Lync Server 2013**, and then click **Lync Server 2013 Control Panel**.</span></span>

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a><span data-ttu-id="df800-136">Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="df800-136">Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="df800-137">Utilisez la procédure suivante pour ouvrir Lync Server 2013 Management Shell pour administrer des serveurs, des utilisateurs, des clients et des appareils dans votre environnement à l’aide de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="df800-137">Use the following procedure to open Lync Server 2013 Management Shell to administer servers, users, clients, and devices in your environment by using the command line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="df800-138">Vous pouvez utiliser un compte d’utilisateur affecté au rôle CsAdministrator pour effectuer une tâche dans Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="df800-138">You can use a user account that is assigned to the CsAdministrator role to perform any task in Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="df800-139">Vous pouvez vous connecter à l’aide d’autres rôles pour effectuer des tâches d’administration spécifiques, en fonction de la tâche que vous devez effectuer.</span><span class="sxs-lookup"><span data-stu-id="df800-139">You can log on using other roles to perform specific administration tasks, depending on the task you need to perform.</span></span> <span data-ttu-id="df800-140">Par exemple, vous pouvez utiliser CSArchivingAdministrator pour exécuter des cmdlets liées à l’administration de l’archivage.</span><span class="sxs-lookup"><span data-stu-id="df800-140">For example, you can use CSArchivingAdministrator to run cmdlets related to Archiving administration.</span></span> <span data-ttu-id="df800-141">Pour plus d’informations sur les rôles, voir <A href="lync-server-2013-planning-for-role-based-access-control.md">planifier le contrôle d’accès basé sur les rôles dans Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="df800-141">For details about roles, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="df800-142">Pour plus d’informations sur les rôles que vous pouvez utiliser pour exécuter une applet de connexion spécifique, voir la documentation relative à l’applet de connexion.</span><span class="sxs-lookup"><span data-stu-id="df800-142">For details about the roles that you can use to run a specific cmdlet, see the documentation for the cmdlet.</span></span><BR><span data-ttu-id="df800-143">Vous pouvez également exécuter certaines cmdlets en utilisant un compte d’utilisateur dans les groupes RTCUniversalServerAdmins, RTCUniversalUserAdmins ou RTCUniversalReadOnlyAdmins, en fonction de l’applet de la cmdlet.</span><span class="sxs-lookup"><span data-stu-id="df800-143">You can also run certain cmdlets by using a user account in the RTCUniversalServerAdmins, RTCUniversalUserAdmins, or RTCUniversalReadOnlyAdmins groups, depending on the cmdlet.</span></span>



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a><span data-ttu-id="df800-144">Pour ouvrir Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="df800-144">To open the Lync Server 2013 Management Shell</span></span>

  - <span data-ttu-id="df800-145">Si vous ouvrez une fenêtre Windows PowerShell plutôt que Lync Server 2013 Management Shell, par défaut, vous ne pouvez pas exécuter les applets de cmdlet Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df800-145">If you open a Windows PowerShell window rather than the Lync Server 2013 Management Shell, by default you cannot run the Lync Server 2013 cmdlets.</span></span> <span data-ttu-id="df800-146">Pour exécuter les applets de commande Lync Server 2013 à partir de Windows PowerShell, tapez la commande suivante à l’invite de commandes Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="df800-146">To run the Lync Server 2013 cmdlets from within Windows PowerShell, type the following at the Windows PowerShell command prompt:</span></span>
    
    `Import-Module Lync`

  - <span data-ttu-id="df800-147">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="df800-147">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="df800-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="df800-148">See Also</span></span>


[<span data-ttu-id="df800-149">Installation des outils d’administration Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df800-149">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)  


[<span data-ttu-id="df800-150">Outils d’administration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df800-150">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

