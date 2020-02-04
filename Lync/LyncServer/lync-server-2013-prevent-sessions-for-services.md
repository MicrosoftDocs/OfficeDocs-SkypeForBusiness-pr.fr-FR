---
title: 'Lync Server 2013 : empêcher les sessions pour les services'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 977dcc5c-2aac-48ef-86a1-a8d47b4d9e74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182553(v=OCS.15)
ms:contentKeyID: 48184866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc90e58fecf5e386600ca91cf764dbb50f9d76c7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services-in-lync-server-2013"></a><span data-ttu-id="eda5d-102">Empêcher les sessions pour les services dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eda5d-102">Prevent sessions for services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eda5d-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="eda5d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="eda5d-104">Le panneau de configuration de Lync Server vous permet d’empêcher les nouvelles sessions de tous les services Lync Server 2013 en cours d’exécution sur un ordinateur spécifique ou d’empêcher de nouvelles sessions pour un service 2013 serveur Lync spécifique.</span><span class="sxs-lookup"><span data-stu-id="eda5d-104">You can use Lync Server Control Panel to prevent new sessions for all the Lync Server 2013 services running on a specific computer or to prevent new sessions for a specific Lync Server 2013 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="eda5d-105">Pour empêcher de nouvelles sessions pour tous les services Lync Server sur un ordinateur</span><span class="sxs-lookup"><span data-stu-id="eda5d-105">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="eda5d-106">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eda5d-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="eda5d-107">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eda5d-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="eda5d-108">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="eda5d-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="eda5d-109">Dans la barre de navigation de gauche, cliquez sur **Topology** , puis sur **Status (statut**).</span><span class="sxs-lookup"><span data-stu-id="eda5d-109">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="eda5d-110">Dans la page **État** , triez ou effectuez une recherche dans la liste selon vos besoins pour trouver l’ordinateur exécutant les services pour lesquels vous voulez éviter de nouvelles sessions, puis cliquez dessus.</span><span class="sxs-lookup"><span data-stu-id="eda5d-110">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="eda5d-111">Cliquez sur **action**.</span><span class="sxs-lookup"><span data-stu-id="eda5d-111">Click **Action**.</span></span>

6.  <span data-ttu-id="eda5d-112">Cliquez sur **empêcher de nouvelles sessions pour tous les services**.</span><span class="sxs-lookup"><span data-stu-id="eda5d-112">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="eda5d-113">Pour empêcher de nouvelles sessions pour un service spécifique</span><span class="sxs-lookup"><span data-stu-id="eda5d-113">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="eda5d-114">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eda5d-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="eda5d-115">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eda5d-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="eda5d-116">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="eda5d-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="eda5d-117">Dans la barre de navigation de gauche, cliquez sur **Topology** , puis sur **Status (statut**).</span><span class="sxs-lookup"><span data-stu-id="eda5d-117">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="eda5d-118">Dans la page **État** , triez ou effectuez une recherche dans la liste selon vos besoins pour trouver l’ordinateur exécutant le service que vous voulez démarrer ou arrêter, puis cliquez dessus.</span><span class="sxs-lookup"><span data-stu-id="eda5d-118">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="eda5d-119">Cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="eda5d-119">Click **Properties**.</span></span>

6.  <span data-ttu-id="eda5d-120">Triez la liste des services, si nécessaire, puis cliquez sur le service pour lequel vous souhaitez éviter de nouvelles sessions.</span><span class="sxs-lookup"><span data-stu-id="eda5d-120">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="eda5d-121">Cliquez sur **action**.</span><span class="sxs-lookup"><span data-stu-id="eda5d-121">Click **Action**.</span></span>

8.  <span data-ttu-id="eda5d-122">Cliquez sur **empêcher de nouvelles sessions pour le service**.</span><span class="sxs-lookup"><span data-stu-id="eda5d-122">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="eda5d-123">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="eda5d-123">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eda5d-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eda5d-124">See Also</span></span>


[<span data-ttu-id="eda5d-125">Gestion de la topologie Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eda5d-125">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

