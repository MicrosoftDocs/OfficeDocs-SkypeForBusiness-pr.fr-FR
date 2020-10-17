---
title: 'Lync Server 2013 : composants et topologies pour le serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Persistent Chat Server
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48184420
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 586a24f4cfacd2ed28947102a7d5a129159a26bd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502501"
---
# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="c3309-102">Composants et topologies pour le serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3309-102">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3309-103">_**Dernière modification de la rubrique :** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="c3309-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="c3309-104">Le serveur de conversation permanente prend en charge les configurations à serveur unique et les configurations à plusieurs serveurs.</span><span class="sxs-lookup"><span data-stu-id="c3309-104">Persistent Chat Server supports both single-server configurations and multiple-server configurations.</span></span> <span data-ttu-id="c3309-105">Le serveur de conversation permanente peut également être exécuté sur un serveur Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c3309-105">Persistent Chat Server can also run on a Lync Server 2013 Standard Edition server.</span></span> <span data-ttu-id="c3309-106">Ces configurations sont constituées des topologies et des composants de serveur de conversation permanente suivants.</span><span class="sxs-lookup"><span data-stu-id="c3309-106">These configurations consist of the following Persistent Chat Server components and topologies.</span></span>

<div>

## <a name="persistent-chat-server-components"></a><span data-ttu-id="c3309-107">Composants de serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="c3309-107">Persistent Chat Server Components</span></span>

<span data-ttu-id="c3309-108">L’installation de la dernière version du serveur de conversation permanente nécessite les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="c3309-108">Installing the latest version of Persistent Chat Server requires the following components:</span></span>

  - <span data-ttu-id="c3309-109">Un ou plusieurs ordinateurs exécutant le serveur de conversation permanente et fournissant les services suivants :</span><span class="sxs-lookup"><span data-stu-id="c3309-109">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
      - <span data-ttu-id="c3309-110">Service de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="c3309-110">Persistent Chat service</span></span>
    
      - <span data-ttu-id="c3309-111">Service de conformité, qui est activé si la conformité est activée</span><span class="sxs-lookup"><span data-stu-id="c3309-111">Compliance service, which is turned on if compliance is enabled</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c3309-112">Dans Lync Server 2013, les services Web de conversation permanente pour le chargement/téléchargement de fichiers sont colocalisés avec le serveur frontal Lync Server 2013 &nbsp; .</span><span class="sxs-lookup"><span data-stu-id="c3309-112">In Lync Server 2013, the Persistent Chat Web Services for File Upload/Download is now collocated with Lync Server 2013&nbsp;Front End Server.</span></span><BR><span data-ttu-id="c3309-113">Les services Web de conversation permanente pour la gestion des salles de conversation sont également colocalisés avec le serveur frontal Lync Server 2013 &nbsp; .</span><span class="sxs-lookup"><span data-stu-id="c3309-113">The Persistent Chat Web Services for Chat Room Management is also collocated with Lync Server 2013&nbsp;Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="c3309-114">Serveur (s) (plus d’un serveur en cas d’utilisation de la mise en miroir) qui héberge la base de données principale SQL Server pour héberger la base de données de contenu de conversation permanente où sont stockées le contenu, les salles et les catégories de la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="c3309-114">Server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c3309-115">La base de données principale stocke des données d’historique de conversation, notamment des informations sur les catégories et les salles de conversation permanente créées.</span><span class="sxs-lookup"><span data-stu-id="c3309-115">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span>

    
    </div>

  - <span data-ttu-id="c3309-116">Si la conformité a été activée, un ou plusieurs serveurs (plusieurs serveurs en cas d’utilisation de la mise en miroir) qui hébergent la base de données principale SQL Server pour héberger la base de données de conformité de la conversation permanente, dans lequel sont stockés les événements de conformité et le contenu de conversation à des fins de conformité.</span><span class="sxs-lookup"><span data-stu-id="c3309-116">If compliance was enabled, a server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>

<span data-ttu-id="c3309-117">Pour administrer le serveur de conversation permanente à partir d’un ordinateur distinct (tel qu’une console d’administration), utilisez le panneau de configuration Lync Server sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c3309-117">To administer Persistent Chat Server from a separate computer (such as an administrative console), use the Lync Server Control Panel on the computer.</span></span> <span data-ttu-id="c3309-118">Cet ordinateur doit ensuite être déployé dans un domaine des services de domaine Active Directory, avec au moins un serveur de catalogue global dans la racine de la forêt.</span><span class="sxs-lookup"><span data-stu-id="c3309-118">This computer must then be deployed in an Active Directory Domain Services domain, with at least one global catalog server in the forest root.</span></span>

