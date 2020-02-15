---
title: 'Lync Server 2013 : configuration du stockage pour l’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up storage for Archiving
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205392(v=OCS.15)
ms:contentKeyID: 48185858
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a3633ee21fc26fe21557731ece31cf5a0bbb171
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a><span data-ttu-id="2b8a7-102">Configuration du stockage pour l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b8a7-102">Setting up storage for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b8a7-103">_**Dernière modification de la rubrique :** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="2b8a7-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="2b8a7-104">Le stockage d’archivage pour Lync Server 2013 inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="2b8a7-104">Archiving storage for Lync Server 2013 includes the following:</span></span>

  - <span data-ttu-id="2b8a7-105">**Stockage des données le**   stockage des données est nécessaire pour stocker le contenu de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="2b8a7-105">**Data storage**   Data storage is required to store IM content.</span></span>

  - <span data-ttu-id="2b8a7-106">\*\*\*\*   Le stockage des fichiers de stockage de fichiers est requis pour stocker le stockage des données de contenu de conférence (réunion) et le stockage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="2b8a7-106">**File storage**   File storage is required to store conferencing (meeting) content data storage and file storage.</span></span>

<div>

## <a name="setting-up-data-storage"></a><span data-ttu-id="2b8a7-107">Configuration du stockage des données</span><span class="sxs-lookup"><span data-stu-id="2b8a7-107">Setting Up Data Storage</span></span>

<span data-ttu-id="2b8a7-108">La configuration requise pour la configuration du stockage des données pour l’archivage dans Lync Server 2013 dépend de la façon dont vous souhaitez stocker les données d’archivage :</span><span class="sxs-lookup"><span data-stu-id="2b8a7-108">Requirements for setting up data storage for Archiving in Lync Server 2013 depend on how you want to store archiving data:</span></span>

  - <span data-ttu-id="2b8a7-109">Intégrez l’archivage Lync Server 2013 avec votre déploiement Exchange pour stocker les données d’archivage à l’aide du stockage Exchange.</span><span class="sxs-lookup"><span data-stu-id="2b8a7-109">Integrate Lync Server 2013 Archiving with your Exchange deployment to store Archiving data using Exchange storage.</span></span>

  - <span data-ttu-id="2b8a7-110">Configurez des serveurs de base de données SQL Server distincts pour stocker les données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="2b8a7-110">Set up separate SQL Server database servers to store Archiving data.</span></span>

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a><span data-ttu-id="2b8a7-111">Configuration du stockage Exchange pour les données d’archivage</span><span class="sxs-lookup"><span data-stu-id="2b8a7-111">Setting Up Exchange Storage for Archiving Data</span></span>

<span data-ttu-id="2b8a7-112">La configuration d’Exchange pour le stockage des données d’archivage nécessite que votre déploiement Exchange exécute Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="2b8a7-112">Setting up Exchange for storage of Archiving data requires that your Exchange deployment is running Exchange 2013.</span></span> <span data-ttu-id="2b8a7-113">De plus, les boîtes aux lettres utilisateur doivent être hébergées sur le serveur Exchange 2013 et leurs boîtes aux lettres doivent être placées en conservation inaltérable.</span><span class="sxs-lookup"><span data-stu-id="2b8a7-113">Additionally, user mailboxes must be homed on the Exchange 2013 server and their mailboxes must be put on In-Place Hold.</span></span> <span data-ttu-id="2b8a7-114">Pour plus d’informations sur la configuration d’Exchange 2013, voir la documentation du produit Exchange.</span><span class="sxs-lookup"><span data-stu-id="2b8a7-114">For details about configuring Exchange 2013, see the Exchange product documentation.</span></span>

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a><span data-ttu-id="2b8a7-115">Configuration des serveurs de base de données SQL Server pour le stockage des données d’archivage</span><span class="sxs-lookup"><span data-stu-id="2b8a7-115">Setting Up SQL Server Database Servers for Storage of Archiving Data</span></span>

