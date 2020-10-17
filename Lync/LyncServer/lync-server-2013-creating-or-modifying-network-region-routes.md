---
title: 'Lync Server 2013 : création ou modification des itinéraires de région réseau'
description: 'Lync Server 2013 : création ou modification des itinéraires de région réseau.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network region routes
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521016(v=OCS.15)
ms:contentKeyID: 48184540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89106c905419778776ea16341f247027d49f1195
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544090"
---
# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="6e134-103">Création ou modification des itinéraires de région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e134-103">Creating or modifying network region routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e134-104">_**Dernière modification de la rubrique :** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="6e134-104">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="6e134-105">Chaque région au sein d’un contrôle d’admission des appels doit disposer d’un moyen lui permettant d’accéder à toutes les autres régions.</span><span class="sxs-lookup"><span data-stu-id="6e134-105">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="6e134-106">Alors que les liens de région définissent des restrictions de bande passante sur les connexions entre les régions et qu’ils représentent également des liens physiques, un itinéraire détermine le chemin lié que la connexion traverse d’une région à une autre.</span><span class="sxs-lookup"><span data-stu-id="6e134-106">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="6e134-107">Vous pouvez utiliser le panneau de configuration Lync Server pour configurer les itinéraires de région réseau.</span><span class="sxs-lookup"><span data-stu-id="6e134-107">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="6e134-108">Dans le panneau de configuration Lync Server, vous pouvez créer, modifier ou supprimer un itinéraire de région réseau.</span><span class="sxs-lookup"><span data-stu-id="6e134-108">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="6e134-109">Utilisez cette rubrique pour créer ou modifier un itinéraire de région réseau.</span><span class="sxs-lookup"><span data-stu-id="6e134-109">Use this topic to create or modify a network region route.</span></span> <span data-ttu-id="6e134-110">Pour plus d’informations sur la suppression d’un itinéraire de région réseau existant, voir [Suppression de routes de région réseau existantes dans Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="6e134-110">For details about deleting an existing network region routes, see [Deleting existing network region routes in Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span></span>

<div>

## <a name="to-create-a-network-region-route"></a><span data-ttu-id="6e134-111">Pour créer un itinéraire de région réseau</span><span class="sxs-lookup"><span data-stu-id="6e134-111">To create a network region route</span></span>

1.  <span data-ttu-id="6e134-112">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="6e134-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6e134-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6e134-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6e134-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6e134-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6e134-115">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Itinéraire de région**.</span><span class="sxs-lookup"><span data-stu-id="6e134-115">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="6e134-116">Dans la page **Itinéraire de région**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="6e134-116">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="6e134-117">Dans **Nouvel itinéraire de région**, tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="6e134-117">In **New Region Route**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6e134-118">Cette valeur doit être unique dans votre déploiement de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6e134-118">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="6e134-119">Dans la liste déroulante **région réseau \# 1** , sélectionnez l’une des deux régions à connecter par cet itinéraire.</span><span class="sxs-lookup"><span data-stu-id="6e134-119">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="6e134-120">Dans la liste déroulante **région réseau \# 2** , sélectionnez l’autre région pour cet itinéraire.</span><span class="sxs-lookup"><span data-stu-id="6e134-120">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="6e134-121">Cette région doit être différente de la région sélectionnée pour la région réseau \# 1.</span><span class="sxs-lookup"><span data-stu-id="6e134-121">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="6e134-p104">Utilisez la zone de liste **Liens de région réseau** pour ajouter des liens de région à l’itinéraire. Cliquez sur le bouton **Ajouter** pour afficher la page **Lien de région**. Cliquez sur un lien de région pour l’ajouter à cet itinéraire, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e134-p104">Use the **Network region links** list box to add region links to the route. Click the **Add** button to display the **Region Link** page. Click a region link to add to this route, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6e134-125">Continuez à cliquer sur le bouton <STRONG>Ajouter</STRONG> pour ajouter davantage de liens, ou sélectionnez un lien et cliquez sur <STRONG>Supprimer</STRONG> pour le supprimer.</span><span class="sxs-lookup"><span data-stu-id="6e134-125">Continue to click the <STRONG>Add</STRONG> button to add more links, or select a link and click <STRONG>Remove</STRONG> to remove a link.</span></span>

    
    </div>

9.  <span data-ttu-id="6e134-126">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="6e134-126">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-route"></a><span data-ttu-id="6e134-127">Pour modifier un itinéraire de région réseau</span><span class="sxs-lookup"><span data-stu-id="6e134-127">To modify a network region route</span></span>

1.  <span data-ttu-id="6e134-128">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="6e134-128">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6e134-129">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6e134-129">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6e134-130">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6e134-130">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6e134-131">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Itinéraire de région**.</span><span class="sxs-lookup"><span data-stu-id="6e134-131">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="6e134-132">Dans la page **Itinéraire de région**, cliquez sur l’itinéraire de région que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="6e134-132">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="6e134-133">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="6e134-133">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="6e134-134">Dans **Modifier l’itinéraire de région**, vous pouvez modifier les régions liées par cet itinéraire et les liens de région qui lui sont associés.</span><span class="sxs-lookup"><span data-stu-id="6e134-134">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="6e134-135">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="6e134-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6e134-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6e134-136">See Also</span></span>


[<span data-ttu-id="6e134-137">Suppression des itinéraires de région réseau existants dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e134-137">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

