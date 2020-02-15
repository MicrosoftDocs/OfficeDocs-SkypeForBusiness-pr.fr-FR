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
ms.openlocfilehash: 5b67dcb92fec16c31c2e2a6be780a29eb1eee295
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a><span data-ttu-id="3a858-102">Suppression d’un site réseau existant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a858-102">Deleting an existing network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a858-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3a858-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3a858-104">Les sites réseau sont les bureaux ou emplacements configurés au sein de chaque région d’un contrôle d’admission des appels (Call Admission Control ou CAC) ou encore d’un déploiement Enhanced 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="3a858-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="3a858-105">Vous pouvez utiliser le panneau de configuration Lync Server 2013 pour configurer des sites et les associer à des régions.</span><span class="sxs-lookup"><span data-stu-id="3a858-105">You can use the Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="3a858-106">Par exemple, vous pouvez associer la région réseau Amérique du Nord à des sites réseau, tels que Chicago, Redmond et Vancouver.</span><span class="sxs-lookup"><span data-stu-id="3a858-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="3a858-107">Un site réseau CAC doit être créé pour chaque site dans l’organisation, même en l’absence de limitation de bande passante pour ce site.</span><span class="sxs-lookup"><span data-stu-id="3a858-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="3a858-108">Dans le panneau de configuration Lync Server, vous pouvez créer, modifier et supprimer des sites réseau.</span><span class="sxs-lookup"><span data-stu-id="3a858-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="3a858-109">Utilisez la procédure suivante pour supprimer un site réseau existant.</span><span class="sxs-lookup"><span data-stu-id="3a858-109">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="3a858-110">Pour plus d’informations sur la création ou la modification de sites réseau, reportez-vous à la rubrique [création ou modification de sites réseau dans Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)</span><span class="sxs-lookup"><span data-stu-id="3a858-110">For details about creating or modifying network sites, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)</span></span>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="3a858-111">Pour supprimer un site réseau</span><span class="sxs-lookup"><span data-stu-id="3a858-111">To delete a network site</span></span>

1.  <span data-ttu-id="3a858-112">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="3a858-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3a858-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3a858-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3a858-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3a858-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3a858-115">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Site**.</span><span class="sxs-lookup"><span data-stu-id="3a858-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="3a858-116">Dans la page **Site**, cliquez sur le site que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="3a858-116">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3a858-p103">Vous pouvez supprimer plusieurs sites à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez plusieurs sites. Ou, pour sélectionner tous les sites, cliquez sur <STRONG>Sélectionner tout</STRONG> dans le menu <STRONG>Edition</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3a858-p103">You can delete more than one site at a time. To do this, press CTRL and select multiple sites while holding down the CTRL key. Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="3a858-120">Dans le menu **Edition**, cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="3a858-120">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="3a858-121">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3a858-121">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="3a858-p104">Vous ne pouvez pas supprimer un site réseau associé à un sous-réseau de réseau. Si vous essayez, vous recevrez un message d’erreur. Pour savoir si un site est associé à des sous-réseaux, cliquez sur le site, puis sur <STRONG>Afficher les détails</STRONG> dans le menu <STRONG>Edition</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3a858-p104">You cannot remove a network site if it is associated with a network subnet. If you attempt to remove a site associated with a subnet you will receive an error message. To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

