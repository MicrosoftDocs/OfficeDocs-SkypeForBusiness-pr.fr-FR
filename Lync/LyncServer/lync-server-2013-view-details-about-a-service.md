---
title: 'Lync Server 2013: afficher les détails d’un service'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View details about a service
ms:assetid: bc8e8202-cd68-47e4-95b2-bb36e51cc124
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182578(v=OCS.15)
ms:contentKeyID: 48185253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65fd84ad7290f3b82130f04d8b81955f6ffb4921
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-details-about-a-service-in-lync-server-2013"></a><span data-ttu-id="94ea5-102">Afficher des détails sur un service dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94ea5-102">View details about a service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94ea5-103">_**Dernière modification de la rubrique:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="94ea5-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="94ea5-104">Vous pouvez utiliser le panneau de configuration de Lync Server pour afficher des détails sur chaque service en cours d’exécution sur un ordinateur spécifique de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="94ea5-104">You can use Lync Server Control Panel to view details about each service that is running on a specific computer in your topology.</span></span> <span data-ttu-id="94ea5-105">Vous pouvez afficher l’état de chaque service et des détails, tels que les bases de données, ports et services dépendants associés.</span><span class="sxs-lookup"><span data-stu-id="94ea5-105">You can view the status of each service and details such as the associated databases, ports, and dependent services.</span></span>

<div>

## <a name="to-view-details-for-a-service"></a><span data-ttu-id="94ea5-106">Pour afficher les détails d’un service</span><span class="sxs-lookup"><span data-stu-id="94ea5-106">To view details for a service</span></span>

1.  <span data-ttu-id="94ea5-107">À partir d’un compte d’utilisateur affecté à un des rôles d’administration prédéfinis pour Lync Server 2013, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="94ea5-107">From a user account that is assigned to any of the predefined administrative roles for Lync Server 2013, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="94ea5-108">Pour plus d’informations sur les rôles d’administration prédéfinis disponibles dans Lync Server 2013, voir [planification du contrôle d’accès basé sur les rôles dans Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="94ea5-108">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="94ea5-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="94ea5-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="94ea5-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="94ea5-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="94ea5-111">Dans la barre de navigation de gauche, cliquez sur **Topology** , puis sur Status ( **statut**).</span><span class="sxs-lookup"><span data-stu-id="94ea5-111">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="94ea5-112">Dans la page **État** , triez ou effectuez une recherche dans la liste, puis cliquez sur l’ordinateur que vous voulez afficher.</span><span class="sxs-lookup"><span data-stu-id="94ea5-112">In the **Status** page, sort or search through the list and then click the computer that you want to view.</span></span>

5.  <span data-ttu-id="94ea5-113">Cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="94ea5-113">Click **Properties**.</span></span>

6.  <span data-ttu-id="94ea5-114">Dans la fenêtre **afficher les détails** de l’ordinateur, triez la liste des services, le cas échéant, puis cliquez sur le service que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="94ea5-114">In the **View Computer Detail** window, sort the list of services, if necessary, and click the service you want to view.</span></span>

7.  <span data-ttu-id="94ea5-115">Effectuez l’une des opérations suivantes selon vos besoins:</span><span class="sxs-lookup"><span data-stu-id="94ea5-115">Do any of the following as needed:</span></span>
    
      - <span data-ttu-id="94ea5-116">Pour afficher le dernier état de ce service, cliquez sur **obtenir l’état du service**.</span><span class="sxs-lookup"><span data-stu-id="94ea5-116">To see the latest status of that specific service, click **Get service status**.</span></span>
    
      - <span data-ttu-id="94ea5-117">Pour afficher les détails de ce service, cliquez sur **Propriétés** , puis sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="94ea5-117">To see the details for that specific service, click **Properties** and then click **Close**.</span></span>
    
      - <span data-ttu-id="94ea5-118">Pour revenir à la liste de tous les ordinateurs de votre topologie, cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="94ea5-118">To return to the list of all computers in your topology, click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="94ea5-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="94ea5-119">See Also</span></span>


[<span data-ttu-id="94ea5-120">Gestion de la topologie Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94ea5-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

