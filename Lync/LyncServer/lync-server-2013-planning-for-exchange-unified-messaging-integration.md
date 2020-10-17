---
title: 'Lync Server 2013 : planification de l’intégration de la messagerie unifiée Exchange'
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
ms.openlocfilehash: 298e0f2667707c0ff73819b6fdd38ab105474d91
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522241"
---
# <a name="planning-for-exchange-unified-messaging-integration-in-lync-server-2013"></a><span data-ttu-id="e2ef1-102">Planification de l’intégration de la messagerie unifiée Exchange dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2ef1-102">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2ef1-103">_**Dernière modification de la rubrique :** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="e2ef1-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="e2ef1-104">Lync Server 2013 prend en charge l’intégration à la messagerie unifiée Exchange pour combiner la messagerie vocale et la messagerie électronique dans une infrastructure de messagerie unique.</span><span class="sxs-lookup"><span data-stu-id="e2ef1-104">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="e2ef1-105">Dans Microsoft Exchange Server 2007 Service Pack 1 (SP1) et Microsoft Exchange Server 2010, la messagerie unifiée Exchange est l’un des rôles serveur Exchange que vous pouvez installer et configurer.</span><span class="sxs-lookup"><span data-stu-id="e2ef1-105">In Microsoft Exchange Server 2007 Service Pack 1 (SP1) and Microsoft Exchange Server 2010, Exchange Unified Messaging (UM) is one of several Exchange server roles that you can install and configure.</span></span>

<span data-ttu-id="e2ef1-106">Dans Microsoft Exchange Server 2013, la messagerie unifiée Exchange s’exécute en tant que service sur un serveur de boîtes aux lettres Exchange.</span><span class="sxs-lookup"><span data-stu-id="e2ef1-106">In Microsoft Exchange Server 2013, Exchange UM runs as a service on an Exchange Mailbox server.</span></span> <span data-ttu-id="e2ef1-107">Pour les déploiements de voix entreprise dans Lync Server 2013, la messagerie unifiée combine la messagerie vocale et la messagerie électronique dans une banque unique disponible à partir d’un téléphone (Outlook Voice Access) ou d’un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="e2ef1-107">For Lync Server 2013 Enterprise Voice deployments, Unified Messaging combines voice messaging and email messaging into a single store that is available from a telephone (Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="e2ef1-108">La messagerie unifiée et Lync Server 2013 collaborent pour fournir des services de répondeur automatique, Outlook Voice Access et de standard automatique aux utilisateurs de voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="e2ef1-108">Unified Messaging and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto-attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="e2ef1-109">Pour plus d’informations sur les modifications apportées à l’architecture de Microsoft Exchange Server 2013, voir « Voice architecture changes » dans la documentation de Microsoft Exchange Server 2013 à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=266730](https://go.microsoft.com/fwlink/p/?linkid=266730) .</span><span class="sxs-lookup"><span data-stu-id="e2ef1-109">For more information about the architecture changes in Microsoft Exchange Server 2013, see “Voice Architecture Changes” in the Microsoft Exchange Server 2013 documentation at [https://go.microsoft.com/fwlink/p/?LinkId=266730](https://go.microsoft.com/fwlink/p/?linkid=266730).</span></span>

<span data-ttu-id="e2ef1-110">Pour que ces fonctionnalités soient prises en charge dans un déploiement de la messagerie unifiée Exchange sur site, vous devez exécuter l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="e2ef1-110">For these features to be supported in an on-premises Exchange UM deployment, you must be running one of the following:</span></span>

  - <span data-ttu-id="e2ef1-111">Microsoft Exchange Server 2007 Service Pack 1 (SP1) ou Service Pack le plus récent</span><span class="sxs-lookup"><span data-stu-id="e2ef1-111">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack</span></span>

  - <span data-ttu-id="e2ef1-112">Microsoft Exchange Server 2010 ou Service Pack le plus récent</span><span class="sxs-lookup"><span data-stu-id="e2ef1-112">Microsoft Exchange Server 2010 or latest service pack</span></span>

  - <span data-ttu-id="e2ef1-113">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2ef1-113">Microsoft Exchange Server 2013</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e2ef1-114">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="e2ef1-114">In This Section</span></span>

  - [<span data-ttu-id="e2ef1-115">Fonctionnalités de la messagerie unifiée intégrée et de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2ef1-115">Features of integrated Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-features-of-integrated-unified-messaging.md)

  - [<span data-ttu-id="e2ef1-116">Composants et topologies pour la messagerie unifiée locale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2ef1-116">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="e2ef1-117">Instructions pour l’intégration de la messagerie unifiée locale et de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2ef1-117">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

  - [<span data-ttu-id="e2ef1-118">Processus de déploiement pour l’intégration de la messagerie unifiée locale et de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2ef1-118">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

