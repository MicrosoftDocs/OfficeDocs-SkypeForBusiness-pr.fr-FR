---
title: 'Lync Server 2013 : suppression d’un site réseau existant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c8e3828bccb84fcddb4404dd7228173c63ab8a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a><span data-ttu-id="576f1-102">Suppression d’un site réseau existant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="576f1-102">Deleting an existing network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="576f1-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="576f1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="576f1-104">Les sites réseau sont les bureaux ou les emplacements configurés dans chaque région d’un contrôle d’admission des appels (CAC) ou un déploiement 9-1-1 amélioré.</span><span class="sxs-lookup"><span data-stu-id="576f1-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="576f1-105">Vous pouvez utiliser le panneau de configuration de Lync Server 2013 pour configurer les sites et les associer à des régions.</span><span class="sxs-lookup"><span data-stu-id="576f1-105">You can use the Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="576f1-106">Par exemple, une région réseau pour l’Amérique du Nord peut être associée à des sites réseaux tels que Chicago, Redmond et Vancouver.</span><span class="sxs-lookup"><span data-stu-id="576f1-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="576f1-107">Un site réseau CAC doit être créé pour chaque site au sein d’une organisation, même si ce site n’a pas de limitations de bande passante.</span><span class="sxs-lookup"><span data-stu-id="576f1-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="576f1-108">Le panneau de configuration de Lync Server vous permet de créer, de modifier et de supprimer des sites réseau.</span><span class="sxs-lookup"><span data-stu-id="576f1-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="576f1-109">Utilisez la procédure suivante pour supprimer un site réseau existant.</span><span class="sxs-lookup"><span data-stu-id="576f1-109">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="576f1-110">Pour plus d’informations sur la création et la modification de sites réseau, voir [création ou modification de sites réseau dans Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)</span><span class="sxs-lookup"><span data-stu-id="576f1-110">For details about creating or modifying network sites, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)</span></span>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="576f1-111">Pour supprimer un site réseau</span><span class="sxs-lookup"><span data-stu-id="576f1-111">To delete a network site</span></span>

1.  <span data-ttu-id="576f1-112">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="576f1-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="576f1-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="576f1-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="576f1-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="576f1-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="576f1-115">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis cliquez sur **site**.</span><span class="sxs-lookup"><span data-stu-id="576f1-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="576f1-116">Sur la page du **site** , cliquez sur le site que vous voulez supprimer.</span><span class="sxs-lookup"><span data-stu-id="576f1-116">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="576f1-117">Vous pouvez supprimer plusieurs sites à la fois.</span><span class="sxs-lookup"><span data-stu-id="576f1-117">You can delete more than one site at a time.</span></span> <span data-ttu-id="576f1-118">Pour cela, appuyez sur CTRL et sélectionnez plusieurs sites tout en maintenant la touche CTRL enfoncée.</span><span class="sxs-lookup"><span data-stu-id="576f1-118">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="576f1-119">Pour sélectionner tous les sites, dans le menu <STRONG>Edition</STRONG> , cliquez sur <STRONG>Sélectionner tout</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="576f1-119">Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="576f1-120">Dans le menu **modifier** , cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="576f1-120">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="576f1-121">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="576f1-121">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="576f1-122">Vous ne pouvez pas supprimer un site réseau s’il est associé à un sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="576f1-122">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="576f1-123">Si vous tentez de supprimer un site associé à un sous-réseau, vous recevez un message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="576f1-123">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="576f1-124">Pour savoir si un site est associé à des sous-réseaux, cliquez sur le site, puis cliquez sur <STRONG>afficher les détails</STRONG> dans le menu <STRONG>modifier</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="576f1-124">To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

