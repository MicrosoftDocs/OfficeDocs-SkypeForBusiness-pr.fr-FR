---
title: 'Lync Server 2013 : déploiement d’un serveur de conversation permanente'
description: 'Lync Server 2013 : déploiement d’un serveur de conversation permanente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b85c0070ab4bcd60d80d57738c25daac1de4faf1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566090"
---
# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="e580c-103">Déploiement du serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e580c-103">Deploying Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e580c-104">_**Dernière modification de la rubrique :** 2014-03-31_</span><span class="sxs-lookup"><span data-stu-id="e580c-104">_**Topic Last Modified:** 2014-03-31_</span></span>

<span data-ttu-id="e580c-105">Lync Server 2013, le serveur de conversation permanente fait partie de l’infrastructure Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e580c-105">Lync Server 2013, Persistent Chat Server is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="e580c-106">Le déploiement du serveur de conversation permanente nécessite les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e580c-106">Deploying Persistent Chat Server requires that you:</span></span>

  - <span data-ttu-id="e580c-107">Utilisez le générateur de topologies pour définir ou importer et publier ultérieurement votre topologie et les composants que vous souhaitez déployer.</span><span class="sxs-lookup"><span data-stu-id="e580c-107">Use Topology Builder to define, or import, and subsequently publish your topology and the components that you want to deploy.</span></span>

  - <span data-ttu-id="e580c-108">Préparez votre environnement pour le déploiement de composants de serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="e580c-108">Prepare your environment for deploying Persistent Chat Server components.</span></span>

  - <span data-ttu-id="e580c-109">Installez et configurez les composants de serveur de conversation permanente pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="e580c-109">Install and configure Persistent Chat Server components for your deployment.</span></span>

<span data-ttu-id="e580c-110">Le serveur de conversation permanente est disponible avec Lync Server 2013 Enterprise Edition en tant que pool distinct (non colocalisé avec les serveurs frontaux Enterprise Edition).</span><span class="sxs-lookup"><span data-stu-id="e580c-110">Persistent Chat Server is available with Lync Server 2013 Enterprise Edition as a separate pool (not collocated with the Enterprise Edition Front End Servers).</span></span> <span data-ttu-id="e580c-111">Le serveur de conversation permanente nécessite un serveur principal SQL Server dans votre pool Enterprise Edition pour stocker le contenu de la salle de conversation et d’autres métadonnées pertinentes.</span><span class="sxs-lookup"><span data-stu-id="e580c-111">Persistent Chat Server requires a SQL Server Back End Server in your Enterprise Edition pool to store the chat room content and other relevant metadata.</span></span> <span data-ttu-id="e580c-112">Nous vous recommandons d’installer le **PersistentChatStore** sur un serveur principal SQL Server dédié, bien que colocaliser serveur principal et **PersistentChatStore** Lync Server 2013 sur la même instance SQL Server soient pris en charge.</span><span class="sxs-lookup"><span data-stu-id="e580c-112">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server, although collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance is supported.</span></span>

<span data-ttu-id="e580c-113">Le serveur de conversation permanente peut également être déployé avec Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e580c-113">Persistent Chat Server can also be deployed with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="e580c-114">Dans ce cas, le serveur frontal **PersistentChatService** est colocalisé sur l’ordinateur Standard Edition et le serveur principal **PersistentChatStore** peut être déployé sur l’instance SQL Server Express locale.</span><span class="sxs-lookup"><span data-stu-id="e580c-114">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition computer, and the **PersistentChatStore** Back End Server can be deployed on the local SQL Server Express instance.</span></span>

<span data-ttu-id="e580c-115">Pour plus d’informations sur les configurations de géolocalisation prises en charge, voir [prise en charge de la colocalisation des serveurs dans Lync server 2013](lync-server-2013-supported-server-collocation.md).</span><span class="sxs-lookup"><span data-stu-id="e580c-115">For details about supported colocation configurations, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e580c-116">Nous ne prenons pas en charge la haute disponibilité pour le serveur de conversation permanente &nbsp; Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e580c-116">We do not support high availability for Persistent Chat Server&nbsp;Standard Edition.</span></span> <span data-ttu-id="e580c-117">Les performances et l’évolutivité seraient limitées.</span><span class="sxs-lookup"><span data-stu-id="e580c-117">Performance and scale will be limited.</span></span> <span data-ttu-id="e580c-118">Par ailleurs, nous prenons en charge uniquement le nouveau serveur de conversation permanente Server &nbsp; Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e580c-118">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server.</span></span> <span data-ttu-id="e580c-119">Nous ne prenons pas en charge la mise à niveau de Lync Server 2010, du serveur de conversation de groupe vers un serveur Lync Server 2013 &nbsp; persistent Chat Server &nbsp; Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e580c-119">We do not support upgrading Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<span data-ttu-id="e580c-120">Si votre organisation a besoin d’une prise en charge de la conformité, vous pouvez installer le service de conformité du serveur de conversation permanente sur le serveur frontal du serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="e580c-120">If your organization requires compliance support, you can install the Persistent Chat Server Compliance service on the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="e580c-121">Une base de données séparée est requise pour la conformité.</span><span class="sxs-lookup"><span data-stu-id="e580c-121">A separate database is required for compliance.</span></span>

