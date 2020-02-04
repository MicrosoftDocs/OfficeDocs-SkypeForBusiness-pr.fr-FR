---
title: >
  Lync Server 2013 : Configuration de la connexion automatique du client pour utiliser le directeur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Automatic Client Sign-In to use the Director
ms:assetid: 85369ffc-53ae-43be-8a23-84a094faecff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398678(v=OCS.15)
ms:contentKeyID: 48184703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9a6d9090796b2c6c2271025ed4d17a134943c11
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757798"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a><span data-ttu-id="de1a2-102">Configuration de la connexion automatique du client pour utiliser le directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de1a2-102">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de1a2-103">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="de1a2-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="de1a2-104">Lorsque vous déployez un serveur Lync Server 2013, un directeur ou un pool de directeurs, nous vous recommandons d’utiliser la connexion automatique à un client comme recommandée.</span><span class="sxs-lookup"><span data-stu-id="de1a2-104">When you deploy a Lync Server 2013, Director or a pool of Directors, we recommend that you use Automatic Client Sign-In as a best practice.</span></span> <span data-ttu-id="de1a2-105">Pour plus d’informations sur la configuration des serveurs DNS pour la connexion automatique au client, voir [configuration DNS requise pour la connexion automatique au client dans Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="de1a2-105">For details about how to configure DNS servers for automatic client sign-in, see [DNS requirements for automatic client sign-in in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) in the Planning documentation.</span></span>

<span data-ttu-id="de1a2-106">Si vous avez déjà déployé la connexion automatique au client, consultez les sections suivantes pour le configurer sur votre ou vos directeurs.</span><span class="sxs-lookup"><span data-stu-id="de1a2-106">If you have already deployed Automatic Client Sign-In, see the following sections to configure it on your Director(s).</span></span>

<div>

## <a name="single-director-instance"></a><span data-ttu-id="de1a2-107">Instance de réalisateur unique</span><span class="sxs-lookup"><span data-stu-id="de1a2-107">Single Director Instance</span></span>

<span data-ttu-id="de1a2-108">Si vous disposez déjà d’une connexion client automatique déployée et qu’elle pointe vers un serveur frontal ou un pool frontal, vous devez modifier l’enregistrement SRV DNS pour qu’il pointe vers le directeur.</span><span class="sxs-lookup"><span data-stu-id="de1a2-108">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director.</span></span>

</div>

<div>

## <a name="director-pool"></a><span data-ttu-id="de1a2-109">Pool de réalisateurs</span><span class="sxs-lookup"><span data-stu-id="de1a2-109">Director Pool</span></span>

<span data-ttu-id="de1a2-110">Si vous avez déjà déployé la connexion automatique au client et qu’elle pointe vers un serveur frontal ou un pool frontal, vous devez modifier l’enregistrement SRV DNS de façon à ce qu’il pointe vers le pool de directeurs.</span><span class="sxs-lookup"><span data-stu-id="de1a2-110">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

