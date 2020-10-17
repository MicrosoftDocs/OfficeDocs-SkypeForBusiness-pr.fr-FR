---
title: 'Lync Server 2013 : ajout d’un serveur de conversation permanente à la topologie'
description: 'Lync Server 2013 : ajoutez un serveur de conversation permanente à la topologie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0321978ce4a0c7381cf2915030267645931f572b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572430"
---
# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a><span data-ttu-id="bf3da-103">Ajouter un serveur de conversation permanente à la topologie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf3da-103">Add Persistent Chat Server to the topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf3da-104">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="bf3da-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="bf3da-105">Vous devez incorporer la prise en charge de Lync Server 2013 et du serveur de conversation permanente dans votre topologie avant de pouvoir configurer votre déploiement pour prendre en charge le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="bf3da-105">You must incorporate Lync Server 2013, Persistent Chat Server support in your topology before you can configure your deployment to support Persistent Chat Server.</span></span> <span data-ttu-id="bf3da-106">Les informations contenues dans cette rubrique expliquent comment utiliser le générateur de topologie pour ajouter la prise en charge du serveur de conversation permanente à votre topologie existante.</span><span class="sxs-lookup"><span data-stu-id="bf3da-106">The information in this topic describes how to use Topology Builder to add Persistent Chat Server support to your existing topology.</span></span>

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a><span data-ttu-id="bf3da-107">Pour ajouter un serveur de conversation permanente à une topologie</span><span class="sxs-lookup"><span data-stu-id="bf3da-107">To add Persistent Chat Server to a topology</span></span>

