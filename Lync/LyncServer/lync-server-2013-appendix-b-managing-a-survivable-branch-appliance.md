---
title: 'Lync Server 2013 : Annexe B : Gestion d’un Survivable Branch Appliance'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e267f81327e9d1f49b81ab0d999c37c02da55b31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a><span data-ttu-id="b6065-102">Annexe B : Gestion d’un Survivable Branch Appliance dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6065-102">Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6065-103">_**Dernière modification de la rubrique:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="b6065-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="b6065-104">Cette rubrique décrit les procédures de gestion d’une unité de branchement survivant.</span><span class="sxs-lookup"><span data-stu-id="b6065-104">This topic describes the procedures for managing a Survivable Branch Appliance.</span></span> <span data-ttu-id="b6065-105">Pour plus d’informations, sur le remplacement d’une unité de branchement Survivable et sur la modification de la liste frontale de Lync Server 2013 à laquelle l’unité de branchement Survivable est associée.</span><span class="sxs-lookup"><span data-stu-id="b6065-105">Specifically, how to replace and rename a Survivable Branch Appliance, and how to change the Lync Server 2013 Front End pool that the Survivable Branch Appliance is associated with.</span></span>

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a><span data-ttu-id="b6065-106">Pour remplacer une unité de branchement survivant</span><span class="sxs-lookup"><span data-stu-id="b6065-106">To Replace a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="b6065-107">Arrêtez tous les services Lync Server 2013 sur l’appareil de branche Survivable.</span><span class="sxs-lookup"><span data-stu-id="b6065-107">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="b6065-108">(Voir la documentation du fabricant de l’appareil de branchement Survivable.)</span><span class="sxs-lookup"><span data-stu-id="b6065-108">(See the Survivable Branch Appliance vendor documentation.)</span></span>

2.  <span data-ttu-id="b6065-109">Recommande Supprimez l’unité de branchement Survivable du domaine.</span><span class="sxs-lookup"><span data-stu-id="b6065-109">(Recommended) Remove the Survivable Branch Appliance from the domain.</span></span>

3.  <span data-ttu-id="b6065-110">Supprimez l’objet de l’unité de l’appareil de branchement Survivable dans les services de domaine Active Directory (AD FS) en procédant comme suit:</span><span class="sxs-lookup"><span data-stu-id="b6065-110">Delete the Survivable Branch Appliance computer object in Active Directory Domain Services, by following these steps:</span></span>
    
      - <span data-ttu-id="b6065-111">Connectez-vous à un serveur membre en tant que membre du groupe administrateurs d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="b6065-111">Log on to a member server as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="b6065-112">Cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **utilisateurs et ordinateurs Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="b6065-112">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="b6065-113">Cliquez avec le bouton droit sur l’objet de l’appareil de branchement survivant, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b6065-113">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