<span data-ttu-id="2b8a7-116">Pour l’archivage dans Lync Server 2013, le logiciel de base de données SQL Server doit être stocké dans les données archivées, sauf si vous intégrez votre déploiement auprès d’Exchange.</span><span class="sxs-lookup"><span data-stu-id="2b8a7-116">Archiving in Lync Server 2013 requires the SQL Server database software to store the archived data, unless you integrate your deployment with Exchange.</span></span>

<span data-ttu-id="2b8a7-117">Pour les bases de données d’archivage SQL Server, vous devez installer SQL Server sur l’ordinateur qui hébergera la base de données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="2b8a7-117">For SQL Server archiving databases, you must install SQL Server on the computer that will host the Archiving database.</span></span> <span data-ttu-id="2b8a7-118">Vous pouvez utiliser la même instance SQL que pour la base de données primaire d’un pool frontal.</span><span class="sxs-lookup"><span data-stu-id="2b8a7-118">You can use the same SQL instance that you use for the back-end database of a Front End pool.</span></span> <span data-ttu-id="2b8a7-119">Pour de meilleures performances, nous vous conseillons de déployer la base de données d’archivage sur un ordinateur distinct du magasin de gestion centralisée.</span><span class="sxs-lookup"><span data-stu-id="2b8a7-119">For best performance, you should deploy the Archiving database on a computer that is separate from the Central Management store.</span></span> <span data-ttu-id="2b8a7-120">Pour plus d’informations sur les composants colocaliser Lync Server 2013, voir [prise en charge de la colocalisation des serveurs dans Lync Server 2013](lync-server-2013-supported-server-collocation.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="2b8a7-120">For details about collocating Lync Server 2013 components, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="2b8a7-121">Chaque serveur de base de données doit exécuter une version prise en charge de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2b8a7-121">Each database server must be running a supported version of SQL Server.</span></span> <span data-ttu-id="2b8a7-122">Pour plus d’informations sur les versions prises en charge, voir [Technical Requirements for Archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="2b8a7-122">For details about the supported versions, see [Technical requirements for Archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="2b8a7-123">Vous devez configurer les plateformes SQL Server avant de déployer et d’activer l’archivage.</span><span class="sxs-lookup"><span data-stu-id="2b8a7-123">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="2b8a7-124">Si le compte à utiliser pour la publication de la topologie est doté des droits et autorisations d’administrateur appropriées, vous pouvez créer la base de données d’archivage (LcsLog) lorsque vous publiez votre topologie.</span><span class="sxs-lookup"><span data-stu-id="2b8a7-124">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="2b8a7-125">Vous pouvez également créer la base de données plus tard, y compris dans le cadre de la procédure d’installation.</span><span class="sxs-lookup"><span data-stu-id="2b8a7-125">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="2b8a7-126">Pour plus d’informations sur SQL Server, voir SQL Server TechCenter [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="2b8a7-126">For details about SQL Server, see the SQL Server TechCenter at [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2b8a7-127">Assurez-vous que le type de démarrage du service de l’agent SQL Server est automatique et que le service SQL Server Agent est en cours d’exécution pour l’instance SQL qui contient la base de données d’archivage, afin que le travail de maintenance SQL Server d’archivage par défaut puisse s’exécuter à sa base planifiée sous le contrôle du service SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="2b8a7-127">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Archiving database, so that the Default Archiving SQL Server Maintenance Job can run on its scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a><span data-ttu-id="2b8a7-128">Configuration du stockage de fichier</span><span class="sxs-lookup"><span data-stu-id="2b8a7-128">Setting Up File Storage</span></span>

<span data-ttu-id="2b8a7-129">L’archivage utilise le partage de fichiers Lync Server 2013 que vous avez spécifié lors de la configuration de votre pool frontal ou de votre serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="2b8a7-129">Archiving uses the Lync Server 2013 file share that you specified when you set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="2b8a7-130">Vous ne pouvez pas modifier le partage de fichiers utilisé pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="2b8a7-130">You cannot change the file share used for Archiving.</span></span> <span data-ttu-id="2b8a7-131">Pour plus d’informations sur les systèmes de stockage de fichiers pris en charge, voir [File Storage Support in Lync Server 2013](lync-server-2013-file-storage-support.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="2b8a7-131">For details about supported file storage systems, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

