---
title: Supprimer un pool frontal ou un serveur Standard Edition
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69a1c36de9aa3cbd4a46dc0bba4c862734b382ef
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500051"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="ac85b-102">Supprimer un pool frontal ou un serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="ac85b-102">Remove Front End pool or Standard Edition server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac85b-103">_**Dernière modification de la rubrique :** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="ac85b-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="ac85b-104">Cette rubrique vous guide tout au long du processus de suppression d’un pool frontal ou d’un serveur frontal Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ac85b-104">This topic guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="ac85b-105">Lorsque vous supprimez un pool frontal, vous supprimez tous les serveurs frontaux qui appartiennent au pool dans le cadre du processus de suppression du pool.</span><span class="sxs-lookup"><span data-stu-id="ac85b-105">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="ac85b-106">Lorsque vous supprimez un serveur frontal Standard Edition, vous devez supprimer la définition du magasin SQL du générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="ac85b-106">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>

<div>

## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="ac85b-107">Pour supprimer un pool de serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="ac85b-107">To remove a Front End Server pool</span></span>

1.  <span data-ttu-id="ac85b-108">Ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="ac85b-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="ac85b-109">Accédez au nœud Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="ac85b-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="ac85b-110">Développez **Pools frontaux Enterprise Edition**, développez le pool frontal, cliquez avec le bouton droit sur le pool frontal que vous souhaitez supprimer, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="ac85b-110">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="ac85b-111">Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Déploiement de Lync Server selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="ac85b-111">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="ac85b-112">Pour supprimer un serveur frontal Standard Edition</span><span class="sxs-lookup"><span data-stu-id="ac85b-112">To remove a Standard Edition Front End server</span></span>

1.  <span data-ttu-id="ac85b-113">Ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="ac85b-113">Open Topology Builder.</span></span>

2.  <span data-ttu-id="ac85b-114">Accédez au nœud Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="ac85b-114">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="ac85b-115">Développez **serveurs frontaux Standard Edition**, cliquez avec le bouton droit sur le serveur frontal que vous souhaitez supprimer, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="ac85b-115">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="ac85b-116">Développez **magasins SQL**, cliquez avec le bouton droit sur la base de données SQL Server associée au serveur frontal Standard Edition, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="ac85b-116">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ac85b-117">Vous devez supprimer la définition des bases de données SQL Server colocalisées à partir du serveur frontal Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ac85b-117">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="ac85b-118">Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Déploiement de Lync Server selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="ac85b-118">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

