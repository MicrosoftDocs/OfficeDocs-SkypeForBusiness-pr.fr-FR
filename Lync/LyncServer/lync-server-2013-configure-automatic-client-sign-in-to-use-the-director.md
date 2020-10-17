---
title: 'Lync Server 2013 : configuration de la Sign-In automatique des clients pour utiliser le directeur'
description: 'Lync Server 2013 : configurez le Sign-In client automatique pour utiliser le directeur.'
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
ms.openlocfilehash: b9c45a1a677d3a30704d8dca1771ef865cef29ec
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546650"
---
# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a><span data-ttu-id="3a547-103">Configuration de la Sign-In automatique des clients pour utiliser le directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a547-103">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a547-104">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="3a547-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="3a547-105">Lorsque vous déployez un serveur Lync Server 2013, un directeur ou un pool de directeurs, nous vous recommandons d’utiliser les Sign-In client automatiques en guise de meilleures pratiques.</span><span class="sxs-lookup"><span data-stu-id="3a547-105">When you deploy a Lync Server 2013, Director or a pool of Directors, we recommend that you use Automatic Client Sign-In as a best practice.</span></span> <span data-ttu-id="3a547-106">Pour plus d’informations sur la configuration des serveurs DNS pour la connexion automatique des clients, voir [configuration DNS requise pour la connexion automatique des clients dans Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="3a547-106">For details about how to configure DNS servers for automatic client sign-in, see [DNS requirements for automatic client sign-in in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) in the Planning documentation.</span></span>

<span data-ttu-id="3a547-107">Si vous avez déjà déployé l’ouverture de session client automatique, consultez les sections suivantes pour la configurer sur votre ou vos directeurs.</span><span class="sxs-lookup"><span data-stu-id="3a547-107">If you have already deployed Automatic Client Sign-In, see the following sections to configure it on your Director(s).</span></span>

<div>

## <a name="single-director-instance"></a><span data-ttu-id="3a547-108">Instance de directeur unique</span><span class="sxs-lookup"><span data-stu-id="3a547-108">Single Director Instance</span></span>

<span data-ttu-id="3a547-109">Si le client automatique Sign-In est déjà déployé et qu’il pointe vers un serveur frontal ou un pool frontal, vous devez modifier l’enregistrement DNS SRV de sorte qu’il pointe vers le directeur.</span><span class="sxs-lookup"><span data-stu-id="3a547-109">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director.</span></span>

</div>

<div>

## <a name="director-pool"></a><span data-ttu-id="3a547-110">Pool directeur</span><span class="sxs-lookup"><span data-stu-id="3a547-110">Director Pool</span></span>

<span data-ttu-id="3a547-111">Si le client automatique Sign-In est déjà déployé et qu’il pointe vers un serveur frontal ou un pool frontal, vous devez modifier l’enregistrement DNS SRV de sorte qu’il pointe vers le pool directeur.</span><span class="sxs-lookup"><span data-stu-id="3a547-111">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

