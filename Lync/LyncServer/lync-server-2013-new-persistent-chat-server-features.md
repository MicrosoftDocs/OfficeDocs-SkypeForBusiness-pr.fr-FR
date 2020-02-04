---
title: 'Lync Server 2013 : Nouvelles fonctionnalités du serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Persistent Chat Server features
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412965(v=OCS.15)
ms:contentKeyID: 48185341
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe207d2469a36d880e9ed519ff1d47d942ed79aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a><span data-ttu-id="0bc0d-102">Nouvelles fonctionnalités du serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bc0d-102">New Persistent Chat Server features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0bc0d-103">_**Dernière modification de la rubrique :** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="0bc0d-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="0bc0d-104">Lync Server 2013, Lync Chat Server vous permet de participer à des conversations à plusieurs sujets qui persistent dans le temps.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="0bc0d-105">Le serveur de chat permanent peut aider votre organisation à effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0bc0d-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="0bc0d-106">Amélioration de la communication entre les équipes géographiquement dispersées et celles à plusieurs fonctions</span><span class="sxs-lookup"><span data-stu-id="0bc0d-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="0bc0d-107">Élargissement de la sensibilisation et de la participation aux informations</span><span class="sxs-lookup"><span data-stu-id="0bc0d-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="0bc0d-108">Améliorer la communication avec votre organisation étendue</span><span class="sxs-lookup"><span data-stu-id="0bc0d-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="0bc0d-109">Réduire la surcharge d’information</span><span class="sxs-lookup"><span data-stu-id="0bc0d-109">Reduce information overload</span></span>

  - <span data-ttu-id="0bc0d-110">Amélioration de la prise en charge des informations</span><span class="sxs-lookup"><span data-stu-id="0bc0d-110">Improve information awareness</span></span>

  - <span data-ttu-id="0bc0d-111">Augmenter la dispersion des connaissances et informations importantes</span><span class="sxs-lookup"><span data-stu-id="0bc0d-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="0bc0d-112">Lync Server 2013, serveur de chat permanent, n’est pas disponible dans Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-112">Lync Server 2013, Persistent Chat Server is not available in Microsoft Office 365.</span></span> <span data-ttu-id="0bc0d-113">Pour le moment, il n’est disponible que pour les clients Lync 2013 locaux.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-113">At this time, it is available only to on-premise Lync 2013 customers.</span></span>

<span data-ttu-id="0bc0d-114">Dans Lync 2013, la fonctionnalité de chat permanent est intégrée au client 2013 de Lync.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-114">In Lync 2013, Persistent Chat functionality is integrated into the Lync 2013 client.</span></span> <span data-ttu-id="0bc0d-115">Par conséquent, les utilisateurs ont accès à la messagerie instantanée, à la présence, à l’audio/à la vidéo, aux conférences et aux discussions permanentes dans le client 2013 Lync.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-115">As a result, users have access to Instant Messaging/Presence, Audio/Video, Conferencing, and Persistent Chat all in the Lync 2013 client.</span></span> <span data-ttu-id="0bc0d-116">Pour plus d’informations sur le client 2013 Lync, <http://go.microsoft.com/fwlink/p/?linkid=270877>reportez-vous à la rubrique.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-116">For more information about the Lync 2013 client, see <http://go.microsoft.com/fwlink/p/?linkid=270877>.</span></span>

