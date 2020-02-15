---
title: 'Lync Server 2013 : associez des sous-réseaux à des sites réseau pour la déviation du trafic multimédia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for media bypass
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48184244
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbe244426b6c2b7f83ef8070f995305a2a02ef31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044776"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="4b361-102">Associer des sous-réseaux à des sites réseau pour la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b361-102">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b361-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="4b361-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4b361-104">Dans cette rubrique, nous partons du principe que vous avez déjà configuré les paramètres globaux de contournement de média, mais aussi la région et les sites de réseau pour le contournement de média.</span><span class="sxs-lookup"><span data-stu-id="4b361-104">This topic assumes that you have configured media bypass global settings and that you have configured network region and network sites for media bypass.</span></span>



</div>

<span data-ttu-id="4b361-p101">Chaque sous-réseau de votre réseau doit être associé à un site réseau spécifique. Ceci est dû au fait que les informations de sous-réseau permettent de déterminer le site réseau sur lequel se trouve un système d’extrémité. Lorsque les emplacements des deux parties sont connus dans une session, le contournement de média peut déterminer où le média doit être envoyé pour traitement.</span><span class="sxs-lookup"><span data-stu-id="4b361-p101">Every subnet in your network must be associated with a specific network site. This is because subnet information is used to determine the network site on which an endpoint is located. When the locations of both parties in a session are known, media bypass can determine where to send media for processing.</span></span>

<span data-ttu-id="4b361-108">Le contournement de média ne doit respecter aucune condition particulière pour associer les sous-réseaux aux sites réseau.</span><span class="sxs-lookup"><span data-stu-id="4b361-108">Media bypass does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="4b361-109">Pour créer une association entre les sous-réseaux et les sites réseau de votre topologie, suivez les procédures décrites dans [associer un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="4b361-109">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a><span data-ttu-id="4b361-110">Étapes suivantes : Créer des profils de stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="4b361-110">Next Steps: Create Bandwidth Policy Profiles</span></span>

<span data-ttu-id="4b361-p103">Une fois que vous avez associé les sous-réseaux à des sites réseau pour le contournement de média, vous devez créer un ou plusieurs profils de stratégie de bande passante qui partitionneront les sous-réseaux en éléments de bonne connectivité et éléments sans connectivité à des fins de contournement de média. Tous les sous-réseaux d’une région réseau comportant des sites réseau qui ne sont soumis à aucune limitation de bande passante disposent d’une bonne connectivité. Ces sous-réseaux peuvent donc utiliser le contournement de média.</span><span class="sxs-lookup"><span data-stu-id="4b361-p103">After you associate subnets with network sites for media bypass, you must create one or more bandwidth policy profiles that will partition subnets into those with good connectivity and those without, for the purposes of media bypass. All subnets within a network region with network sites that do not have bandwidth constraints have good connectivity, and, therefore, those subnets can use media bypass.</span></span>

<span data-ttu-id="4b361-113">Pour connaître les procédures de configuration des profils de stratégie de bande passante, voir [Create Bandwidth Policy Profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="4b361-113">For procedures to configure bandwidth policy profiles, see [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

