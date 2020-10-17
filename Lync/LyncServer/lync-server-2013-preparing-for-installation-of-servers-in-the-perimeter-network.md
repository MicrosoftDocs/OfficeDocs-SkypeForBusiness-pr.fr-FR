---
title: Préparation de l’installation des serveurs dans le réseau de périmètre
description: Préparation de l’installation des serveurs dans le réseau de périmètre.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for installation of servers in the perimeter network
ms:assetid: 5e6c457a-f964-4ef7-a709-97abda9c673a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398416(v=OCS.15)
ms:contentKeyID: 48184292
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5689d7990cc1ddf91ad6487d8abed08f40cd3db5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549920"
---
# <a name="preparing-for-installation-of-servers-in-the-perimeter-network-for-lync-server-2013"></a><span data-ttu-id="2a59c-103">Préparation de l’installation des serveurs dans le réseau de périmètre pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a59c-103">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a59c-104">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="2a59c-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="2a59c-105">Avant de configurer des composants de serveur Edge, vous devez vous assurer que les ordinateurs que vous configurez respectent la configuration système requise et effectuer les autres étapes préalables nécessaires au déploiement des composants de serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="2a59c-105">Before you set up Edge Server components, you need to ensure that computers that you are setting up meet system requirements and complete other prerequisite steps required for deployment of Edge Server components.</span></span>

<span data-ttu-id="2a59c-106">Avant de commencer, vérifiez les informations contenues dans les rubriques suivantes de la documentation de planification, pour l’architecture de référence que vous souhaitez déployer :</span><span class="sxs-lookup"><span data-stu-id="2a59c-106">Before you begin, review the details in the following topics in the Planning documentation for the reference architecture that you want to deploy:</span></span>

  - [<span data-ttu-id="2a59c-107">Serveur Edge consolidé unique avec des adresses IP privées et une interface NAT dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a59c-107">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="2a59c-108">Serveur Edge consolidé unique avec adresses IP publiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a59c-108">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="2a59c-109">Serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a59c-109">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="2a59c-110">Serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP publiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a59c-110">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="2a59c-111">Serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a59c-111">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>

## <a name="in-this-section"></a><span data-ttu-id="2a59c-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="2a59c-112">In This Section</span></span>

  - [<span data-ttu-id="2a59c-113">Configuration de DNS pour la prise en charge du serveur Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a59c-113">Configure DNS for edge support in Lync Server 2013</span></span>](lync-server-2013-configure-dns-for-edge-support.md)

  - [<span data-ttu-id="2a59c-114">Configuration des équilibreurs de charge matérielle pour les topologies Edge mises à l’horizontale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a59c-114">Set up hardware load balancers for scaled edge topologies in Lync Server 2013</span></span>](lync-server-2013-set-up-hardware-load-balancers-for-scaled-edge-topologies.md)

  - [<span data-ttu-id="2a59c-115">Configurer les pare-feu et les ports pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a59c-115">Configure firewalls and ports for external user access in Lync Server 2013</span></span>](lync-server-2013-configure-firewalls-and-ports-for-external-user-access.md)

  - [<span data-ttu-id="2a59c-116">Déterminer la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a59c-116">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="2a59c-117">Demander des certificats pour les composants Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a59c-117">Request certificates for edge components in Lync Server 2013</span></span>](lync-server-2013-request-certificates-for-edge-components.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

