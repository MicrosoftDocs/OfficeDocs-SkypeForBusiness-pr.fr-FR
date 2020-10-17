---
title: 'Lync Server 2013 : associez des sous-réseaux à des sites réseau pour le contrôle d’admission des opérations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for CAC
ms:assetid: a749c9b3-15f3-4e74-9f43-1507d3c2c940
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412786(v=OCS.15)
ms:contentKeyID: 48185017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fde0eb443a643371072c4c0018c05e2cd4538d0e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531601"
---
# <a name="associate-subnets-with-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="93ef8-102">Associer des sous-réseaux à des sites réseau pour le contrôle d’admission des serveurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93ef8-102">Associate subnets with network sites for CAC in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93ef8-103">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="93ef8-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="93ef8-p101">Chaque sous-réseau de votre réseau doit être associé à un site réseau spécifique. Ceci est dû au fait que les informations de sous-réseau permettent de déterminer le site réseau sur lequel se trouve un point de terminaison. Lorsque les emplacements des deux parties dans une session sont connus, le contrôle d’admission des appels peut déterminer si la bande passante est suffisante pour établir un appel.</span><span class="sxs-lookup"><span data-stu-id="93ef8-p101">Every subnet in your network must be associated with a specific network site. This is because subnet information is used to determine the network site on which an endpoint is located. When the locations of both parties in a session are known, call admission control (CAC) can determine if there is sufficient bandwidth to establish a call.</span></span>

<span data-ttu-id="93ef8-107">Le contrôle d’admission des appels ne présente aucune exigence particulière quant à l’association des sous-réseaux aux sites réseau.</span><span class="sxs-lookup"><span data-stu-id="93ef8-107">Call admission control does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="93ef8-108">Pour créer une association entre les sous-réseaux et les sites réseau de votre topologie, suivez les procédures décrites dans [associer un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="93ef8-108">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span> <span data-ttu-id="93ef8-109">Pour afficher les sites réseau (et leurs sous-réseaux respectifs) dans l’exemple de topologie réseau pour le contrôle d’admission des appels, voir [example : Gathering Your Requirements for Call Admission Control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="93ef8-109">To view the network sites (and their respective subnets) in the example network topology for call admission control, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

