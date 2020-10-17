---
title: Migrer le serveur de médiation
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87d1e9eaee83f4db6c1ca30cd143d62d45852988
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527521"
---
# <a name="migrate-mediation-server"></a><span data-ttu-id="eb05d-102">Migrer le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="eb05d-102">Migrate Mediation Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb05d-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="eb05d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="eb05d-104">Votre serveur de médiation est fusionné dans votre topologie pilote Lync Server 2013 lorsque vous exécutez l’Assistant Fusion et publipostage.</span><span class="sxs-lookup"><span data-stu-id="eb05d-104">Your Mediation Server is merged into your Lync Server 2013 pilot topology when you run the Merge wizard.</span></span> <span data-ttu-id="eb05d-105">Vous configurez le serveur de médiation Lync Server 2013, cependant, une fois tous les utilisateurs migrés, car un pool Office Communications Server 2007 R2 ne peut pas communiquer avec un serveur de médiation Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eb05d-105">You configure the Lync Server 2013 Mediation Server, however, after all users are migrated because an Office Communications Server 2007 R2 pool cannot communicate with a Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="eb05d-106">Lors de la migration côte à côte, le pool Lync Server 2013 communique avec le serveur de médiation Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="eb05d-106">During the side-by-side migration, the Lync Server 2013 pool communicates with the Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="eb05d-107">Lorsque vous configurez votre serveur de médiation Lync Server 2013, vous devez également mettre à niveau ou remplacer vos passerelles Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="eb05d-107">When you configure your Lync Server 2013 Mediation Server, you must also upgrade or replace your Office Communications Server 2007 R2 gateways.</span></span> <span data-ttu-id="eb05d-108">Les passerelles Office Communications Server 2007 R2 ne prennent pas en charge le serveur de médiation Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eb05d-108">Office Communications Server 2007 R2 gateways do not support Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="eb05d-109">Vous devez déployer des passerelles certifiées pour Lync Server 2013 et les associer au serveur de médiation Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eb05d-109">You need to deploy gateways that are certified for Lync Server 2013 and associate them with the Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="eb05d-110">Cette étape est requise pour pouvoir désaffecter entièrement votre déploiement d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="eb05d-110">This step is required before you can completely decommission your Office Communications Server 2007 R2 deployment.</span></span>

<span data-ttu-id="eb05d-111">Les rubriques de cette section décrivent les tâches de configuration que vous devez effectuer une fois que vous avez terminé la migration du serveur de médiation Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eb05d-111">The topics in this section describe configuration tasks that you need to perform after you have completed your migration of Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="eb05d-112">La transition du serveur de médiation colocalisé vers un serveur de médiation autonome est une tâche facultative.</span><span class="sxs-lookup"><span data-stu-id="eb05d-112">Transitioning the collocated Mediation Server to a stand-alone Mediation Server is an optional task.</span></span>

  - [<span data-ttu-id="eb05d-113">Configurer le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="eb05d-113">Configure Mediation Server</span></span>](configure-mediation-server.md)

  - [<span data-ttu-id="eb05d-114">Modifier les itinéraires de communications vocales pour utiliser le nouveau serveur de médiation Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb05d-114">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [<span data-ttu-id="eb05d-115">Transition d’un serveur de médiation colocalisé à un serveur de médiation autonome (facultatif)</span><span class="sxs-lookup"><span data-stu-id="eb05d-115">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

