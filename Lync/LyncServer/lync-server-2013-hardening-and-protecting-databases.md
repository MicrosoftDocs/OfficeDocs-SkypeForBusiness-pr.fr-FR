---
title: 'Lync Server 2013 : renforcement et protection des bases de données'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting the databases of Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518330(v=OCS.15)
ms:contentKeyID: 62625490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77e02a5fd0f90367f23e7b0fb314f037f7b31e45
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a><span data-ttu-id="d071a-102">Renforcement et protection des bases de données de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d071a-102">Hardening and protecting the databases of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d071a-103">_**Dernière modification de la rubrique :** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="d071a-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="d071a-104">Microsoft Lync Server 2013 dépend également de bases de données SQL Server pour le stockage des informations utilisateur, de l’état de conférences, des données d’archivage et des enregistrements des détails des appels.</span><span class="sxs-lookup"><span data-stu-id="d071a-104">Microsoft Lync Server 2013 also depends on SQL Server databases for storing user information, conference state, archiving data, and Call Detail Records (CDRs).</span></span> <span data-ttu-id="d071a-105">Vous pouvez optimiser la disponibilité des données Lync Server 2013 sur les bases de données principales de Lync Server en partitionnant les données d’application d’une façon qui améliore la tolérance de panne et simplifie la résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="d071a-105">You can maximize the availability of Lync Server 2013 data on Lync Server back-end databases, by partitioning the application data in a way that improves fault tolerance and simplifies troubleshooting.</span></span> <span data-ttu-id="d071a-106">Pour ce faire, vous pouvez partitionner les données d’application de la façon suivante :</span><span class="sxs-lookup"><span data-stu-id="d071a-106">To achieve these goals, partition the application data by:</span></span>

  - <span data-ttu-id="d071a-107">**L’utilisation de meilleures pratiques**   de partitionnement de serveur permet de séparer les fichiers de votre système d’exploitation, de l’application et du programme de vos fichiers de données.</span><span class="sxs-lookup"><span data-stu-id="d071a-107">**Using server partitioning best practices**   Separate your operating system, application, and program files from your data files.</span></span>

  - <span data-ttu-id="d071a-108">**Le stockage des fichiers journaux des transactions et des fichiers**   de base de données stocke ces fichiers séparément pour améliorer la tolérance de panne et optimiser la récupération, et les stocker sur un disque ou un volume chiffré.</span><span class="sxs-lookup"><span data-stu-id="d071a-108">**Storing transaction log files and database files**   Store these files separately to increase fault tolerance and optimize recovery, and store them on an encrypted disk or volume.</span></span>

  - <span data-ttu-id="d071a-109">**L’utilisation**   de clusters de serveurs pour mettre en cluster les serveurs principaux pour optimiser la disponibilité du système Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d071a-109">**Using server clustering**   Cluster the back-end servers to optimize Lync Server 2013 system availability.</span></span>

  - <span data-ttu-id="d071a-110">**Assurez-vous que toutes les sauvegardes de données sont chiffrées et correctement gérées**   , supprimées, ou les médias de sauvegarde déplacés peuvent constituer une menace significative de la sécurité des données pour les déploiements de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d071a-110">**Ensure that all data backups are encrypted and properly handled**   Lost, discarded, or misplaced backup media can pose a significant threat to data security for Lync Server 2013 deployments</span></span>

