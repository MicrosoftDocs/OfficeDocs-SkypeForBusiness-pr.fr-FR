---
title: 'Lync Server 2013 : afficher une liste d’ordinateurs exécutant Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of computers running Lync Server 2013
ms:assetid: 44eeec27-8b99-44f0-b0bd-622c12393d34
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520987(v=OCS.15)
ms:contentKeyID: 48184030
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b11c6234cbe646888946313df8dd77abc60837fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-computers-running-lync-server-2013"></a><span data-ttu-id="9d4c9-102">Afficher une liste d’ordinateurs exécutant Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d4c9-102">View a list of computers running Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d4c9-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9d4c9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9d4c9-104">Vous pouvez utiliser le panneau de configuration de Lync Server 2013 pour afficher la liste de tous les ordinateurs exécutant Lync Server 2013 dans votre topologie et afficher l’état des services.</span><span class="sxs-lookup"><span data-stu-id="9d4c9-104">You can use Lync Server 2013 Control Panel to view a list of all the computers that are running Lync Server 2013 in your topology and see the service status of each.</span></span> <span data-ttu-id="9d4c9-105">Vous pouvez trier la liste sur un ordinateur, un pool ou un site.</span><span class="sxs-lookup"><span data-stu-id="9d4c9-105">You can sort the list by computer, pool, or site.</span></span>

<div>

## <a name="to-view-a-list-of-computers-running-lync-server"></a><span data-ttu-id="9d4c9-106">Pour afficher une liste d’ordinateurs exécutant Lync Server</span><span class="sxs-lookup"><span data-stu-id="9d4c9-106">To view a list of computers running Lync Server</span></span>

1.  <span data-ttu-id="9d4c9-107">À partir d’un compte d’utilisateur affecté à un des rôles d’administration prédéfinis pour Lync Server 2013, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="9d4c9-107">From a user account that is assigned to any of the predefined administrative roles for Lync Server 2013, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="9d4c9-108">Pour plus d’informations sur les rôles d’administration prédéfinis disponibles dans Lync Server 2013, voir [planification du contrôle d’accès basé sur les rôles dans Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="9d4c9-108">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="9d4c9-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9d4c9-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9d4c9-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9d4c9-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9d4c9-111">Dans la barre de navigation de gauche, cliquez sur **Topology** , puis sur **Status (statut**).</span><span class="sxs-lookup"><span data-stu-id="9d4c9-111">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="9d4c9-112">Dans la page **État** , effectuez l’une des opérations suivantes si nécessaire :</span><span class="sxs-lookup"><span data-stu-id="9d4c9-112">On the **Status** page, do any of the following as needed:</span></span>
    
      - <span data-ttu-id="9d4c9-113">Triez la liste en cliquant sur l’en-tête de la colonne **ordinateur**, **pool**ou **site** , puis en cliquant sur la flèche vers le haut ou la flèche vers le bas.</span><span class="sxs-lookup"><span data-stu-id="9d4c9-113">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span>
    
      - <span data-ttu-id="9d4c9-114">Cliquez sur **Actualiser** pour afficher la liste la plus à jour.</span><span class="sxs-lookup"><span data-stu-id="9d4c9-114">Click **Refresh** to view the most up-to-date list.</span></span>
    
      - <span data-ttu-id="9d4c9-115">Recherchez un ordinateur en particulier en tapant le nom de l’ordinateur dans le champ de recherche.</span><span class="sxs-lookup"><span data-stu-id="9d4c9-115">Search for a specific computer by typing the computer name in the search field.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9d4c9-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9d4c9-116">See Also</span></span>


[<span data-ttu-id="9d4c9-117">Gestion de la topologie Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d4c9-117">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

