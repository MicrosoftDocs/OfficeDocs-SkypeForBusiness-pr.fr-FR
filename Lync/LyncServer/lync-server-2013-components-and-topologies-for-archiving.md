---
title: 'Lync Server 2013 : composants et topologies pour l’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Archiving
ms:assetid: 5893063d-a44a-4034-aba9-cbe883ecf710
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204916(v=OCS.15)
ms:contentKeyID: 48184213
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ca674be0059a235439df637f07cb4ca834806d4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="7b86c-102">Composants et topologies pour l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b86c-102">Components and topologies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b86c-103">_**Dernière modification de la rubrique :** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="7b86c-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="7b86c-104">Si vous souhaitez archiver le contenu de messagerie instantanée et de conférence Lync Server 2013, vous pouvez implémenter l’archivage dans Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7b86c-104">If you want to archive Lync Server 2013 IM and conferencing content, you can implement Archiving in Lync Server.</span></span>

<div>

## <a name="archiving-components"></a><span data-ttu-id="7b86c-105">Composants d’archivage</span><span class="sxs-lookup"><span data-stu-id="7b86c-105">Archiving Components</span></span>

<span data-ttu-id="7b86c-106">La fonctionnalité Archivage inclut les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="7b86c-106">The Archiving feature includes the following components:</span></span>

  - <span data-ttu-id="7b86c-p101">**Argents d’archivage**. Les agents d’archivage (également connus sous le nom d’agents de collecte de données unifiée) sont installés et activés automatiquement sur chaque pool frontal et serveur Standard Edition. Bien que les agents d’archivage soient activés automatiquement, aucun message n’est réellement capturé tant que l’archivage n’est pas activé et correctement configuré.</span><span class="sxs-lookup"><span data-stu-id="7b86c-p101">**Archiving agents**. Archiving agents (also known as unified data collection agents) are installed and activated automatically on every Front End pool and Standard Edition server. Although archiving agents are activated automatically, no messages are actually captured until Archiving is enabled and appropriately configured.</span></span>

  - <span data-ttu-id="7b86c-110">**Stockage des données d’archivage**.</span><span class="sxs-lookup"><span data-stu-id="7b86c-110">**Archiving data storage**.</span></span> <span data-ttu-id="7b86c-111">Le stockage de données pour Lync Server 2013 peut être l’un des suivants :</span><span class="sxs-lookup"><span data-stu-id="7b86c-111">Data storage for Lync Server 2013 can be either of the following:</span></span>
    
      - <span data-ttu-id="7b86c-112">Stockage Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="7b86c-112">Exchange 2013 storage.</span></span> <span data-ttu-id="7b86c-113">Si vous activez l’option d’intégration de Microsoft Exchange, les boîtes aux lettres utilisateur hébergées sur le serveur Exchange 2013 utilisent le stockage Exchange 2013 pour les données archivées, mais uniquement si elles ont été placées en conservation inaltérable.</span><span class="sxs-lookup"><span data-stu-id="7b86c-113">If you enable the Microsoft Exchange integration option, user mailboxes homed on the Exchange 2013 server use Exchange 2013 storage for archived data, but only if the mailboxes have been put on In-Place Hold.</span></span>
    
      - <span data-ttu-id="7b86c-114">Stockage SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7b86c-114">SQL Server storage.</span></span> <span data-ttu-id="7b86c-115">Si certains de vos utilisateurs sont hébergés sur Lync Server 2013, vous pouvez configurer des bases de données d’archivage qui exécutent une version prise en charge de SQL Server afin d’activer l’archivage pour ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7b86c-115">If you have users in your deployment who are homed on Lync Server 2013, you can set up Archiving databases that run a supported version of SQL Server to enable archiving for those users.</span></span>

<span data-ttu-id="7b86c-116">L’archivage nécessite également le stockage de fichiers. Toutefois, l’archivage utilise le même type de stockage de fichiers que les serveurs frontaux ou le serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7b86c-116">Archiving also requires file storage, but Archiving uses the same file storage as the Front End Servers or Standard Edition server.</span></span>

