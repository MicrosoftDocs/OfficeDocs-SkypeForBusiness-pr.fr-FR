---
title: Vérifier les informations de la topologie
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ef4c2884d9810793b6431c9d518c92bdcd1a3a4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518041"
---
# <a name="verify-topology-information"></a><span data-ttu-id="0cfd4-102">Vérifier les informations de la topologie</span><span class="sxs-lookup"><span data-stu-id="0cfd4-102">Verify topology information</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cfd4-103">_**Dernière modification de la rubrique :** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="0cfd4-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="0cfd4-104">La première étape de la vérification de la fusion réussie consiste à afficher les informations de topologie Office Communications Server 2007 R2 que vous avez fusionnées avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0cfd4-104">The first step in verifying the merge completed successfully is to view the Office Communications Server 2007 R2 topology information that you merged with Lync Server 2013.</span></span> <span data-ttu-id="0cfd4-105">Dans le générateur de topologies, le nœud **BackCompatSite** affiche le nom de domaine complet (FQDN) de chaque pool et serveur Office Communications Server 2007 R2 que vous avez fusionnés.</span><span class="sxs-lookup"><span data-stu-id="0cfd4-105">In Topology Builder, the **BackCompatSite** node displays the fully qualified domain name (FQDN) of each Office Communications Server 2007 R2 pool and server that you merged.</span></span>

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a><span data-ttu-id="0cfd4-106">Pour afficher BackCompatSite dans le Générateur de topologies</span><span class="sxs-lookup"><span data-stu-id="0cfd4-106">To view BackCompatSite in Topology Builder</span></span>

1.  <span data-ttu-id="0cfd4-107">Dans votre environnement Office Communications Server 2007 R2, ouvrez l’outil d’administration Office Communications Server 2007 R2 et notez les noms de domaine complets des pools et serveurs hérités.</span><span class="sxs-lookup"><span data-stu-id="0cfd4-107">In your Office Communications Server 2007 R2 environment, open the Office Communications Server 2007 R2 administrative tool and note the FQDNs of the legacy pools and servers.</span></span>

2.  <span data-ttu-id="0cfd4-108">Dans votre environnement Lync Server 2013, ouvrez le générateur de topologies, puis développez le nœud **BackCompatSite** .</span><span class="sxs-lookup"><span data-stu-id="0cfd4-108">In your Lync Server 2013 environment, open Topology Builder and then expand the **BackCompatSite** node.</span></span>

3.  <span data-ttu-id="0cfd4-109">Vérifiez que les noms de domaine complets des pools et serveurs que vous fusionnez sont affichés.</span><span class="sxs-lookup"><span data-stu-id="0cfd4-109">Verify that the FQDNs for the pools and servers that you merge are displayed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0cfd4-110">Aucune information n’est affichée dans <STRONG>BackCompatSite</STRONG> pour les rôles serveur colocalisés sur un serveur frontal ou un serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0cfd4-110">You do not see any information in <STRONG>BackCompatSite</STRONG> for server roles that are collocated on a Front End Server or Standard Edition server.</span></span> <span data-ttu-id="0cfd4-111">Seuls les rôles serveur requis pour l’interopérabilité entre Office Communications Server 2007 R2 et Lync Server 2013 sont affichés.</span><span class="sxs-lookup"><span data-stu-id="0cfd4-111">Only server roles that are required for interoperability between Office Communications Server 2007 R2 and Lync Server 2013 are shown.</span></span>

    
    </div>

<span data-ttu-id="0cfd4-112">![Boîte de dialogue BackCompatSite du générateur de topologies](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Boîte de dialogue BackCompatSite du générateur de topologies")</span><span class="sxs-lookup"><span data-stu-id="0cfd4-112">![Topology Builder BackCompatSite dialog box](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder BackCompatSite dialog box")</span></span>

