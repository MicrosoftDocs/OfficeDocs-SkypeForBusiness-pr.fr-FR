---
title: 'Lync Server 2013 : Déploiement d’un serveur de conversation permanente'
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
ms.openlocfilehash: 7fe18bf750eabdb1f53c97a349b553da4f13dec8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740864"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="0c33f-102">Déploiement d’un serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c33f-102">Deploying Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c33f-103">_**Dernière modification de la rubrique :** 2014-03-31_</span><span class="sxs-lookup"><span data-stu-id="0c33f-103">_**Topic Last Modified:** 2014-03-31_</span></span>

<span data-ttu-id="0c33f-104">Lync Server 2013, permanent Chat Server fait partie de l’infrastructure Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0c33f-104">Lync Server 2013, Persistent Chat Server is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="0c33f-105">Le déploiement de Server chat permanent nécessite les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="0c33f-105">Deploying Persistent Chat Server requires that you:</span></span>

  - <span data-ttu-id="0c33f-106">Utilisez le générateur de topologie pour définir, importer et publier ultérieurement votre topologie et les composants que vous voulez déployer.</span><span class="sxs-lookup"><span data-stu-id="0c33f-106">Use Topology Builder to define, or import, and subsequently publish your topology and the components that you want to deploy.</span></span>

  - <span data-ttu-id="0c33f-107">Préparez votre environnement pour le déploiement de composants serveur Chat permanent.</span><span class="sxs-lookup"><span data-stu-id="0c33f-107">Prepare your environment for deploying Persistent Chat Server components.</span></span>

  - <span data-ttu-id="0c33f-108">Installez et configurez les composants serveur Chat permanent pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="0c33f-108">Install and configure Persistent Chat Server components for your deployment.</span></span>

<span data-ttu-id="0c33f-109">Le serveur Chat permanent est disponible avec Lync Server 2013 Enterprise Edition en tant que pool distinct (non localisé aux serveurs frontaux Enterprise Edition).</span><span class="sxs-lookup"><span data-stu-id="0c33f-109">Persistent Chat Server is available with Lync Server 2013 Enterprise Edition as a separate pool (not collocated with the Enterprise Edition Front End Servers).</span></span> <span data-ttu-id="0c33f-110">Le serveur Chat permanent nécessite un serveur principal SQL Server dans votre pool Enterprise Edition pour stocker le contenu de la salle de conversation et d’autres métadonnées pertinentes.</span><span class="sxs-lookup"><span data-stu-id="0c33f-110">Persistent Chat Server requires a SQL Server Back End Server in your Enterprise Edition pool to store the chat room content and other relevant metadata.</span></span> <span data-ttu-id="0c33f-111">Nous vous recommandons d’installer le **PersistentChatStore** sur un serveur principal SQL Server dédié, même si le serveur principal collocating Lync Server 2013 et **PersistentChatStore** sur la même instance SQL Server est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="0c33f-111">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server, although collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance is supported.</span></span>

<span data-ttu-id="0c33f-112">Le serveur de chat permanent peut également être déployé avec Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0c33f-112">Persistent Chat Server can also be deployed with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="0c33f-113">Dans ce cas, le serveur frontal **PersistentChatService** est colocalisé sur l’ordinateur Standard Edition, et le serveur principal **PersistentChatStore** peut être déployé dans l’instance SQL Server Express locale.</span><span class="sxs-lookup"><span data-stu-id="0c33f-113">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition computer, and the **PersistentChatStore** Back End Server can be deployed on the local SQL Server Express instance.</span></span>

<span data-ttu-id="0c33f-114">Pour plus d’informations sur les configurations de colocation prises en charge, voir [prise en charge de la colocalisation du serveur dans Lync server 2013](lync-server-2013-supported-server-collocation.md).</span><span class="sxs-lookup"><span data-stu-id="0c33f-114">For details about supported colocation configurations, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0c33f-115">Nous ne prenons pas en charge la haute disponibilité pour&nbsp;le service Chat Server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0c33f-115">We do not support high availability for Persistent Chat Server&nbsp;Standard Edition.</span></span> <span data-ttu-id="0c33f-116">Les performances et l’évolutivité seront limitées.</span><span class="sxs-lookup"><span data-stu-id="0c33f-116">Performance and scale will be limited.</span></span> <span data-ttu-id="0c33f-117">Par ailleurs, nous ne prenons en charge que&nbsp;le nouveau serveur de chat permanent Server Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="0c33f-117">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server.</span></span> <span data-ttu-id="0c33f-118">Nous ne prenons pas en charge la mise à niveau de Lync Server 2010, Server Chat Server&nbsp;vers lync Server&nbsp;2013 permanent Chat Server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0c33f-118">We do not support upgrading Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<span data-ttu-id="0c33f-119">Si votre organisation a besoin d’une prise en charge de la conformité, vous pouvez installer le service de compatibilité de chat serveur permanent sur le serveur frontal de chat permanent du serveur.</span><span class="sxs-lookup"><span data-stu-id="0c33f-119">If your organization requires compliance support, you can install the Persistent Chat Server Compliance service on the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="0c33f-120">Une base de données distincte est requise pour la conformité.</span><span class="sxs-lookup"><span data-stu-id="0c33f-120">A separate database is required for compliance.</span></span>

