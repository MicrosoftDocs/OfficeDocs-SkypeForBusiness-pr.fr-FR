---
title: 'Lync Server 2013 : configuration des plateformes système'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59aafcda7cbe94401cdbd77479eecf38e3e9e351
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a><span data-ttu-id="19cf3-102">Configuration des plateformes système dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19cf3-102">Set up system platforms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19cf3-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="19cf3-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="19cf3-104">Avant de commencer le déploiement du serveur de conversation permanente, vous devez installer le système d’exploitation requis sur le matériel qui répond à la configuration système requise sur les serveurs :</span><span class="sxs-lookup"><span data-stu-id="19cf3-104">Before starting the deployment of Persistent Chat Server, you must install the required operating system on hardware that meets system requirements on servers:</span></span>

<span data-ttu-id="19cf3-105">Pour plus d’informations sur le matériel pris en charge pour les serveurs exécutant Lync Server 2013, les serveurs de bases de données et les serveurs de fichiers, voir [matériel pris en charge pour Lync server 2013](lync-server-2013-supported-hardware.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="19cf3-105">For details about supported hardware for servers running Lync Server 2013, database servers, and file servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span> <span data-ttu-id="19cf3-106">Pour plus d’informations sur les systèmes d’exploitation et les logiciels de base de données pris en charge, voir [Server Software and Infrastructure Support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="19cf3-106">For details about supported operating systems and database software, see [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="19cf3-107">Pour plus d’informations sur la configuration requise pour Windows Update, voir [prise en charge et configuration requise des serveurs supplémentaires dans Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="19cf3-107">For details about Windows update requirements, see [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md) in the Supportability documentation.</span></span>

<span data-ttu-id="19cf3-108">Le serveur frontal de serveur de conversation permanente **PersistentChatService**peut être déployé sur un ou plusieurs ordinateurs autonomes dans un pool Lync Server 2013 Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="19cf3-108">The Persistent Chat Server Front End Server, **PersistentChatService**, can be deployed on one or more stand-alone computers in a Lync Server 2013 Enterprise Edition pool.</span></span> <span data-ttu-id="19cf3-109">Elles ne peuvent pas être colocalisées sur les serveurs frontaux Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="19cf3-109">They cannot be collocated on the Lync Server Enterprise Edition Front End Servers.</span></span> <span data-ttu-id="19cf3-110">Le serveur de conversation permanente peut être déployé par le programme d’amorçage, comme d’autres rôles Lync Server.</span><span class="sxs-lookup"><span data-stu-id="19cf3-110">Persistent Chat Server can be deployed by the Bootstrapper, just like other Lync Server roles.</span></span> <span data-ttu-id="19cf3-111">Les **services Web de conversation permanente pour le chargement/téléchargement de fichiers**et les **services Web de conversation permanente pour la gestion des salles de conversation** sont des composants Web déployés sur les serveurs frontaux Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="19cf3-111">The **Persistent Chat Web Services for File Upload/Download**, and **Persistent Chat Web Services for Chat Room Management** are web components deployed on the Lync Server 2013 Front End Servers.</span></span>

<span data-ttu-id="19cf3-112">Un seul serveur frontal de serveur de conversation permanente peut prendre en charge 20 000 utilisateurs actifs.</span><span class="sxs-lookup"><span data-stu-id="19cf3-112">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="19cf3-113">Vous pouvez disposer d’un pool de serveurs de conversation permanente avec jusqu’à 4 serveurs frontaux actifs prenant en charge un total de 80 000 utilisateurs simultanés.</span><span class="sxs-lookup"><span data-stu-id="19cf3-113">You can have a Persistent Chat Server pool with up to 4 active front ends supporting a total of 80,000 concurrent users.</span></span> <span data-ttu-id="19cf3-114">Le serveur principal de conversation permanente **PersistentChatStore**, stocke les salles de conversation et les catégories.</span><span class="sxs-lookup"><span data-stu-id="19cf3-114">The Persistent Chat Back End Server, **PersistentChatStore**, stores the chat rooms and categories.</span></span> <span data-ttu-id="19cf3-115">Nous vous recommandons d’installer le **PersistentChatStore** sur un serveur principal SQL Server dédié dans votre pool Enterprise Edition ; Bien que nous prenons en charge colocaliser serveur principal et **PersistentChatStore** Lync Server 2013 sur la même instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="19cf3-115">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server in your Enterprise Edition pool; although we support collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance.</span></span>

<span data-ttu-id="19cf3-116">Si votre organisation a besoin d’une prise en charge de la conformité, vous pouvez l’installer à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="19cf3-116">If your organization requires compliance support, you can install it by using Topology Builder.</span></span> <span data-ttu-id="19cf3-117">Le service de conformité du serveur de conversation permanente est installé sur le même ordinateur que le serveur frontal de serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="19cf3-117">The Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="19cf3-118">Une base de données séparée est requise pour la conformité.</span><span class="sxs-lookup"><span data-stu-id="19cf3-118">A separate database is required for compliance.</span></span> <span data-ttu-id="19cf3-119">Pour plus d’informations sur les exigences de conformité pour le serveur de conversation permanente, voir [Planning for persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="19cf3-119">For details about compliance requirements for Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

<span data-ttu-id="19cf3-120">Chaque topologie requiert au minimum un serveur sur lequel Lync Server 2013 est installé et un serveur sur lequel le logiciel de base de données SQL Server est installé.</span><span class="sxs-lookup"><span data-stu-id="19cf3-120">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span> <span data-ttu-id="19cf3-121">Le générateur de topologie prend en charge plusieurs pools de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="19cf3-121">Topology Builder supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="19cf3-122">Suivez les mêmes instructions de déploiement pour le déploiement de plusieurs pools de serveurs de conversation permanente comme vous le feriez pour n’importe quel pool du [déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="19cf3-122">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool from [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="19cf3-123">Vous pouvez également déployer le serveur de conversation permanente avec Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="19cf3-123">You can also deploy Persistent Chat Server with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="19cf3-124">Dans ce cas, le serveur frontal **PersistentChatService** est colocalisé sur le serveur Standard Edition, et vous pouvez déployer le serveur principal **PersistentChatStore** sur l’instance SQL Server Express locale.</span><span class="sxs-lookup"><span data-stu-id="19cf3-124">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition server, and you can deploy the **PersistentChatStore** Back End Server on the local SQL Server Express instance.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="19cf3-125">Nous ne prenons pas en charge le&nbsp;serveur de conversation permanente pour la haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="19cf3-125">We do not support Persistent Chat Server&nbsp;Standard Edition for high availability.</span></span> <span data-ttu-id="19cf3-126">Les performances et l’évolutivité seraient limitées.</span><span class="sxs-lookup"><span data-stu-id="19cf3-126">Performance and scale will be limited.</span></span> <span data-ttu-id="19cf3-127">En outre, nous ne prenons en charge que&nbsp;les nouveaux déploiements de serveur de conversation permanente Server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="19cf3-127">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server deployments.</span></span> <span data-ttu-id="19cf3-128">Nous ne prenons pas en charge la mise à niveau de Lync Server 2010, Group Chat Server vers&nbsp;un serveur lync&nbsp;Server 2013 persistent Chat Server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="19cf3-128">We do not support an upgrade of Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="19cf3-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="19cf3-129">See Also</span></span>


[<span data-ttu-id="19cf3-130">Prise en charge supplémentaire des serveurs et configuration requise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19cf3-130">Additional server support and requirements in Lync Server 2013</span></span>](lync-server-2013-additional-server-support-and-requirements.md)  


[<span data-ttu-id="19cf3-131">Matériel pris en charge pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19cf3-131">Supported hardware for Lync Server 2013</span></span>](lync-server-2013-supported-hardware.md)  
[<span data-ttu-id="19cf3-132">Prise en charge du logiciel et de l’infrastructure serveur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19cf3-132">Server software and infrastructure support in Lync Server 2013</span></span>](lync-server-2013-server-software-and-infrastructure-support.md)  
[<span data-ttu-id="19cf3-133">Planification du serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19cf3-133">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
[<span data-ttu-id="19cf3-134">Déploiement de Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19cf3-134">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