<span data-ttu-id="0bc0d-117">Cette rubrique décrit les modifications apportées aux fonctionnalités entre la nouvelle version de Lync Server 2013, le serveur de chat permanent et la version précédente (Microsoft Lync Server 2010, discussion de groupe), y compris :</span><span class="sxs-lookup"><span data-stu-id="0bc0d-117">This topic describes feature changes between the new version of Lync Server 2013, Persistent Chat Server and the previous version (Microsoft Lync Server 2010, Group Chat), including:</span></span>

  - <span data-ttu-id="0bc0d-118">Offrir une interface d’administration dans le panneau de configuration de Lync Server et éliminer l’outil d’administration de discussion de groupe</span><span class="sxs-lookup"><span data-stu-id="0bc0d-118">Provide an administrative experience in Lync Server Control Panel, and eliminate the Group Chat Admin Tool</span></span>

  - <span data-ttu-id="0bc0d-119">Intégrez les paramètres de configuration du serveur de chat permanent au générateur de topologie en éliminant l’outil de configuration des discussions de groupe.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-119">Integrate configuration settings for Persistent Chat Server into Topology Builder by eliminating the Group Chat Configuration tool</span></span>

  - <span data-ttu-id="0bc0d-120">Simplification de la migration et de la mise à niveau à partir de versions précédentes du serveur de chat permanent</span><span class="sxs-lookup"><span data-stu-id="0bc0d-120">Ease migration and upgrade from previous versions of Persistent Chat Server</span></span>

  - <span data-ttu-id="0bc0d-121">Fournir des solutions de haute disponibilité et de reprise après sinistre</span><span class="sxs-lookup"><span data-stu-id="0bc0d-121">Provide high availability and disaster recovery solutions</span></span>

<span data-ttu-id="0bc0d-122">Pour plus d’informations sur la dernière version de chat permanent, voir les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="0bc0d-122">For additional details about the latest version of Persistent Chat Server, see the following:</span></span>

  - <span data-ttu-id="0bc0d-123">Dans <http://go.microsoft.com/fwlink/p/?linkid=270945> cette rubrique, l’aide de la messagerie instantanée, qui fournit une liste détaillée des fonctionnalités de chat permanent, leur fonctionnement et la façon de les utiliser lorsque vous exécutez le serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-123">The Persistent Chat Help at <http://go.microsoft.com/fwlink/p/?linkid=270945> which provides a detailed list of Persistent Chat features, how they work, and how to use them while running Persistent Chat Server.</span></span>

  - <span data-ttu-id="0bc0d-124">[Planning pour le serveur de chat permanent dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) dans la documentation de planification, déploiement d’un [serveur de chat permanent dans Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) dans la documentation de déploiement, [migration à partir de Lync Server 2010, d’une conversation de groupe ou d’une conversation de groupe Office Communications Server 2007 R2 vers Lync Server 2013, serveur de messagerie persistante](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) dans la documentation de Migration et [gestion de Lync Server 2013](managing-lync-server-2013-persistent-chat-server.md) Serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-124">The [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation, [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) in the Migration documentation, and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) in the Operations documentation, all of which provide instructions for setting up Persistent Chat Server.</span></span>

  - <span data-ttu-id="0bc0d-125">Le fichier persistent Chat Server Documentation. msi (fichier Windows Installer) permet aux utilisateurs d’accéder à la documentation détaillée hors connexion sur le serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-125">The Persistent Chat Server Documentation.msi file (Windows Installer file) lets users access comprehensive offline documentation about Persistent Chat Server.</span></span>

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a><span data-ttu-id="0bc0d-126">Changements de topologie clés pour le serveur de chat permanent</span><span class="sxs-lookup"><span data-stu-id="0bc0d-126">Key Topology Changes for Persistent Chat Server</span></span>

<span data-ttu-id="0bc0d-127">Les modifications suivantes ont été apportées au serveur Chat permanent :</span><span class="sxs-lookup"><span data-stu-id="0bc0d-127">The following high-level changes for Persistent Chat Server include:</span></span>

