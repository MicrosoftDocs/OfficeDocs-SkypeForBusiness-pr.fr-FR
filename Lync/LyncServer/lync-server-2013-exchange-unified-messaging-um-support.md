---
title: 'Lync Server 2013 : Prise en charge de la messagerie unifiée Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exchange Unified Messaging (UM) support
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48183405
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8c952ed8aa407e2a4cbc836372c9238d4888572
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a><span data-ttu-id="01539-102">Prise en charge de la messagerie unifiée Exchange dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01539-102">Exchange Unified Messaging (UM) support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01539-103">_**Dernière modification de la rubrique:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="01539-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="01539-104">Lync Server 2013 prend en charge l’intégration à la messagerie unifiée Exchange pour combiner la boîte vocale et la messagerie électronique en une seule infrastructure de messagerie.</span><span class="sxs-lookup"><span data-stu-id="01539-104">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="01539-105">Dans Exchange 2013, la messagerie unifiée Exchange est composée du service de messagerie unifiée Exchange qui est installé et s’exécute sur le serveur de boîtes aux lettres et sur le routeur d’appel de MU qui est installé et s’exécute sur le serveur d’accès client.</span><span class="sxs-lookup"><span data-stu-id="01539-105">In Exchange 2013, Exchange UM consists of the Exchange UM service, which is installed and runs on the Mailbox server, and the UM Call Router, which is installed and runs on the Client Access server.</span></span> <span data-ttu-id="01539-106">Pour les déploiements de la voix entreprise de Lync Server 2013, la messagerie UNIFIÉe Exchange combine la messagerie vocale et la messagerie électronique dans un magasin unique accessible à partir d’un téléphone (Outlook Voice Access) ou d’un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="01539-106">For Lync Server 2013 Enterprise Voice deployments, Exchange UM combines voice messaging and email messaging into a single store that is accessible from a telephone (that is, Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="01539-107">Exchange UM et Lync Server 2013 collaborent de manière à fournir des réponses aux appels, à Outlook Voice Access et aux services de standard automatique aux utilisateurs d’Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="01539-107">Exchange UM and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="01539-108">Outre la prise en charge de l’intégration avec des déploiements de messagerie unifiée Exchange, Lync Server 2013 prend en charge l’intégration à la messagerie unifiée Exchange hébergée.</span><span class="sxs-lookup"><span data-stu-id="01539-108">In addition to the support for integration with on-premises deployments of Exchange UM, Lync Server 2013 supports integration with hosted Exchange UM.</span></span> <span data-ttu-id="01539-109">Cela vous permet de fournir une boîte vocale à vos utilisateurs si vous migrez tout ou partie de ces éléments vers un fournisseur de services Exchange hébergé tel que Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="01539-109">This enables you to provide voice messaging to your users if you migrate some or all of them to a hosted Exchange service provider such as Microsoft Exchange Online.</span></span>

<span data-ttu-id="01539-110">Lync Server 2013 prend en charge les versions suivantes:</span><span class="sxs-lookup"><span data-stu-id="01539-110">Lync Server 2013 supports the following versions:</span></span>

  - <span data-ttu-id="01539-111">Microsoft Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="01539-111">Microsoft Exchange 2013</span></span>

  - <span data-ttu-id="01539-112">Microsoft Exchange Server 2010 (requis) ou avec le dernier Service Pack (recommandé)</span><span class="sxs-lookup"><span data-stu-id="01539-112">Microsoft Exchange Server 2010 (required) or with latest service pack (recommended)</span></span>

  - <span data-ttu-id="01539-113">Microsoft Exchange Server 2007 avec Service Pack 1 (SP1) (requis) ou le dernier Service Pack (recommandé)</span><span class="sxs-lookup"><span data-stu-id="01539-113">Microsoft Exchange Server 2007 with Service Pack 1 (SP1) (required) or latest service pack (recommended)</span></span>

<span data-ttu-id="01539-114">Vous ne pouvez pas collocate Exchange UM avec Lync Server 2013 ou une base de données Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="01539-114">You cannot collocate Exchange UM with Lync Server 2013 or a Lync Server 2013 database.</span></span> <span data-ttu-id="01539-115">Vous pouvez installer Exchange UM et Lync Server 2013 dans des forêts distinctes.</span><span class="sxs-lookup"><span data-stu-id="01539-115">You can install Exchange UM and Lync Server 2013 in separate forests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="01539-116">Exchange UM ne peut pas être requis pour les déploiements vocaux d’entreprise ayant déployé un système PBX, car le système PBX peut continuer à fournir des messages vocaux et des services associés à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="01539-116">Exchange UM may not be required for Enterprise Voice deployments that have a PBX deployed, because the PBX can continue to provide voice mail and related services to all users.</span></span> <span data-ttu-id="01539-117">Si vous avez finalement désactivé le PBX (par exemple, si vous déployez le trunking SIP pour une connectivité PSTN), vous devez reconfigurer la messagerie UNIFIÉe Exchange pour fournir la messagerie vocale aux utilisateurs qui ont utilisé le système de messagerie vocale PBX.</span><span class="sxs-lookup"><span data-stu-id="01539-117">If you eventually retire the PBX (for example, if you deploy SIP trunking for public switched telephone network (PSTN) connectivity), you must reconfigure Exchange UM to provide voice mail to users who previously used the PBX voice mail system.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="01539-118">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="01539-118">In This Section</span></span>

  - [<span data-ttu-id="01539-119">Composants et topologies de la messagerie unifiée locale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01539-119">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="01539-120">Prise en charge de l’intégration de la messagerie unifiée Exchange hébergée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01539-120">Support for hosted Exchange UM integration in Lync Server 2013</span></span>](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

