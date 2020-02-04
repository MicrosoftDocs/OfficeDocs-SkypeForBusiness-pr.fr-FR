---
title: 'Lync Server 2013 : Démarrez ou arrêtez Lync Server services'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start or stop Lync Server 2013 services
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520958(v=OCS.15)
ms:contentKeyID: 48183554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a986f0bef8c41cf5113e99504369974562e294a2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-or-stop-lync-server-2013-services"></a><span data-ttu-id="e5058-102">Démarrer ou arrêter les services Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5058-102">Start or stop Lync Server 2013 services</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5058-103">_**Dernière modification de la rubrique :** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="e5058-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="e5058-104">Vous pouvez utiliser le panneau de configuration de Lync Server pour démarrer ou arrêter l’exécution de tous les services Lync Server 2013 sur un ordinateur spécifique ou pour démarrer ou arrêter un service spécifique.</span><span class="sxs-lookup"><span data-stu-id="e5058-104">You can use Lync Server Control Panel to start or stop all the Lync Server 2013 services running on a specific computer or to start or stop a specific service.</span></span>

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a><span data-ttu-id="e5058-105">Pour démarrer ou arrêter tous les services Lync Server sur un ordinateur</span><span class="sxs-lookup"><span data-stu-id="e5058-105">To start or stop all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="e5058-106">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5058-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span> <span data-ttu-id="e5058-107">Vous pouvez déterminer si vous avez reçu le rôle CsServerAdministrator ou CsAdministrator RBAC en exécutant une commande semblable à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="e5058-107">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  <span data-ttu-id="e5058-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e5058-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e5058-109">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e5058-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e5058-110">Dans la barre de navigation de gauche, cliquez sur **Topology** , puis sur **Status (statut**).</span><span class="sxs-lookup"><span data-stu-id="e5058-110">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="e5058-111">Dans la page **État** , triez ou effectuez une recherche dans la liste selon vos besoins pour trouver l’ordinateur exécutant les services que vous voulez démarrer ou arrêter, puis cliquez dessus.</span><span class="sxs-lookup"><span data-stu-id="e5058-111">On the **Status** page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="e5058-112">Cliquez sur **action**.</span><span class="sxs-lookup"><span data-stu-id="e5058-112">Click **Action**.</span></span>

6.  <span data-ttu-id="e5058-113">Cliquez sur **Démarrer tout le service** ou **arrêter tous les services**.</span><span class="sxs-lookup"><span data-stu-id="e5058-113">Click **Start All services** or **Stop All services**.</span></span>

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a><span data-ttu-id="e5058-114">Pour démarrer ou arrêter un service spécifique</span><span class="sxs-lookup"><span data-stu-id="e5058-114">To start or stop a specific service</span></span>

1.  <span data-ttu-id="e5058-115">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="e5058-115">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e5058-116">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e5058-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e5058-117">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e5058-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e5058-118">Dans la barre de navigation de gauche, cliquez sur **Topology** , puis sur **Status (statut**).</span><span class="sxs-lookup"><span data-stu-id="e5058-118">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="e5058-119">Dans la page **État** , triez ou effectuez une recherche dans la liste selon vos besoins pour trouver l’ordinateur exécutant le service que vous voulez démarrer ou arrêter, puis cliquez dessus.</span><span class="sxs-lookup"><span data-stu-id="e5058-119">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="e5058-120">Cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="e5058-120">Click **Properties**.</span></span>

6.  <span data-ttu-id="e5058-121">Triez la liste des services, si nécessaire, puis cliquez sur le service que vous voulez démarrer ou arrêter.</span><span class="sxs-lookup"><span data-stu-id="e5058-121">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>

7.  <span data-ttu-id="e5058-122">Cliquez sur **action**.</span><span class="sxs-lookup"><span data-stu-id="e5058-122">Click **Action**.</span></span>

8.  <span data-ttu-id="e5058-123">Cliquez sur **Démarrer le service** ou arrêter le **service**.</span><span class="sxs-lookup"><span data-stu-id="e5058-123">Click **Start service** or **Stop service**.</span></span>

9.  <span data-ttu-id="e5058-124">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="e5058-124">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e5058-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e5058-125">See Also</span></span>


[<span data-ttu-id="e5058-126">Empêcher les sessions pour les services dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5058-126">Prevent sessions for services in Lync Server 2013</span></span>](lync-server-2013-prevent-sessions-for-services.md)  


[<span data-ttu-id="e5058-127">Gestion de la topologie Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5058-127">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

