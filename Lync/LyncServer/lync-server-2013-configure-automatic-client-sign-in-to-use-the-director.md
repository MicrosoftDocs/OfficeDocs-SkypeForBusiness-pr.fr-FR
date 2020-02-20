---
title: 'Lync Server 2013 : configuration de la connexion automatique du client pour utiliser le directeur'
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
ms.openlocfilehash: ad7a81a662e4d69ac8ee88cfdbce2f5448d195ec
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a><span data-ttu-id="2bfcc-102">Configuration de la connexion automatique du client pour utiliser le directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2bfcc-102">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bfcc-103">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="2bfcc-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="2bfcc-104">Lorsque vous déployez un serveur Lync Server 2013, un directeur ou un pool de directeurs, nous vous recommandons d’utiliser la connexion automatique des clients comme meilleure pratique.</span><span class="sxs-lookup"><span data-stu-id="2bfcc-104">When you deploy a Lync Server 2013, Director or a pool of Directors, we recommend that you use Automatic Client Sign-In as a best practice.</span></span> <span data-ttu-id="2bfcc-105">Pour plus d’informations sur la configuration des serveurs DNS pour la connexion automatique des clients, voir [configuration DNS requise pour la connexion automatique des clients dans Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="2bfcc-105">For details about how to configure DNS servers for automatic client sign-in, see [DNS requirements for automatic client sign-in in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) in the Planning documentation.</span></span>

<span data-ttu-id="2bfcc-106">Si vous avez déjà déployé l’ouverture de session client automatique, consultez les sections suivantes pour la configurer sur votre ou vos directeurs.</span><span class="sxs-lookup"><span data-stu-id="2bfcc-106">If you have already deployed Automatic Client Sign-In, see the following sections to configure it on your Director(s).</span></span>

<div>

## <a name="single-director-instance"></a><span data-ttu-id="2bfcc-107">Instance de directeur unique</span><span class="sxs-lookup"><span data-stu-id="2bfcc-107">Single Director Instance</span></span>

<span data-ttu-id="2bfcc-108">Si vous avez déjà déployé la connexion client automatique et qu’elle pointe vers un serveur frontal ou un pool frontal, vous devez modifier l’enregistrement DNS SRV de sorte qu’il pointe vers le directeur.</span><span class="sxs-lookup"><span data-stu-id="2bfcc-108">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director.</span></span>

</div>

<div>

## <a name="director-pool"></a><span data-ttu-id="2bfcc-109">Pool directeur</span><span class="sxs-lookup"><span data-stu-id="2bfcc-109">Director Pool</span></span>

<span data-ttu-id="2bfcc-110">Si vous avez déjà déployé la connexion client automatique et qu’elle pointe vers un serveur frontal ou un pool frontal, vous devez modifier l’enregistrement DNS SRV de sorte qu’il pointe vers le pool directeur.</span><span class="sxs-lookup"><span data-stu-id="2bfcc-110">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