<span data-ttu-id="0bc0d-128">Le serveur Chat permanent est désormais un rôle serveur.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-128">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="0bc0d-129">Dans Microsoft Lync Server 2010, le serveur de discussion de groupe était une application de confiance tierce pour Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-129">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="0bc0d-130">La conversation permanente peut être ajoutée à votre topologie Lync Server 2013 à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-130">Persistent Chat can be added to your Lync Server 2013 topology by using Topology Builder.</span></span> <span data-ttu-id="0bc0d-131">Dans Lync Server 2013, la fonctionnalité de serveur Chat permanent est implémentée en utilisant trois nouveaux rôles de serveur :</span><span class="sxs-lookup"><span data-stu-id="0bc0d-131">In Lync Server 2013, Persistent Chat Server functionality is implemented by using three new server roles:</span></span>

  - <span data-ttu-id="0bc0d-132">**PersistentChatService :** C’est le rôle frontal d’une conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-132">**PersistentChatService:** This is the front end role for Persistent Chat.</span></span> <span data-ttu-id="0bc0d-133">Dans les déploiements Standard Edition, le rôle de service de chat permanent du serveur est colocalisé sur le serveur Standard Edition déployé par le programme de démarrage, comme tout autre rôle serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-133">In Standard Edition deployments, Persistent Chat Server Service Role is collocated on the Standard Edition server deployed by Bootstrapper, like any other Lync Server role.</span></span> <span data-ttu-id="0bc0d-134">Dans les déploiements Enterprise Edition, le rôle service de chat permanent est déployé sur des ordinateurs autonomes par le programme de démarrage, comme tout autre rôle serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-134">In Enterprise Edition deployments, Persistent Chat Service Role is deployed on stand-alone computers by Bootstrapper, like any other Lync Server role.</span></span>

  - <span data-ttu-id="0bc0d-135">**PersistentChatStore :** Serveur principal qui correspond à la base de données de contenu de conversation permanente, dans laquelle se trouve tout le contenu de la discussion.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-135">**PersistentChatStore:** Back End Server that corresponds to the Persistent Chat content database, where all the chat content is stored.</span></span>

  - <span data-ttu-id="0bc0d-136">**PersistentChatComplianceStore :** Le rôle serveur principal qui correspond à la base de données de compatibilité des conversations permanentes, qui stocke tous les événements de conformité.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-136">**PersistentChatComplianceStore:** Back End Server role that corresponds to the Persistent Chat Compliance database, where all compliance events are stored.</span></span>

<span data-ttu-id="0bc0d-137">Ces rôles serveur de chat permanent sont facultatifs et installés uniquement par les clients qui ont besoin des fonctionnalités complètes du serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-137">These Persistent Chat Server roles are optional, and are installed only by customers who want comprehensive Persistent Chat Server functionality.</span></span> <span data-ttu-id="0bc0d-138">Le rôle **PersistentChatComplianceStore** est requis uniquement si vous choisissez de déployer la conformité à la conversation persistante.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-138">The **PersistentChatComplianceStore** role is needed only if you choose to deploy Persistent Chat Compliance.</span></span>

<span data-ttu-id="0bc0d-139">Le rôle **PersistentChatService** exécute deux services :</span><span class="sxs-lookup"><span data-stu-id="0bc0d-139">The **PersistentChatService** role runs two services:</span></span>

  - <span data-ttu-id="0bc0d-140">Service Chat permanent</span><span class="sxs-lookup"><span data-stu-id="0bc0d-140">Persistent Chat service</span></span>

  - <span data-ttu-id="0bc0d-141">Service de Compliance chat permanent</span><span class="sxs-lookup"><span data-stu-id="0bc0d-141">Persistent Chat Compliance service</span></span>

<span data-ttu-id="0bc0d-142">L’exécution de ces services sur chaque serveur de chat permanent fournit une disponibilité élevée pour ces services dans un pool de serveurs de chat permanent multiserveur.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-142">Having these services run on each Persistent Chat Server provides high availability for these services in a multiserver Persistent Chat Server pool.</span></span>

