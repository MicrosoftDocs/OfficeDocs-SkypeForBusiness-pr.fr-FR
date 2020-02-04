---
title: Préparation de l’installation des serveurs sur le réseau de périmètre
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
ms.openlocfilehash: a28fc1e77a98e2a6123537ec5c062dca5d0c6ffb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-for-installation-of-servers-in-the-perimeter-network-for-lync-server-2013"></a><span data-ttu-id="57f01-102">Préparation de l’installation des serveurs sur le réseau de périmètre pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57f01-102">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57f01-103">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="57f01-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="57f01-104">Avant de configurer les composants Edge Server, vous devez vous assurer que les ordinateurs que vous configurez répondent à la configuration système requise et que vous avez effectué les étapes prérequises pour le déploiement des composants du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="57f01-104">Before you set up Edge Server components, you need to ensure that computers that you are setting up meet system requirements and complete other prerequisite steps required for deployment of Edge Server components.</span></span>

<span data-ttu-id="57f01-105">Avant de commencer, reportez-vous aux rubriques suivantes de la documentation de planification pour l’architecture de référence que vous souhaitez déployer :</span><span class="sxs-lookup"><span data-stu-id="57f01-105">Before you begin, review the details in the following topics in the Planning documentation for the reference architecture that you want to deploy:</span></span>

  - [<span data-ttu-id="57f01-106">Serveur Edge consolidé unique avec des adresses IP privées et la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57f01-106">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="57f01-107">Serveur Edge consolidé unique avec adresses IP publiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57f01-107">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="57f01-108">Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57f01-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="57f01-109">Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec des adresses IP publiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57f01-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="57f01-110">Topologie Edge consolidée mise à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57f01-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>

## <a name="in-this-section"></a><span data-ttu-id="57f01-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="57f01-111">In This Section</span></span>

  - [<span data-ttu-id="57f01-112">Configuration de DNS pour la prise en charge de périphérie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57f01-112">Configure DNS for edge support in Lync Server 2013</span></span>](lync-server-2013-configure-dns-for-edge-support.md)

  - [<span data-ttu-id="57f01-113">Configuration des équilibreurs de charge matérielle pour les topologies Edge mises à échelle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57f01-113">Set up hardware load balancers for scaled edge topologies in Lync Server 2013</span></span>](lync-server-2013-set-up-hardware-load-balancers-for-scaled-edge-topologies.md)

  - [<span data-ttu-id="57f01-114">Configuration des pare-feux et des ports pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57f01-114">Configure firewalls and ports for external user access in Lync Server 2013</span></span>](lync-server-2013-configure-firewalls-and-ports-for-external-user-access.md)

  - [<span data-ttu-id="57f01-115">Définition de la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57f01-115">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="57f01-116">Demande des certificats pour les composants Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57f01-116">Request certificates for edge components in Lync Server 2013</span></span>](lync-server-2013-request-certificates-for-edge-components.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

