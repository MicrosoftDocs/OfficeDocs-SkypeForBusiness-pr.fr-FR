---
title: 'Lync Server 2013: composants et topologies pour le serveur de chat permanent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for Persistent Chat Server
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48184420
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14ae22b2afed27109fb6e2c514211293cef42a46
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="94fac-102">Composants et topologies pour le serveur de chat permanent dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94fac-102">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94fac-103">_**Dernière modification de la rubrique:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="94fac-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="94fac-104">Le serveur Chat permanent prend en charge les configurations à serveur unique et les configurations à plusieurs serveurs.</span><span class="sxs-lookup"><span data-stu-id="94fac-104">Persistent Chat Server supports both single-server configurations and multiple-server configurations.</span></span> <span data-ttu-id="94fac-105">Le serveur de chat permanent peut également être exécuté sur un serveur Lync Server 2013 Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="94fac-105">Persistent Chat Server can also run on a Lync Server 2013 Standard Edition server.</span></span> <span data-ttu-id="94fac-106">Ces configurations se composent des topologies et composants serveur de chat permanent suivants.</span><span class="sxs-lookup"><span data-stu-id="94fac-106">These configurations consist of the following Persistent Chat Server components and topologies.</span></span>

<div>

## <a name="persistent-chat-server-components"></a><span data-ttu-id="94fac-107">Composants serveur de chat permanent</span><span class="sxs-lookup"><span data-stu-id="94fac-107">Persistent Chat Server Components</span></span>

<span data-ttu-id="94fac-108">Pour installer la dernière version de Chat Server, vous devez disposer des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="94fac-108">Installing the latest version of Persistent Chat Server requires the following components:</span></span>

  - <span data-ttu-id="94fac-109">Un ou plusieurs ordinateurs exécutant un serveur Chat permanent et fournissant les services suivants:</span><span class="sxs-lookup"><span data-stu-id="94fac-109">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
      - <span data-ttu-id="94fac-110">Service Chat permanent</span><span class="sxs-lookup"><span data-stu-id="94fac-110">Persistent Chat service</span></span>
    
      - <span data-ttu-id="94fac-111">Service de conformité, activé si la conformité est activée</span><span class="sxs-lookup"><span data-stu-id="94fac-111">Compliance service, which is turned on if compliance is enabled</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="94fac-112">Dans Lync Server 2013, les services Web chat permanent pour le chargement et le téléchargement de fichiers sont désormais colocalisés avec le serveur frontal de Lync Server 2013&nbsp;.</span><span class="sxs-lookup"><span data-stu-id="94fac-112">In Lync Server 2013, the Persistent Chat Web Services for File Upload/Download is now collocated with Lync Server 2013&nbsp;Front End Server.</span></span><BR><span data-ttu-id="94fac-113">Les services Web chat permanent pour la gestion des salles de conversation sont également colocalisés avec le serveur frontal Lync Server 2013&nbsp;.</span><span class="sxs-lookup"><span data-stu-id="94fac-113">The Persistent Chat Web Services for Chat Room Management is also collocated with Lync Server 2013&nbsp;Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="94fac-114">Serveur (s) (plusieurs serveurs si la mise en miroir est utilisée) qui héberge la base de données principale SQL Server pour l’hébergement de la base de données de contenu de conversation permanente où le contenu, les salles et les catégories de salle de conversation sont stockés.</span><span class="sxs-lookup"><span data-stu-id="94fac-114">Server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="94fac-115">La base de données principale stocke les données de l’historique des conversations, y compris les informations sur les catégories et les salles de conversation permanentes qui sont créées.</span><span class="sxs-lookup"><span data-stu-id="94fac-115">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span>

    
    </div>

  - <span data-ttu-id="94fac-116">Si la conformité a été activée, un ou plusieurs serveurs (serveur si la mise en miroir est utilisé) qui héberge la base de données principale SQL Server pour l’hébergement de la base de données de compatibilité des conversations permanentes, où les événements de conformité et le contenu des discussions sont stockés dans le cadre de la conformité.</span><span class="sxs-lookup"><span data-stu-id="94fac-116">If compliance was enabled, a server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>