<span data-ttu-id="0bc0d-143">Par ailleurs, pour prendre en charge le chargement et le téléchargement de fichiers dans des salles de conversation permanentes, le serveur Chat permanent inclut un service Web.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-143">Additionally, to support the file upload and download in Persistent Chat rooms, Persistent Chat Server includes a web service.</span></span> <span data-ttu-id="0bc0d-144">Auparavant, ce service avait colocalisé sur le serveur de chat permanent, le serveur frontal et les services Internet (IIS) requis pour être installés comme condition préalable.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-144">Previously, this service was collocated on the Persistent Chat Server, Front End Server and required Internet Information Services (IIS) to be installed as a prerequisite.</span></span> <span data-ttu-id="0bc0d-145">Dans Lync Server 2013 persistent Chat Server, le service Web de chargement/téléchargement de fichiers est colocalisé avec le serveur frontal de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-145">In Lync Server 2013 Persistent Chat Server, the File Upload/Download web service is collocated with the Lync Server 2013 Front End Server.</span></span> <span data-ttu-id="0bc0d-146">Comme un effet secondaire, Internet Information Services (IIS) n’est plus indispensable pour le serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-146">As a side effect, Internet Information Services (IIS) is no longer a prerequisite for Persistent Chat Server.</span></span> <span data-ttu-id="0bc0d-147">Le service Web de chargement/téléchargement de fichier est identifié comme **PersistentChat** dans le gestionnaire des services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="0bc0d-147">The File Upload/Download web service is identified as **PersistentChat** in the Internet Information Services (IIS) Manager.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0bc0d-148">Le rôle <STRONG>PersistentChatService</STRONG> peut s’exécuter sur le même serveur qu’un serveur frontal&nbsp;Lync Server 2013 uniquement si ce serveur frontal est un serveur frontal standard&nbsp;Edition.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-148">The <STRONG>PersistentChatService</STRONG> role can run on the same server as a Lync Server 2013&nbsp;Front End Server only if that Front End Server is a Standard Edition&nbsp;Front End Server.</span></span> <span data-ttu-id="0bc0d-149">Le rôle <STRONG>PersistentChatService</STRONG> ne peut pas s’exécuter indépendamment d’un&nbsp;serveur frontal Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-149">The <STRONG>PersistentChatService</STRONG> role cannot run independently of a Lync Server 2013&nbsp;Front End Server.</span></span> <span data-ttu-id="0bc0d-150">Elle peut être installée uniquement dans le cadre d’un déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-150">It can be installed only in the context of a Lync Server 2013 deployment.</span></span>



</div>

<span data-ttu-id="0bc0d-151">Dans serveur Chat permanent, le service de recherche a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-151">In Persistent Chat Server, Lookup service has been eliminated.</span></span> <span data-ttu-id="0bc0d-152">Dans Lync Server 2010, les discussions de groupe, le service de recherche s’exécutait sur chaque serveur frontal du serveur de messagerie de groupe et effectuait le routage vers l’un des serveurs de canaux.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-152">In Lync Server 2010, Group Chat, the Lookup service ran on every Group Chat Server Front End Server, and performed routing to one of the Channel Servers.</span></span> <span data-ttu-id="0bc0d-153">Lync Server 2013 repose sur le routage à l’aide d’objets de contact dans lesquels chaque pool de serveurs de chat permanent est représenté par un objet de contact utilisé par les serveurs frontaux de Lync Server pour identifier et acheminer les demandes vers un pool de serveurs de chat permanent approprié l’un des ordinateurs exécutant une conversation permanente sur le pool.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-153">Lync Server 2013 relies on routing by using contact objects, where each Persistent Chat Server pool is represented by a contact object that is used by the Lync Server Front End Servers to identify and route requests to an appropriate Persistent Chat Server pool, and to one of the computers running Persistent Chat Server in the pool.</span></span>

