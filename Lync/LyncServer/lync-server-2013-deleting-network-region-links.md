---
title: 'Lync Server 2013 : suppression de liens de région réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network region links
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49733712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 158537f2473beba686daa51c5384a45f01432320
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-region-links-in-lync-server-2013"></a><span data-ttu-id="4c94b-102">Supprimer des liens de région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c94b-102">Deleting network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c94b-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4c94b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4c94b-104">Vous pouvez configurer des liens entre deux régions réseau dans le cadre de la commande d’admission des appels (CAC).</span><span class="sxs-lookup"><span data-stu-id="4c94b-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="4c94b-105">Les régions d’un réseau sont liées par le biais de la connectivité du réseau étendu (WAN) physique.</span><span class="sxs-lookup"><span data-stu-id="4c94b-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="4c94b-106">Le panneau de configuration de Lync Server vous permet de supprimer un lien existant entre deux zones du réseau.</span><span class="sxs-lookup"><span data-stu-id="4c94b-106">You can use the Lync Server Control Panel to delete an existing link between two network regions.</span></span> <span data-ttu-id="4c94b-107">Pour plus d’informations sur la création ou la modification du lien de région de réseau, voir [configuration de liens de région réseau dans Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span><span class="sxs-lookup"><span data-stu-id="4c94b-107">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span></span>

<div>

## <a name="to-delete-a-network-region-link"></a><span data-ttu-id="4c94b-108">Pour supprimer un lien de zone réseau</span><span class="sxs-lookup"><span data-stu-id="4c94b-108">To delete a network region link</span></span>

1.  <span data-ttu-id="4c94b-109">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="4c94b-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4c94b-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4c94b-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4c94b-111">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4c94b-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4c94b-112">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **liaison de région**.</span><span class="sxs-lookup"><span data-stu-id="4c94b-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="4c94b-113">Dans la page de liaison de la **zone** , cliquez sur le lien dans la région que vous voulez supprimer.</span><span class="sxs-lookup"><span data-stu-id="4c94b-113">On the **Region Link** page, click the region link that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4c94b-114">Vous pouvez supprimer plusieurs liens vers une région à la fois.</span><span class="sxs-lookup"><span data-stu-id="4c94b-114">You can delete more than one region link at a time.</span></span> <span data-ttu-id="4c94b-115">Pour cela, appuyez sur CTRL et sélectionnez les liens de plusieurs régions tout en maintenant la touche CTRL enfoncée.</span><span class="sxs-lookup"><span data-stu-id="4c94b-115">To do this, press CTRL and select multiple region links while holding down the CTRL key.</span></span> <span data-ttu-id="4c94b-116">Pour sélectionner tous les liens de région, cliquez sur <STRONG>Sélectionner tout</STRONG> dans le menu <STRONG>Edition</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="4c94b-116">Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="4c94b-117">Dans le menu **modifier** , sélectionnez **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="4c94b-117">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="4c94b-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c94b-118">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4c94b-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4c94b-119">See Also</span></span>


[<span data-ttu-id="4c94b-120">Configuration de liens de région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c94b-120">Configuring network region links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