<span data-ttu-id="bf3da-108">Procédez comme suit pour installer un seul pool de serveurs de conversation permanente sans une configuration de récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="bf3da-108">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="bf3da-109">Pour configurer un pool de serveurs de conversation permanente étiré pour la haute disponibilité et la récupération d’urgence, reportez-vous à la rubrique [configuration du serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="bf3da-109">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

<span data-ttu-id="bf3da-110">Pour déployer plusieurs pools de serveurs de conversation permanente, répétez la même procédure pour chaque pool.</span><span class="sxs-lookup"><span data-stu-id="bf3da-110">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>

1.  <span data-ttu-id="bf3da-111">Sur un ordinateur exécutant Lync Server 2013 ou sur lequel les outils d’administration Lync Server sont installés, ouvrez une session à l’aide d’un compte membre du groupe utilisateurs local (ou d’un compte doté de droits d’utilisateur équivalents).</span><span class="sxs-lookup"><span data-stu-id="bf3da-111">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bf3da-112">Vous pouvez définir une topologie à l’aide d’un compte membre du groupe utilisateurs local, mais pour publier une topologie, qui est nécessaire pour installer un serveur Lync Server 2013, vous devez utiliser un compte membre du groupe <STRONG>administrateurs du domaine</STRONG> et du groupe <STRONG>RTCUniversalServerAdmins</STRONG> et qui dispose des autorisations contrôle total (c’est-à-dire, lecture, écriture et modification) sur le magasin de fichiers que vous allez utiliser pour le magasin de fichiers du serveur de conversation permanente (c’est-à-dire que le générateur de topologies peut configurer les DACL requises) ou un compte avec des droits équivalents.</span><span class="sxs-lookup"><span data-stu-id="bf3da-112">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install a Lync Server 2013 server, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (that is, so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="bf3da-113">Démarrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="bf3da-113">Start Topology Builder.</span></span>

3.  <span data-ttu-id="bf3da-114">Dans l’arborescence de la console, accédez au nœud **pools de conversations permanentes** et développez-le pour sélectionner un pool de serveurs de conversation permanente, ou cliquez avec le bouton droit sur le nœud et sélectionnez **nouveau pool de conversations permanentes**.</span><span class="sxs-lookup"><span data-stu-id="bf3da-114">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Persistent Chat Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="bf3da-115">Vous devez définir le nom de domaine complet (FQDN) du pool et indiquer si le pool sera un déploiement de pool à serveur unique ou à plusieurs serveurs.</span><span class="sxs-lookup"><span data-stu-id="bf3da-115">You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="bf3da-116">Vous pouvez choisir un **Pool de plusieurs ordinateurs** ou un **Pool d’un seul ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="bf3da-116">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="bf3da-117">Choisissez le premier si vous envisagez d’avoir plusieurs serveurs frontaux de serveur de conversation permanente dans votre pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="bf3da-117">Choose the former if you are planning to have more than one Persistent Chat Server Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="bf3da-118">Effectuez ce choix maintenant, ou ultérieurement, car une fois créé un pool d’un seul ordinateur, vous ne pourrez pas ajouter d’autres serveurs.</span><span class="sxs-lookup"><span data-stu-id="bf3da-118">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="bf3da-119">Si vous choisissez un pool de plusieurs ordinateurs, entrez les noms des serveurs frontaux individuels de serveur de conversation permanente qui composent le pool.</span><span class="sxs-lookup"><span data-stu-id="bf3da-119">If you choose a multiple computer pool, enter the names of the individual Persistent Chat Server Front End Servers that comprise the pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bf3da-120">Si le rôle serveur de conversation permanente est installé sur un serveur Lync Server 2013 &nbsp; Standard Edition, le nom de domaine complet doit correspondre au nom de domaine complet du serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="bf3da-120">If the Persistent Chat Server role is being installed on a Lync Server 2013&nbsp;Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span>

    
    </div>

4.  <span data-ttu-id="bf3da-121">Définissez un **nom complet** simple pour le pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="bf3da-121">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="bf3da-122">Le nom d’affichage peut être utilisé par les clients personnalisés, en particulier lorsqu’il existe plusieurs pools de serveurs de conversation permanente, pour différencier les salles.</span><span class="sxs-lookup"><span data-stu-id="bf3da-122">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools, to differentiate rooms.</span></span>

5.  <span data-ttu-id="bf3da-123">Définissez le port utilisé par le serveur de conversation permanente pour communiquer avec les serveurs frontaux Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bf3da-123">Define the port used by the Persistent Chat Server to communicate with Lync Server Front End Servers.</span></span> <span data-ttu-id="bf3da-124">Le port par défaut est 5041.</span><span class="sxs-lookup"><span data-stu-id="bf3da-124">The default port is 5041.</span></span>

6.  <span data-ttu-id="bf3da-125">Si votre organisation nécessite la prise en charge de la conformité, cochez la case **Activer la conformité**.</span><span class="sxs-lookup"><span data-stu-id="bf3da-125">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="bf3da-126">Si vous choisissez, le service de conformité du serveur de conversation permanente est installé sur le même ordinateur que le serveur frontal du serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="bf3da-126">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="bf3da-127">Vous êtes invité à sélectionner un serveur principal SQL Server pour la conformité du serveur de conversation permanente par la suite.</span><span class="sxs-lookup"><span data-stu-id="bf3da-127">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>

7.  <span data-ttu-id="bf3da-128">Affectez l’affinité de site pour le pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="bf3da-128">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="bf3da-129">Activez la case à cocher **utiliser ce pool \<SiteName\> comme site par défaut pour le site** ou **Utilisez ce pool comme valeur par défaut pour tous les sites** pour désigner ce pool de serveurs de conversation permanente comme pool par défaut pour le site actuel ou tous les sites.</span><span class="sxs-lookup"><span data-stu-id="bf3da-129">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="bf3da-130">Lorsque le client Lync 2013 est utilisé pour créer et gérer des salles, le pool par défaut associé au site de l’utilisateur est utilisé par l’expérience de création et de gestion de salle afin de pouvoir acheminer les opérations de création et de gestion de salle vers ce pool.</span><span class="sxs-lookup"><span data-stu-id="bf3da-130">When the Lync 2013 client is used to create and manage rooms, the default pool associated with the user’s site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="bf3da-131">Ceci s’applique uniquement lorsque vous avez déployé plusieurs pools de serveurs de conversation permanente et que vous souhaitez utiliser les fonctionnalités de création et de gestion de salle du serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="bf3da-131">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bf3da-132">Vous pouvez personnaliser les fonctionnalités de création et de gestion de salle à l’aide du kit de développement logiciel (SDK) de serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="bf3da-132">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span><BR><span data-ttu-id="bf3da-133">Pour plus d’informations sur la configuration des bases de données de sauvegarde SQL Server pour la récupération d’urgence, voir <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">configuration du serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="bf3da-133">For details about how to configure SQL Server backup databases for disaster recovery, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="bf3da-134">Définissez le **magasin SQL pour le serveur de conversation permanente (où le contenu de la salle de conversation est stocké)** en effectuant l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="bf3da-134">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
      - <span data-ttu-id="bf3da-135">Pour utiliser une base de données SQL Server existante, dans la liste déroulante, cliquez sur le nom de la base de données SQL Server que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="bf3da-135">To use an existing SQL Server database, in the drop-down list, click the name of the SQL Server database that you want to use.</span></span>
    
      - <span data-ttu-id="bf3da-136">Pour spécifier une nouvelle base de données SQL Server, cliquez sur **nouveau**, puis dans **définir un nouveau magasin SQL**, effectuez les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="bf3da-136">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="bf3da-137">Dans **nom de domaine complet SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur SQL Server sur lequel vous voulez créer la nouvelle base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bf3da-137">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
      - <span data-ttu-id="bf3da-138">Sélectionnez **Instance par défaut** pour utiliser l’instance par défaut ou, pour spécifier une autre instance, sélectionnez **Instance nommée**, et spécifiez l’instance que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="bf3da-138">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>

9.  <span data-ttu-id="bf3da-139">Définissez la base de données de conformité SQL Server si vous avez activé la conformité.</span><span class="sxs-lookup"><span data-stu-id="bf3da-139">Define the SQL Server compliance database if you enabled Compliance.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bf3da-140">Pour plus d’informations sur la configuration des miroirs SQL Server pour la haute disponibilité de la base de données du serveur de conversation permanente et de la base de données de conformité du serveur de conversation permanente, reportez-vous à la rubrique <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">configuration du serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="bf3da-140">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

10. <span data-ttu-id="bf3da-141">Définissez le magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="bf3da-141">Define the file store.</span></span> <span data-ttu-id="bf3da-142">Un magasin de fichiers est un dossier dans lequel une copie des fichiers téléchargés dans le référentiel est stockée (par exemple, le stockage des pièces jointes publiées dans une salle de conversation).</span><span class="sxs-lookup"><span data-stu-id="bf3da-142">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="bf3da-143">Dans le cas d’une topologie de serveur de conversation permanente à plusieurs serveurs, il doit s’agir d’un chemin d’accès UNC (Universal Naming Convention); pour une topologie de serveur de conversation permanente à serveur unique, il peut s’agir d’un chemin d’accès de fichier local.</span><span class="sxs-lookup"><span data-stu-id="bf3da-143">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="bf3da-144">Pour utiliser un magasin de fichiers existant, procédez ainsi :</span><span class="sxs-lookup"><span data-stu-id="bf3da-144">To use an existing file store, perform the following steps:</span></span>
    
      - <span data-ttu-id="bf3da-145">Dans **Nom de domaine complet du serveur de fichiers**, indiquez le nom de domaine complet du magasin de fichiers dans lequel vous voulez créer le nouveau magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="bf3da-145">In **File Server FQDN**, specify the FQDN of the file store on which you want to create the new file store.</span></span>
    
      - <span data-ttu-id="bf3da-146">Dans **Partage de fichiers**, indiquez le magasin de fichiers à utiliser.</span><span class="sxs-lookup"><span data-stu-id="bf3da-146">In **File Share**, specify the file store that you want to use.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bf3da-147">Vous pouvez définir le magasin de fichiers dans le générateur de topologie avant de créer le magasin de fichiers, mais vous devez créer le magasin de fichiers à l’emplacement défini que vous définissez avant de publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="bf3da-147">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span>

    
    </div>

11. <span data-ttu-id="bf3da-148">Sélectionnez le pool de serveurs frontaux à utiliser comme tronçon suivant pour ce pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="bf3da-148">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="bf3da-149">Il s’agit du pool de serveurs frontaux qui pourra acheminer les demandes de serveur de conversation permanente vers ce pool.</span><span class="sxs-lookup"><span data-stu-id="bf3da-149">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>

12. <span data-ttu-id="bf3da-150">Pour enregistrer la configuration, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="bf3da-150">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="bf3da-151">Le pool de serveurs de conversation permanente apparaît dans le générateur de topologie, accompagné de vos paramètres de pool spécifiques.</span><span class="sxs-lookup"><span data-stu-id="bf3da-151">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="bf3da-152">Pour publier votre topologie mise à jour sur laquelle vous avez un serveur de conversation permanente, voir [publier la topologie mise à jour dans Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="bf3da-152">To now publish your updated topology to which you’ve Persistent Chat Server, see [Publish the updated topology in Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bf3da-153">Lorsque le générateur de topologies est déjà ouvert, vous pouvez passer à l’étape 3 de <A href="lync-server-2013-publish-the-updated-topology.md">la publication de la topologie mise à jour dans Lync Server 2013</A> pour commencer à publier votre topologie mise à jour.</span><span class="sxs-lookup"><span data-stu-id="bf3da-153">With Topology Builder already open, you can proceed to step 3 in <A href="lync-server-2013-publish-the-updated-topology.md">Publish the updated topology in Lync Server 2013</A> to begin publishing your updated topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