<span data-ttu-id="0bc0d-154">Dans Lync Server 2013, il existe des modifications du service de conformité :</span><span class="sxs-lookup"><span data-stu-id="0bc0d-154">In Lync Server 2013, there are Compliance service modifications:</span></span>

  - <span data-ttu-id="0bc0d-155">Dans Lync Server 2010, le service de conformité s’est exécuté en mode autonome (non localisé), et sur un seul serveur.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-155">In Lync Server 2010, the Compliance service ran stand-alone (non-collocated), and only on a single server.</span></span> <span data-ttu-id="0bc0d-156">Le service de conformité est désormais exécuté sur tous les serveurs front-end serveur de chat permanent, en plus du service de chat permanent et fournit ainsi une haute disponibilité dans un pool de serveurs de chat permanent multiserveur.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-156">The Compliance service now runs on all the Persistent Chat Server Front End Servers, alongside the Persistent Chat service, and thereby provides high availability in a multiserver Persistent Chat Server pool.</span></span> <span data-ttu-id="0bc0d-157">Un seul adaptateur de conformité peut être configuré pour extraire les données de la base de données de conformité et dans l’un des autres systèmes (fichier XML, Archives hébergées sur Exchange, etc.).</span><span class="sxs-lookup"><span data-stu-id="0bc0d-157">A single compliance adapter can be configured to extract data from the compliance database and into one of the other systems (XML file, Exchange-hosted archives, and so on).</span></span> <span data-ttu-id="0bc0d-158">Le serveur Chat permanent inclut un adaptateur XML.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-158">Persistent Chat Server includes an XML adapter.</span></span>

  - <span data-ttu-id="0bc0d-159">La file d’attente Message Queuing (également appelée MSMQ) partagée par le service Chat permanent et le service de conformité sur chaque serveur frontal de Chat Server permanent est désormais une file d’attente privée uniquement partagée par les deux services.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-159">The Message Queuing (also known as MSMQ) queue that is shared by the Persistent Chat service and the Compliance service on each Persistent Chat Server Front End Server is now a private queue shared only by the two services.</span></span> <span data-ttu-id="0bc0d-160">Tous les services de conformité écrivent dans la même base de données de fin de conformité.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-160">All compliance services write to the same Compliance Back End database.</span></span> <span data-ttu-id="0bc0d-161">Ils sont également lus à partir de cette base de données afin d’envoyer les données à leur instance de la carte.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-161">They also all read from that database, for the purpose of sending the data to their instance of the adapter.</span></span> <span data-ttu-id="0bc0d-162">Le serveur principal de conformité est représenté en tant que nouveau rôle serveur principal.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-162">The Compliance Back End Server is represented as a new Back End Server role.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0bc0d-163">Comme dans les versions précédentes, toutes les données de conformité sont traitées une seule fois.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-163">As in previous versions, all compliance data is processed only once.</span></span> <span data-ttu-id="0bc0d-164">Les données sont traitées par l’une des instances d’adaptateur invoquées par le service de conformité exécuté sur les divers serveurs Lync Server 2013 et les ordinateurs serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-164">The data may be processed by any of the adapter instances invoked by the compliance service running on the various Lync Server 2013, Persistent Chat Server computers.</span></span> <span data-ttu-id="0bc0d-165">Dans serveur Chat permanent, l’une des instances de carte peut traiter les données.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-165">In Persistent Chat Server, any one of the adapter instances could process the data.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0bc0d-166">Pour plus d’informations sur l’installation de Message Queuing, voir <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">installation de systèmes d’exploitation et logiciels prérequis sur des serveurs pour Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-166">For information about installing Message Queuing, see <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Install operating systems and prerequisite software on servers for Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="0bc0d-167">Dans Lync Server 2013, il existe de nouvelles améliorations en matière de haute disponibilité et de récupération d’urgence :</span><span class="sxs-lookup"><span data-stu-id="0bc0d-167">In Lync Server 2013, there are improvements in both high availability and disaster recovery:</span></span>

  - <span data-ttu-id="0bc0d-168">Améliorations de la haute disponibilité : la mise en miroir SQL Server est utilisée pour fournir une haute disponibilité pour la base de données de contenu du serveur de chat permanent et la base de données de conformité des conversations permanentes au sein d’un centre de données (sur site).</span><span class="sxs-lookup"><span data-stu-id="0bc0d-168">High availability improvements: SQL Server mirroring is used to provide high availability for the Persistent Chat Server content database and Persistent Chat compliance database within a data center (in-site).</span></span>

  - <span data-ttu-id="0bc0d-169">Amélioration de la reprise après sinistre : le serveur Chat permanent prend en charge une architecture de réserve étirée qui permet d’étendre un pool unique de serveurs de chat permanent sur deux sites (c’est-à-dire un pool logique unique dans la topologie, avec les serveurs du pool physiquement situés sur deux sites).</span><span class="sxs-lookup"><span data-stu-id="0bc0d-169">Disaster recovery improvements: Persistent Chat Server supports a stretched pool architecture that enables a single Persistent Chat Server pool to be stretched across two sites (that is, a single logical pool in the topology, with servers in the pool physically located across two sites).</span></span> <span data-ttu-id="0bc0d-170">L’expédition du journal SQL Server est utilisée pour une reprise après sinistre entre sites.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-170">SQL Server Log Shipping is used for cross-site disaster recovery.</span></span>

