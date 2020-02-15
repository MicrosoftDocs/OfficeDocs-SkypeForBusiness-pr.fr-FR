---
title: 'Lync Server 2013 : définition et configuration de la topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4f4f5ef6dfe595c87745571d061d104916067c8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a><span data-ttu-id="99cb3-102">Définition et configuration de la topologie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99cb3-102">Defining and configuring the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99cb3-103">_**Dernière modification de la rubrique :** 2012-09-14_</span><span class="sxs-lookup"><span data-stu-id="99cb3-103">_**Topic Last Modified:** 2012-09-14_</span></span>

<span data-ttu-id="99cb3-104">Vous définissez et configurez votre topologie à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="99cb3-104">You define and configure your topology by using Topology Builder.</span></span> <span data-ttu-id="99cb3-105">Le générateur de topologie ne requiert pas que vous soyez membre du groupe Administrateurs local ou d’un groupe de domaine privilégié (tel que Admins du domaine).</span><span class="sxs-lookup"><span data-stu-id="99cb3-105">Topology Builder does not require you to be a member of the local Administrators group or a privileged domain group (such as Domain Admins).</span></span> <span data-ttu-id="99cb3-106">Vous pouvez définir votre topologie en tant qu’utilisateur standard.</span><span class="sxs-lookup"><span data-stu-id="99cb3-106">You can define your topology as a standard user.</span></span> <span data-ttu-id="99cb3-107">Lorsque vous démarrez le Générateur de topologies pour la première fois et lors des sessions de modification ultérieures, le système vous invite à spécifier l’emplacement où le Générateur de topologies doit charger le document de configuration actuel.</span><span class="sxs-lookup"><span data-stu-id="99cb3-107">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="99cb3-108">Les choix sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="99cb3-108">The choices are the following:</span></span>

  - <span data-ttu-id="99cb3-109">Télécharger la topologie à partir d’un déploiement existant</span><span class="sxs-lookup"><span data-stu-id="99cb3-109">Download topology from existing deployment</span></span>

  - <span data-ttu-id="99cb3-110">Ouvrir la topologie à partir d’un fichier local</span><span class="sxs-lookup"><span data-stu-id="99cb3-110">Open topology from a local file</span></span>

  - <span data-ttu-id="99cb3-111">Nouvelle topologie</span><span class="sxs-lookup"><span data-stu-id="99cb3-111">New topology</span></span>

<span data-ttu-id="99cb3-112">Si vous avez déjà défini une topologie et que vous avez établi le magasin central de gestion, vous devez choisir de télécharger une topologie à partir d’un déploiement existant.</span><span class="sxs-lookup"><span data-stu-id="99cb3-112">If you have already defined a topology and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="99cb3-113">Le Générateur de topologies lit la base de données et récupère la définition actuelle.</span><span class="sxs-lookup"><span data-stu-id="99cb3-113">Topology Builder will read the database and retrieve the current definition.</span></span> <span data-ttu-id="99cb3-114">Si vous disposez d’un magasin central de gestion, vous devez toujours choisir cette option.</span><span class="sxs-lookup"><span data-stu-id="99cb3-114">If you have an existing Central Management store, you should always choose this option.</span></span>

<span data-ttu-id="99cb3-115">Si vous n’avez pas établi de magasin central de gestion et que vous souhaitez modifier une configuration enregistrée précédemment, vous devez choisir d’ouvrir la topologie à partir d’un fichier local.</span><span class="sxs-lookup"><span data-stu-id="99cb3-115">If you have not established a Central Management store and want to edit a previously saved configuration, you should choose to open the topology from a local file.</span></span> <span data-ttu-id="99cb3-116">Le fichier que vous ouvrirez sera le fichier de configuration qui a été enregistré dans une session précédente.</span><span class="sxs-lookup"><span data-stu-id="99cb3-116">The file that you will open would be the configuration file that was saved in a previous session.</span></span> <span data-ttu-id="99cb3-117">Vous pouvez utiliser cette option pour modifier la topologie précédemment enregistrée.</span><span class="sxs-lookup"><span data-stu-id="99cb3-117">You can use this option to edit the previously saved topology.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="99cb3-p104">Si vous disposez déjà d’une topologie publiée, ne chargez aucun fichier de configuration local. Choisissez de télécharger la topologie à partir d’un déploiement existant.</span><span class="sxs-lookup"><span data-stu-id="99cb3-p104">If you already have a published topology, you should not load a local configuration file. You should choose to download the topology from an existing deployment.</span></span>



</div>

<span data-ttu-id="99cb3-120">Choisissez de créer une nouvelle topologie, si vous voulez créer une nouvelle configuration de générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="99cb3-120">Choose to create a new topology, if you want to create a new Topology Builder configuration.</span></span> <span data-ttu-id="99cb3-121">Une conception précédemment enregistrée n’est pas remplacée sauf si vous choisissez de l’enregistrer à la place du fichier que vous avez créé lors d’une session de conception précédente.</span><span class="sxs-lookup"><span data-stu-id="99cb3-121">A previously saved design is not overwritten unless you choose to save it as the same file that you created in an earlier design session.</span></span>

<span data-ttu-id="99cb3-122">Dans chacune de ces options, vous serez invité à indiquer l’emplacement de stockage du fichier de configuration du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="99cb3-122">In each of these options, you will be prompted for a location to store the Topology Builder configuration file.</span></span> <span data-ttu-id="99cb3-123">L’emplacement du fichier peut être un emplacement local, un emplacement partagé sur un partage de fichiers défini ou un média amovible.</span><span class="sxs-lookup"><span data-stu-id="99cb3-123">The location for the file could be a local location, a shared location on an established file share, or removable media.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="99cb3-124">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="99cb3-124">In This Section</span></span>

  - [<span data-ttu-id="99cb3-125">Définition et configuration d’une topologie dans le générateur de topologies pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99cb3-125">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [<span data-ttu-id="99cb3-126">Définition et configuration d’un pool frontal ou d’un serveur Standard Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99cb3-126">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="99cb3-127">Déploiement de pools frontaux couplés pour la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99cb3-127">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [<span data-ttu-id="99cb3-128">Déploiement de la mise en miroir SQL pour la haute disponibilité des serveurs principaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99cb3-128">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [<span data-ttu-id="99cb3-129">Modifier ou configurer des URL simples dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99cb3-129">Edit or configure simple URLs in Lync Server 2013</span></span>](lync-server-2013-edit-or-configure-simple-urls.md)

  - [<span data-ttu-id="99cb3-130">Sélectionnez le serveur de gestion centralisée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99cb3-130">Select the Central Management Server in Lync Server 2013</span></span>](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