<span data-ttu-id="d071a-111">Sur tout serveur Lync Server 2013, à l’exception de Standard Edition Server, l’instance SQL Server Express (instance RTCLOCAL) n’est pas accessible à distance et aucune exception de pare-feu local n’est créée, à l’exception de SQL Server Express sur un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="d071a-111">On any Lync Server 2013 server except Standard Edition server, the SQL Server Express instance (RTCLOCAL instance) is not remotely accessible, and no local firewall exceptions are created, except for SQL Server Express on a Standard Edition server.</span></span> <span data-ttu-id="d071a-112">Sur un serveur Standard Edition Server, la base de données principale et la Banque centrale de gestion (CMS) sont configurées pour être accessibles à distance.</span><span class="sxs-lookup"><span data-stu-id="d071a-112">On a Standard Edition server, both the back-end database and the Central Management store (CMS) are set up to be remotely accessible.</span></span> <span data-ttu-id="d071a-113">Pour renforcer les bases de données SQL Server, vous pouvez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="d071a-113">To harden SQL Server databases, you can do the following:</span></span>

  - <span data-ttu-id="d071a-114">Personnalisez le pare-feu SQL Server Express sur les serveurs Standard Edition afin de limiter l’étendue des serveurs qui peuvent accéder à distance à la base de données.</span><span class="sxs-lookup"><span data-stu-id="d071a-114">Customize the SQL Server Express firewall on Standard Edition servers, limiting the scope of servers that can remotely access the database.</span></span> <span data-ttu-id="d071a-115">Par défaut, toute adresse IP peut accéder à distance à la base de données.</span><span class="sxs-lookup"><span data-stu-id="d071a-115">By default, any IP address can remotely access the database.</span></span>

  - <span data-ttu-id="d071a-116">Utilisez SQL Server Configuration Manager pour spécifier les protocoles, adresses IP et ports pour l’accès distant SQL Server :</span><span class="sxs-lookup"><span data-stu-id="d071a-116">Use SQL Server Configuration Manager to specify the protocols, IP addresses, and ports for SQL Server remote access:</span></span>
    
      - <span data-ttu-id="d071a-117">Lync Server 2013 utilise le protocole TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="d071a-117">Lync Server 2013 uses the TCP/IP protocol.</span></span> <span data-ttu-id="d071a-118">Il prend en charge le protocole IP version 4 (IPv4), mais pas le protocole IP version 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="d071a-118">It supports IP version 4 (IPv4), but not IP version 6 (IPv6).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d071a-119">Lync Server 2013 peut fonctionner dans un réseau doté d’une pile IP double activée.</span><span class="sxs-lookup"><span data-stu-id="d071a-119">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

        
        </div>
    
      - <span data-ttu-id="d071a-120">Lync Server 2013 prend en charge plusieurs adresses IP (cartes d’adresses réseau multi-résidentes).</span><span class="sxs-lookup"><span data-stu-id="d071a-120">Lync Server 2013 supports multiple IP address (multi-homed network address cards).</span></span> <span data-ttu-id="d071a-121">Vous pouvez spécifier que SQL Server écoute uniquement les adresses IP spécifiques (adresse individuelle ou sous-réseau) et utiliser des protocoles spécifiques uniquement.</span><span class="sxs-lookup"><span data-stu-id="d071a-121">You can specify that SQL Server listen only to specific IP addresses (individual address or by subnet) and only use specific protocols.</span></span>
    
      - <span data-ttu-id="d071a-122">Lync Server 2013 prend en charge les ports SQL Server statiques et dynamiques.</span><span class="sxs-lookup"><span data-stu-id="d071a-122">Lync Server 2013 supports static and dynamic SQL Server ports.</span></span>

  - <span data-ttu-id="d071a-123">Exécutez SQL Server sur un port statique (non défini par défaut) et n’exécutez pas le navigateur SQL Server (de sorte qu’il ne puisse pas signaler le port d’écoute au client).</span><span class="sxs-lookup"><span data-stu-id="d071a-123">Run SQL Server on a static (non-default) port, and do not run SQL Server Browser (so it cannot report the listening port to the client).</span></span> <span data-ttu-id="d071a-124">Pour cela, il est nécessaire de disposer d’une configuration personnalisée sur chaque client SQL Server, y compris sur les serveurs frontaux, le serveur de surveillance, le serveur d’archivage et les consoles d’administration (exécutant Lync Server Management Shell, le panneau de configuration de Lync Server ou le générateur de topologie), et tous les autres serveurs exécutant des bases de données serveur Lync).</span><span class="sxs-lookup"><span data-stu-id="d071a-124">This requires a custom configuration on each SQL Server client, including Front End Servers, Monitoring Server, Archiving Server, and administrative consoles (running Lync Server Management Shell, Lync Server Control Panel, or Topology Builder), and all other servers running Lync Server databases).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d071a-125">L’accès aux bases de données doit être limité aux administrateurs de base de données approuvés.</span><span class="sxs-lookup"><span data-stu-id="d071a-125">Access to databases must be limited to trusted database administrators.</span></span> <span data-ttu-id="d071a-126">Un administrateur de base de données malveillant pouvait insérer ou modifier des données dans les bases de données pour obtenir des privilèges sur les serveurs Lync Server 2013 ou obtenir des informations sensibles de ces services, même si l’administrateur de la base de données n’a pas reçu d’accès direct ou contrôle des serveurs Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d071a-126">A malicious database administrator could insert or modify data into the databases to acquire privileges over the Lync Server 2013 servers or obtain sensitive information from the services, even if the database administrator has not been granted direct access or control of the Lync Server 2013 servers.</span></span>



</div>

<span data-ttu-id="d071a-127">Pour plus d’informations sur les configurations personnalisées et le renforcement de bases de données SQL Server, voir l’article de blog NextHop intitulé « utilisation de Lync Server 2010 avec une configuration [http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008)réseau SQL Server personnalisée ».</span><span class="sxs-lookup"><span data-stu-id="d071a-127">For details about custom configurations and hardening SQL Server databases, see the NextHop blog article, "Using Lync Server 2010 with a Custom SQL Server Network Configuration," at [http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d071a-128">Vous pouvez également renforcer la protection des serveurs d’applications et des systèmes d’exploitation, mais vous pouvez utiliser une stratégie de groupe pour mettre en œuvre les verrouillages de sécurité dans le déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d071a-128">You can also harden operating systems and applications servers, and you can use Group Policy to implement security lockdowns in your Lync Server deployment.</span></span> <span data-ttu-id="d071a-129">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">renforcement et protection des serveurs et applications pour Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d071a-129">For details, see <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Hardening and protecting servers and applications for Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