<span data-ttu-id="0bc0d-171">Pour plus d’informations sur la haute disponibilité et la reprise après sinistre, voir [configurer le serveur de chat permanent pour une haute disponibilité et une reprise après sinistre dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-171">For more information about high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a><span data-ttu-id="0bc0d-172">Modifications de l’administration et de la gestion des clés pour le serveur de chat permanent</span><span class="sxs-lookup"><span data-stu-id="0bc0d-172">Key Administration and Management Changes for Persistent Chat Server</span></span>

<span data-ttu-id="0bc0d-173">Lync Server 2013 a facilité l’administration et la gestion du serveur de chat permanent grâce aux éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="0bc0d-173">Lync Server 2013 has made it easier to administer and manage Persistent Chat Server by providing:</span></span>

  - <span data-ttu-id="0bc0d-174">Administration et gestion unifiées.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-174">Unified administration and management.</span></span> <span data-ttu-id="0bc0d-175">Lync Server 2013 simplifie la gestion et l’administration du serveur de chat permanent en utilisant des outils déjà familiers pour les administrateurs Lync.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-175">Lync Server 2013 makes it easier to manage and administer Persistent Chat Server by using tools that are already familiar to Lync administrators.</span></span> <span data-ttu-id="0bc0d-176">Le serveur Chat permanent inclut une interface utilisateur d’administration intégrée au panneau de configuration de Lync Server, qui permet de résoudre les problèmes de performances liés aux versions précédentes de l’interface utilisateur du serveur de conversation de groupe.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-176">Persistent Chat Server includes an administrative user interface experience that is integrated with the Lync Server Control Panel, which addresses performance issues with the previous versions of the Group Chat Server user interface.</span></span> <span data-ttu-id="0bc0d-177">Par ailleurs, le serveur Chat permanent inclut une collection d’applets de dialogue Windows PowerShell permettant d’administrer et de gérer les catégories serveur de chat permanent, des salles de conversation permanentes (y compris la suppression de salles et la suppression du contenu obsolète) et des compléments.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-177">Also, Persistent Chat Server includes a collection of Windows PowerShell cmdlets to administer and manage Persistent Chat Server categories, Persistent Chat Server rooms (including deleting rooms and purging obsolete content), and add-ins.</span></span>

  - <span data-ttu-id="0bc0d-178">Modèle d’administration simplifié.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-178">Simplified administration model.</span></span> <span data-ttu-id="0bc0d-179">Lync Server 2013 a changé et simplifié le modèle de serveur de chat permanent en répondant à la configuration requise pour les clients suivants :</span><span class="sxs-lookup"><span data-stu-id="0bc0d-179">Lync Server 2013 has changed and simplified the Persistent Chat Server model by addressing the following key customer requirements:</span></span>
    
      - <span data-ttu-id="0bc0d-180">Supprimez les hiérarchies imbriquées complexes d’étendues et de catégories.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-180">Remove the complex nested hierarchies of scopes and categories.</span></span>
    
      - <span data-ttu-id="0bc0d-181">La prise en charge de la définition de listes de refus ainsi que des listes autorisées (étendues) pour les clients MindAlign actuels qui envisagent de migrer vers un serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-181">Support to define deny lists as well as allowed lists (scopes) for current MindAlign customers who are planning to migrate to Persistent Chat Server.</span></span>

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a><span data-ttu-id="0bc0d-182">Quels sont les différences en ce qui concerne les rôles d’utilisateur dans les versions précédentes du serveur de discussion de groupe ?</span><span class="sxs-lookup"><span data-stu-id="0bc0d-182">What’s Different about User Roles from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="0bc0d-183">Lync Server 2010, une discussion de groupe possédant un rôle d’administrateur d’utilisateur, un rôle d’administrateur de salle de conversation et un rôle d’administrateur de Lync Server pouvant gérer les compléments. le serveur de conversation permanent fournit simplement un rôle d’administrateur de chat permanent (similaire à celui d’une autre Lync). Rôles de contrôle d’accès basés sur le rôle serveur (RBAC).</span><span class="sxs-lookup"><span data-stu-id="0bc0d-183">Lync Server 2010, Group Chat had a user administrator role, a chat room administrator role and a Lync Server administrator role that could manage add-ins. Persistent Chat Server simply provides a Persistent Chat Administrator role (which is similar to other Lync Server role-based access control (RBAC) roles).</span></span> <span data-ttu-id="0bc0d-184">Toute personne qui fait partie de ce rôle RBAC peut gérer des salles de conversation, des compléments et des catégories (et, par conséquent, bénéficier d’un accès utilisateur pour ces catégories) et configurer le pool de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-184">Anyone who is a member of this RBAC role can manage chat rooms, add-ins, and categories (and therefore gain user access for these categories), and configuration of the Persistent Chat Server pool.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a><span data-ttu-id="0bc0d-185">Quels sont les différences en ce qui concerne les catégories de salle de conversation des versions précédentes du serveur de discussion de groupe ?</span><span class="sxs-lookup"><span data-stu-id="0bc0d-185">What’s Different about Chat Room Categories from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="0bc0d-186">Les catégories de salle de conversation ne peuvent plus être imbriquées et la catégorie racine ne peut plus être modifiée.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-186">Chat room categories can no longer be nested, and the root category can no longer be modified.</span></span> <span data-ttu-id="0bc0d-187">AllowedMembers/DeniedMembers comprend ce qu’est une étendue utilisée dans les versions serveur de chat de groupe héritées (sauf qu’elle ne prend pas en charge la spécification d’une liste refusée).</span><span class="sxs-lookup"><span data-stu-id="0bc0d-187">AllowedMembers/DeniedMembers comprise what a scope used to be in legacy Group Chat Server versions (except that it didn’t support specifying a Denied list).</span></span> <span data-ttu-id="0bc0d-188">Les étendues ne peuvent pas être remplacées, car il n’y a pas de catégories imbriquées.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-188">Scopes can no longer be overridden, because there are no nested categories.</span></span> <span data-ttu-id="0bc0d-189">Un administrateur de chat permanent dans Lync Server 2013 peut créer et gérer des catégories de salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-189">A Persistent Chat Administrator in Lync Server 2013 can create and manage chat room categories.</span></span> <span data-ttu-id="0bc0d-190">Dans le cadre de la création et de la gestion des catégories de salle de conversation, un administrateur de chat permanent peut configurer des principales (groupes Active Directory/conteneurs) qui peuvent être membres/créateurs de salles de conversation d’une catégorie spécifique.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-190">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="0bc0d-191">Un administrateur de chat permanent peut également ajouter des DeniedMembers à une catégorie, qui deviennent des exclusions explicites de la liste autorisée.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-191">A Persistent Chat Administrator can also add DeniedMembers to a category, and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="0bc0d-192">Les éléments DeniedMembers remplacent les éléments AllowedMembers.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-192">DeniedMembers override what’s in AllowedMembers.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a><span data-ttu-id="0bc0d-193">Quels sont les différences en ce qui concerne les propriétés d’une salle de conversation dans les versions précédentes du serveur de discussion de groupe ?</span><span class="sxs-lookup"><span data-stu-id="0bc0d-193">What’s Different about Chat Room Properties from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="0bc0d-194">Un nouveau concept de salles de conversation ouvertes existe dans Lync Server 2013, serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-194">A new concept of open chat rooms exists in Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="0bc0d-195">Tous les membres autorisés peuvent rejoindre une salle de conversation sans être abonnés exclusifs.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-195">All allowed members can join the chat room, without exclusive membership.</span></span>

<span data-ttu-id="0bc0d-196">Les propriétés de salle de conversation suivantes qui étaient incluses dans les versions précédentes de chat permanent du serveur ont été supprimées :</span><span class="sxs-lookup"><span data-stu-id="0bc0d-196">The following chat room properties that were included in previous versions of Persistent Chat Server have been eliminated:</span></span>

  - <span data-ttu-id="0bc0d-197">Sujet : une salle possède désormais une description.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-197">Topic: A Room now only has a Description.</span></span>

  - <span data-ttu-id="0bc0d-198">Créer une liste de membres : dans le serveur de chat permanent, toutes les salles de conversation commencent par une appartenance vide (et permettent d’optimiser l’appartenance aux membres autorisés).</span><span class="sxs-lookup"><span data-stu-id="0bc0d-198">Create New Member list: In Persistent Chat Server, all chat rooms start with empty membership (and can maximize to a membership equaling the Allowed Members).</span></span>

  - <span data-ttu-id="0bc0d-199">Chargement de fichier : permet de définir un paramètre par salle de conversation pour contrôler l’autorisation de chargement/téléchargement de fichiers.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-199">File Upload: Used to be a setting per chat room to control whether file upload/downloads were allowed.</span></span> <span data-ttu-id="0bc0d-200">Il s’agit désormais de définir uniquement le niveau de catégorie et s’applique à toutes les salles de cette catégorie.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-200">This is now set only the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="0bc0d-201">Historique des conversations : il s’agit d’un paramètre par salle de conversation pour contrôler si l’historique des discussions a été activé, mais qu’il n’est pas défini pour le niveau catégorie et qu’il s’applique également à toutes les salles de cette catégorie.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-201">Chat History: Used to be a setting per chat room to control if Chat History was enabled, but is now set only at the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="0bc0d-202">Invitations : une salle hérite toujours du paramètre d’invitations pour la catégorie ; Il peut également être désactivé dans la salle.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-202">Invites: A room always inherits the Invites setting for the category; or it can be turned off on the room.</span></span> <span data-ttu-id="0bc0d-203">Une salle ne peut pas activer les invitations si la catégorie a été configurée pour invites.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-203">A room cannot turn on Invites if the category was previously set to Invites off.</span></span>

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a><span data-ttu-id="0bc0d-204">Quels sont les différences en ce qui concerne les stratégies des versions précédentes du serveur de discussion de groupe ?</span><span class="sxs-lookup"><span data-stu-id="0bc0d-204">What’s Different about Policies from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="0bc0d-205">Le serveur Chat permanent possède une nouvelle stratégie Lync activée avec les discussions permanentes, par utilisateur/pool/site/paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-205">Persistent Chat Server has a new Lync policy enabled with Persistent Chat, per user/pool/site/global settings.</span></span> <span data-ttu-id="0bc0d-206">Dans le client Lync 2013, l’environnement chat permanent est disponible uniquement pour les utilisateurs qui sont activés par la stratégie de conversation permanente (directement ou par le biais du pool/site/paramètre global).</span><span class="sxs-lookup"><span data-stu-id="0bc0d-206">In the Lync 2013 client, the Persistent Chat environment is available only for users who are enabled by policy for Persistent Chat (either directly or through the pool/site/global setting).</span></span>

<span data-ttu-id="0bc0d-207">Les versions précédentes de Server Chat Server n’avaient pas de stratégies intégrées aux stratégies du serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-207">Previous versions of Group Chat Server did not have any policies integrated into the Lync Server policies.</span></span> <span data-ttu-id="0bc0d-208">Par utilisateur et par catégorie/par salle, en utilisant la fonctionnalité **peut télécharger des fichiers** par utilisateur, vous pouvez faire de l’utilisateur un administrateur d’utilisateur, un administrateur de salle de conversation ou configurer la capacité de télécharger des fichiers par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-208">On a per user and per category/room basis, by using the **Can Upload Files** per user feature, you could make the user a User administrator, a chat room administrator, or configure the user’s ability to upload files.</span></span> <span data-ttu-id="0bc0d-209">La fonction de **chargement de fichiers** du serveur de chat permanent n’est qu’une par catégorie.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-209">The Persistent Chat Server **File Upload** feature is just per category.</span></span>

</div>

<div>

## <a name="logging"></a><span data-ttu-id="0bc0d-210">Journalisation</span><span class="sxs-lookup"><span data-stu-id="0bc0d-210">Logging</span></span>

<span data-ttu-id="0bc0d-211">La journalisation des conversations permanentes Server et System Center Operations Manager est intégrée à la journalisation de suivi de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0bc0d-211">Logging for Persistent Chat Server and System Center Operations Manager is integrated into the Lync Server 2013 trace logging.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0bc0d-212">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0bc0d-212">See Also</span></span>


[<span data-ttu-id="0bc0d-213">Planification du serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bc0d-213">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

