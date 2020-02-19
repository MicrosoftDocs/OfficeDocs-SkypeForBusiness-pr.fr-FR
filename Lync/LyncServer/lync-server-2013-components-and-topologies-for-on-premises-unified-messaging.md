---
title: 'Lync Server 2013 : composants et topologies pour la messagerie unifiée locale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for on-premises Unified Messaging
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425711(v=OCS.15)
ms:contentKeyID: 48183619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 543af1cc9b4dbb437b36273945f9f2cb6112c6b6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a><span data-ttu-id="ebda7-102">Composants et topologies pour la messagerie unifiée locale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ebda7-102">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebda7-103">_**Dernière modification de la rubrique :** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="ebda7-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="ebda7-104">Cette rubrique décrit les composants Microsoft Exchange Server 2013 requis pour fournir des fonctionnalités de messagerie unifiée Exchange au déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ebda7-104">This topic describes the Microsoft Exchange Server 2013 components required to provide Exchange Unified Messaging (UM) features to Lync Server 2013 deployment.</span></span> <span data-ttu-id="ebda7-105">Il décrit également les topologies prises en charge pour l’intégration de la messagerie unifiée Exchange sur site.</span><span class="sxs-lookup"><span data-stu-id="ebda7-105">It also describes the supported topologies for on-premises Exchange UM integration.</span></span>

<div>

## <a name="exchange-server-components"></a><span data-ttu-id="ebda7-106">Composants d’Exchange Server</span><span class="sxs-lookup"><span data-stu-id="ebda7-106">Exchange Server Components</span></span>

<span data-ttu-id="ebda7-107">Pour fournir les services et fonctionnalités de messagerie unifiée Exchange décrits dans les [fonctionnalités de la messagerie unifiée intégrée et de Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) aux utilisateurs de voix entreprise dans votre organisation, vous devez déployer un serveur de boîtes aux lettres Microsoft Exchange et un serveur d’accès au client, qui héberge les boîtes aux lettres utilisateur et fournit un emplacement de stockage unique pour la messagerie et la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="ebda7-107">To provide the Exchange UM features and services described in [Features of integrated Unified Messaging and Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) to Enterprise Voice users in your organization, you must deploy an Microsoft Exchange Mailbox server and Client Access server, which hosts user mailboxes and provides a single storage location for email and voice mail.</span></span> <span data-ttu-id="ebda7-108">La messagerie unifiée Exchange s’exécute en tant que service sur les serveurs de boîtes aux lettres et d’accès au client Exchange.</span><span class="sxs-lookup"><span data-stu-id="ebda7-108">Exchange UM runs as a service on Exchange Mailbox and Client Access servers.</span></span>

