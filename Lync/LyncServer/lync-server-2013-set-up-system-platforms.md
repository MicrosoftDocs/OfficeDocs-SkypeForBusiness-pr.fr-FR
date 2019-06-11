---
title: 'Lync Server 2013 : Configuration des plateformes système'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 317bfe0efed0417d49cc59dc8f6e7ad3bcca7d7a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a><span data-ttu-id="12ea3-102">Configuration des plateformes système dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12ea3-102">Set up system platforms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12ea3-103">_**Dernière modification de la rubrique:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="12ea3-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="12ea3-104">Avant de démarrer le déploiement du serveur de chat permanent, vous devez installer le système d’exploitation requis sur le matériel qui répond à la configuration système requise sur les serveurs:</span><span class="sxs-lookup"><span data-stu-id="12ea3-104">Before starting the deployment of Persistent Chat Server, you must install the required operating system on hardware that meets system requirements on servers:</span></span>

<span data-ttu-id="12ea3-105">Pour plus d’informations sur le matériel pris en charge pour les serveurs exécutant Lync Server 2013, les serveurs de base de données et les serveurs de fichiers, voir [matériel compatible pour Lync server 2013](lync-server-2013-supported-hardware.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="12ea3-105">For details about supported hardware for servers running Lync Server 2013, database servers, and file servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span> <span data-ttu-id="12ea3-106">Pour plus d’informations sur les systèmes d’exploitation et les logiciels de base de données pris en charge, voir [prise en charge des logiciels et de l’infrastructure du serveur dans Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) dans la documentation de support technique.</span><span class="sxs-lookup"><span data-stu-id="12ea3-106">For details about supported operating systems and database software, see [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="12ea3-107">Pour plus d’informations sur la configuration requise pour Windows Update, voir [prise en charge supplémentaire du serveur et configuration requise dans Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md) dans la documentation relative à la prise en charge.</span><span class="sxs-lookup"><span data-stu-id="12ea3-107">For details about Windows update requirements, see [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md) in the Supportability documentation.</span></span>

<span data-ttu-id="12ea3-108">Le serveur frontal de chat permanent, **PersistentChatService**, peut être déployé sur un ou plusieurs ordinateurs autonomes dans un pool Lync Server 2013 Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="12ea3-108">The Persistent Chat Server Front End Server, **PersistentChatService**, can be deployed on one or more stand-alone computers in a Lync Server 2013 Enterprise Edition pool.</span></span> <span data-ttu-id="12ea3-109">Elles ne peuvent pas être colocalisées sur les serveurs frontaux Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="12ea3-109">They cannot be collocated on the Lync Server Enterprise Edition Front End Servers.</span></span> <span data-ttu-id="12ea3-110">Le serveur de chat permanent peut être déployé par le programme de démarrage, comme d’autres rôles serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="12ea3-110">Persistent Chat Server can be deployed by the Bootstrapper, just like other Lync Server roles.</span></span> <span data-ttu-id="12ea3-111">Les **services Web chat permanent pour la gestion du chargement/téléchargement de fichiers**, et les **services Web chat permanent pour la gestion des salles de conversation** sont des composants Web déployés sur les serveurs Front End de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12ea3-111">The **Persistent Chat Web Services for File Upload/Download**, and **Persistent Chat Web Services for Chat Room Management** are web components deployed on the Lync Server 2013 Front End Servers.</span></span>

<span data-ttu-id="12ea3-112">Un seul serveur frontal de chat permanent peut prendre en charge des utilisateurs actifs de 20 000.</span><span class="sxs-lookup"><span data-stu-id="12ea3-112">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="12ea3-113">Vous pouvez disposer d’un pool de serveurs de chat permanent comprenant jusqu’à 4 terminaisons actives prenant en charge un nombre total d’utilisateurs concurrents 80 000.</span><span class="sxs-lookup"><span data-stu-id="12ea3-113">You can have a Persistent Chat Server pool with up to 4 active front ends supporting a total of 80,000 concurrent users.</span></span> <span data-ttu-id="12ea3-114">Le serveur principal de chat permanent, **PersistentChatStore**, stocke les salles et les catégories de discussion.</span><span class="sxs-lookup"><span data-stu-id="12ea3-114">The Persistent Chat Back End Server, **PersistentChatStore**, stores the chat rooms and categories.</span></span> <span data-ttu-id="12ea3-115">Nous vous recommandons d’installer le **PersistentChatStore** sur un serveur principal SQL Server dédié dans votre pool Enterprise Edition. Bien que nous puissions prendre en charge le serveur principal collocating Lync Server 2013 et **PersistentChatStore** sur la même instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="12ea3-115">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server in your Enterprise Edition pool; although we support collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance.</span></span>

<span data-ttu-id="12ea3-116">Si votre organisation nécessite une prise en charge de la conformité, vous pouvez l’installer à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="12ea3-116">If your organization requires compliance support, you can install it by using Topology Builder.</span></span> <span data-ttu-id="12ea3-117">Le service de compatibilité de chat permanent du serveur est installé sur le même ordinateur que le serveur frontal de Chat Server permanent.</span><span class="sxs-lookup"><span data-stu-id="12ea3-117">The Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="12ea3-118">Une base de données distincte est requise pour la conformité.</span><span class="sxs-lookup"><span data-stu-id="12ea3-118">A separate database is required for compliance.</span></span> <span data-ttu-id="12ea3-119">Pour plus d’informations sur les exigences en matière de conformité pour le serveur de chat permanent, voir [planification du serveur de chat permanent dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="12ea3-119">For details about compliance requirements for Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

<span data-ttu-id="12ea3-120">Au minimum, chaque topologie nécessite un serveur sur lequel Lync Server 2013 est installé et un serveur sur lequel sont installés les logiciels de base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="12ea3-120">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span> <span data-ttu-id="12ea3-121">Le générateur de topologie prend en charge plusieurs pools de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="12ea3-121">Topology Builder supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="12ea3-122">Suivez les mêmes instructions de déploiement pour le déploiement de plusieurs pools de serveurs de chat permanent, comme vous le feriez pour n’importe quel pool de [déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="12ea3-122">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool from [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="12ea3-123">Vous pouvez également déployer le serveur de chat permanent avec Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="12ea3-123">You can also deploy Persistent Chat Server with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="12ea3-124">Dans ce cas, le serveur frontal **PersistentChatService** est colocalisé sur le serveur Standard Edition Server et vous pouvez déployer le serveur principal **PersistentChatStore** dans l’instance SQL Server Express locale.</span><span class="sxs-lookup"><span data-stu-id="12ea3-124">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition server, and you can deploy the **PersistentChatStore** Back End Server on the local SQL Server Express instance.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="12ea3-125">Nous ne prenons pas en charge le&nbsp;service Chat Server Standard Edition pour une haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="12ea3-125">We do not support Persistent Chat Server&nbsp;Standard Edition for high availability.</span></span> <span data-ttu-id="12ea3-126">Les performances et l’évolutivité seront limitées.</span><span class="sxs-lookup"><span data-stu-id="12ea3-126">Performance and scale will be limited.</span></span> <span data-ttu-id="12ea3-127">Par ailleurs, nous ne prenons en charge que&nbsp;de nouveaux déploiements de serveurs de chat permanent Server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="12ea3-127">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server deployments.</span></span> <span data-ttu-id="12ea3-128">Nous ne prenons pas en charge la mise à niveau de Lync Server 2010, Server Chat Server vers&nbsp;lync Server 2013&nbsp;permanent Chat Server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="12ea3-128">We do not support an upgrade of Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="12ea3-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="12ea3-129">See Also</span></span>


[<span data-ttu-id="12ea3-130">Autres prises en charge et configurations de serveur requises dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12ea3-130">Additional server support and requirements in Lync Server 2013</span></span>](lync-server-2013-additional-server-support-and-requirements.md)  


[<span data-ttu-id="12ea3-131">Matériel pris en charge pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12ea3-131">Supported hardware for Lync Server 2013</span></span>](lync-server-2013-supported-hardware.md)  
[<span data-ttu-id="12ea3-132">Prise en charge des infrastructures et des logiciels de serveur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12ea3-132">Server software and infrastructure support in Lync Server 2013</span></span>](lync-server-2013-server-software-and-infrastructure-support.md)  
[<span data-ttu-id="12ea3-133">Planification du serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12ea3-133">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
[<span data-ttu-id="12ea3-134">Déploiement de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12ea3-134">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

