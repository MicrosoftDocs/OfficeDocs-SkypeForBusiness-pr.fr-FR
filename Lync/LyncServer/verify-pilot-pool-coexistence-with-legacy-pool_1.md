---
title: Vérification de la coexistence du pool pilote avec le pool hérité
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48184209
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a7ddba431e1c921df9b3880ee9af73f71584b5f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515921"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="bb401-102">Vérification de la coexistence du pool pilote avec le pool hérité</span><span class="sxs-lookup"><span data-stu-id="bb401-102">Verify pilot pool coexistence with legacy pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb401-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="bb401-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a><span data-ttu-id="bb401-104">Vérifier le pool dans l’outil d’administration d’Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="bb401-104">Verify the Pool in Office Communications Server 2007 R2 Administrative Tool</span></span>

1.  <span data-ttu-id="bb401-105">Ouvrez l’outil d’administration Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bb401-105">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="bb401-106">Développez le nœud **Forêt**, développez le nœud **serveur Standard Edition Servers** ou **pools d’entreprise**, puis développez le nom du pool ou du serveur.</span><span class="sxs-lookup"><span data-stu-id="bb401-106">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="bb401-107">Assurez-vous que les services Office Communications Server 2007 R2 sont en cours d’exécution sur le pool.</span><span class="sxs-lookup"><span data-stu-id="bb401-107">Ensure that the Office Communications Server 2007 R2 services are running on the pool.</span></span>
    
    <span data-ttu-id="bb401-108">![Office Communications Server 2007 R2, console d’administration](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2, console d’administration")</span><span class="sxs-lookup"><span data-stu-id="bb401-108">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a><span data-ttu-id="bb401-109">Vérifier le pool pilote dans le panneau de configuration Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb401-109">Verify the Pilot Pool in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="bb401-110">À partir d’un compte d’utilisateur membre du rôle CsAdministrator, ouvrez une session sur le serveur frontal Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bb401-110">From a user account that is a member of the CsAdministrator role, log on to the Lync Server 2013 Front End server.</span></span>

2.  <span data-ttu-id="bb401-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bb401-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bb401-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bb401-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bb401-113">Cliquez sur **Topologie**.</span><span class="sxs-lookup"><span data-stu-id="bb401-113">Click **Topology**.</span></span>

4.  <span data-ttu-id="bb401-114">Vérifiez que les serveurs que vous avez déployés sont présents dans votre pool pilote.</span><span class="sxs-lookup"><span data-stu-id="bb401-114">Verify that the servers you deployed are present in your pilot pool.</span></span>
    
    <span data-ttu-id="bb401-115">![Page topologie du panneau de configuration Lync Server](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Page topologie du panneau de configuration Lync Server")</span><span class="sxs-lookup"><span data-stu-id="bb401-115">![Lync Server Control Panel Topology page](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Lync Server Control Panel Topology page")</span></span>  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a><span data-ttu-id="bb401-116">Vérifier que les services Lync Server 2013 ont démarré</span><span class="sxs-lookup"><span data-stu-id="bb401-116">Verify Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="bb401-117">Sur le serveur frontal Lync Server 2013, ouvrez l’applet **services** à partir du groupe **Outils d’administration** .</span><span class="sxs-lookup"><span data-stu-id="bb401-117">On the Lync Server 2013 Front End Server, open the **Services** applet from the **Administrative Tools** group.</span></span>

2.  <span data-ttu-id="bb401-118">Vérifiez que les services répertoriés correspondent à la liste présentée dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="bb401-118">Verify that the services listed match the list in the following figure.</span></span>
    
    <span data-ttu-id="bb401-119">![Page services affichant le démarrage de Lync services](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Page services affichant le démarrage de Lync services")</span><span class="sxs-lookup"><span data-stu-id="bb401-119">![Services page showing Lync services started](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Services page showing Lync services started")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

