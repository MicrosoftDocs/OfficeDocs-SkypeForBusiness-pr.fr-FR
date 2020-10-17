---
title: Topologies prises en charge par Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4754881d2ed3205c4f06d5468001c6e45880278c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523961"
---
# <a name="supported-topologies-in-lync-server-2013"></a><span data-ttu-id="df3fa-102">Topologies prises en charge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df3fa-102">Supported topologies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df3fa-103">_**Dernière modification de la rubrique :** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="df3fa-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="df3fa-104">Lync Server 2013 prend en charge le déploiement de sites sur site dans une organisation et l’intégration de déploiements sur site avec des déploiements Lync Online, qui est appelé déploiement hybride.</span><span class="sxs-lookup"><span data-stu-id="df3fa-104">Lync Server 2013 supports deployment of sites on premises in an organization and integration of on-premises deployments with Lync Online deployments, which is known as a hybrid deployment.</span></span> <span data-ttu-id="df3fa-105">Dans un déploiement hybride, certains utilisateurs sont hébergés localement et d’autres sont hébergés en ligne.</span><span class="sxs-lookup"><span data-stu-id="df3fa-105">In a hybrid deployment, some users are homed on-premises and some users are homed online.</span></span>

<span data-ttu-id="df3fa-106">Pour les déploiements locaux, Lync Server 2013 prend en charge le déploiement d’un ou plusieurs sites qui peuvent être ajustés pour répondre aux exigences de haute disponibilité et d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="df3fa-106">For on-premises deployments, Lync Server 2013 supports deployment of one or more sites that can be scaled to meet high availability and location requirements.</span></span> <span data-ttu-id="df3fa-107">Vous pouvez structurer ces sites et leurs composants pour qu’ils répondent aux exigences de résistance et d’accès de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="df3fa-107">You can structure these sites and their components to meet the access and resiliency requirements of your organization.</span></span>