<span data-ttu-id="c3309-119">Pour plus d’informations sur la configuration matérielle et logicielle requise pour le serveur de conversation permanente, voir [Technical Requirements for persistent Chat Server in Lync server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), supported [Hardware for Lync Server 2013](lync-server-2013-supported-hardware.md), and [Server Software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="c3309-119">For details about hardware and software requirements for Persistent Chat Server, see [Technical requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md), and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="c3309-120">Colocalisation prise en charge</span><span class="sxs-lookup"><span data-stu-id="c3309-120">Supported Collocation</span></span>

<span data-ttu-id="c3309-121">Lync Server 2013 prend en charge un grand nombre de scénarios de colocalisation, ce qui vous permet d’économiser les coûts matériels en exécutant plusieurs composants sur un seul serveur (si vous avez une petite organisation) ou pour exécuter des composants individuels sur des serveurs différents (si votre organisation est de grande taille qui a besoin d’une évolutivité et de performances).</span><span class="sxs-lookup"><span data-stu-id="c3309-121">Lync Server 2013 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="c3309-122">Vous devez considérer les facteurs d’extensibilité avant de décider si vous allez colocaliser des composants.</span><span class="sxs-lookup"><span data-stu-id="c3309-122">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="c3309-123">Le service de conformité de conversation permanente, si la conformité est activée, est colocalisé avec le serveur frontal Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c3309-123">The Persistent Chat Compliance service, if compliance is enabled, is collocated with the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="c3309-124">Le serveur de conversation permanente peut être déployé sur le serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c3309-124">Persistent Chat Server can be deployed on the Standard Edition server.</span></span> <span data-ttu-id="c3309-125">Le serveur principal du serveur de conversation permanente et la base de données de conformité de conversation permanente peuvent être colocalisés sur le serveur Standard Edition Server sur le serveur principal SQL Server Express local.</span><span class="sxs-lookup"><span data-stu-id="c3309-125">The Persistent Chat Server Back End Server and the Persistent Chat Compliance database can be collocated on the Standard Edition server on the local SQL Server Express Back End Server.</span></span> <span data-ttu-id="c3309-126">Pour plus d’informations sur les composants qui peuvent être colocalisés, voir [prise en charge de la colocalisation des serveurs dans Lync server 2013](lync-server-2013-supported-server-collocation.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="c3309-126">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="c3309-127">Pour Lync Server 2013 Enterprise Edition, les serveurs de conversation permanente ne peuvent pas être colocalisés sur le serveur Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="c3309-127">For Lync Server 2013 Enterprise Edition, Persistent Chat Servers cannot be collocated on the Enterprise Edition server.</span></span> <span data-ttu-id="c3309-128">La base de données SQL Server pour le serveur de conversation permanente peut être colocalisée avec la base de données du serveur principal d’un pool frontal Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="c3309-128">The SQL Server database for Persistent Chat Server can be collocated with the Back End Server database of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="c3309-129">La base de données SQL Server pour la conformité de la conversation permanente peut également être colocalisée avec la base de données du serveur principal d’un pool Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="c3309-129">The SQL Server database for Persistent Chat compliance can also be collocated with the Back End Server database of an Enterprise Edition pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c3309-130">Le serveur qui héberge la base de données de conversation permanente peut héberger d’autres bases de données.</span><span class="sxs-lookup"><span data-stu-id="c3309-130">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="c3309-131">Toutefois, lorsque vous considérez la base de données de conversation permanente avec d’autres bases de données, sachez que si vous stockez les messages de plus de quelques utilisateurs, l’espace disque nécessaire pour la base de données de conversation permanente peut augmenter considérablement.</span><span class="sxs-lookup"><span data-stu-id="c3309-131">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="c3309-132">Pour cette raison, nous vous déconseillons de colocaliser la base de données de conversation permanente avec la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="c3309-132">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span>



</div>

<span data-ttu-id="c3309-133">Si vous colocaliser la base de données de conversation permanente avec la base de données principale, vous pouvez utiliser une instance unique de SQL Server pour une partie ou l’ensemble des bases de données, ou vous pouvez utiliser une instance distincte de SQL Server pour chaque base de données, avec la limitation suivante :</span><span class="sxs-lookup"><span data-stu-id="c3309-133">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database, with the following limitation:</span></span>

  - <span data-ttu-id="c3309-134">Chaque instance de SQL Server ne peut contenir qu’une seule base de données principale et une seule base de données de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="c3309-134">Each instance of SQL Server can contain only a single back-end database and a single Persistent Chat database.</span></span>

<span data-ttu-id="c3309-135">Pour plus d’informations sur la colocalisation de tous les rôles serveur et bases de données, voir [prise en charge de la colocalisation des serveurs dans Lync server 2013](lync-server-2013-supported-server-collocation.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="c3309-135">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="c3309-136">Topologies de serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="c3309-136">Persistent Chat Server Topologies</span></span>

<span data-ttu-id="c3309-137">Le serveur de conversation permanente prend en charge les topologies suivantes :</span><span class="sxs-lookup"><span data-stu-id="c3309-137">Persistent Chat Server supports the following topologies:</span></span>

  - <span data-ttu-id="c3309-138">Lync Server 2013 Enterprise Edition serveur frontal de serveur de conversation permanente à serveur unique</span><span class="sxs-lookup"><span data-stu-id="c3309-138">Lync Server 2013 Enterprise Edition single server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="c3309-139">Lync Server 2013 Enterprise Edition serveur frontal de serveur de conversation permanente à plusieurs serveurs</span><span class="sxs-lookup"><span data-stu-id="c3309-139">Lync Server 2013 Enterprise Edition multiple server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="c3309-140">Serveur Lync Server 2013 Standard Edition avec SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="c3309-140">Lync Server 2013 Standard Edition server using SQL Server Express</span></span>

  - <span data-ttu-id="c3309-141">Serveur Lync Server 2013 Standard Edition et serveur de conversation permanente sur un serveur distinct utilisant le serveur Standard Edition comme serveur du tronçon suivant.</span><span class="sxs-lookup"><span data-stu-id="c3309-141">Lync Server 2013 Standard Edition server and Persistent Chat Server on a separate server using Standard Edition server as the next hop server.</span></span>

<span data-ttu-id="c3309-142">Vous pouvez ajouter un serveur de conversation permanente à votre déploiement Lync Server 2013 à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="c3309-142">You can add Persistent Chat Server to your Lync Server 2013 deployment by using Topology Builder.</span></span> <span data-ttu-id="c3309-143">Vous pouvez ajouter un serveur unique ou un pool de serveurs de conversation permanente de plusieurs serveurs à votre topologie.</span><span class="sxs-lookup"><span data-stu-id="c3309-143">You can add a single server or a multiple server Persistent Chat Server pool to your topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c3309-144">Une fois que vous avez créé un pool de serveurs de conversation permanente avec un seul serveur à l’aide du générateur de topologie, vous ne pouvez pas ajouter de serveurs supplémentaires au pool.</span><span class="sxs-lookup"><span data-stu-id="c3309-144">After you create a Persistent Chat Server pool with a single server by using Topology Builder, you cannot add additional servers to the pool.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="c3309-145">Topologie à serveur unique</span><span class="sxs-lookup"><span data-stu-id="c3309-145">Single-Server Topology</span></span>

<span data-ttu-id="c3309-146">La configuration minimale et le déploiement le plus simple pour le serveur de conversation permanente est une seule topologie de serveur frontal de serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="c3309-146">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="c3309-147">Ce déploiement nécessite un serveur unique qui exécute le serveur de conversation permanente (qui exécute éventuellement le service de conformité, si la conformité est activée), un serveur qui héberge la base de données SQL Server et, si la conformité est requise, la base de données SQL Server pour stocker les données de conformité.</span><span class="sxs-lookup"><span data-stu-id="c3309-147">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c3309-148">Vous ne pouvez pas ajouter d’autres serveurs à un pool de serveurs de conversation permanente qui est démarré en tant que déploiement à serveur unique dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="c3309-148">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="c3309-149">Nous vous recommandons d’utiliser la topologie de pool à plusieurs serveurs, même si vous utilisez un seul serveur, de manière à ce que vous puissiez ajouter d’autres serveurs par la suite si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="c3309-149">We recommend using the multiple-server pool topology, even if you’re using a single server, so that you can add more servers later, if needed..</span></span>



</div>

<span data-ttu-id="c3309-150">La figure suivante illustre tous les composants requis et facultatifs d’une topologie pour un seul serveur frontal de serveur de conversation permanente avec conformité.</span><span class="sxs-lookup"><span data-stu-id="c3309-150">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="c3309-151">**Serveur de conversations permanentes unique**</span><span class="sxs-lookup"><span data-stu-id="c3309-151">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="c3309-152">![Topologie à serveur unique avec service de conformité](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologie à serveur unique avec service de conformité")</span><span class="sxs-lookup"><span data-stu-id="c3309-152">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="c3309-153">Topologie à plusieurs serveurs</span><span class="sxs-lookup"><span data-stu-id="c3309-153">Multiple-Server Topology</span></span>

<span data-ttu-id="c3309-154">Pour augmenter la capacité et la fiabilité, vous pouvez déployer une topologie à plusieurs serveurs, comme décrit dans la rubrique [Planning for persistent Chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="c3309-154">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="c3309-155">La topologie à plusieurs serveurs peut inclure jusqu’à quatre ordinateurs actifs exécutant un serveur de conversation permanente (les configurations de haute disponibilité et de récupération d’urgence autorisent jusqu’à huit, mais seulement quatre peuvent être actives et les quatre autres en attente).</span><span class="sxs-lookup"><span data-stu-id="c3309-155">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="c3309-156">Chaque serveur peut prendre en charge jusqu’à 20 000 utilisateurs simultanés, soit un total de 80 000 utilisateurs simultanés connectés à un pool de serveurs de conversation permanente avec 4 serveurs.</span><span class="sxs-lookup"><span data-stu-id="c3309-156">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="c3309-157">Une topologie à plusieurs serveurs est identique à la topologie à serveur unique, à ceci près que plusieurs serveurs hébergent le serveur de conversation permanente et peuvent être plus évolutifs.</span><span class="sxs-lookup"><span data-stu-id="c3309-157">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="c3309-158">Plusieurs ordinateurs exécutant le serveur de conversation permanente doivent résider dans le même domaine des services de domaine Active Directory que Lync Server et le service de conformité.</span><span class="sxs-lookup"><span data-stu-id="c3309-158">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="c3309-159">La figure suivante illustre tous les composants d’une topologie à plusieurs serveurs avec plusieurs ordinateurs exécutant un serveur de conversation permanente, le service de conformité facultatif et une base de données de conformité distincte.</span><span class="sxs-lookup"><span data-stu-id="c3309-159">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="c3309-160">**Plusieurs serveurs de conversation permanente**</span><span class="sxs-lookup"><span data-stu-id="c3309-160">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="c3309-161">![Topologie à plusieurs serveurs](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologie à plusieurs serveurs")</span><span class="sxs-lookup"><span data-stu-id="c3309-161">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="c3309-162">Les topologies à plusieurs serveurs permettent de regrouper les fonctionnalités des serveurs.</span><span class="sxs-lookup"><span data-stu-id="c3309-162">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="c3309-163">Dans un pool de serveurs, les services de conversation permanente communiquent et partagent des données.</span><span class="sxs-lookup"><span data-stu-id="c3309-163">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="c3309-164">Par exemple, l’historique de la conversation qui a été initialement publié sur un service de conversation permanente est disponible à partir de n’importe quel service de conversation permanente dans le système.</span><span class="sxs-lookup"><span data-stu-id="c3309-164">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="c3309-165">Tout service de conversation permanente peut accéder à un fichier téléchargé via un service de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="c3309-165">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="c3309-166">Les utilisateurs peuvent être connectés à différents serveurs frontaux de serveur de conversation permanente et peuvent discuter et communiquer les uns avec les autres.</span><span class="sxs-lookup"><span data-stu-id="c3309-166">Users can be connected to different Persistent Chat Server Front End Servers and can be chatting and communicating with each other.</span></span>

<span data-ttu-id="c3309-167">Le port par défaut TCP 8011 connecte un serveur à un pool de serveurs et est utilisé par le service de conversation permanente pour communiquer entre eux ou à des fins administratives.</span><span class="sxs-lookup"><span data-stu-id="c3309-167">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat service to communicate between themselves, or for administrative purposes.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