<span data-ttu-id="7b86c-117">Pour obtenir la liste des configurations matérielle et logicielle requises pour l’archivage, voir [matériel pris en charge pour Lync server 2013](lync-server-2013-supported-hardware.md) et [Server Software and Infrastructure Support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="7b86c-117">For a list of hardware and software requirements for Archiving, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="7b86c-118">Topologies prises en charge</span><span class="sxs-lookup"><span data-stu-id="7b86c-118">Supported Topologies</span></span>

<span data-ttu-id="7b86c-119">Vous déployez l’archivage dans chaque pool où des utilisateurs ont besoin d’une prise en charge de d’archivage.</span><span class="sxs-lookup"><span data-stu-id="7b86c-119">You deploy Archiving in each pool that has users that require archiving support.</span></span> <span data-ttu-id="7b86c-120">L’archivage s’exécute sur les serveurs frontaux dans les pools Enterprise Edition et sur les serveurs Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7b86c-120">Archiving runs on Front End Servers in Enterprise Edition pools and on Standard Edition servers.</span></span> <span data-ttu-id="7b86c-121">Le stockage des données d’archivage peut se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="7b86c-121">Archiving data storage can be the following:</span></span>

  - <span data-ttu-id="7b86c-122">Intégration avec le stockage Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="7b86c-122">Integrated with Exchange 2013 storage</span></span>

  - <span data-ttu-id="7b86c-123">Déploiement à l’aide de bases de données SQL Server distinctes</span><span class="sxs-lookup"><span data-stu-id="7b86c-123">Deployed using separate SQL Server databases</span></span>

<span data-ttu-id="7b86c-124">Si votre déploiement Exchange 2013 n’inclut pas tous les utilisateurs dans votre déploiement Lync Server, vous devez utiliser l’intégration de Microsoft Exchange pour les utilisateurs dont les boîtes aux lettres sont hébergées sur des serveurs Exchange 2013 et vous devez déployer des bases de données SQL Server distinctes pour tous les autres Utilisateurs de Lync à utiliser pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="7b86c-124">If your Exchange 2013 deployment does not include all users in your Lync Server deployment, you must use Microsoft Exchange integration for the users whose mailboxes are home on Exchange 2013 servers, and you must deploy separate SQL Server databases for all other Lync users to use for archiving.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="7b86c-125">Colocalisation prise en charge</span><span class="sxs-lookup"><span data-stu-id="7b86c-125">Supported Collocation</span></span>

<span data-ttu-id="7b86c-126">Lync Server 2013 prend en charge un grand nombre de scénarios de colocalisation, ce qui vous permet d’économiser des coûts matériels en exécutant plusieurs composants sur un seul serveur (si vous avez une petite organisation) ou pour exécuter des composants individuels sur des serveurs différents (si vous disposez d’un plus grand organisation qui a besoin d’une évolutivité et de performances).</span><span class="sxs-lookup"><span data-stu-id="7b86c-126">Lync Server 2013 supports a variety of collocation scenarios, allowing you flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="7b86c-127">Vous devez considérer les facteurs d’extensibilité avant de décider si vous allez colocaliser des composants.</span><span class="sxs-lookup"><span data-stu-id="7b86c-127">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="7b86c-128">L’archivage est déployé sur les serveurs frontaux d’un pool ou de serveurs Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7b86c-128">Archiving is deployed on the Front End Servers of a pool or Standard Edition servers.</span></span> <span data-ttu-id="7b86c-129">Pour plus d’informations sur les composants qui peuvent être colocalisés, voir [prise en charge de la colocalisation des serveurs dans Lync server 2013](lync-server-2013-supported-server-collocation.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="7b86c-129">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="7b86c-130">Si vous utilisez des bases de données SQL Server distinctes pour l’archivage, au lieu ou en plus de l’intégration du stockage au stockage Exchange 2013, vous pouvez colocaliser la base de données d’archivage avec l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="7b86c-130">If you use separate SQL Server databases for Archiving, instead of or in addition to integrating storage with Exchange 2013 storage, you can collocate the Archiving database with any of the following:</span></span>

  - <span data-ttu-id="7b86c-131">Base de données de surveillance</span><span class="sxs-lookup"><span data-stu-id="7b86c-131">Monitoring database</span></span>

  - <span data-ttu-id="7b86c-132">Base de données principale d’un pool frontal Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="7b86c-132">Back-end database of an Enterprise Edition Front End pool</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7b86c-p108">Le serveur qui héberge la base de données d’archivage peut également héberger d’autres bases de données. Toutefois, quand vous envisagez de colocaliser la base de données d’archivage avec d’autres bases de données, sachez que si vous archivez les messages d’un certain nombre d’utilisateurs, les besoins en espace disque de la base de données d’archivage peuvent devenir très importants. C’est la raison pour laquelle nous vous déconseillons de colocaliser la base de données d’archivage avec la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="7b86c-p108">The server hosting the Archiving database can host other databases. However, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large. For this reason, we do not recommend collocating the Archiving database with the back-end database.</span></span>



</div>

<span data-ttu-id="7b86c-136">Si vous colocalisez la base de données d’archivage avec la base de données de surveillance, la base de données principale ou les deux à la fois, vous avez le choix entre utiliser une instance SQL unique pour la ou les bases de données ou utiliser une instance SQL distincte pour chaque base de données, tout en sachant qu’il existe les limitations suivantes :</span><span class="sxs-lookup"><span data-stu-id="7b86c-136">If you collocate the Archiving database with the Monitoring database, back-end database, or both of these databases, you can either use a single SQL instance for any or all of the databases, or you can use a separate SQL instance for each database, with the following limitation:</span></span>

  - <span data-ttu-id="7b86c-137">Chaque instance SQL ne peut contenir qu’une seule base de données principale, une base de données de surveillance unique et une base de données d’archivage unique.</span><span class="sxs-lookup"><span data-stu-id="7b86c-137">Each SQL instance can contain only a single back-end database, single Monitoring database, and single Archiving database.</span></span>

<span data-ttu-id="7b86c-138">Pour plus d’informations sur la colocalisation de tous les rôles serveur et bases de données, voir [prise en charge de la colocalisation des serveurs dans Lync server 2013](lync-server-2013-supported-server-collocation.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="7b86c-138">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

