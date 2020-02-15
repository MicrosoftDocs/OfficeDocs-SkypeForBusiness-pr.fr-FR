---
title: 'Lync Server 2013 : vue d’ensemble du directeur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48185393
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55875699e2411527d9202565ae5d31cc72e776f7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-director-in-lync-server-2013"></a><span data-ttu-id="155ba-102">Vue d’ensemble du directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="155ba-102">Overview of the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="155ba-103">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="155ba-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="155ba-104">Un directeur est un serveur exécutant Lync Server 2013 qui authentifie les demandes des utilisateurs, mais qui n’héberge pas de comptes d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="155ba-104">A Director is a server running Lync Server 2013 that authenticates user requests, but does not home any user accounts.</span></span> <span data-ttu-id="155ba-105">Vous pouvez également déployer un directeur dans les deux scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="155ba-105">You optionally can deploy a Director in the following two scenarios:</span></span>

  - <span data-ttu-id="155ba-106">Si vous activez l’accès des utilisateurs externes en déployant des serveurs Edge, vous devez également déployer un directeur.</span><span class="sxs-lookup"><span data-stu-id="155ba-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="155ba-107">Dans ce scénario, le directeur authentifie les utilisateurs externes, puis transmet leur trafic aux serveurs internes.</span><span class="sxs-lookup"><span data-stu-id="155ba-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="155ba-108">Lorsqu’un directeur est utilisé pour authentifier les utilisateurs externes, il allège la charge des serveurs de pools frontaux à l’exécution de l’authentification de ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="155ba-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="155ba-109">Il permet également d’isoler les pools frontaux internes du trafic malveillant, tels que les attaques par déni de service.</span><span class="sxs-lookup"><span data-stu-id="155ba-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="155ba-110">Si le réseau est saturé par du trafic externe non valide dans le cadre d’une telle attaque, tout ce trafic s’arrête au niveau du directeur.</span><span class="sxs-lookup"><span data-stu-id="155ba-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>

  - <span data-ttu-id="155ba-111">Si vous déployez plusieurs pools frontaux sur un site central, en ajoutant un directeur à ce site, vous pouvez rationaliser les demandes d’authentification et améliorer les performances.</span><span class="sxs-lookup"><span data-stu-id="155ba-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="155ba-112">Dans ce scénario, toutes les demandes sont d’abord adressées au directeur, qui les achemine vers le pool frontal correct.</span><span class="sxs-lookup"><span data-stu-id="155ba-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

