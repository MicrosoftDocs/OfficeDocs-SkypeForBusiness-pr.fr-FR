---
title: 'Lync Server 2013 : prise en charge de la messagerie unifiée Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange Unified Messaging (UM) support
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48183405
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac42e46bf92e7fa170ee3dff059edc1b5871aafd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533121"
---
# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a><span data-ttu-id="7785d-102">Prise en charge de la messagerie unifiée Exchange dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7785d-102">Exchange Unified Messaging (UM) support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7785d-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="7785d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="7785d-104">Lync Server 2013 prend en charge l’intégration à la messagerie unifiée Exchange pour combiner la messagerie vocale et la messagerie électronique dans une infrastructure de messagerie unique.</span><span class="sxs-lookup"><span data-stu-id="7785d-104">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="7785d-105">Dans Exchange 2013, la messagerie unifiée Exchange se compose du service de messagerie unifiée Exchange, qui est installé et s’exécute sur le serveur de boîtes aux lettres, et du routeur d’appels de messagerie unifiée, qui est installé et s’exécute sur le serveur d’accès au client.</span><span class="sxs-lookup"><span data-stu-id="7785d-105">In Exchange 2013, Exchange UM consists of the Exchange UM service, which is installed and runs on the Mailbox server, and the UM Call Router, which is installed and runs on the Client Access server.</span></span> <span data-ttu-id="7785d-106">Pour les déploiements de voix entreprise dans Lync Server 2013, la messagerie UNIFIÉe Exchange combine la messagerie vocale et la messagerie électronique dans un magasin unique accessible à partir d’un téléphone (Outlook Voice Access) ou d’un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="7785d-106">For Lync Server 2013 Enterprise Voice deployments, Exchange UM combines voice messaging and email messaging into a single store that is accessible from a telephone (that is, Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="7785d-107">La messagerie unifiée Exchange et Lync Server 2013 collaborent pour fournir des services de répondeur automatique, Outlook Voice Access et de standard automatique aux utilisateurs de voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="7785d-107">Exchange UM and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="7785d-108">En plus de la prise en charge de l’intégration avec des déploiements locaux de la messagerie unifiée Exchange, Lync Server 2013 prend en charge l’intégration à la messagerie unifiée Exchange hébergée.</span><span class="sxs-lookup"><span data-stu-id="7785d-108">In addition to the support for integration with on-premises deployments of Exchange UM, Lync Server 2013 supports integration with hosted Exchange UM.</span></span> <span data-ttu-id="7785d-109">Cela vous permet d’offrir la fonctionnalité de messagerie vocale aux utilisateurs si vous procédez à la migration de la totalité des utilisateurs ou de certains d’entre eux vers un fournisseur de service Exchange hébergé tel que Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7785d-109">This enables you to provide voice messaging to your users if you migrate some or all of them to a hosted Exchange service provider such as Microsoft Exchange Online.</span></span>

<span data-ttu-id="7785d-110">Lync Server 2013 prend en charge les versions suivantes :</span><span class="sxs-lookup"><span data-stu-id="7785d-110">Lync Server 2013 supports the following versions:</span></span>

  - <span data-ttu-id="7785d-111">Microsoft Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="7785d-111">Microsoft Exchange 2013</span></span>

  - <span data-ttu-id="7785d-112">Microsoft Exchange Server 2010 (requis) ou avec le Service Pack le plus récent (recommandé)</span><span class="sxs-lookup"><span data-stu-id="7785d-112">Microsoft Exchange Server 2010 (required) or with latest service pack (recommended)</span></span>

  - <span data-ttu-id="7785d-113">Microsoft Exchange Server 2007 avec Service Pack 1 (SP1) (requis) ou le Service Pack le plus récent (recommandé)</span><span class="sxs-lookup"><span data-stu-id="7785d-113">Microsoft Exchange Server 2007 with Service Pack 1 (SP1) (required) or latest service pack (recommended)</span></span>

<span data-ttu-id="7785d-114">Vous ne pouvez pas colocaliser la messagerie unifiée Exchange avec Lync Server 2013 ou une base de données Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7785d-114">You cannot collocate Exchange UM with Lync Server 2013 or a Lync Server 2013 database.</span></span> <span data-ttu-id="7785d-115">Vous pouvez installer la messagerie unifiée Exchange et Lync Server 2013 dans des forêts distinctes.</span><span class="sxs-lookup"><span data-stu-id="7785d-115">You can install Exchange UM and Lync Server 2013 in separate forests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7785d-116">Il est possible que la messagerie unifiée Exchange ne soit pas indispensable pour les déploiements de Voix Entreprise intégrant un système PBX, car ce dernier peut continuer à fournir à tous les utilisateurs des services de messagerie vocale et d’autres services connexes.</span><span class="sxs-lookup"><span data-stu-id="7785d-116">Exchange UM may not be required for Enterprise Voice deployments that have a PBX deployed, because the PBX can continue to provide voice mail and related services to all users.</span></span> <span data-ttu-id="7785d-117">Si vous avez finalement retiré le PBX (par exemple, si vous déployez la jonction SIP pour la connectivité PSTN), vous devez reconfigurer la messagerie UNIFIÉe Exchange pour qu’elle fournisse des messages vocaux aux utilisateurs qui ont utilisé le système de messagerie vocale PBX.</span><span class="sxs-lookup"><span data-stu-id="7785d-117">If you eventually retire the PBX (for example, if you deploy SIP trunking for public switched telephone network (PSTN) connectivity), you must reconfigure Exchange UM to provide voice mail to users who previously used the PBX voice mail system.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7785d-118">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="7785d-118">In This Section</span></span>

  - [<span data-ttu-id="7785d-119">Composants et topologies pour la messagerie unifiée locale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7785d-119">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="7785d-120">Prise en charge de l’intégration de la messagerie unifiée Exchange hébergée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7785d-120">Support for hosted Exchange UM integration in Lync Server 2013</span></span>](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