4.  <span data-ttu-id="b6065-114">Ajoutez à nouveau l’objet de l’appareil de branchement Survivable.</span><span class="sxs-lookup"><span data-stu-id="b6065-114">Add the Survivable Branch Appliance computer object again.</span></span> <span data-ttu-id="b6065-115">(Voir [Ajouter une unité de branchement survivant à Active Directory dans Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)</span><span class="sxs-lookup"><span data-stu-id="b6065-115">(See [Add a Survivable Branch Appliance to Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)</span></span>

5.  <span data-ttu-id="b6065-116">Attendez que la réplication Active Directory intervient.</span><span class="sxs-lookup"><span data-stu-id="b6065-116">Wait for Active Directory replication to take place.</span></span>

6.  <span data-ttu-id="b6065-117">Ouvrez Lync Server Management Shell, puis tapez **Enable-CSTopology**.</span><span class="sxs-lookup"><span data-stu-id="b6065-117">Open the Lync Server Management Shell, and type **Enable-CSTopology**.</span></span>

7.  <span data-ttu-id="b6065-118">Connectez la nouvelle appliance de succursale survivant au réseau, puis suivez les étapes décrites dans l’article [déploiement d’une unité ou d’un serveur de succursales survivant avec Lync server 2013-tâches de site central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) et [déploiement d’une unité ou d’un serveur Survivables avec Lync Server 2013- tâche de succursale](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span><span class="sxs-lookup"><span data-stu-id="b6065-118">Connect the new Survivable Branch Appliance to the network, and follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a><span data-ttu-id="b6065-119">Pour renommer une unité de branchement survivant</span><span class="sxs-lookup"><span data-stu-id="b6065-119">To Rename a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="b6065-120">Déplacer des utilisateurs vers le site central.</span><span class="sxs-lookup"><span data-stu-id="b6065-120">Move users to the central site.</span></span> <span data-ttu-id="b6065-121">Pour plus d’informations, voir [déplacer des utilisateurs vers un autre pool dans Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="b6065-121">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="b6065-122">Arrêtez tous les services Lync Server 2013 sur l’appareil de branche Survivable.</span><span class="sxs-lookup"><span data-stu-id="b6065-122">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="b6065-123">(Voir la documentation du fabricant de l’appareil de branchement Survivable.)</span><span class="sxs-lookup"><span data-stu-id="b6065-123">(See the Survivable Branch Appliance vendor documentation.)</span></span>

3.  <span data-ttu-id="b6065-124">Supprimez l’appareil de branchement survivant de la topologie en procédant comme suit:</span><span class="sxs-lookup"><span data-stu-id="b6065-124">Remove the Survivable Branch Appliance from the topology, by following these steps:</span></span>
    
      - <span data-ttu-id="b6065-125">Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server**, puis sur **Générateur de topologie de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b6065-125">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="b6065-126">Dans l’arborescence de la console, développez **sites**de succursales, cliquez sur l’unité de branchement Survivable, puis cliquez sur **supprimer** dans le volet action.</span><span class="sxs-lookup"><span data-stu-id="b6065-126">In the console tree, expand **Branch Sites**, click the Survivable Branch Appliance, and then click **Delete** on the Action pane.</span></span>

4.  <span data-ttu-id="b6065-127">Supprimez l’unité de branchement Survivable du domaine.</span><span class="sxs-lookup"><span data-stu-id="b6065-127">Remove the Survivable Branch Appliance from the domain.</span></span>

5.  <span data-ttu-id="b6065-128">Supprimez l’objet de l’unité de branchement Survivable dans Active Directory en procédant comme suit:</span><span class="sxs-lookup"><span data-stu-id="b6065-128">Delete the Survivable Branch Appliance computer object in Active Directory, by following these steps:</span></span>
    
      - <span data-ttu-id="b6065-129">Ouvrez une session sur un contrôleur de domaine en tant que membre du groupe administrateurs d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="b6065-129">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="b6065-130">Cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **utilisateurs et ordinateurs Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="b6065-130">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="b6065-131">Cliquez avec le bouton droit sur l’objet de l’appareil de branchement survivant, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b6065-131">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

6.  <span data-ttu-id="b6065-132">Restaurez les commutateurs par défaut de l’appareil de branchement survivant.</span><span class="sxs-lookup"><span data-stu-id="b6065-132">Restore the Survivable Branch Appliance to factory defaults.</span></span> <span data-ttu-id="b6065-133">(Voir la documentation du fabricant de l’appareil de branchement Survivable.)</span><span class="sxs-lookup"><span data-stu-id="b6065-133">(See the Survivable Branch Appliance vendor documentation.)</span></span>

7.  <span data-ttu-id="b6065-134">Suivez les étapes décrites dans l’article [déploiement d’une unité ou d’un serveur de succursales survivant avec Lync server 2013-tâches de site central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) et [déploiement d’une unité ou d’un serveur de succursales survivant avec Lync Server 2013-Task site](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span><span class="sxs-lookup"><span data-stu-id="b6065-134">Follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

8.  <span data-ttu-id="b6065-135">Déplacez les utilisateurs vers l’appareil de succursales survivant renommé.</span><span class="sxs-lookup"><span data-stu-id="b6065-135">Move users to the renamed Survivable Branch Appliance.</span></span> <span data-ttu-id="b6065-136">Pour plus d’informations, voir [déplacer des utilisateurs vers un autre pool dans Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="b6065-136">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a><span data-ttu-id="b6065-137">Pour modifier le pool frontal de Lync Server auquel est associé l’unité de branchement Survivable</span><span class="sxs-lookup"><span data-stu-id="b6065-137">To Change the Lync Server Front End Pool that the Survivable Branch Appliance Is Associated With</span></span>

1.  <span data-ttu-id="b6065-138">Déplacez les utilisateurs de l’unité de branchement Survivable vers le pool frontal de Lync Server sur le site central.</span><span class="sxs-lookup"><span data-stu-id="b6065-138">Move users from the Survivable Branch Appliance to the Lync Server Front End pool at the central site.</span></span> <span data-ttu-id="b6065-139">Pour plus d’informations, voir [déplacer des utilisateurs vers un autre pool dans Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="b6065-139">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="b6065-140">Arrêtez tous les services Lync Server sur l’unité de branchement Survivable.</span><span class="sxs-lookup"><span data-stu-id="b6065-140">Stop all Lync Server services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="b6065-141">(Pour plus d’informations, consultez la documentation du fabricant de l’appareil pour succursales survivant).</span><span class="sxs-lookup"><span data-stu-id="b6065-141">(See the Survivable Branch Appliance vendor documentation).</span></span>

3.  <span data-ttu-id="b6065-142">Mettez à jour le pool frontal du serveur Lync pour lequel est associé l’unité de branchement survivant, en procédant comme suit:</span><span class="sxs-lookup"><span data-stu-id="b6065-142">Update the Lync Server Front End pool that the Survivable Branch Appliance is associated with, by following these steps:</span></span>
    
      - <span data-ttu-id="b6065-143">Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server**, puis sur **Générateur de topologie de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b6065-143">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="b6065-144">Développez **sites**de succursales.</span><span class="sxs-lookup"><span data-stu-id="b6065-144">Expand **Branch Sites**.</span></span>
    
      - <span data-ttu-id="b6065-145">Cliquez avec le bouton droit sur l’objet de l’appareil de branchement survivant à modifier, puis cliquez sur **modifier les propriétés** .</span><span class="sxs-lookup"><span data-stu-id="b6065-145">Right-click the Survivable Branch Appliance object to modify, and click **Edit Properties**</span></span>
    
      - <span data-ttu-id="b6065-146">Sous résilience, sélectionnez le nouveau pool frontal pour lequel vous souhaitez associer l’unité de branchement survivant, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="b6065-146">Under Resiliency, select the new Front End pool the Survivable Branch Appliance is to be associated to, and then click **Next**.</span></span>
    
      - <span data-ttu-id="b6065-147">Dans l’arborescence de la console, cliquez avec le bouton droit sur la nouvelle branche Survivable, cliquez sur **Topology**, puis sur **publier**.</span><span class="sxs-lookup"><span data-stu-id="b6065-147">In the console tree, right-click the new Survivable Branch Appliance, click **Topology**, and then click **Publish**.</span></span>

4.  <span data-ttu-id="b6065-148">Redémarrez tous les services Lync Server sur l’unité de branchement Survivable.</span><span class="sxs-lookup"><span data-stu-id="b6065-148">Restart all Lync Server Services on the Survivable Branch Appliance.</span></span>

5.  <span data-ttu-id="b6065-149">Testez l’appareil de branchement Survivable.</span><span class="sxs-lookup"><span data-stu-id="b6065-149">Test the Survivable Branch Appliance.</span></span> <span data-ttu-id="b6065-150">Pour plus d’informations, reportez-vous à [la section utilisateurs domestiques d’une unité ou d’un serveur de succursales survivables dans Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="b6065-150">For details, see [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

6.  <span data-ttu-id="b6065-151">Déplacez les utilisateurs du pool frontal de Lync Server vers le site central vers l’unité de branchement Survivable.</span><span class="sxs-lookup"><span data-stu-id="b6065-151">Move users from the Lync Server Front End pool at the central site to the Survivable Branch Appliance.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