<span data-ttu-id="0cfd4-113">Vous pouvez également utiliser le panneau de configuration Lync Server 2013 pour afficher votre topologie fusionnée.</span><span class="sxs-lookup"><span data-stu-id="0cfd4-113">You can also use Lync Server 2013 Control Panel to view your merged topology.</span></span> <span data-ttu-id="0cfd4-114">Dans le panneau de configuration Lync Server 2013, vous pouvez voir le nom de domaine complet du serveur, le nom de domaine complet du pool et le nom du site pour votre topologie fusionnée.</span><span class="sxs-lookup"><span data-stu-id="0cfd4-114">In Lync Server 2013 Control Panel, you can see each server FQDN, pool FQDN, and site name for your merged topology.</span></span> <span data-ttu-id="0cfd4-115">Les serveurs fusionnés porte le nom **Site\*\*\*\*BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="0cfd4-115">Merged servers have a **Site** name of **BackCompatSite**.</span></span>

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a><span data-ttu-id="0cfd4-116">Pour afficher la topologie fusionnée dans le panneau de configuration Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0cfd4-116">To view the merged topology in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="0cfd4-117">Ouvrez le panneau de configuration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0cfd4-117">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="0cfd4-118">Cliquez sur **Topologie**.</span><span class="sxs-lookup"><span data-stu-id="0cfd4-118">Click **Topology**.</span></span>

3.  <span data-ttu-id="0cfd4-119">Sous l’onglet **Statut**, vérifiez que les serveurs et pools que vous avez fusionnés apparaissent en recherchant **BackCompatSite** dans la colonne **Site**.</span><span class="sxs-lookup"><span data-stu-id="0cfd4-119">On the **Status** tab, verify that servers and pools you merged appear by looking for **BackCompatSite** in the **Site** column.</span></span>

<span data-ttu-id="0cfd4-120">![Panneau de configuration Lync Server affichant la topologie fusionnée](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Panneau de configuration Lync Server affichant la topologie fusionnée")</span><span class="sxs-lookup"><span data-stu-id="0cfd4-120">![Lync Server Control Panel showing merged topology](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Lync Server Control Panel showing merged topology")</span></span>

<span data-ttu-id="0cfd4-121">Pour afficher plus d’informations sur un pool fusionné, utilisez l’applet de commande **Get-CsPool**.</span><span class="sxs-lookup"><span data-stu-id="0cfd4-121">To see more detail about a merged pool, use the **Get-CsPool** cmdlet.</span></span> <span data-ttu-id="0cfd4-122">Outre les informations disponibles dans le panneau de configuration du générateur de topologies et de Lync Server 2013, cette applet de commande affiche les services exécutés sur le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0cfd4-122">In addition to the information that is available in Topology Builder and Lync Server 2013 Control Panel, this cmdlet displays the services that run on the Lync Server 2013 pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0cfd4-123">Lorsque vous publiez la topologie après avoir exécuté l’Assistant fusion dans le générateur de topologies, les annuaires de conférence sont fusionnés avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0cfd4-123">When you publish the topology after running the Merge wizard in Topology Builder, conference directories are merged to Lync Server 2013.</span></span> <span data-ttu-id="0cfd4-124">Les annuaires des conférences peuvent être vérifiés en exécutant l’applet de commande <STRONG>Get-CsConferenceDirectory</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="0cfd4-124">Conference directories can be verified by running the <STRONG>Get-CsConferenceDirectory</STRONG> cmdlet.</span></span>



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a><span data-ttu-id="0cfd4-125">Pour afficher les services sur un pool fusionné</span><span class="sxs-lookup"><span data-stu-id="0cfd4-125">To view services on a merged pool</span></span>

1.  <span data-ttu-id="0cfd4-126">Ouvrez Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0cfd4-126">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="0cfd4-127">Sur la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="0cfd4-127">At the command line, type the following:</span></span>
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    <span data-ttu-id="0cfd4-128">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="0cfd4-128">For example:</span></span>
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a><span data-ttu-id="0cfd4-129">Pour vérifier les annuaires des conférences fusionnés</span><span class="sxs-lookup"><span data-stu-id="0cfd4-129">To verify conference directories merged</span></span>

1.  <span data-ttu-id="0cfd4-130">Ouvrez Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0cfd4-130">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="0cfd4-131">Dans la ligne de commande, tapez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="0cfd4-131">At the command line, type the following:</span></span>
    
        Get-CsConferenceDirectory

3.  <span data-ttu-id="0cfd4-132">Vérifiez que tous les annuaires des conférences du pool ou du serveur que vous fusionnez figurent désormais dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0cfd4-132">Verify that all the conference directories for the pool or server you are merging are now in Lync Server 2013.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

