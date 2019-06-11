---
title: 'Lync Server 2013 : Ajout d’un serveur de conversation permanente à la topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8985ee2fd28a81f3630e4f80c0ac4dd5a23d4475
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a><span data-ttu-id="f719a-102">Ajout d’un serveur de conversation permanente à la topologie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f719a-102">Add Persistent Chat Server to the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f719a-103">_**Dernière modification de la rubrique:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="f719a-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="f719a-104">Pour pouvoir configurer votre déploiement pour la prise en charge de la messagerie instantanée, vous devez disposer de Lync Server 2013 et de la prise en charge du serveur de chat permanent dans votre topologie.</span><span class="sxs-lookup"><span data-stu-id="f719a-104">You must incorporate Lync Server 2013, Persistent Chat Server support in your topology before you can configure your deployment to support Persistent Chat Server.</span></span> <span data-ttu-id="f719a-105">Les informations fournies dans cette rubrique décrivent comment utiliser le générateur de topologie pour ajouter le support technique de chat permanent à votre topologie existante.</span><span class="sxs-lookup"><span data-stu-id="f719a-105">The information in this topic describes how to use Topology Builder to add Persistent Chat Server support to your existing topology.</span></span>

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a><span data-ttu-id="f719a-106">Pour ajouter le serveur de chat permanent à une topologie</span><span class="sxs-lookup"><span data-stu-id="f719a-106">To add Persistent Chat Server to a topology</span></span>