<span data-ttu-id="0c33f-121">Au minimum, chaque topologie nécessite un serveur sur lequel Lync Server 2013 est installé et un serveur sur lequel sont installés les logiciels de base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0c33f-121">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span>

<span data-ttu-id="0c33f-122">Utilisez le générateur de topologie pour ajouter le serveur de chat permanent aux déploiements de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0c33f-122">Use Topology Builder to add Persistent Chat Server to your Lync Server 2013 deployments.</span></span> <span data-ttu-id="0c33f-123">Vous avez la possibilité d’ajouter un ou plusieurs pools de serveurs de chat permanent à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="0c33f-123">You can choose to add one or more Persistent Chat Server pools using Topology Builder.</span></span> <span data-ttu-id="0c33f-124">Suivez les mêmes instructions de déploiement pour déployer plusieurs pools de serveurs de chat permanent que pour n’importe quel pool.</span><span class="sxs-lookup"><span data-stu-id="0c33f-124">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool.</span></span> <span data-ttu-id="0c33f-125">Pour plus d’informations, reportez-vous à [déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="0c33f-125">For details, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="0c33f-126">Pour plus d’informations sur les topologies disponibles et la configuration logicielle requise pour l’installation d’un serveur de chat permanent, voir [planification du serveur de chat permanent dans Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) dans la documentation de planification, fonctionnement du serveur Chat permanent dans lync Server [2013](lync-server-2013-how-persistent-chat-server-works.md) de la documentation de planification, de la documentation de déploiement ou de l’opération, et [matériel compatible pour Lync Server 2013](lync-server-2013-supported-hardware.md) dans la documentation de support</span><span class="sxs-lookup"><span data-stu-id="0c33f-126">For details about available topologies and the technical and software requirements for installing Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation, and [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

<span data-ttu-id="0c33f-127">Pour plus d’informations sur l’acquisition de certificats, la création de la base de données SQL Server et la création de magasins de fichiers, voir [déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="0c33f-127">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="0c33f-128">Un seul serveur frontal de chat permanent peut prendre en charge des utilisateurs actifs de 20 000.</span><span class="sxs-lookup"><span data-stu-id="0c33f-128">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="0c33f-129">Vous pouvez disposer d’un pool de serveurs de chat permanent comprenant jusqu’à 4 serveurs frontaux actifs prenant en charge un nombre total d’utilisateurs simultanés de 80 000.</span><span class="sxs-lookup"><span data-stu-id="0c33f-129">You can have a Persistent Chat Server pool with up to 4 active Front End Servers supporting a total of 80,000 concurrent users.</span></span>

<span data-ttu-id="0c33f-130">Le serveur Chat permanent est également pris en charge sur un serveur virtuel.</span><span class="sxs-lookup"><span data-stu-id="0c33f-130">Persistent Chat Server is also supported on a virtual server.</span></span> <span data-ttu-id="0c33f-131">Le serveur virtuel peut prendre en charge jusqu’à 20 000 utilisateurs simultanés s’il répond aux spécifications du serveur physique.</span><span class="sxs-lookup"><span data-stu-id="0c33f-131">The virtual server can support up to 20,000 concurrent users if it matches the specifications of the physical server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0c33f-132">Le serveur de chat permanent doit être installé sur un système de fichiers NTFS pour garantir la sécurité du système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="0c33f-132">Persistent Chat Server must be installed on an NTFS file system to help enforce file system security.</span></span> <span data-ttu-id="0c33f-133">FAT32 n’est pas un système de fichiers pris en charge pour le serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="0c33f-133">FAT32 is not a supported file system for Persistent Chat Server.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0c33f-134">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="0c33f-134">In This Section</span></span>

  - [<span data-ttu-id="0c33f-135">Fonctionnement du serveur Chat permanent dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c33f-135">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="0c33f-136">Liste de vérification du déploiement pour le serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c33f-136">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [<span data-ttu-id="0c33f-137">Configuration requise pour le serveur de chat permanent dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c33f-137">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="0c33f-138">Configuration des systèmes et de l’infrastructure pour le serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c33f-138">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="0c33f-139">Ajout d’un serveur de conversation permanente à votre déploiement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c33f-139">Adding Persistent Chat Server to your deployment in Lync Server 2013</span></span>](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [<span data-ttu-id="0c33f-140">Installation du serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c33f-140">Installing Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-installing-persistent-chat-server.md)

  - [<span data-ttu-id="0c33f-141">Ajout d’un administrateur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c33f-141">Adding a Persistent Chat administrator in Lync Server 2013</span></span>](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [<span data-ttu-id="0c33f-142">Configuration du serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c33f-142">Configuring Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server.md)

  - [<span data-ttu-id="0c33f-143">Configuration du serveur de conversation permanentte avec les applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c33f-143">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="0c33f-144">Résolution des problèmes de configuration d’un serveur de conversation permanente avec les applets de commande Windows PowerShell dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c33f-144">Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="0c33f-145">Configuration d’un serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c33f-145">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="0c33f-146">Basculement et restauration d’un serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c33f-146">Failing over and failing back Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

