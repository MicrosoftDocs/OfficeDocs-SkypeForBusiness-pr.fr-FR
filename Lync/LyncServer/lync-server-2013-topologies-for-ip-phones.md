---
title: 'Lync Server 2013 : topologies pour téléphones IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1b01e4d98ced806b40cd5f092c0b8051ce86f47
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a><span data-ttu-id="b63f1-102">Topologies de téléphones IP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b63f1-102">Topologies for IP phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b63f1-103">_**Dernière modification de la rubrique :** 2012-06-21_</span><span class="sxs-lookup"><span data-stu-id="b63f1-103">_**Topic Last Modified:** 2012-06-21_</span></span>

<span data-ttu-id="b63f1-104">Cette section fournit une vue d’ensemble du processus de connexion et explique les différences qui existent entre le mode de connexion d’un téléphone IP à un réseau interne ou externe.</span><span class="sxs-lookup"><span data-stu-id="b63f1-104">This section provides an overview of the connectivity process and explains the differences between how an IP phone connects in an internal and external network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b63f1-105">Lync Server prend en charge les téléphones IP suivants : le téléphone de partie commune Aastra 6721ip, Aastra 6725ip téléphone, le téléphone IP HP 4110 (téléphone de partie commune), HP 4120 IP Phone (téléphone de bureau), Polycom CX600 de bureau de bureau IP, Polycom CX700 IP de bureau, Polycom CX500 IP Téléphone de partie commune et téléphone de conférence IP Polycom CX3000.</span><span class="sxs-lookup"><span data-stu-id="b63f1-105">Lync Server provides support for the following IP phones: the Aastra 6721ip common area phone, Aastra 6725ip desk phone, HP 4110 IP Phone (common area phone), HP 4120 IP Phone (desk phone), Polycom CX600 IP desk phone, Polycom CX700 IP desk phone, Polycom CX500 IP common area phone, and Polycom CX3000 IP conference phone.</span></span> <span data-ttu-id="b63f1-106">Ces téléphones, à l’exception du CX700 Polycom, peuvent exécuter Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="b63f1-106">Of those phones, all but the Polycom CX700 can run Lync Phone Edition.</span></span>



</div>

<span data-ttu-id="b63f1-107">Le diagramme suivant décrit tous les composants impliqués dans la connectivité d’appareil au sein d’un environnement d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="b63f1-107">The following diagram describes all the components involved in device connectivity within the corporate environment.</span></span>

<span data-ttu-id="b63f1-108">**Topologie interne**</span><span class="sxs-lookup"><span data-stu-id="b63f1-108">**Internal Topology**</span></span>

<span data-ttu-id="b63f1-109">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span><span class="sxs-lookup"><span data-stu-id="b63f1-109">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b63f1-110">L’illustration précédente est une représentation logique, et non une vue d’ensemble physique.</span><span class="sxs-lookup"><span data-stu-id="b63f1-110">The previous figure is a logical representation, not a physical overview.</span></span> <span data-ttu-id="b63f1-111">Par exemple, les services de domaine Active Directory (AD DS) se trouvent rarement sur le même ordinateur que n’importe quel composant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b63f1-111">For example, Active Directory Domain Services (AD DS) is rarely located on the same machine as any Lync Server components.</span></span> <span data-ttu-id="b63f1-112">Le magasin d’utilisateurs peut être situé sur le serveur principal ou sur les serveurs d’archivage et de surveillance.</span><span class="sxs-lookup"><span data-stu-id="b63f1-112">The user store can be located on the Back End Server or on the Archiving and Monitoring Servers.</span></span> <span data-ttu-id="b63f1-113">Lync Server Management Shell, le serveur Web et les services de mise à jour font partie du rôle de serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="b63f1-113">The Lync Server Management Shell, web server, and update services are all part of the Front End Server role.</span></span>



</div>

<span data-ttu-id="b63f1-114">Le diagramme suivant fournit une vue d’ensemble des composants impliqués lorsque l’appareil est situé à l’extérieur du réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="b63f1-114">The following diagram provides an overview of the components involved when the device is located outside the corporate network.</span></span>

<span data-ttu-id="b63f1-115">**Topologie externe**</span><span class="sxs-lookup"><span data-stu-id="b63f1-115">**External Topology**</span></span>

<span data-ttu-id="b63f1-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span><span class="sxs-lookup"><span data-stu-id="b63f1-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b63f1-117">Le service web de mise à jour des appareils fournit un site web externe et interne, mais seul le site externe est indiqué ici.</span><span class="sxs-lookup"><span data-stu-id="b63f1-117">The Device Update Web service provides an external and internal website, but only the external one is shown here.</span></span><BR><span data-ttu-id="b63f1-p103">L’emplacement du serveur d’inscriptions et l’URL du service web de mise à jour des appareils pour l’organisation doivent être publiés dans le système DNS si l’accès externe doit être activé. Par ailleurs, le serveur Edge doit être déployé et correctement configuré afin d’autoriser les communications externes à partir de l’appareil vers l’environnement d’entreprise et vice-versa. Cela n’apparaît pas sur le diagramme précédent car le déploiement du serveur Edge n’est pas effectué en fonction de la connectivité de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="b63f1-p103">The location of the Registrar and the URL of the Device Update Web service for the organization must be published in DNS if external access is to be enabled. Additionally, the Edge Server must be deployed and correctly configured to allow external communications from the device to the corporate environment and back. This is omitted from the previous diagram because Edge deployment is not specific to device connectivity.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