<span data-ttu-id="94fac-117">Pour administrer le serveur de chat permanent depuis un autre ordinateur (par exemple, une console d’administration), utilisez le panneau de configuration de Lync Server sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="94fac-117">To administer Persistent Chat Server from a separate computer (such as an administrative console), use the Lync Server Control Panel on the computer.</span></span> <span data-ttu-id="94fac-118">Cet ordinateur doit ensuite être déployé dans un domaine AD FS (Active Directory Domain Services), avec au moins un serveur de catalogue global dans la racine de la forêt.</span><span class="sxs-lookup"><span data-stu-id="94fac-118">This computer must then be deployed in an Active Directory Domain Services domain, with at least one global catalog server in the forest root.</span></span>

<span data-ttu-id="94fac-119">Pour plus d’informations sur les configurations matérielles et logicielles requises pour le serveur de chat permanent, voir [configuration logicielle requise pour le serveur de chat permanent dans Lync server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [matériel compatible pour Lync Server 2013](lync-server-2013-supported-hardware.md), et [logiciels et infrastructure du serveur. la prise en charge de Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) dans la documentation relative à la prise en charge.</span><span class="sxs-lookup"><span data-stu-id="94fac-119">For details about hardware and software requirements for Persistent Chat Server, see [Technical requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md), and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="94fac-120">Colocalisation prises en charge</span><span class="sxs-lookup"><span data-stu-id="94fac-120">Supported Collocation</span></span>

<span data-ttu-id="94fac-121">Lync Server 2013 prend en charge un large éventail de scénarios de colocalisation, qui vous permettent de gagner en souplesse en exécutant plusieurs composants sur un serveur (si vous disposez d’une petite organisation) ou pour exécuter des composants individuels sur des serveurs différents (si vous disposez d’un compte grande organisation nécessitant une évolutivité et des performances optimales.</span><span class="sxs-lookup"><span data-stu-id="94fac-121">Lync Server 2013 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="94fac-122">Prenez en compte les facteurs d’évolutivité avant de décider de collocater ou non les composants.</span><span class="sxs-lookup"><span data-stu-id="94fac-122">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="94fac-123">Le service de Compliance chat permanent, si la conformité est activée, est colocalisé sur le serveur frontal de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94fac-123">The Persistent Chat Compliance service, if compliance is enabled, is collocated with the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="94fac-124">Le serveur de chat permanent peut être déployé sur un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="94fac-124">Persistent Chat Server can be deployed on the Standard Edition server.</span></span> <span data-ttu-id="94fac-125">Le serveur principal de chat de chat serveur et la base de données de conformité des conversations permanentes peuvent être colocalisées sur le serveur Standard Edition Server du serveur principal SQL Server Express local.</span><span class="sxs-lookup"><span data-stu-id="94fac-125">The Persistent Chat Server Back End Server and the Persistent Chat Compliance database can be collocated on the Standard Edition server on the local SQL Server Express Back End Server.</span></span> <span data-ttu-id="94fac-126">Pour plus d’informations sur les composants qui peuvent être colocalisés à partir de cet emplacement, voir [prise en charge de la coexistence du serveur dans Lync server 2013](lync-server-2013-supported-server-collocation.md) dans la documentation de support.</span><span class="sxs-lookup"><span data-stu-id="94fac-126">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="94fac-127">Pour Lync Server 2013 Enterprise Edition, les serveurs de chat permanent ne peuvent pas être colocalisés sur le serveur Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="94fac-127">For Lync Server 2013 Enterprise Edition, Persistent Chat Servers cannot be collocated on the Enterprise Edition server.</span></span> <span data-ttu-id="94fac-128">La base de données SQL Server pour le serveur de chat permanent peut être colocalisée avec la base de données serveur principal d’un pool frontal Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="94fac-128">The SQL Server database for Persistent Chat Server can be collocated with the Back End Server database of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="94fac-129">La base de données SQL Server pour la conformité à la conversation permanente peut également être colocalisée avec la base de données serveur dorsal d’un pool Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="94fac-129">The SQL Server database for Persistent Chat compliance can also be collocated with the Back End Server database of an Enterprise Edition pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="94fac-130">Le serveur qui héberge la base de données de chat permanent peut héberger d’autres bases de données.</span><span class="sxs-lookup"><span data-stu-id="94fac-130">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="94fac-131">Toutefois, si vous envisagez de collocating la base de données de chat persistante avec d’autres bases de données, n’ayez pas besoin d’augmenter la taille de la base de données de chat persistante.</span><span class="sxs-lookup"><span data-stu-id="94fac-131">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="94fac-132">C’est pourquoi nous vous déconseillons de collocating la base de données de chat persistante avec la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="94fac-132">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span>



</div>

<span data-ttu-id="94fac-133">Si vous collocate la base de données de chat permanent avec la base de données principale, vous pouvez utiliser une instance unique de SQL Server pour tout ou partie des bases de données, ou vous pouvez utiliser une instance distincte de SQL Server pour chaque base de données, avec la limite suivante:</span><span class="sxs-lookup"><span data-stu-id="94fac-133">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database, with the following limitation:</span></span>

  - <span data-ttu-id="94fac-134">Chaque instance de SQL Server peut contenir uniquement une seule base de données principale et une seule base de données de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="94fac-134">Each instance of SQL Server can contain only a single back-end database and a single Persistent Chat database.</span></span>

<span data-ttu-id="94fac-135">Pour plus d’informations sur la colocalisation de tous les rôles de serveur et bases de données, voir prise en charge de la colocalisation du [serveur dans Lync server 2013](lync-server-2013-supported-server-collocation.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="94fac-135">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="94fac-136">Topologies serveur de chat permanent</span><span class="sxs-lookup"><span data-stu-id="94fac-136">Persistent Chat Server Topologies</span></span>

<span data-ttu-id="94fac-137">Le serveur Chat permanent prend en charge les topologies suivantes:</span><span class="sxs-lookup"><span data-stu-id="94fac-137">Persistent Chat Server supports the following topologies:</span></span>

  - <span data-ttu-id="94fac-138">Lync Server 2013 Enterprise Edition serveur unique de chat serveur serveur principal</span><span class="sxs-lookup"><span data-stu-id="94fac-138">Lync Server 2013 Enterprise Edition single server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="94fac-139">Lync Server 2013 Enterprise Edition serveur multiserveur de chat permanent serveur serveur principal</span><span class="sxs-lookup"><span data-stu-id="94fac-139">Lync Server 2013 Enterprise Edition multiple server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="94fac-140">Lync Server 2013 Standard Edition Server avec SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="94fac-140">Lync Server 2013 Standard Edition server using SQL Server Express</span></span>

  - <span data-ttu-id="94fac-141">Lync Server 2013 Standard Edition Server et serveur de chat permanent sur un serveur distinct utilisant Standard Edition Server comme serveur de tronçon suivant.</span><span class="sxs-lookup"><span data-stu-id="94fac-141">Lync Server 2013 Standard Edition server and Persistent Chat Server on a separate server using Standard Edition server as the next hop server.</span></span>

<span data-ttu-id="94fac-142">Vous pouvez ajouter le serveur de chat permanent à votre déploiement de Lync Server 2013 à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="94fac-142">You can add Persistent Chat Server to your Lync Server 2013 deployment by using Topology Builder.</span></span> <span data-ttu-id="94fac-143">Vous pouvez ajouter un serveur unique ou un pool de serveurs de chat permanent multiples à votre topologie.</span><span class="sxs-lookup"><span data-stu-id="94fac-143">You can add a single server or a multiple server Persistent Chat Server pool to your topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="94fac-144">Après avoir créé un pool de serveurs de chat permanent avec un serveur unique à l’aide du générateur de topologie, vous ne pouvez pas ajouter de serveurs supplémentaires au pool.</span><span class="sxs-lookup"><span data-stu-id="94fac-144">After you create a Persistent Chat Server pool with a single server by using Topology Builder, you cannot add additional servers to the pool.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="94fac-145">Topologie à serveur unique</span><span class="sxs-lookup"><span data-stu-id="94fac-145">Single-Server Topology</span></span>

<span data-ttu-id="94fac-146">La configuration minimum et le déploiement le plus simple pour le serveur de chat permanent est une topologie de serveur frontal de chat permanent unique.</span><span class="sxs-lookup"><span data-stu-id="94fac-146">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="94fac-147">Ce déploiement nécessite un serveur unique exécutant chat permanent (qui exécute éventuellement le service de conformité, si la conformité est activée), un serveur qui héberge la base de données SQL Server et si la conformité est requise, la base de données SQL Server pour stocker le données de conformité.</span><span class="sxs-lookup"><span data-stu-id="94fac-147">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="94fac-148">Vous ne pouvez pas ajouter de serveurs supplémentaires à un pool de serveurs de chat permanent démarré comme déploiement d’un serveur unique dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="94fac-148">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="94fac-149">Nous vous recommandons d’utiliser la topologie de pool multiserveur, même si vous utilisez un serveur unique, afin que vous puissiez ajouter d’autres serveurs ultérieurement, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="94fac-149">We recommend using the multiple-server pool topology, even if you’re using a single server, so that you can add more servers later, if needed..</span></span>



</div>

<span data-ttu-id="94fac-150">La figure suivante montre tous les composants obligatoires et facultatifs d’une topologie pour un seul serveur frontal de chat permanent avec conformité.</span><span class="sxs-lookup"><span data-stu-id="94fac-150">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="94fac-151">**Serveur de chat permanent unique**</span><span class="sxs-lookup"><span data-stu-id="94fac-151">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="94fac-152">![Topologie de serveur unique avec service de conformité] (images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologie de serveur unique avec service de conformité")</span><span class="sxs-lookup"><span data-stu-id="94fac-152">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="94fac-153">Topologie de plusieurs serveurs</span><span class="sxs-lookup"><span data-stu-id="94fac-153">Multiple-Server Topology</span></span>

<span data-ttu-id="94fac-154">Afin d’offrir une plus grande capacité et une fiabilité accrue, vous pouvez déployer une topologie multiserveur, comme décrit dans [planification pour le serveur de chat permanent dans Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="94fac-154">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="94fac-155">La topologie multiserveur peut inclure jusqu’à quatre ordinateurs actifs exécutant chat permanent (les configurations de haute disponibilité et de récupération d’urgence peuvent prendre jusqu’à 8, mais seules quatre peuvent être actives et les quatre autres en veille).</span><span class="sxs-lookup"><span data-stu-id="94fac-155">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="94fac-156">Chaque serveur peut prendre en charge autant d’utilisateurs simultanés qu' 20 000, soit un total d' 80 000 utilisateurs simultanés connectés à un pool de serveurs de chat permanent doté de 4 serveurs.</span><span class="sxs-lookup"><span data-stu-id="94fac-156">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="94fac-157">Une topologie multiserveur est la même que celle de la topologie sur un serveur, à l’exception de l’hébergement de plusieurs serveurs et de la possibilité d’augmenter leur taille.</span><span class="sxs-lookup"><span data-stu-id="94fac-157">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="94fac-158">Plusieurs ordinateurs exécutant un serveur Chat permanent doivent résider dans le même domaine de services de domaine Active Directory que Lync Server et le service de conformité.</span><span class="sxs-lookup"><span data-stu-id="94fac-158">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="94fac-159">La figure suivante montre tous les composants d’une topologie multiserveur avec plusieurs ordinateurs exécutant une conversation permanente serveur, le service de conformité facultatif et une base de données de conformité séparée.</span><span class="sxs-lookup"><span data-stu-id="94fac-159">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="94fac-160">**Plusieurs serveurs de chat permanent**</span><span class="sxs-lookup"><span data-stu-id="94fac-160">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="94fac-161">![Topologie de plusieurs serveurs] (images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologie de plusieurs serveurs")</span><span class="sxs-lookup"><span data-stu-id="94fac-161">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="94fac-162">Les topologies à plusieurs serveurs permettent de regrouper les fonctionnalités des serveurs.</span><span class="sxs-lookup"><span data-stu-id="94fac-162">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="94fac-163">Dans un pool de serveurs, les services de chat permanent communiquent et partagent des données.</span><span class="sxs-lookup"><span data-stu-id="94fac-163">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="94fac-164">Par exemple, l’historique des discussions publié à l’origine dans un service de chat permanent est disponible à partir de n’importe quel service de chat permanent du système.</span><span class="sxs-lookup"><span data-stu-id="94fac-164">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="94fac-165">Un service de chat permanent peut accéder à un fichier téléchargé par le biais d’un service de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="94fac-165">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="94fac-166">Les utilisateurs peuvent se connecter à différents serveurs front-end serveur de chat permanent et communiquer entre eux.</span><span class="sxs-lookup"><span data-stu-id="94fac-166">Users can be connected to different Persistent Chat Server Front End Servers and can be chatting and communicating with each other.</span></span>

<span data-ttu-id="94fac-167">Le port TCP 8011 par défaut connecte un serveur à un pool de serveurs et est utilisé par le service de chat permanent pour communiquer entre eux ou à des fins d’administration.</span><span class="sxs-lookup"><span data-stu-id="94fac-167">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat service to communicate between themselves, or for administrative purposes.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

