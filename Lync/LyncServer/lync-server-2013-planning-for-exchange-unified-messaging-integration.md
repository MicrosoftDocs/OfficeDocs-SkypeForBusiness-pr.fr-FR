---
title: 'Lync Server 2013 : Planification de l’intégration de la messagerie unifiée Exchange'
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
ms.openlocfilehash: 9325cdce67113c46ec02879417748a2e3dd0397d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41752254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-exchange-unified-messaging-integration-in-lync-server-2013"></a><span data-ttu-id="0f532-102">Planification de l’intégration de la messagerie unifiée Exchange dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f532-102">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f532-103">_**Dernière modification de la rubrique :** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="0f532-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="0f532-104">Lync Server 2013 prend en charge l’intégration à la messagerie unifiée Exchange pour combiner la boîte vocale et la messagerie électronique en une seule infrastructure de messagerie.</span><span class="sxs-lookup"><span data-stu-id="0f532-104">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="0f532-105">Dans Microsoft Exchange Server 2007 Service Pack 1 (SP1) et Microsoft Exchange Server 2010, la messagerie unifiée Exchange (UM) est l’un des rôles Exchange Server que vous pouvez installer et configurer.</span><span class="sxs-lookup"><span data-stu-id="0f532-105">In Microsoft Exchange Server 2007 Service Pack 1 (SP1) and Microsoft Exchange Server 2010, Exchange Unified Messaging (UM) is one of several Exchange server roles that you can install and configure.</span></span>

<span data-ttu-id="0f532-106">Dans Microsoft Exchange Server 2013, la messagerie unifiée Exchange s’exécute en tant que service sur un serveur de boîtes aux lettres Exchange.</span><span class="sxs-lookup"><span data-stu-id="0f532-106">In Microsoft Exchange Server 2013, Exchange UM runs as a service on an Exchange Mailbox server.</span></span> <span data-ttu-id="0f532-107">Pour les déploiements vocaux Lync Server 2013 Enterprise, la messagerie unifiée combine la messagerie vocale et la messagerie électronique dans un emplacement unique accessible à partir d’un téléphone (Outlook Voice Access) ou d’un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="0f532-107">For Lync Server 2013 Enterprise Voice deployments, Unified Messaging combines voice messaging and email messaging into a single store that is available from a telephone (Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="0f532-108">La messagerie unifiée et Lync Server 2013 collaborent de manière à fournir des réponses aux appels, à Outlook Voice Access et aux services de standard automatique aux utilisateurs d’Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="0f532-108">Unified Messaging and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto-attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="0f532-109">Pour plus d’informations sur les modifications apportées à l’architecture dans Microsoft Exchange Server 2013, voir « modifications de l’architecture vocale » [http://go.microsoft.com/fwlink/p/?LinkId=266730](http://go.microsoft.com/fwlink/p/?linkid=266730)dans la documentation Microsoft exchange Server 2013 à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="0f532-109">For more information about the architecture changes in Microsoft Exchange Server 2013, see “Voice Architecture Changes” in the Microsoft Exchange Server 2013 documentation at [http://go.microsoft.com/fwlink/p/?LinkId=266730](http://go.microsoft.com/fwlink/p/?linkid=266730).</span></span>

<span data-ttu-id="0f532-110">Pour que ces fonctionnalités soient prises en charge dans un déploiement Exchange UM local, vous devez exécuter l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0f532-110">For these features to be supported in an on-premises Exchange UM deployment, you must be running one of the following:</span></span>

  - <span data-ttu-id="0f532-111">Microsoft Exchange Server 2007 Service Pack 1 (SP1) ou le dernier Service Pack</span><span class="sxs-lookup"><span data-stu-id="0f532-111">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack</span></span>

  - <span data-ttu-id="0f532-112">Microsoft Exchange Server 2010 ou le dernier Service Pack</span><span class="sxs-lookup"><span data-stu-id="0f532-112">Microsoft Exchange Server 2010 or latest service pack</span></span>

  - <span data-ttu-id="0f532-113">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f532-113">Microsoft Exchange Server 2013</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0f532-114">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="0f532-114">In This Section</span></span>

  - [<span data-ttu-id="0f532-115">Fonctionnalités de la messagerie unifiée intégrée et de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f532-115">Features of integrated Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-features-of-integrated-unified-messaging.md)

  - [<span data-ttu-id="0f532-116">Composants et topologies de la messagerie unifiée locale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f532-116">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="0f532-117">Instructions d’intégration de la messagerie unifiée locale et de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f532-117">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

  - [<span data-ttu-id="0f532-118">Processus de déploiement pour l’intégration de la messagerie unifiée locale et de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f532-118">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

