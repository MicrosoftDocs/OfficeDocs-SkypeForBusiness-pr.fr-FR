---
title: 'Lync Server 2013 : création ou modification des itinéraires de la région réseau'
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
ms.openlocfilehash: d877de116cc2cf3e0c3354bb6e53d69c211cb482
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="bba2b-102">Création ou modification des itinéraires de région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bba2b-102">Creating or modifying network region routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bba2b-103">_**Dernière modification de la rubrique :** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="bba2b-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="bba2b-104">Chaque région au sein d’une configuration de contrôle d’admission des appels (CAC) doit disposer d’un moyen d’accéder à toutes les autres régions.</span><span class="sxs-lookup"><span data-stu-id="bba2b-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="bba2b-105">Lorsque les liaisons de zone définissent des limitations de bande passante pour les connexions entre les régions et représentent également les liens physiques, un itinéraire détermine le chemin d’accès lié que la connexion traverse d’une région à l’autre.</span><span class="sxs-lookup"><span data-stu-id="bba2b-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="bba2b-106">Vous pouvez utiliser le panneau de configuration de Lync Server pour configurer les itinéraires de région réseau.</span><span class="sxs-lookup"><span data-stu-id="bba2b-106">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="bba2b-107">Dans le panneau de configuration de Lync Server, vous pouvez créer, modifier ou supprimer un itinéraire de la région du réseau.</span><span class="sxs-lookup"><span data-stu-id="bba2b-107">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="bba2b-108">Utilisez cette rubrique pour créer ou modifier un itinéraire de la région du réseau.</span><span class="sxs-lookup"><span data-stu-id="bba2b-108">Use this topic to create or modify a network region route.</span></span> <span data-ttu-id="bba2b-109">Pour plus d’informations sur la suppression d’un itinéraire de région réseau existant, voir [Suppression d’itinéraires de région réseau existants dans Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="bba2b-109">For details about deleting an existing network region routes, see [Deleting existing network region routes in Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span></span>

<div>

## <a name="to-create-a-network-region-route"></a><span data-ttu-id="bba2b-110">Pour créer un itinéraire de la région du réseau</span><span class="sxs-lookup"><span data-stu-id="bba2b-110">To create a network region route</span></span>

1.  <span data-ttu-id="bba2b-111">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="bba2b-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bba2b-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bba2b-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bba2b-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bba2b-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bba2b-114">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **itinéraire des régions**.</span><span class="sxs-lookup"><span data-stu-id="bba2b-114">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="bba2b-115">Sur la page itinéraire de la **région** , cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="bba2b-115">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="bba2b-116">Dans la **zone nouvel itinéraire**de la région, tapez une valeur dans le champ **nom** .</span><span class="sxs-lookup"><span data-stu-id="bba2b-116">In **New Region Route**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bba2b-117">Cette valeur doit être unique dans le cadre de votre déploiement de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bba2b-117">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="bba2b-118">Dans la liste déroulante \*\* \#région de réseau 1\*\* , sélectionnez l’une des deux régions auxquelles vous voulez être connectée par cet itinéraire.</span><span class="sxs-lookup"><span data-stu-id="bba2b-118">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="bba2b-119">Dans la liste déroulante de la \*\* \#région réseau 2\*\* , sélectionnez une autre région pour ce routage.</span><span class="sxs-lookup"><span data-stu-id="bba2b-119">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="bba2b-120">Cette région doit être différente de la région sélectionnée pour la région \#réseau 1.</span><span class="sxs-lookup"><span data-stu-id="bba2b-120">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="bba2b-121">Utilisez la zone de liste **liaisons de région réseau** pour ajouter des liens de région à l’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="bba2b-121">Use the **Network region links** list box to add region links to the route.</span></span> <span data-ttu-id="bba2b-122">Cliquez sur le bouton **Ajouter** pour afficher la page de liaison de la **zone** .</span><span class="sxs-lookup"><span data-stu-id="bba2b-122">Click the **Add** button to display the **Region Link** page.</span></span> <span data-ttu-id="bba2b-123">Cliquez sur le lien d’une région pour l’ajouter à ce routage, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bba2b-123">Click a region link to add to this route, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bba2b-124">Continuez à cliquer sur le bouton <STRONG>Ajouter</STRONG> pour ajouter d’autres liens, ou sélectionnez un lien et cliquez sur <STRONG>supprimer</STRONG> pour supprimer un lien.</span><span class="sxs-lookup"><span data-stu-id="bba2b-124">Continue to click the <STRONG>Add</STRONG> button to add more links, or select a link and click <STRONG>Remove</STRONG> to remove a link.</span></span>

    
    </div>

9.  <span data-ttu-id="bba2b-125">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="bba2b-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-route"></a><span data-ttu-id="bba2b-126">Pour modifier un itinéraire de la région du réseau</span><span class="sxs-lookup"><span data-stu-id="bba2b-126">To modify a network region route</span></span>

1.  <span data-ttu-id="bba2b-127">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="bba2b-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bba2b-128">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bba2b-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bba2b-129">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bba2b-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bba2b-130">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **itinéraire des régions**.</span><span class="sxs-lookup"><span data-stu-id="bba2b-130">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="bba2b-131">Sur la page itinéraire de la **région** , cliquez sur le secteur que vous voulez modifier.</span><span class="sxs-lookup"><span data-stu-id="bba2b-131">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="bba2b-132">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="bba2b-132">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="bba2b-133">Dans la **zone modifier le routage**des régions, vous pouvez modifier les régions jointes par cet itinéraire et les liaisons de région associées à l’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="bba2b-133">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="bba2b-134">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="bba2b-134">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bba2b-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bba2b-135">See Also</span></span>


[<span data-ttu-id="bba2b-136">Supprimer des itinéraires de région réseau existants dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bba2b-136">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

