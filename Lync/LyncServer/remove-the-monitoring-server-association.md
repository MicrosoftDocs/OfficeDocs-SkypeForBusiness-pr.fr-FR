---
title: Supprimer l’association au serveur de surveillance
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the Monitoring server association
ms:assetid: c45b22ae-fc06-484a-a05b-735bd1bb7448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721877(v=OCS.15)
ms:contentKeyID: 49733810
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aa78a49686ca555fdbc26d3ffd4953d88d64a95
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="ae3d7-102">Supprimer l’association au serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="ae3d7-102">Remove the Monitoring server association</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae3d7-103">_**Dernière modification de la rubrique :** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="ae3d7-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="ae3d7-104">Pour supprimer le serveur de surveillance, vous devez modifier ou supprimer la dépendance sur le pool frontal associé, le serveur frontal, le Survivable Branch appliance et le serveur Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="ae3d7-104">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="ae3d7-105">Vous modifiez les propriétés du pool frontal, du serveur frontal, du Survivable Branch appliance et du serveur Survivable Branch Server pour supprimer la dépendance.</span><span class="sxs-lookup"><span data-stu-id="ae3d7-105">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="ae3d7-106">Une fois que vous avez effacé la dépendance et supprimé le serveur dans le générateur de topologies, vous êtes informé que l’objet de magasin de bases de données associé dans le générateur de topologies est également supprimé.</span><span class="sxs-lookup"><span data-stu-id="ae3d7-106">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="ae3d7-107">Pour supprimer l’association du serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="ae3d7-107">To remove the Monitoring Server association</span></span>

1.  <span data-ttu-id="ae3d7-108">Ouvrez le serveur frontal Lync Server 2013, puis ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="ae3d7-108">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="ae3d7-109">Accédez au nœud Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="ae3d7-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="ae3d7-110">Dans le générateur de topologies, développez **Pools frontaux Enterprise Edition**, **serveurs frontaux Standard Edition**ou **sites de succursale**, en fonction de l’emplacement où le serveur de surveillance est défini.</span><span class="sxs-lookup"><span data-stu-id="ae3d7-110">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Monitoring Server is defined.</span></span>

4.  <span data-ttu-id="ae3d7-111">Si vous avez un serveur Survivable Branch Server associé, développez **sites de succursale**, développez le nom du site de succursale, puis développez **Survivable Branch Appliances**.</span><span class="sxs-lookup"><span data-stu-id="ae3d7-111">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ae3d7-112"><STRONG>Survivable Branch Appliances</STRONG> dans l’interface utilisateur s’applique aux serveurs Survivable Branch Server et Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="ae3d7-112"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="ae3d7-113">Cliquez avec le bouton droit sur le pool, le serveur ou le périphérique associé au serveur de surveillance, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ae3d7-113">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="ae3d7-114">Dans **Modifier les propriétés**, sous **Général**, sous **Associations**, décochez la case **Associer un serveur de surveillance**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae3d7-114">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="ae3d7-115">Répétez l’étape précédente pour tout autre pool, serveur ou périphérique associé au serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="ae3d7-115">Repeat the previous step for any other pool, server or device associated with the Monitoring Server.</span></span>

8.  <span data-ttu-id="ae3d7-116">Cliquez avec le bouton droit sur le serveur de surveillance, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="ae3d7-116">Right-click the Monitoring Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="ae3d7-117">Dans **Supprimer les magasins dépendants**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae3d7-117">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="ae3d7-118">Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Déploiement de Lync Server selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="ae3d7-118">Publish the topology, check replication status, and run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

