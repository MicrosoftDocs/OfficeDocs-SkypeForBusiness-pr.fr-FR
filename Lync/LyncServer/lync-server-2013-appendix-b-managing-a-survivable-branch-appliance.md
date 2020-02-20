---
title: 'Lync Server 2013 : annexe B : gestion d’un Survivable Branch Appliance'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df6e2dc473da81177dacb8d53ee673c9a5457c98
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a><span data-ttu-id="0c7d8-102">Annexe B : gestion d’un Survivable Branch Appliance dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c7d8-102">Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c7d8-103">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="0c7d8-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="0c7d8-104">Cette rubrique décrit les procédures de gestion d’un Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-104">This topic describes the procedures for managing a Survivable Branch Appliance.</span></span> <span data-ttu-id="0c7d8-105">En particulier, le remplacement et le changement de nom d’un Survivable Branch appliance, ainsi que la modification du pool frontal Lync Server 2013 auquel le Survivable Branch Appliance est associé.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-105">Specifically, how to replace and rename a Survivable Branch Appliance, and how to change the Lync Server 2013 Front End pool that the Survivable Branch Appliance is associated with.</span></span>

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a><span data-ttu-id="0c7d8-106">Pour remplacer un Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="0c7d8-106">To Replace a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="0c7d8-107">Arrêtez tous les services Lync Server 2013 sur le Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-107">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="0c7d8-108">(Voir la documentation du fournisseur du Survivable Branch Appliance.)</span><span class="sxs-lookup"><span data-stu-id="0c7d8-108">(See the Survivable Branch Appliance vendor documentation.)</span></span>

2.  <span data-ttu-id="0c7d8-109">Recommandation Supprimez le Survivable Branch Appliance du domaine.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-109">(Recommended) Remove the Survivable Branch Appliance from the domain.</span></span>

3.  <span data-ttu-id="0c7d8-110">Supprimez l’objet d’ordinateur Survivable Branch Appliance dans les services de domaine Active Directory, en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="0c7d8-110">Delete the Survivable Branch Appliance computer object in Active Directory Domain Services, by following these steps:</span></span>
    
      - <span data-ttu-id="0c7d8-111">Ouvrez une session sur un serveur membre, en tant que membre du groupe Administrateurs d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-111">Log on to a member server as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="0c7d8-112">Cliquez sur **Démarrer**, sur **Outils d'administration**, puis sur **Utilisateurs et ordinateurs Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-112">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="0c7d8-113">Cliquez avec le bouton droit sur l’objet Survivable Branch appliance, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-113">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

4.  <span data-ttu-id="0c7d8-114">Ajoutez à nouveau l’objet ordinateur Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-114">Add the Survivable Branch Appliance computer object again.</span></span> <span data-ttu-id="0c7d8-115">(Voir [Ajouter un Survivable Branch appliance à Active Directory dans Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)</span><span class="sxs-lookup"><span data-stu-id="0c7d8-115">(See [Add a Survivable Branch Appliance to Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)</span></span>

5.  <span data-ttu-id="0c7d8-116">Attendez que la réplication Active Directory ait lieu.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-116">Wait for Active Directory replication to take place.</span></span>

6.  <span data-ttu-id="0c7d8-117">Ouvrez Lync Server Management Shell et tapez **Enable-CSTopology**.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-117">Open the Lync Server Management Shell, and type **Enable-CSTopology**.</span></span>

