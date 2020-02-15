---
title: 'Lync Server 2013 : suppression des régions réseau existantes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network regions
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49733815
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 664eea747c9cea637b86377760f30c59bb21e7e7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-regions-in-lync-server-2013"></a><span data-ttu-id="4c932-102">Suppression des régions réseau existantes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c932-102">Deleting existing network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c932-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4c932-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4c932-104">Une région réseau interconnecte diverses parties d’un réseau sur plusieurs zones géographiques.</span><span class="sxs-lookup"><span data-stu-id="4c932-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="4c932-105">Chaque région réseau doit être associée à un site central.</span><span class="sxs-lookup"><span data-stu-id="4c932-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="4c932-106">Le site central est celui du centre de données dans lequel le service de stratégie de bande passante du contrôle d’admission des appels (CAC) s’exécute.</span><span class="sxs-lookup"><span data-stu-id="4c932-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="4c932-107">Vous pouvez utiliser le panneau de configuration Lync Server pour configurer des régions réseau.</span><span class="sxs-lookup"><span data-stu-id="4c932-107">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="4c932-108">Celles-ci incluent des paramètres qui déterminent si d’autres chemins peuvent être empruntés sur Internet pour les connexions audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="4c932-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="4c932-109">Dans le panneau de configuration Lync Server, vous pouvez créer, modifier ou supprimer une région réseau.</span><span class="sxs-lookup"><span data-stu-id="4c932-109">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="4c932-110">Consultez la rubrique pour supprimer des régions réseau.</span><span class="sxs-lookup"><span data-stu-id="4c932-110">Use this topic to delete existing network regions.</span></span> <span data-ttu-id="4c932-111">Pour plus d’informations sur la création ou la modification de régions réseau existantes, voir [Creating or Modifying Network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="4c932-111">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-delete-a-network-region"></a><span data-ttu-id="4c932-112">Pour supprimer une région réseau</span><span class="sxs-lookup"><span data-stu-id="4c932-112">To delete a network region</span></span>

1.  <span data-ttu-id="4c932-113">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="4c932-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4c932-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4c932-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4c932-115">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4c932-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4c932-116">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Région**.</span><span class="sxs-lookup"><span data-stu-id="4c932-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="4c932-117">Dans la page **Région**, cliquez sur la région à supprimer.</span><span class="sxs-lookup"><span data-stu-id="4c932-117">On the **Region** page, click the region you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4c932-p103">Vous pouvez supprimer plusieurs régions à la fois. Pour cela, appuyez sur la touche Ctrl et, tout en la maintenant enfoncée, sélectionnez plusieurs régions. Pour sélectionner toutes les régions, cliquez sur <STRONG>Sélectionner tout</STRONG> dans le menu <STRONG>Edition</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4c932-p103">You can delete more than one region at a time. To do this, press CTRL and select multiple regions while holding down the CTRL key. Or, to select all regions, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="4c932-121">Dans le menu **Edition**, cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="4c932-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="4c932-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c932-122">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="4c932-p104">Vous ne pouvez pas supprimer une région réseau si elle est associée à un site réseau. Si vous essayez, un message d’erreur s’affiche. Pour savoir si une région est associée à des sites, sélectionnez-la, puis cliquez sur <STRONG>Afficher les détails</STRONG> dans le menu <STRONG>Edition</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4c932-p104">A network region cannot be removed if it is associated with a network site. If you attempt to remove a region associated with a site you will receive an error message. To see if a region is associated with any sites, select the region and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4c932-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4c932-126">See Also</span></span>


[<span data-ttu-id="4c932-127">Création ou modification de régions réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c932-127">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

