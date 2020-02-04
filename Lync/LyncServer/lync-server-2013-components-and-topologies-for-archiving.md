---
title: 'Lync Server 2013 : Composants et topologies utilisés pour l’archivage'
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
ms.openlocfilehash: b3ccb77d8d2d0b7bd7d4d564087a69b7605863fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="cb835-102">Composants et topologies utilisés pour l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb835-102">Components and topologies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb835-103">_**Dernière modification de la rubrique :** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="cb835-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="cb835-104">Si vous souhaitez archiver du contenu de messagerie instantanée et de conférences Lync Server 2013, vous pouvez implémenter l’archivage dans Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cb835-104">If you want to archive Lync Server 2013 IM and conferencing content, you can implement Archiving in Lync Server.</span></span>

<div>

## <a name="archiving-components"></a><span data-ttu-id="cb835-105">Archivage des composants</span><span class="sxs-lookup"><span data-stu-id="cb835-105">Archiving Components</span></span>

<span data-ttu-id="cb835-106">La fonctionnalité d’archivage inclut les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="cb835-106">The Archiving feature includes the following components:</span></span>

  - <span data-ttu-id="cb835-107">**Argents d’archivage**.</span><span class="sxs-lookup"><span data-stu-id="cb835-107">**Archiving agents**.</span></span> <span data-ttu-id="cb835-108">Les agents d’archivage (également appelés agents de collection de données unifiées) sont installés et activés automatiquement sur chaque pool frontal et serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="cb835-108">Archiving agents (also known as unified data collection agents) are installed and activated automatically on every Front End pool and Standard Edition server.</span></span> <span data-ttu-id="cb835-109">Bien que les agents d’archivage soient activés automatiquement, aucun message n’est réellement capturé tant qu’il n’est pas activé et configuré de manière appropriée.</span><span class="sxs-lookup"><span data-stu-id="cb835-109">Although archiving agents are activated automatically, no messages are actually captured until Archiving is enabled and appropriately configured.</span></span>

  - <span data-ttu-id="cb835-110">**Archivage du stockage des données**.</span><span class="sxs-lookup"><span data-stu-id="cb835-110">**Archiving data storage**.</span></span> <span data-ttu-id="cb835-111">Le stockage de données pour Lync Server 2013 peut être l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="cb835-111">Data storage for Lync Server 2013 can be either of the following:</span></span>
    
      - <span data-ttu-id="cb835-112">Stockage 2013 Exchange.</span><span class="sxs-lookup"><span data-stu-id="cb835-112">Exchange 2013 storage.</span></span> <span data-ttu-id="cb835-113">Si vous activez l’option d’intégration de Microsoft Exchange, les boîtes aux lettres d’utilisateur hébergées sur le serveur Exchange 2013 utilisent le stockage Exchange 2013 pour les données archivées, mais uniquement si celles-ci sont placées sur le blocage sur place.</span><span class="sxs-lookup"><span data-stu-id="cb835-113">If you enable the Microsoft Exchange integration option, user mailboxes homed on the Exchange 2013 server use Exchange 2013 storage for archived data, but only if the mailboxes have been put on In-Place Hold.</span></span>
    
      - <span data-ttu-id="cb835-114">Stockage SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cb835-114">SQL Server storage.</span></span> <span data-ttu-id="cb835-115">Si votre déploiement comporte des utilisateurs qui sont hébergés sur Lync Server 2013, vous pouvez configurer des bases de données d’archivage qui exécutent une version prise en charge de SQL Server pour permettre l’archivage de ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="cb835-115">If you have users in your deployment who are homed on Lync Server 2013, you can set up Archiving databases that run a supported version of SQL Server to enable archiving for those users.</span></span>

<span data-ttu-id="cb835-116">L’archivage nécessite également le stockage de fichiers, mais l’archivage utilise le même stockage de fichiers que le serveur frontal ou les serveurs Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="cb835-116">Archiving also requires file storage, but Archiving uses the same file storage as the Front End Servers or Standard Edition server.</span></span>

<span data-ttu-id="cb835-117">Pour obtenir la liste des configurations matérielles et logicielles requises pour l’archivage, voir [matériel compatible pour Lync server 2013](lync-server-2013-supported-hardware.md) et les [logiciels et l’infrastructure pris en charge dans Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) dans la documentation sur la prise en charge.</span><span class="sxs-lookup"><span data-stu-id="cb835-117">For a list of hardware and software requirements for Archiving, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="cb835-118">Topologies prises en charge</span><span class="sxs-lookup"><span data-stu-id="cb835-118">Supported Topologies</span></span>

<span data-ttu-id="cb835-119">Le déploiement de l’archivage dans chaque liste incluant des utilisateurs nécessitent une prise en charge de l’archivage.</span><span class="sxs-lookup"><span data-stu-id="cb835-119">You deploy Archiving in each pool that has users that require archiving support.</span></span> <span data-ttu-id="cb835-120">L’archivage s’exécute sur les serveurs frontaux dans les groupes Enterprise Edition et sur les serveurs Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="cb835-120">Archiving runs on Front End Servers in Enterprise Edition pools and on Standard Edition servers.</span></span> <span data-ttu-id="cb835-121">Le stockage des données d’archivage peut être ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="cb835-121">Archiving data storage can be the following:</span></span>

  - <span data-ttu-id="cb835-122">Intégration avec le stockage 2013 Exchange</span><span class="sxs-lookup"><span data-stu-id="cb835-122">Integrated with Exchange 2013 storage</span></span>

  - <span data-ttu-id="cb835-123">Déploiement à l’aide de bases de données SQL Server distinctes</span><span class="sxs-lookup"><span data-stu-id="cb835-123">Deployed using separate SQL Server databases</span></span>