7.  <span data-ttu-id="0c7d8-118">Connectez le nouveau Survivable Branch Appliance au réseau, puis suivez les étapes décrites dans [Deploying a Survivable Branch Appliance or Server with Lync server 2013-central site Tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) et [Deploy a Survivable Branch Appliance or Server with Lync Server 2013-Branch site Task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span><span class="sxs-lookup"><span data-stu-id="0c7d8-118">Connect the new Survivable Branch Appliance to the network, and follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a><span data-ttu-id="0c7d8-119">Pour renommer un Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="0c7d8-119">To Rename a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="0c7d8-120">Déplacez les utilisateurs vers le site central.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-120">Move users to the central site.</span></span> <span data-ttu-id="0c7d8-121">Pour plus d’informations, consultez la rubrique [déplacer des utilisateurs vers un autre pool dans Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="0c7d8-121">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="0c7d8-122">Arrêtez tous les services Lync Server 2013 sur le Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-122">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="0c7d8-123">(Voir la documentation du fournisseur du Survivable Branch Appliance.)</span><span class="sxs-lookup"><span data-stu-id="0c7d8-123">(See the Survivable Branch Appliance vendor documentation.)</span></span>

3.  <span data-ttu-id="0c7d8-124">Supprimez le Survivable Branch appliance de la topologie, en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="0c7d8-124">Remove the Survivable Branch Appliance from the topology, by following these steps:</span></span>
    
      - <span data-ttu-id="0c7d8-125">Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Microsoft Lync Server**, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-125">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="0c7d8-126">Dans l’arborescence de la console, développez **sites de succursale**, cliquez sur le Survivable Branch appliance, puis cliquez sur **supprimer** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-126">In the console tree, expand **Branch Sites**, click the Survivable Branch Appliance, and then click **Delete** on the Action pane.</span></span>

4.  <span data-ttu-id="0c7d8-127">Supprimez le Survivable Branch Appliance du domaine.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-127">Remove the Survivable Branch Appliance from the domain.</span></span>

5.  <span data-ttu-id="0c7d8-128">Supprimez l’objet d’ordinateur Survivable Branch Appliance dans Active Directory en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="0c7d8-128">Delete the Survivable Branch Appliance computer object in Active Directory, by following these steps:</span></span>
    
      - <span data-ttu-id="0c7d8-129">Ouvrez une session sur un contrôleur de domaine, en tant que membre du groupe Administrateurs d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-129">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="0c7d8-130">Cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **Utilisateurs et ordinateurs Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-130">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="0c7d8-131">Cliquez avec le bouton droit sur l’objet Survivable Branch appliance, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-131">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

6.  <span data-ttu-id="0c7d8-132">Restaurez le Survivable Branch Appliance aux paramètres d’usine.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-132">Restore the Survivable Branch Appliance to factory defaults.</span></span> <span data-ttu-id="0c7d8-133">(Voir la documentation du fournisseur du Survivable Branch Appliance.)</span><span class="sxs-lookup"><span data-stu-id="0c7d8-133">(See the Survivable Branch Appliance vendor documentation.)</span></span>

7.  <span data-ttu-id="0c7d8-134">Suivez les étapes décrites dans [Deploying a Survivable Branch Appliance or Server with Lync server 2013-central site Tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) et [Deploy a Survivable Branch Appliance or Server with Lync Server 2013-Branch site Task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span><span class="sxs-lookup"><span data-stu-id="0c7d8-134">Follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

8.  <span data-ttu-id="0c7d8-135">Déplacez les utilisateurs vers le Survivable Branch Appliance renommé.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-135">Move users to the renamed Survivable Branch Appliance.</span></span> <span data-ttu-id="0c7d8-136">Pour plus d’informations, consultez la rubrique [déplacer des utilisateurs vers un autre pool dans Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="0c7d8-136">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a><span data-ttu-id="0c7d8-137">Pour changer le pool de serveurs frontaux Lync Server auquel le Survivable Branch Appliance est associé</span><span class="sxs-lookup"><span data-stu-id="0c7d8-137">To Change the Lync Server Front End Pool that the Survivable Branch Appliance Is Associated With</span></span>

1.  <span data-ttu-id="0c7d8-138">Déplacez les utilisateurs du Survivable Branch Appliance vers le pool frontal Lync Server au niveau du site central.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-138">Move users from the Survivable Branch Appliance to the Lync Server Front End pool at the central site.</span></span> <span data-ttu-id="0c7d8-139">Pour plus d’informations, consultez la rubrique [déplacer des utilisateurs vers un autre pool dans Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="0c7d8-139">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="0c7d8-140">Arrêtez tous les services Lync Server sur le Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-140">Stop all Lync Server services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="0c7d8-141">(Consultez la documentation du fournisseur Survivable Branch Appliance Vendor).</span><span class="sxs-lookup"><span data-stu-id="0c7d8-141">(See the Survivable Branch Appliance vendor documentation).</span></span>

3.  <span data-ttu-id="0c7d8-142">Mettez à jour le pool frontal Lync Server auquel le Survivable Branch Appliance est associé, en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="0c7d8-142">Update the Lync Server Front End pool that the Survivable Branch Appliance is associated with, by following these steps:</span></span>
    
      - <span data-ttu-id="0c7d8-143">Cliquez sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server**, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-143">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="0c7d8-144">Développez **Sites de succursales**.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-144">Expand **Branch Sites**.</span></span>
    
      - <span data-ttu-id="0c7d8-145">Cliquez avec le bouton droit sur l’objet Survivable Branch appliance à modifier, puis cliquez sur **modifier les propriétés** .</span><span class="sxs-lookup"><span data-stu-id="0c7d8-145">Right-click the Survivable Branch Appliance object to modify, and click **Edit Properties**</span></span>
    
      - <span data-ttu-id="0c7d8-146">Sous résistance, sélectionnez le nouveau pool frontal auquel le Survivable Branch appliance doit être associé, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-146">Under Resiliency, select the new Front End pool the Survivable Branch Appliance is to be associated to, and then click **Next**.</span></span>
    
      - <span data-ttu-id="0c7d8-147">Dans l’arborescence de la console, cliquez avec le bouton droit sur le nouveau Survivable Branch appliance, cliquez sur **topologie**, puis cliquez sur **publier**.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-147">In the console tree, right-click the new Survivable Branch Appliance, click **Topology**, and then click **Publish**.</span></span>

4.  <span data-ttu-id="0c7d8-148">Redémarrez tous les services Lync Server sur le Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-148">Restart all Lync Server Services on the Survivable Branch Appliance.</span></span>

5.  <span data-ttu-id="0c7d8-149">Testez le Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-149">Test the Survivable Branch Appliance.</span></span> <span data-ttu-id="0c7d8-150">Pour plus d’informations, consultez [la rubrique utilisateurs familiaux sur un Survivable Branch Appliance ou un serveur Survivable Branch Server dans Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="0c7d8-150">For details, see [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

6.  <span data-ttu-id="0c7d8-151">Déplacez les utilisateurs du pool frontal Lync Server du site central vers le Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="0c7d8-151">Move users from the Lync Server Front End pool at the central site to the Survivable Branch Appliance.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