<span data-ttu-id="e580c-122">Chaque topologie requiert au minimum un serveur sur lequel Lync Server 2013 est installé et un serveur sur lequel le logiciel de base de données SQL Server est installé.</span><span class="sxs-lookup"><span data-stu-id="e580c-122">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span>

<span data-ttu-id="e580c-123">Utilisez le générateur de topologie pour ajouter un serveur de conversation permanente à vos déploiements Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e580c-123">Use Topology Builder to add Persistent Chat Server to your Lync Server 2013 deployments.</span></span> <span data-ttu-id="e580c-124">Vous pouvez choisir d’ajouter un ou plusieurs pools de serveurs de conversation permanente à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="e580c-124">You can choose to add one or more Persistent Chat Server pools using Topology Builder.</span></span> <span data-ttu-id="e580c-125">Suivez les mêmes instructions de déploiement pour le déploiement de plusieurs pools de serveurs de conversation permanente comme vous le feriez pour n’importe quel pool.</span><span class="sxs-lookup"><span data-stu-id="e580c-125">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool.</span></span> <span data-ttu-id="e580c-126">Pour plus d’informations, voir [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) (contenu éventuellement en anglais) dans la documentation relative au déploiement.</span><span class="sxs-lookup"><span data-stu-id="e580c-126">For details, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e580c-127">Pour plus d’informations sur les topologies disponibles et les configurations techniques et logicielles requises pour l’installation du serveur de conversation permanente, voir [Planning for persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) dans la documentation de planification, [How the persistent Chat Server in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations, ainsi que le [matériel pris en charge pour Lync 2013 Server](lync-server-2013-supported-hardware.md)</span><span class="sxs-lookup"><span data-stu-id="e580c-127">For details about available topologies and the technical and software requirements for installing Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation, and [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

<span data-ttu-id="e580c-128">Pour plus d’informations sur l’acquisition de certificats, la création de la base de données SQL Server et la création de magasins de fichiers, voir [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="e580c-128">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e580c-129">Un seul serveur frontal de serveur de conversation permanente peut prendre en charge 20 000 utilisateurs actifs.</span><span class="sxs-lookup"><span data-stu-id="e580c-129">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="e580c-130">Vous pouvez disposer d’un pool de serveurs de conversation permanente avec jusqu’à 4 serveurs frontaux actifs prenant en charge un total de 80 000 utilisateurs simultanés.</span><span class="sxs-lookup"><span data-stu-id="e580c-130">You can have a Persistent Chat Server pool with up to 4 active Front End Servers supporting a total of 80,000 concurrent users.</span></span>

<span data-ttu-id="e580c-131">Le serveur de conversation permanente est également pris en charge sur un serveur virtuel.</span><span class="sxs-lookup"><span data-stu-id="e580c-131">Persistent Chat Server is also supported on a virtual server.</span></span> <span data-ttu-id="e580c-132">Le serveur virtuel peut prendre en charge jusqu’à 20 000 utilisateurs simultanés s’il respecte les spécifications du serveur physique.</span><span class="sxs-lookup"><span data-stu-id="e580c-132">The virtual server can support up to 20,000 concurrent users if it matches the specifications of the physical server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e580c-133">Le serveur de conversation permanente doit être installé sur un système de fichiers NTFS pour renforcer la sécurité du système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="e580c-133">Persistent Chat Server must be installed on an NTFS file system to help enforce file system security.</span></span> <span data-ttu-id="e580c-134">FAT32 n’est pas un système de fichiers pris en charge pour le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="e580c-134">FAT32 is not a supported file system for Persistent Chat Server.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e580c-135">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="e580c-135">In This Section</span></span>

  - [<span data-ttu-id="e580c-136">Fonctionnement du serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e580c-136">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="e580c-137">Liste de vérification du déploiement pour le serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e580c-137">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [<span data-ttu-id="e580c-138">Configuration technique requise pour le serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e580c-138">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="e580c-139">Configuration des systèmes et de l’infrastructure pour le serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e580c-139">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="e580c-140">Ajout d’un serveur de conversation permanente à votre déploiement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e580c-140">Adding Persistent Chat Server to your deployment in Lync Server 2013</span></span>](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [<span data-ttu-id="e580c-141">Installation du serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e580c-141">Installing Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-installing-persistent-chat-server.md)

  - [<span data-ttu-id="e580c-142">Ajout d’un administrateur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e580c-142">Adding a Persistent Chat administrator in Lync Server 2013</span></span>](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [<span data-ttu-id="e580c-143">Configuration du serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e580c-143">Configuring Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server.md)

  - [<span data-ttu-id="e580c-144">Configuration du serveur de conversation permanente à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e580c-144">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="e580c-145">Résolution des problèmes de configuration du serveur de conversation permanente à l’aide des applets de commande Windows PowerShell dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e580c-145">Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="e580c-146">Configuration du serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e580c-146">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="e580c-147">Basculement et restauration d’un serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e580c-147">Failing over and failing back Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

