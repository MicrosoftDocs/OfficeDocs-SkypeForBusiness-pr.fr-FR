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
ms.openlocfilehash: 8587e0a07e4e6bdb0e2231d557e0d475152daa16
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-network-region-links-in-lync-server-2013"></a><span data-ttu-id="a906c-102">Suppression de liens de région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a906c-102">Deleting network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a906c-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a906c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a906c-104">Vous pouvez configurer les liens entre deux régions réseau dans le cadre du service Contrôle d’admission des appels (CAC).</span><span class="sxs-lookup"><span data-stu-id="a906c-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="a906c-105">Au sein d’un réseau, les régions sont liées par une connectivité physique au réseau étendu (WAN).</span><span class="sxs-lookup"><span data-stu-id="a906c-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="a906c-106">Vous pouvez utiliser le panneau de configuration Lync Server pour supprimer un lien existant entre deux régions réseau.</span><span class="sxs-lookup"><span data-stu-id="a906c-106">You can use the Lync Server Control Panel to delete an existing link between two network regions.</span></span> <span data-ttu-id="a906c-107">Pour plus d’informations sur la création ou la modification d’un lien de région réseau, voir [Configuring Network Region Links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span><span class="sxs-lookup"><span data-stu-id="a906c-107">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span></span>

<div>

## <a name="to-delete-a-network-region-link"></a><span data-ttu-id="a906c-108">Pour supprimer un lien de région réseau</span><span class="sxs-lookup"><span data-stu-id="a906c-108">To delete a network region link</span></span>

1.  <span data-ttu-id="a906c-109">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="a906c-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a906c-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a906c-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a906c-111">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a906c-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a906c-112">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Lien de région**.</span><span class="sxs-lookup"><span data-stu-id="a906c-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="a906c-113">Dans la page **Lien de région**, cliquez sur le lien de région que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="a906c-113">On the **Region Link** page, click the region link that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a906c-p103">Vous pouvez supprimer plusieurs liens de région à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez plusieurs liens de région. Ou, pour sélectionner tous les liens de région, cliquez sur <STRONG>Sélectionner tout</STRONG> dans le menu <STRONG>Edition</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a906c-p103">You can delete more than one region link at a time. To do this, press CTRL and select multiple region links while holding down the CTRL key. Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="a906c-117">Dans le menu **Edition**, sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="a906c-117">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="a906c-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a906c-118">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a906c-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a906c-119">See Also</span></span>


[<span data-ttu-id="a906c-120">Configuration des liens de région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a906c-120">Configuring network region links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