<span data-ttu-id="f719a-107">Suivez les étapes ci-dessous pour installer une seule liste de serveurs de chat permanent sans configuration de reprise après sinistre.</span><span class="sxs-lookup"><span data-stu-id="f719a-107">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="f719a-108">Pour configurer un pool de serveurs de chat permanent étiré en vue d’une haute disponibilité et d’une reprise après sinistre, reportez-vous à la rubrique [configuration du serveur de chat permanent pour une haute disponibilité et une reprise après sinistre dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="f719a-108">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

<span data-ttu-id="f719a-109">Pour déployer plusieurs pools de serveurs de chat permanent, répétez la même procédure pour chaque liste.</span><span class="sxs-lookup"><span data-stu-id="f719a-109">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>

1.  <span data-ttu-id="f719a-110">Sur un ordinateur exécutant Lync Server 2013 ou sur lequel sont installés les outils d’administration de Lync Server, connectez-vous à l’aide d’un compte qui est membre du groupe utilisateurs local (ou d’un compte disposant de droits d’utilisateur équivalents).</span><span class="sxs-lookup"><span data-stu-id="f719a-110">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f719a-111">Vous pouvez définir une topologie à l’aide d’un compte membre du groupe utilisateurs locaux, mais pour publier une topologie qui est requise pour l’installation d’un serveur Lync Server 2013, vous devez utiliser un compte membre du groupe <STRONG>administrateurs de domaine</STRONG> et de <STRONG>RTCUniversalS erverAdmins</STRONG> et qui dispose des autorisations de contrôle total (en lecture, écriture et modification) sur le magasin de fichiers que vous allez utiliser pour le stockage des fichiers du serveur de messagerie instantanée (c’est-à-dire que le générateur de topologie peut configurer les DACL requis) ou un compte droits équivalents.</span><span class="sxs-lookup"><span data-stu-id="f719a-111">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install a Lync Server 2013 server, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (that is, so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="f719a-112">Démarrer le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="f719a-112">Start Topology Builder.</span></span>

3.  <span data-ttu-id="f719a-113">Dans l’arborescence de la console, accédez au nœud Pools de **conversations permanentes** et développez-le pour sélectionner un pool de serveurs de chat permanent, ou cliquez avec le bouton droit sur le nœud et sélectionnez **nouvelle liste de conversations permanentes**.</span><span class="sxs-lookup"><span data-stu-id="f719a-113">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Persistent Chat Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="f719a-114">You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span><span class="sxs-lookup"><span data-stu-id="f719a-114">You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="f719a-115">Vous pouvez choisir un **Pool de plusieurs ordinateurs** ou un **Pool d’un seul ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="f719a-115">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="f719a-116">Choisissez le premier si vous envisagez de disposer de plusieurs serveurs front-end serveur de chat permanent dans votre pool de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="f719a-116">Choose the former if you are planning to have more than one Persistent Chat Server Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="f719a-117">Effectuez ce choix maintenant, ou ultérieurement, car une fois que vous aurez créé un pool d’un seul ordinateur, vous ne pourrez pas ajouter d’autres serveurs.</span><span class="sxs-lookup"><span data-stu-id="f719a-117">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="f719a-118">Si vous choisissez un pool d’ordinateurs multiples, entrez le nom de chaque serveur frontal de chat permanent qui comprend le pool.</span><span class="sxs-lookup"><span data-stu-id="f719a-118">If you choose a multiple computer pool, enter the names of the individual Persistent Chat Server Front End Servers that comprise the pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f719a-119">Si le rôle serveur Chat permanent est installé sur un serveur Lync Server 2013&nbsp;Standard Edition Server, le FQDN doit correspondre au nom de domaine complet (FQDN) du serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="f719a-119">If the Persistent Chat Server role is being installed on a Lync Server 2013&nbsp;Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span>

    
    </div>

4.  <span data-ttu-id="f719a-120">Définissez un **nom complet** simple pour le pool de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="f719a-120">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="f719a-121">Le nom d’affichage peut être utilisé par les clients personnalisés, en particulier lorsqu’il existe plusieurs pools de serveurs de chat permanent pour différencier des salles.</span><span class="sxs-lookup"><span data-stu-id="f719a-121">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools, to differentiate rooms.</span></span>

5.  <span data-ttu-id="f719a-122">Définissez le port utilisé par le serveur de chat permanent pour communiquer avec les serveurs front-end de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f719a-122">Define the port used by the Persistent Chat Server to communicate with Lync Server Front End Servers.</span></span> <span data-ttu-id="f719a-123">Le port par défaut est 5041.</span><span class="sxs-lookup"><span data-stu-id="f719a-123">The default port is 5041.</span></span>

6.  <span data-ttu-id="f719a-124">Si votre organisation nécessite la prise en charge de la conformité, cochez la case **Activer la conformité**.</span><span class="sxs-lookup"><span data-stu-id="f719a-124">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="f719a-125">Le cas échéant, le service de conformité serveur Chat permanent est installé sur le même ordinateur que le serveur frontal de chat permanent du serveur.</span><span class="sxs-lookup"><span data-stu-id="f719a-125">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="f719a-126">Vous êtes invité à sélectionner un serveur principal SQL Server pour la compatibilité avec le serveur Chat permanent plus tard.</span><span class="sxs-lookup"><span data-stu-id="f719a-126">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>

7.  <span data-ttu-id="f719a-127">Attribuez une affinité de site pour le pool de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="f719a-127">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="f719a-128">Activez la case à cocher **utiliser ce pool \<comme\> option par défaut pour le site SiteName** ou **Utilisez ce pool par défaut pour tous les sites** pour désigner ce pool de serveurs de chat permanent comme pool par défaut pour le site actuel ou pour tous les sites.</span><span class="sxs-lookup"><span data-stu-id="f719a-128">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="f719a-129">Lorsque le client 2013 Lync est utilisé pour créer et gérer des salles, le pool par défaut associé au site de l’utilisateur est utilisé par l’interface de création et de gestion de la salle, afin de pouvoir diriger les opérations de création et de gestion de salle vers ce pool.</span><span class="sxs-lookup"><span data-stu-id="f719a-129">When the Lync 2013 client is used to create and manage rooms, the default pool associated with the user’s site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="f719a-130">Ce comportement s’applique uniquement lorsque vous avez déployé plusieurs pools de serveurs de chat permanent et que vous voulez utiliser les fonctionnalités de création et de gestion de la salle du serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="f719a-130">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f719a-131">Vous pouvez personnaliser les fonctionnalités de création et de gestion d’une salle à l’aide du kit de développement logiciel (SDK) serveur Chat permanent.</span><span class="sxs-lookup"><span data-stu-id="f719a-131">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span><BR><span data-ttu-id="f719a-132">Pour plus d’informations sur la configuration des bases de données de sauvegarde SQL Server pour la récupération d’urgence, reportez-vous à la rubrique <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">configuration d’un serveur de chat permanent pour une disponibilité élevée et une reprise après sinistre dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="f719a-132">For details about how to configure SQL Server backup databases for disaster recovery, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="f719a-133">Définissez le **SQL Store pour le serveur de chat permanent (emplacement de stockage du contenu d’une salle de conversation)** en effectuant l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="f719a-133">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
      - <span data-ttu-id="f719a-134">Pour utiliser une base de données SQL Server existante, dans la liste déroulante, cliquez sur le nom de la base de données SQL Server que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="f719a-134">To use an existing SQL Server database, in the drop-down list, click the name of the SQL Server database that you want to use.</span></span>
    
      - <span data-ttu-id="f719a-135">Pour spécifier une nouvelle base de données SQL Server, cliquez sur **nouveau**, puis dans **définir un nouveau SQL Store**, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="f719a-135">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="f719a-136">Dans **nom de domaine complet SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur SQL sur lequel vous voulez créer la nouvelle base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f719a-136">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
      - <span data-ttu-id="f719a-137">Sélectionnez **Instance par défaut** pour utiliser l’instance par défaut ou, pour spécifier une autre instance, sélectionnez **Instance nommée**, et spécifiez l’instance que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="f719a-137">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>

9.  <span data-ttu-id="f719a-138">Définissez la base de données de conformité SQL Server si vous avez activé la conformité.</span><span class="sxs-lookup"><span data-stu-id="f719a-138">Define the SQL Server compliance database if you enabled Compliance.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f719a-139">Pour plus d’informations sur la configuration des miroirs SQL Server en vue de la disponibilité de la base de données serveur Chat permanent et de la base de données de conformité serveur Chat <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md"> Serveur 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="f719a-139">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

10. <span data-ttu-id="f719a-140">Définissez le magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="f719a-140">Define the file store.</span></span> <span data-ttu-id="f719a-141">Un magasin de fichiers est un dossier dans lequel une copie des fichiers téléchargés dans le référentiel est stockée (par exemple, le stockage des pièces jointes publiées dans une salle de conversation).</span><span class="sxs-lookup"><span data-stu-id="f719a-141">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="f719a-142">Dans le cas d’une topologie de serveur de chat permanent multiserveur, il doit s’agir d’un chemin UNC (Universal Naming Convention); dans le cas d’une topologie de serveur de chat permanent d’un serveur unique, il peut s’agir d’un chemin d’accès de fichier local.</span><span class="sxs-lookup"><span data-stu-id="f719a-142">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="f719a-143">Pour utiliser un magasin de fichiers existant, procédez ainsi :</span><span class="sxs-lookup"><span data-stu-id="f719a-143">To use an existing file store, perform the following steps:</span></span>
    
      - <span data-ttu-id="f719a-144">Dans **nom de domaine complet du serveur de fichiers**, spécifiez le nom de domaine complet (FQDN) du magasin de fichiers sur lequel vous souhaitez créer le nouveau magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="f719a-144">In **File Server FQDN**, specify the FQDN of the file store on which you want to create the new file store.</span></span>
    
      - <span data-ttu-id="f719a-145">Dans **Partage de fichiers**, indiquez le magasin de fichiers à utiliser.</span><span class="sxs-lookup"><span data-stu-id="f719a-145">In **File Share**, specify the file store that you want to use.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f719a-146">Vous pouvez définir le magasin de fichiers dans le générateur de topologie avant de créer le magasin de fichiers, mais vous devez créer le magasin de fichiers à l’emplacement défini que vous définissez avant de publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="f719a-146">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span>

    
    </div>

11. <span data-ttu-id="f719a-147">Sélectionnez le pool de serveurs frontal à utiliser comme tronçon suivant pour ce pool de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="f719a-147">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="f719a-148">Il s’agit du pool de serveurs frontal qui sera en mesure d’acheminer les demandes de serveur de chat permanent vers ce pool.</span><span class="sxs-lookup"><span data-stu-id="f719a-148">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>

12. <span data-ttu-id="f719a-149">Pour enregistrer la configuration, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="f719a-149">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="f719a-150">Le pool de serveurs de chat permanent apparaît dans le générateur de topologie accompagné de vos paramètres de réserve spécifiques.</span><span class="sxs-lookup"><span data-stu-id="f719a-150">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="f719a-151">Pour maintenant publier votre topologie mise à jour sur laquelle vous avez permanent le serveur de conversation, voir [publier la topologie mise à jour dans Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="f719a-151">To now publish your updated topology to which you’ve Persistent Chat Server, see [Publish the updated topology in Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f719a-152">Lorsque le générateur de topologie est déjà ouvert, vous pouvez passer à l’étape 3 de <A href="lync-server-2013-publish-the-updated-topology.md">la rubrique publier la topologie mise à jour dans Lync Server 2013</A> pour commencer à publier votre topologie mise à jour.</span><span class="sxs-lookup"><span data-stu-id="f719a-152">With Topology Builder already open, you can proceed to step 3 in <A href="lync-server-2013-publish-the-updated-topology.md">Publish the updated topology in Lync Server 2013</A> to begin publishing your updated topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