<span data-ttu-id="cb835-124">Si votre déploiement d’Exchange 2013 n’inclut pas tous les utilisateurs dans le déploiement de Lync Server, vous devez utiliser l’intégration de Microsoft Exchange pour les utilisateurs dont la boîte aux lettres est située sur les serveurs Exchange 2013 et vous devez déployer des bases de données SQL Server distinctes pour toutes les autres. Utilisateurs de Lync à utiliser pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="cb835-124">If your Exchange 2013 deployment does not include all users in your Lync Server deployment, you must use Microsoft Exchange integration for the users whose mailboxes are home on Exchange 2013 servers, and you must deploy separate SQL Server databases for all other Lync users to use for archiving.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="cb835-125">Colocalisation prises en charge</span><span class="sxs-lookup"><span data-stu-id="cb835-125">Supported Collocation</span></span>

<span data-ttu-id="cb835-126">Lync Server 2013 prend en charge un large éventail de scénarios de colocalisation, qui vous permettent de gagner en souplesse en exécutant plusieurs composants sur un serveur (si vous disposez d’une petite organisation) ou pour exécuter des composants individuels sur différents serveurs (si vous avez une plus grande Organisation nécessitant une évolutivité et des performances optimales.</span><span class="sxs-lookup"><span data-stu-id="cb835-126">Lync Server 2013 supports a variety of collocation scenarios, allowing you flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="cb835-127">Prenez en compte les facteurs d’évolutivité avant de décider de collocater ou non les composants.</span><span class="sxs-lookup"><span data-stu-id="cb835-127">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="cb835-128">L’archivage est déployé sur les serveurs front-end d’une réserve ou d’un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="cb835-128">Archiving is deployed on the Front End Servers of a pool or Standard Edition servers.</span></span> <span data-ttu-id="cb835-129">Pour plus d’informations sur les composants qui peuvent être colocalisés à partir de cet emplacement, voir [prise en charge de la coexistence du serveur dans Lync server 2013](lync-server-2013-supported-server-collocation.md) dans la documentation de support.</span><span class="sxs-lookup"><span data-stu-id="cb835-129">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="cb835-130">Si vous utilisez des bases de données SQL Server distinctes pour l’archivage, au lieu de ou en plus de l’intégration de stockage avec le stockage 2013 Exchange, vous pouvez collocate la base de données d’archivage de l’une des façons suivantes :</span><span class="sxs-lookup"><span data-stu-id="cb835-130">If you use separate SQL Server databases for Archiving, instead of or in addition to integrating storage with Exchange 2013 storage, you can collocate the Archiving database with any of the following:</span></span>

  - <span data-ttu-id="cb835-131">Base de données de surveillance</span><span class="sxs-lookup"><span data-stu-id="cb835-131">Monitoring database</span></span>

  - <span data-ttu-id="cb835-132">Base de données principale d’un pool frontal Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="cb835-132">Back-end database of an Enterprise Edition Front End pool</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cb835-p108">Le serveur qui héberge la base de données d’archivage peut également héberger d’autres bases de données. Cependant, quand vous envisagez de colocaliser la base de données d’archivage avec d’autres bases de données, sachez que si vous archivez les messages d’un certain nombre d’utilisateurs, les besoins en espace disque de la base de données d’archivage peuvent devenir très importants. C’est la raison pour laquelle nous vous déconseillons de colocaliser la base de données d’archivage avec la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="cb835-p108">The server hosting the Archiving database can host other databases. However, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large. For this reason, we do not recommend collocating the Archiving database with the back-end database.</span></span>



</div>

<span data-ttu-id="cb835-136">Si vous collocate la base de données d’archivage avec la base de données de surveillance, la base de données principale, ou les deux, vous pouvez utiliser une instance SQL unique pour tout ou partie des bases de données, ou vous pouvez utiliser une instance SQL distincte pour chaque base de données, comme suit : modér</span><span class="sxs-lookup"><span data-stu-id="cb835-136">If you collocate the Archiving database with the Monitoring database, back-end database, or both of these databases, you can either use a single SQL instance for any or all of the databases, or you can use a separate SQL instance for each database, with the following limitation:</span></span>

  - <span data-ttu-id="cb835-137">Chaque instance SQL ne peut contenir qu’une seule base de données principale, une base de données de surveillance unique et une seule base de données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="cb835-137">Each SQL instance can contain only a single back-end database, single Monitoring database, and single Archiving database.</span></span>

<span data-ttu-id="cb835-138">Pour plus d’informations sur la colocalisation de tous les rôles de serveur et bases de données, voir [prise en charge de la colocalisation du serveur dans Lync server 2013](lync-server-2013-supported-server-collocation.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="cb835-138">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