<span data-ttu-id="ebda7-109">Pour plus d’informations sur les composants de messagerie unifiée Exchange dans Microsoft Exchange Server 2007 et Microsoft Exchange Server 2010, consultez la rubrique [Deploying on-premises Exchange um to Preserver 2013 Voice Mail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="ebda7-109">For details about Exchange UM components in Microsoft Exchange Server 2007 and Microsoft Exchange Server 2010, see [Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="ebda7-110">Topologies prises en charge</span><span class="sxs-lookup"><span data-stu-id="ebda7-110">Supported Topologies</span></span>

<span data-ttu-id="ebda7-111">Vous pouvez déployer Lync Server 2013 et la messagerie unifiée Exchange dans la même forêt ou plusieurs forêts.</span><span class="sxs-lookup"><span data-stu-id="ebda7-111">You can deploy Lync Server 2013 and Exchange Unified Messaging (UM) in the same forest or multiple forests.</span></span> <span data-ttu-id="ebda7-112">Si le déploiement s’étend sur plusieurs forêts, vous devez effectuer les étapes d’intégration d’Exchange pour chaque forêt de messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="ebda7-112">If the deployment spans multiple forests, you must perform the Exchange integration steps for each Exchange UM forest.</span></span> <span data-ttu-id="ebda7-113">Par ailleurs, vous devez configurer chaque forêt Microsoft Exchange pour qu’elle approuve la forêt Lync Server 2013 et la forêt Lync Server 2013 pour approuver chaque forêt de messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="ebda7-113">Furthermore, you must configure each Microsoft Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange UM forest.</span></span> <span data-ttu-id="ebda7-114">En plus de cette approbation de forêt, les paramètres de messagerie unifiée Exchange pour tous les utilisateurs doivent être définis sur les objets utilisateur de la forêt Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ebda7-114">In addition to this forest trust, the Exchange UM settings for all users must be set on the user objects in the Lync Server 2013 forest.</span></span>

<span data-ttu-id="ebda7-115">Lync Server 2013 prend en charge les topologies suivantes pour l’intégration de la messagerie unifiée Exchange :</span><span class="sxs-lookup"><span data-stu-id="ebda7-115">Lync Server 2013 supports the following topologies for Exchange UM integration:</span></span>

  - <span data-ttu-id="ebda7-116">Forêt unique</span><span class="sxs-lookup"><span data-stu-id="ebda7-116">Single forest</span></span>

  - <span data-ttu-id="ebda7-117">Domaine unique (c’est-à-dire une forêt unique avec un seul domaine).</span><span class="sxs-lookup"><span data-stu-id="ebda7-117">Single domain (that is, a single forest with a single domain).</span></span> <span data-ttu-id="ebda7-118">Lync Server 2013, Microsoft Exchange et les utilisateurs résident tous dans le même domaine.</span><span class="sxs-lookup"><span data-stu-id="ebda7-118">Lync Server 2013, Microsoft Exchange, and users all reside in the same domain.</span></span>

  - <span data-ttu-id="ebda7-119">Plusieurs domaines (à savoir, un domaine racine comportant un ou plusieurs domaines enfants).</span><span class="sxs-lookup"><span data-stu-id="ebda7-119">Multiple domain (that is, a root domain with one or more child domains).</span></span> <span data-ttu-id="ebda7-120">Lync Server 2013 et les serveurs Microsoft Exchange sont déployés dans des domaines différents du domaine dans lequel vous créez des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ebda7-120">Lync Server 2013, and Microsoft Exchange servers are deployed in different domains from the domain where you create users.</span></span> <span data-ttu-id="ebda7-121">Les serveurs de messagerie unifiée Exchange peuvent être déployés dans différents domaines à partir du pool Lync Server 2013 qu’ils prennent en charge.</span><span class="sxs-lookup"><span data-stu-id="ebda7-121">Exchange UM servers can be deployed in different domains from the Lync Server 2013 pool they support.</span></span>

  - <span data-ttu-id="ebda7-122">Forêt multiple (autrement dit, forêt de ressources).</span><span class="sxs-lookup"><span data-stu-id="ebda7-122">Multiple forest (that is, resource forest).</span></span> <span data-ttu-id="ebda7-123">Lync Server 2013 est déployé dans une forêt unique, puis les utilisateurs sont répartis entre plusieurs forêts.</span><span class="sxs-lookup"><span data-stu-id="ebda7-123">Lync Server 2013 is deployed in a single forest, and then users are distributed across multiple forests.</span></span> <span data-ttu-id="ebda7-124">Les attributs de messagerie unifiée d’Exchange des utilisateurs doivent être répliqués sur la forêt Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ebda7-124">The users’ Exchange UM attributes must be replicated over to the Lync Server 2013 forest.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ebda7-125">Exchange peut être déployé dans plusieurs forêts.</span><span class="sxs-lookup"><span data-stu-id="ebda7-125">Exchange can be deployed in multiple forests.</span></span> <span data-ttu-id="ebda7-126">Chaque organisation Exchange peut fournir la messagerie unifiée Exchange à ses utilisateurs, ou le serveur de messagerie unifiée Exchange peut être déployé dans la même forêt que Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ebda7-126">Each Exchange organization can provide Exchange UM to its users, or Exchange UM can be deployed in the same forest as Lync Server 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

