---
title: 'Lync Server 2013 : planification de l’intégration de la messagerie unifiée Exchange'
description: 'Lync Server 2013 : planification de l’intégration de la messagerie unifiée Exchange.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Exchange Unified Messaging integration
ms:assetid: e7c63a71-2d99-4aa9-b649-36c1a431bdf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399031(v=OCS.15)
ms:contentKeyID: 48185880
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31296444d21a86a7837da3e29fc2152f3ca96ccc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571880"
---
# <a name="planning-for-exchange-unified-messaging-integration-in-lync-server-2013"></a><span data-ttu-id="a31de-103">Planification de l’intégration de la messagerie unifiée Exchange dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a31de-103">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a31de-104">_**Dernière modification de la rubrique :** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="a31de-104">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="a31de-105">Lync Server 2013 prend en charge l’intégration à la messagerie unifiée Exchange pour combiner la messagerie vocale et la messagerie électronique dans une infrastructure de messagerie unique.</span><span class="sxs-lookup"><span data-stu-id="a31de-105">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="a31de-106">Dans Microsoft Exchange Server 2007 Service Pack 1 (SP1) et Microsoft Exchange Server 2010, la messagerie unifiée Exchange est l’un des rôles serveur Exchange que vous pouvez installer et configurer.</span><span class="sxs-lookup"><span data-stu-id="a31de-106">In Microsoft Exchange Server 2007 Service Pack 1 (SP1) and Microsoft Exchange Server 2010, Exchange Unified Messaging (UM) is one of several Exchange server roles that you can install and configure.</span></span>

<span data-ttu-id="a31de-107">Dans Microsoft Exchange Server 2013, la messagerie unifiée Exchange s’exécute en tant que service sur un serveur de boîtes aux lettres Exchange.</span><span class="sxs-lookup"><span data-stu-id="a31de-107">In Microsoft Exchange Server 2013, Exchange UM runs as a service on an Exchange Mailbox server.</span></span> <span data-ttu-id="a31de-108">Pour les déploiements de voix entreprise dans Lync Server 2013, la messagerie unifiée combine la messagerie vocale et la messagerie électronique dans une banque unique disponible à partir d’un téléphone (Outlook Voice Access) ou d’un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="a31de-108">For Lync Server 2013 Enterprise Voice deployments, Unified Messaging combines voice messaging and email messaging into a single store that is available from a telephone (Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="a31de-109">La messagerie unifiée et Lync Server 2013 collaborent pour fournir des services de répondeur automatique, Outlook Voice Access et de standard automatique aux utilisateurs de voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="a31de-109">Unified Messaging and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto-attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="a31de-110">Pour plus d’informations sur les modifications apportées à l’architecture de Microsoft Exchange Server 2013, voir « Voice architecture changes » dans la documentation de Microsoft Exchange Server 2013 à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=266730](https://go.microsoft.com/fwlink/p/?linkid=266730) .</span><span class="sxs-lookup"><span data-stu-id="a31de-110">For more information about the architecture changes in Microsoft Exchange Server 2013, see “Voice Architecture Changes” in the Microsoft Exchange Server 2013 documentation at [https://go.microsoft.com/fwlink/p/?LinkId=266730](https://go.microsoft.com/fwlink/p/?linkid=266730).</span></span>

<span data-ttu-id="a31de-111">Pour que ces fonctionnalités soient prises en charge dans un déploiement de la messagerie unifiée Exchange sur site, vous devez exécuter l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a31de-111">For these features to be supported in an on-premises Exchange UM deployment, you must be running one of the following:</span></span>

  - <span data-ttu-id="a31de-112">Microsoft Exchange Server 2007 Service Pack 1 (SP1) ou Service Pack le plus récent</span><span class="sxs-lookup"><span data-stu-id="a31de-112">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack</span></span>

  - <span data-ttu-id="a31de-113">Microsoft Exchange Server 2010 ou Service Pack le plus récent</span><span class="sxs-lookup"><span data-stu-id="a31de-113">Microsoft Exchange Server 2010 or latest service pack</span></span>

  - <span data-ttu-id="a31de-114">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="a31de-114">Microsoft Exchange Server 2013</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a31de-115">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="a31de-115">In This Section</span></span>

  - [<span data-ttu-id="a31de-116">Fonctionnalités de la messagerie unifiée intégrée et de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a31de-116">Features of integrated Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-features-of-integrated-unified-messaging.md)

  - [<span data-ttu-id="a31de-117">Composants et topologies pour la messagerie unifiée locale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a31de-117">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="a31de-118">Instructions pour l’intégration de la messagerie unifiée locale et de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a31de-118">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

  - [<span data-ttu-id="a31de-119">Processus de déploiement pour l’intégration de la messagerie unifiée locale et de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a31de-119">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