<span data-ttu-id="df3fa-108">Un déploiement sur site de Lync Server 2013 se compose des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="df3fa-108">A Lync Server 2013 on-premises deployment consists of the following:</span></span>

  - <span data-ttu-id="df3fa-p103">Votre déploiement doit inclure au moins un site central (également appelé centre de données). Chaque site central doit comporter au moins un pool de serveurs frontaux Enterprise Edition ou un serveur Standard Edition. Cela consiste en les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="df3fa-p103">Your deployment must include at least one central site (also known as a data center). Each central site must contain at least one Enterprise Edition Front End pool or one Standard Edition server. These consist of the following:</span></span>
    
      - <span data-ttu-id="df3fa-112">Un pool de serveurs frontaux Enterprise Edition, qui se compose d’un ou de plusieurs serveurs frontaux (généralement au moins deux serveurs frontaux, pour l’extensibilité) et d’un serveur principal distinct.</span><span class="sxs-lookup"><span data-stu-id="df3fa-112">Enterprise Edition Front End pool, which consists of one or more Front End Servers (typically, at least two Front End Servers for scalability) and a separate Back End Server.</span></span> <span data-ttu-id="df3fa-113">Un pool frontal peut contenir un maximum de douze serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="df3fa-113">A Front End pool can contain a maximum of twelve Front End Servers.</span></span> <span data-ttu-id="df3fa-114">L’équilibrage de charge est requis en cas de plusieurs serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="df3fa-114">Load balancing is required for multiple Front End Servers.</span></span> <span data-ttu-id="df3fa-115">Nous conseillons l’équilibrage de la charge DNS pour le trafic SIP, mais l’équilibrage de la charge matérielle est également pris en charge.</span><span class="sxs-lookup"><span data-stu-id="df3fa-115">For SIP traffic, we recommend DNS load balancing, but hardware load balancing is also supported.</span></span> <span data-ttu-id="df3fa-116">Si vous utilisez l’équilibrage de la charge DNS pour le trafic SIP, un équilibreur de la charge matérielle est tout de même nécessaire pour le trafic HTTP.</span><span class="sxs-lookup"><span data-stu-id="df3fa-116">If you use DNS load balancing for SIP traffic, you still need a hardware load balancer for HTTP traffic.</span></span> <span data-ttu-id="df3fa-117">Nous recommandons la mise en miroir SQL Server pour la haute disponibilité des bases de données.</span><span class="sxs-lookup"><span data-stu-id="df3fa-117">We recommend SQL Server mirroring for high availability of databases.</span></span> <span data-ttu-id="df3fa-118">La base de données principale requiert une instance séparée, mais vous pouvez colocaliser les bases de données d’archivage, de surveillance, de conversation permanente et de conformité de la conversation permanente avec elle.</span><span class="sxs-lookup"><span data-stu-id="df3fa-118">The back-end database requires a separate instance, but you can collocate the archiving database, monitoring database, persistent chat database, and persistent chat compliance database with it.</span></span> <span data-ttu-id="df3fa-119">Lync Server 2013 prend en charge l’utilisation d’un cluster partagé pour les partages de fichiers de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="df3fa-119">Lync Server 2013 supports the use of a shared cluster for the file shares in your deployment.</span></span> <span data-ttu-id="df3fa-120">Pour plus d’informations sur les exigences de stockage des bases de données, voir [Database Software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="df3fa-120">For details about database storage requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="df3fa-121">Pour plus d’informations sur les exigences en matière de stockage de fichiers, voir [File Storage Support in Lync Server 2013](lync-server-2013-file-storage-support.md).</span><span class="sxs-lookup"><span data-stu-id="df3fa-121">For details about file storage requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="df3fa-122">Si vous colocaliser des bases de données Lync Server, nous vous recommandons vivement d’évaluer tous les facteurs susceptibles d’affecter la disponibilité et les performances.</span><span class="sxs-lookup"><span data-stu-id="df3fa-122">If you collocate Lync Server databases, we highly recommend assessing all factors that might affect availability and performance.</span></span> <span data-ttu-id="df3fa-123">Pour vérifier les capacités de basculement, il est recommandé de tester tous les scénarios de basculement.</span><span class="sxs-lookup"><span data-stu-id="df3fa-123">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>

        
        </div>
    
      - <span data-ttu-id="df3fa-124">Le serveur Standard Edition, qui comporte une base de données SQL Server Express colocalisée.</span><span class="sxs-lookup"><span data-stu-id="df3fa-124">Standard Edition server, which includes a collocated SQL Server Express database.</span></span>

  - <span data-ttu-id="df3fa-125">Votre déploiement peut également inclure un ou plusieurs sites de succursale associés à un site central.</span><span class="sxs-lookup"><span data-stu-id="df3fa-125">Your deployment can also have one or more branch sites associated with a central site.</span></span>

<span data-ttu-id="df3fa-126">Cette section décrit les sites et les composants d’un déploiement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df3fa-126">This section describes the sites and components of a Lync Server 2013 deployment.</span></span> <span data-ttu-id="df3fa-127">Pour plus d’informations sur le site, la topologie et la planification des composants de Lync Server 2013, voir concepts de base de la [topologie que vous devez connaître avant la planification de Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) et des [topologies de référence dans Lync Server 2013](lync-server-2013-reference-topologies.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="df3fa-127">For details about Lync Server 2013 site, topology, and component planning, see [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) and [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="df3fa-128">Pour plus d’informations sur l’intégration des composants de versions précédentes, voir [prise en charge des chemins de migration et scénarios de coexistence dans Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="df3fa-128">For details about integration of components of previous releases, see [Supported migration paths and coexistence scenarios in Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="df3fa-129">Les pools étirés ne sont pas pris en charge pour les rôles serveur frontal, serveur Edge, médiation et directeur.</span><span class="sxs-lookup"><span data-stu-id="df3fa-129">Stretched pools are not supported for the Front End, Edge, Mediation, and Director server roles.</span></span>



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a><span data-ttu-id="df3fa-130">Topologies et composants de site central (localement)</span><span class="sxs-lookup"><span data-stu-id="df3fa-130">Central Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="df3fa-131">Bien qu’une topologie de site central doive obligatoirement inclure un pool de serveurs frontaux ou un seul serveur Standard Edition, chaque site central peut héberger les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="df3fa-131">Although a central site topology must include one Front End pool or one Standard Edition server, each central site can also contain the following:</span></span>

  - <span data-ttu-id="df3fa-p107">Plusieurs pools de serveurs frontaux, qui peuvent résider dans le même domaine ou dans des domaines différents. Toutefois, tous les serveurs frontaux d’un pool et le serveur principal de ce même pool doivent résider dans le même domaine.</span><span class="sxs-lookup"><span data-stu-id="df3fa-p107">Multiple Front End pools, which can be in the same domain or different domains. However, all Front End Servers in a Front End pool, and the Back End Server for that pool, must be in the same domain.</span></span>

  - <span data-ttu-id="df3fa-134">Plusieurs serveurs Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="df3fa-134">Multiple Standard Edition servers.</span></span>

  - <span data-ttu-id="df3fa-135">Office Web Apps Server, qui est utilisé avec les applications Office Web dans Lync Server 2013 pour gérer le partage et le rendu des présentations Microsoft PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="df3fa-135">Office Web Apps Server, which is used with Office Web Applications in Lync Server 2013 to handle the sharing and rendering of Microsoft PowerPoint presentations.</span></span>

  - <span data-ttu-id="df3fa-136">Serveur Edge ou pool de serveurs Edge dans votre réseau de périmètre, si vous souhaitez que votre déploiement prenne en charge les partenaires fédérés, la connectivité PIC, une passerelle XMPP, l’accès des utilisateurs distants, la participation des utilisateurs anonymes à des réunions ou la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="df3fa-136">Edge Server or Edge pool in your perimeter network, if you want your deployment to support federated partners, public IM connectivity, an extensible messaging and presence protocol (XMPP) gateway, remote user access, participation of anonymous users in meetings, or Exchange Unified Messaging (UM).</span></span> <span data-ttu-id="df3fa-137">Vous ne pouvez pas colocaliser d’autres rôles serveur avec le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="df3fa-137">You cannot collocate any other server role with an Edge Server.</span></span> <span data-ttu-id="df3fa-138">Nous recommandons l’équilibrage de la charge DNS, lorsqu’il est approprié, mais l’équilibrage de la charge matérielle est également pris en charge.</span><span class="sxs-lookup"><span data-stu-id="df3fa-138">We recommend DNS load balancing, where appropriate, but hardware load balancing is also supported.</span></span> <span data-ttu-id="df3fa-139">Les interfaces Edge interne et externe doivent utiliser le même type d’équilibrage de la charge.</span><span class="sxs-lookup"><span data-stu-id="df3fa-139">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="df3fa-140">Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur l’une des interfaces Edge et l’équilibrage de la charge matérielle sur l’autre.</span><span class="sxs-lookup"><span data-stu-id="df3fa-140">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span> <span data-ttu-id="df3fa-141">Pour plus d’informations sur les exigences et la prise en charge de l’équilibrage de charge, voir [Planning for External User Access in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) dans la documentation de planification et [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="df3fa-141">For details about load balancing requirements and support, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="df3fa-142">Serveur de médiation ou pool, si vous souhaitez prendre en charge voix entreprise ou conférence rendez-vous dans un pool frontal sur le site central.</span><span class="sxs-lookup"><span data-stu-id="df3fa-142">Mediation Server or pool, if you want to support Enterprise Voice or dial-in conferencing in a Front End pool at the central site.</span></span> <span data-ttu-id="df3fa-143">En fonction de la façon dont vous déployez la prise en charge voix entreprise, vous pouvez colocaliser le serveur de médiation dans un pool frontal (valeur par défaut) ou déployer un serveur de médiation ou un pool autonome.</span><span class="sxs-lookup"><span data-stu-id="df3fa-143">Depending on how you deploy Enterprise Voice support, you can collocate the Mediation Server in a Front End pool (the default) or deploy a stand-alone Mediation Server or pool.</span></span> <span data-ttu-id="df3fa-144">Vous pouvez utiliser DNS, le matériel ou l’équilibrage de charge d’application (le cas échéant) pour distribuer le trafic à partir de l’homologue de passerelle d’un pool de serveurs de médiation, y compris une passerelle RTC, un système IP-PBX ou un contrôle de frontière de session de jonction SIP. Pour plus d’informations sur la planification de la topologie de serveur de médiation appropriée, voir [Deployment Guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="df3fa-144">You can use DNS, hardware, or application load balancing (when appropriate) to distribute traffic from a Mediation Server pool’s gateway peer, including a PSTN gateway, IP-PBX, or SIP trunk Session Border Control (SBC).For details about planning the appropriate Mediation Server topology, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="df3fa-145">Serveur de conversation permanente : Si vous souhaitez que les utilisateurs puissent participer à des conversations en plusieurs rubriques basées sur des sujets qui persistent dans le temps.</span><span class="sxs-lookup"><span data-stu-id="df3fa-145">Persistent Chat Server, if you want to users to be able to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="df3fa-146">Pour augmenter la capacité et la fiabilité, votre topologie peut inclure plusieurs ordinateurs exécutant un serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="df3fa-146">To provide more capacity and increased reliability, your topology can include multiple computers running Persistent Chat Server.</span></span> <span data-ttu-id="df3fa-147">Vous ne pouvez pas colocaliser le serveur de conversation permanente avec d’autres rôles serveur dans un pool d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="df3fa-147">You cannot collocate Persistent Chat Server with other server roles in an Enterprise pool.</span></span> <span data-ttu-id="df3fa-148">Toutefois, vous pouvez colocaliser le serveur de conversation permanente sur un serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="df3fa-148">However, you can collocate Persistent Chat Server on a Standard Edition server.</span></span> <span data-ttu-id="df3fa-149">La conversation permanente requiert une base de données et, si vous implémentez la conformité de conversation permanente, une base de données de conformité de conversation permanente, mais ces bases de données peuvent être colocalisées avec les bases de données d’archivage, de surveillance ou sur le server principal d’un pool de serveurs frontaux Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="df3fa-149">Persistent chat requires a database and, if you implement persistent chat compliance, a persistent chat compliance database, but the databases can be collocated with the Archiving database, Monitoring database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="df3fa-150">Pour plus d’informations sur la planification de la topologie de serveur de conversation permanente appropriée, voir [Planning for persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="df3fa-150">For details about planning the appropriate Persistent Chat Server topology, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="df3fa-151">Une surveillance, si vous voulez prendre en charge la collecte des données pour la qualité de l’expérience (QoE) audio/vidéo et l’enregistrement des détails des appels (CDR) pour les conférences Voix Entreprise et A/V de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="df3fa-151">Monitoring, if you want to support data collection for audio/video Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="df3fa-152">Vous pouvez également installer Microsoft System Center Operations Manager (anciennement Microsoft Operations Manager), qui utilise la surveillance des données de type CDR et QoE pour générer des alertes quasi en temps réel qui indiquent l’intégrité de la fiabilité des appels et de la qualité des médias.</span><span class="sxs-lookup"><span data-stu-id="df3fa-152">Optionally, you can install the Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which uses Monitoring CDR and QoE data to generate near real-time alerts that show the health of call reliability and media quality.</span></span> <span data-ttu-id="df3fa-153">La surveillance, lorsqu’elle est déployée, est colocalisée sur des serveurs frontaux ou un serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="df3fa-153">Monitoring, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="df3fa-154">La surveillance requiert une base de données, mais celle-ci peut être colocalisée avec les bases de données d’archivage, de conversation permanente, de conformité de conversation permanente ou sur le serveur principal d’un pool de serveurs frontaux Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="df3fa-154">Monitoring requires a database, but the database can be collocated with the Archiving database, persistent chat database, persistent chat compliance database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span>

  - <span data-ttu-id="df3fa-155">L’archivage, si vous voulez archiver les communications de messagerie instantanée et le contenu des réunions (pour des raisons de conformité) dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="df3fa-155">Archiving, if you want to archive IM communications and meeting content (for compliance reasons) in your deployment.</span></span> <span data-ttu-id="df3fa-156">L’archivage, lorsqu’il est déployé, est colocalisé sur des serveurs frontaux ou un serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="df3fa-156">Archiving, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="df3fa-157">Le stockage d’archivage nécessite le déploiement d’une base de données d’archivage ou l’intégration avec le stockage Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="df3fa-157">Archiving storage requires either deployment of an Archiving database or integration with Exchange 2013 storage.</span></span> <span data-ttu-id="df3fa-158">Si vous utilisez les deux, appelé *mode mixte*, le stockage Exchange 2013 est utilisé pour stocker les données d’archivage des utilisateurs hébergés sur Exchange 2013, et la base de données d’archivage est utilisée pour archiver les données pour tous les autres utilisateurs de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="df3fa-158">If you use both, which is known as *mixed mode*, Exchange 2013 storage is used to store archive data for users who are homed on Exchange 2013, and the Archiving database is used to archive data for all other users in your deployment.</span></span> <span data-ttu-id="df3fa-159">Si vous avez besoin d’une base de données d’archivage, elle peut être colocalisée avec les bases de données de surveillance, de conversation permanente, de conformité de conversation permanente ou sur le serveur principal d’un pool de serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="df3fa-159">If you require an Archiving database, the database can be collocated on the Monitoring database, persistent chat database, persistent chat compliance database, or on the Back End Server of a Front End pool.</span></span> <span data-ttu-id="df3fa-160">Pour plus d’informations sur la planification de la topologie d’archivage appropriée, voir [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="df3fa-160">For details about planning the appropriate Archiving topology, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="df3fa-161">Directeur ou pool Directeur, si vous souhaitez faciliter la résistance et la redirection des demandes utilisateur Lync Server 2013 vers le pool d’accueil de l’utilisateur, qui peut être un pool frontal Enterprise Edition ou un serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="df3fa-161">Director or Director pool, if you want to facilitate resiliency and redirection of Lync Server 2013 user requests to the user’s home pool, which can be either an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="df3fa-162">Nous vous recommandons de déployer un directeur ou un pool directeur dans chaque site central prenant en charge l’accès des utilisateurs externes et dans chaque site central dans lequel vous déployez un ou plusieurs pools de serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="df3fa-162">We recommend that you deploy a Director or Director pool in each central site that supports external user access and in each central site in which you deploy one or more Front End pools.</span></span> <span data-ttu-id="df3fa-163">Chaque pool directeur peut contenir jusqu’à dix directeurs.</span><span class="sxs-lookup"><span data-stu-id="df3fa-163">Each Director pool can contain a maximum of ten Directors.</span></span> <span data-ttu-id="df3fa-164">Un directeur ne peut pas être colocalisé avec un autre rôle serveur.</span><span class="sxs-lookup"><span data-stu-id="df3fa-164">A Director cannot be collocated with any other server role.</span></span> <span data-ttu-id="df3fa-165">Pour plus d’informations sur la planification de la topologie de directeur appropriée, reportez-vous à la rubrique [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="df3fa-165">For details about planning the appropriate Director topology, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="df3fa-166">Proxy inverse, qui n’est pas un composant Lync Server 2013, mais qui est nécessaire si vous souhaitez prendre en charge le partage de contenu Web pour les utilisateurs fédérés ou pour prendre en charge le trafic de mobilité.</span><span class="sxs-lookup"><span data-stu-id="df3fa-166">Reverse proxy, which is not a Lync Server 2013 component, but is required if you want to support sharing of web content for federated users or to support Mobility traffic.</span></span> <span data-ttu-id="df3fa-167">Vous ne pouvez pas colocaliser un serveur proxy inverse avec un rôle serveur Lync Server 2013, mais vous pouvez implémenter la prise en charge du proxy inverse pour un déploiement Lync Server 2013 en configurant la prise en charge sur un serveur proxy inverse existant de votre organisation qui est utilisé pour d’autres applications.</span><span class="sxs-lookup"><span data-stu-id="df3fa-167">You cannot collocate a reverse proxy server with any Lync Server 2013 server role, but you can implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span> <span data-ttu-id="df3fa-168">Pour plus d’informations sur les serveurs proxy inverses, voir [Setting up Reverse Proxy Servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="df3fa-168">For details about reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="df3fa-169">Dans Lync Server 2013, la conférence A/V, la surveillance et l’archivage s’exécutent sur les serveurs frontaux et ne sont plus des rôles serveur distincts.</span><span class="sxs-lookup"><span data-stu-id="df3fa-169">In Lync Server 2013, A/V Conferencing, Monitoring, and Archiving run on Front End Servers and are no longer separate server roles.</span></span>



</div>

<span data-ttu-id="df3fa-170">Tous les pools frontaux et les serveurs Standard Edition Server que vous déployez sur un site central partagent tout ou partie des éléments suivants sur le site central :</span><span class="sxs-lookup"><span data-stu-id="df3fa-170">All Front End pools and Standard Edition servers that you deploy at a central site share any of the following that you deploy for the central site:</span></span>

  - <span data-ttu-id="df3fa-171">Directeur ou pool directeur</span><span class="sxs-lookup"><span data-stu-id="df3fa-171">Director or Director pool</span></span>

  - <span data-ttu-id="df3fa-172">Serveur ou pool de serveurs de médiation autonome</span><span class="sxs-lookup"><span data-stu-id="df3fa-172">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="df3fa-173">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="df3fa-173">Office Web Apps Server</span></span>

  - <span data-ttu-id="df3fa-174">Serveur ou pool de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="df3fa-174">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="df3fa-175">Pool ou serveur de conversations permanentes</span><span class="sxs-lookup"><span data-stu-id="df3fa-175">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="df3fa-176">Surveillance</span><span class="sxs-lookup"><span data-stu-id="df3fa-176">Monitoring</span></span>

  - <span data-ttu-id="df3fa-177">Archivage</span><span class="sxs-lookup"><span data-stu-id="df3fa-177">Archiving</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="df3fa-178">Un serveur de messagerie unifiée Exchange peut être implémenté avec votre déploiement Lync Server 2013 si vous souhaitez prendre en charge l’intégration de la messagerie unifiée Exchange 2013, mais il ne s’agit pas d’un composant du site Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df3fa-178">An Exchange UM Server can be implemented with your Lync Server 2013 deployment if you want to support integration of Exchange 2013 Unified Messaging, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="df3fa-179">Plusieurs sites centraux peuvent partager tout ou partie des éléments suivants déployés sur le site central :</span><span class="sxs-lookup"><span data-stu-id="df3fa-179">Multiple central sites can also share any of the following that you deploy in one central site:</span></span>

  - <span data-ttu-id="df3fa-180">Serveur ou pool de serveurs de médiation autonome</span><span class="sxs-lookup"><span data-stu-id="df3fa-180">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="df3fa-181">Serveur ou pool de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="df3fa-181">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="df3fa-182">Pool ou serveur de conversations permanentes</span><span class="sxs-lookup"><span data-stu-id="df3fa-182">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="df3fa-183">Archivage</span><span class="sxs-lookup"><span data-stu-id="df3fa-183">Archiving</span></span>

  - <span data-ttu-id="df3fa-184">Surveillance</span><span class="sxs-lookup"><span data-stu-id="df3fa-184">Monitoring</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="df3fa-185">Un serveur de messagerie unifiée Exchange peut être implémenté avec votre déploiement Lync Server 2013 et partagé par plusieurs sites centraux, mais il ne s’agit pas d’un composant du site Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df3fa-185">An Exchange UM Server can be implemented with your Lync Server 2013 deployment and shared by multiple central sites, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="df3fa-186">Pour plus d’informations sur les rôles serveur et les fonctionnalités de Lync Server 2013, voir [rôles serveur dans Lync server 2013](lync-server-2013-server-roles.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="df3fa-186">For details about Lync Server 2013 server roles and functionality, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md) in the Planning documentation.</span></span>

<span data-ttu-id="df3fa-187">Pour obtenir un résumé de la prise en charge de la colocalisation des serveurs Lync Server 2013, voir prise en charge de la [colocalisation 2013 de serveur](lync-server-2013-supported-server-collocation.md)</span><span class="sxs-lookup"><span data-stu-id="df3fa-187">For a summary of Lync Server 2013 server collocation support, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<span data-ttu-id="df3fa-188">Outre les rôles serveur et les fonctionnalités abordés dans cette section, Lync Server 2013 comporte des composants et des options supplémentaires, qui peuvent inclure une partie ou l’ensemble des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="df3fa-188">In addition to the server roles and functionality covered previously in this section, Lync Server 2013 has additional components and options, which can include some or all of the following:</span></span>

  - <span data-ttu-id="df3fa-189">Pare-feu</span><span class="sxs-lookup"><span data-stu-id="df3fa-189">Firewalls</span></span>

  - <span data-ttu-id="df3fa-190">Passerelles PSTN (si Voix Entreprise est déployé)</span><span class="sxs-lookup"><span data-stu-id="df3fa-190">PSTN gateways (if deploying Enterprise Voice)</span></span>

  - <span data-ttu-id="df3fa-191">Serveur de messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="df3fa-191">Exchange UM Server</span></span>

  - <span data-ttu-id="df3fa-192">Équilibrage de charge DNS</span><span class="sxs-lookup"><span data-stu-id="df3fa-192">DNS load balancing</span></span>

  - <span data-ttu-id="df3fa-193">Programmes d’équilibrage de la charge matérielle</span><span class="sxs-lookup"><span data-stu-id="df3fa-193">Hardware load balancers</span></span>

  - <span data-ttu-id="df3fa-194">Bases de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="df3fa-194">SQL Server databases</span></span>

  - <span data-ttu-id="df3fa-195">Partages de fichiers</span><span class="sxs-lookup"><span data-stu-id="df3fa-195">File shares</span></span>

<span data-ttu-id="df3fa-196">Pour plus d’informations sur toutes les fonctionnalités, composants et options de Lync Server 2013, reportez-vous à la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="df3fa-196">For details about all of the Lync Server 2013 features, components, and options, see the Planning documentation.</span></span>

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a><span data-ttu-id="df3fa-197">Topologies et composants de sites de succursale (localement)</span><span class="sxs-lookup"><span data-stu-id="df3fa-197">Branch Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="df3fa-p115">Un site de succursale est associé à un site central et chaque Survivable Branch Appliance d’un site de succursale est associé à un pool de serveurs frontaux Enterprise Edition ou à un serveur Standard Edition hébergé dans le site central associé. Les sites de succursale offrent des fonctionnalités différentes selon le site central auxquels ils sont associés. Pour cette raison, les sites de succursale ne comportent que les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="df3fa-p115">A branch site is associated with a central site, and each Survivable Branch Appliance in a branch site is associated with an Enterprise Edition Front End pool or a Standard Edition server in the associated central site. Branch sites depend on the central site for most of their functionality, so components at a branch site contain only the following:</span></span>

  - <span data-ttu-id="df3fa-200">Un Survivable Branch appliance, qui combine une passerelle RTC (réseau téléphonique commuté) avec certaines fonctionnalités Lync Server.</span><span class="sxs-lookup"><span data-stu-id="df3fa-200">A Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway with some Lync Server functionality.</span></span> <span data-ttu-id="df3fa-201">Un serveur de médiation peut être colocalisé avec l’instance du serveur d’inscriptions sur le Survivable Branch appliance et vous pouvez déployer un serveur de médiation autonome ou un pool de serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="df3fa-201">A Mediation Server can be collocated with the instance of the Registrar on the Survivable Branch Appliance, and you can deploy a stand-alone Mediation Server or pool of Mediation Servers.</span></span>

  - <span data-ttu-id="df3fa-202">Un serveur Survivable Branch Server, qui est un serveur exécutant Windows Server sur lequel le logiciel de serveur d’inscriptions et de médiation Lync Server 2013 est installé.</span><span class="sxs-lookup"><span data-stu-id="df3fa-202">A Survivable Branch Server, which is a server running Windows Server that has Lync Server 2013 Registrar and Mediation Server software installed.</span></span>

  - <span data-ttu-id="df3fa-203">Une passerelle PSTN autonome (indépendante du Survivable Branch Appliance) et un serveur de médiation autonome.</span><span class="sxs-lookup"><span data-stu-id="df3fa-203">A stand-alone PSTN gateway (not part of the Survivable Branch Appliance) and a stand-alone Mediation Server.</span></span>

<span data-ttu-id="df3fa-204">La configuration requise pour les serveurs Survivable Branch Server est identique à celle requise pour tout rôle serveur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df3fa-204">The requirements for Survivable Branch Servers are the same as the requirements for any Lync Server 2013 server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

