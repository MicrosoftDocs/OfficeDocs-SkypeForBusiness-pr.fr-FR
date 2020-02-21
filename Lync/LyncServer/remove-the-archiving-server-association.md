---
title: Supprimer l’Association du serveur d’archivage
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93c53ef1e70b174681149593237db3f9d0268209
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="7fb3d-102">Supprimer l’Association du serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="7fb3d-102">Remove the Archiving server association</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fb3d-103">_**Dernière modification de la rubrique :** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="7fb3d-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="7fb3d-104">Pour supprimer un serveur d’archivage, vous devez modifier ou supprimer la dépendance sur le pool frontal associé, le serveur frontal, le Survivable Branch appliance et le serveur Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="7fb3d-104">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="7fb3d-105">Vous modifiez les propriétés du pool frontal, du serveur frontal, du Survivable Branch appliance et du serveur Survivable Branch Server pour supprimer la dépendance.</span><span class="sxs-lookup"><span data-stu-id="7fb3d-105">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="7fb3d-106">Une fois que vous avez effacé la dépendance et supprimé le serveur dans le générateur de topologies, vous êtes informé que l’objet de magasin de bases de données associé dans le générateur de topologies est également supprimé.</span><span class="sxs-lookup"><span data-stu-id="7fb3d-106">After you clear the dependency and you delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="7fb3d-107">Pour supprimer l’association au serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="7fb3d-107">To remove the Archiving Server association</span></span>

1.  <span data-ttu-id="7fb3d-108">Ouvrez le serveur frontal Lync Server 2013, puis ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="7fb3d-108">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="7fb3d-109">Accédez au nœud Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7fb3d-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="7fb3d-110">Dans le générateur de topologies, développez **Pools frontaux Enterprise Edition**, **serveurs frontaux Standard Edition**ou **sites de succursale**, en fonction de l’emplacement où le serveur d’archivage est défini.</span><span class="sxs-lookup"><span data-stu-id="7fb3d-110">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Archiving Server is defined.</span></span>

4.  <span data-ttu-id="7fb3d-111">Si vous avez un serveur Survivable Branch Server associé, développez **sites de succursale**, développez le nom du site de succursale, puis développez **Survivable Branch Appliances**.</span><span class="sxs-lookup"><span data-stu-id="7fb3d-111">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7fb3d-112"><STRONG>Survivable Branch Appliances</STRONG> dans l’interface utilisateur s’applique aux serveurs Survivable Branch Server et Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="7fb3d-112"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="7fb3d-113">Cliquez avec le bouton droit sur le pool, le serveur ou le périphérique associé au serveur d’archivage, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="7fb3d-113">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="7fb3d-114">Dans **Modifier les propriétés**, sous **Général**, sous **Associations**, désactivez la case à cocher **Associer un serveur d’archivage**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7fb3d-114">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="7fb3d-115">Répétez l’étape précédente pour tout autre pool, serveur ou périphérique associé au serveur d’archivage que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="7fb3d-115">Repeat the previous step for any other pool, server or device associated with the Archiving Server that you want to remove.</span></span>

8.  <span data-ttu-id="7fb3d-116">Cliquez avec le bouton droit sur le serveur d’archivage, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="7fb3d-116">Right-click the Archiving Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="7fb3d-117">Dans **Supprimer les magasins dépendants**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7fb3d-117">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="7fb3d-118">Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Déploiement de Lync Server selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="7fb3d-118">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

