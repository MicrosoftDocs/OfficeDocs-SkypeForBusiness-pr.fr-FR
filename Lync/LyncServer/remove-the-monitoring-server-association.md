---
title: Supprimer l’association au serveur de surveillance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the Monitoring server association
ms:assetid: c45b22ae-fc06-484a-a05b-735bd1bb7448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721877(v=OCS.15)
ms:contentKeyID: 49733810
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5703153bb1034f1318fbe14ca3583ad5744ffdb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="fbde7-102">Supprimer l’association au serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="fbde7-102">Remove the Monitoring server association</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbde7-103">_**Dernière modification de la rubrique:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="fbde7-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="fbde7-104">Pour supprimer le serveur de surveillance, vous devez modifier ou effacer la dépendance sur le pool frontal associé, le serveur frontal, l’unité de branchement Survivable et le serveur de succursales survivant.</span><span class="sxs-lookup"><span data-stu-id="fbde7-104">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="fbde7-105">Vous pouvez modifier les propriétés du pool frontal, du serveur frontal, de l’unité de branchement Survivable et du serveur de succursales survivant pour supprimer la dépendance.</span><span class="sxs-lookup"><span data-stu-id="fbde7-105">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="fbde7-106">Dès lors que vous effacez la dépendance et que vous avez supprimé le serveur dans le générateur de topologie, vous êtes informé que l’objet magasin de base de données associé dans le générateur de topologie sera également supprimé.</span><span class="sxs-lookup"><span data-stu-id="fbde7-106">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="fbde7-107">Pour supprimer l’Association du serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="fbde7-107">To remove the Monitoring Server association</span></span>

1.  <span data-ttu-id="fbde7-108">Ouvrez le serveur frontal Lync Server 2013, ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="fbde7-108">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="fbde7-109">Accédez au nœud Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="fbde7-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="fbde7-110">Dans le générateur de topologie, développez **Pools frontal Enterprise Edition**, **serveurs front end Standard Edition**ou **sites**de succursales en fonction de la définition du serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="fbde7-110">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Monitoring Server is defined.</span></span>

4.  <span data-ttu-id="fbde7-111">Si vous avez un serveur de succursales Survivable associé, développez **sites**de succursales, développez le nom du site de la succursale, puis développez **appareils de branchement survivables**.</span><span class="sxs-lookup"><span data-stu-id="fbde7-111">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fbde7-112">Les <STRONG>appareils de branchement survivables</STRONG> dans l’interface utilisateur s’appliquent à la fois au serveur de succursales survivant et au dispositif de branchement survivant.</span><span class="sxs-lookup"><span data-stu-id="fbde7-112"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="fbde7-113">Cliquez avec le bouton droit sur le pool, le serveur ou l’appareil associé au serveur de surveillance, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="fbde7-113">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="fbde7-114">Dans la boîte de **dialogue Modifier les propriétés**, sous **général**, sous **associations**, décochez la case associer le **serveur de suivi** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fbde7-114">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="fbde7-115">Répétez l’étape précédente pour tout autre serveur ou appareil associé au serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="fbde7-115">Repeat the previous step for any other pool, server or device associated with the Monitoring Server.</span></span>

8.  <span data-ttu-id="fbde7-116">Cliquez avec le bouton droit sur le serveur de surveillance, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="fbde7-116">Right-click the Monitoring Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="fbde7-117">Sur **Supprimer les magasins**dépendants, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fbde7-117">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="fbde7-118">Publiez la topologie, vérifiez l’état de la réplication et exécutez l’Assistant Déploiement de Lync Server selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="fbde7-118">Publish the topology, check replication status, and run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

