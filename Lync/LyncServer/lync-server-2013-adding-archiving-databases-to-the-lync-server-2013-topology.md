---
title: 'Lync Server 2013: ajout de bases de données d’archivage à la topologie Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding Archiving databases to the Lync Server 2013 topology
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48183338
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe77c57050d6d6c70d5818405fd657d5a8fd3f0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a><span data-ttu-id="b4f85-102">Ajouter des bases de données d’archivage à la topologie Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4f85-102">Adding Archiving databases to the Lync Server 2013 topology</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4f85-103">_**Dernière modification de la rubrique:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="b4f85-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="b4f85-104">Vous devez incorporer l’archivage dans votre topologie avant de configurer votre déploiement pour qu’il prenne en charge l’archivage.</span><span class="sxs-lookup"><span data-stu-id="b4f85-104">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="b4f85-105">Les informations contenues dans cet article vous expliquent comment utiliser le générateur de topologie pour ajouter l’archivage à votre topologie existante.</span><span class="sxs-lookup"><span data-stu-id="b4f85-105">The information in this topic explains how to use Topology Builder to add archiving to your existing topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b4f85-106">Si vous souhaitez utiliser l’intégration de Microsoft Exchange pour stocker les données et fichiers d’archivage sur les serveurs Exchange 2013 pour tous les utilisateurs de votre déploiement, ne spécifiez pas <STRONG>l’archivage de SQL Server Store</STRONG> ou n’utilisez pas les informations de <STRONG>mise en miroir SQL Server Store</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="b4f85-106">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers for all your users in your deployment, do not specify <STRONG>Archiving SQL Server store</STRONG> or <STRONG>Use SQL Server Store mirroring</STRONG> information.</span></span>



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a><span data-ttu-id="b4f85-107">Pour ajouter la prise en charge de la base de données d’archivage à votre topologie</span><span class="sxs-lookup"><span data-stu-id="b4f85-107">To add Archiving database support to your topology</span></span>

1.  <span data-ttu-id="b4f85-108">Sur un ordinateur exécutant Lync Server 2013 ou sur lequel sont installés les outils d’administration de Lync Server, connectez-vous à l’aide d’un compte qui est membre du groupe utilisateurs local (ou d’un compte disposant de droits d’utilisateur équivalents).</span><span class="sxs-lookup"><span data-stu-id="b4f85-108">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b4f85-109">Vous pouvez définir une topologie à l’aide d’un compte membre du groupe utilisateurs locaux, mais pour publier une topologie, qui est nécessaire pour ajouter un serveur à la topologie, vous devez utiliser un compte membre du groupe <STRONG>administrateurs de domaine</STRONG> et de la <STRONG>RTCUniversalServer. </STRONG>Le groupe administrateurs et qui dispose des autorisations contrôle total (lecture, écriture et modification) sur le partage de fichiers que vous utilisez pour le magasin de fichiers 2013 de Lync Server (c’est-à-dire, afin que le générateur de topologie puisse configurer la liste de contrôle d’accès discrétionnaire requise (DACL) ou un compte disposant de droits équivalents.</span><span class="sxs-lookup"><span data-stu-id="b4f85-109">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="b4f85-110">Démarrer le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="b4f85-110">Start Topology Builder.</span></span>

3.  <span data-ttu-id="b4f85-111">Dans l’arborescence de la console, naviguez jusqu’au pool frontal dans lequel vous voulez déployer l’archivage, puis cliquez sur le nom du pool frontal pour lequel vous voulez déployer l’archivage.</span><span class="sxs-lookup"><span data-stu-id="b4f85-111">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy Archiving.</span></span>

4.  <span data-ttu-id="b4f85-112">Dans le menu **Action**, cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b4f85-112">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="b4f85-113">Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **Général**.</span><span class="sxs-lookup"><span data-stu-id="b4f85-113">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="b4f85-114">Faites défiler la liste jusqu’à **Archivage**.</span><span class="sxs-lookup"><span data-stu-id="b4f85-114">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="b4f85-115">Activez la case à cocher **Archivage**.</span><span class="sxs-lookup"><span data-stu-id="b4f85-115">Select the **Archiving** check box.</span></span>

8.  <span data-ttu-id="b4f85-116">Sous **archivage de SQL Server Store,** effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="b4f85-116">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
      - <span data-ttu-id="b4f85-117">Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="b4f85-117">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="b4f85-118">Si tous vos utilisateurs sont hébergés sur Microsoft Exchange Server 2013 ou une version ultérieure, vous pouvez archiver les communications Lync pour tous vos utilisateurs dans Exchange.</span><span class="sxs-lookup"><span data-stu-id="b4f85-118">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Lync communications for all your users in Exchange.</span></span> <span data-ttu-id="b4f85-119">Dans ce cas, vous n’avez pas besoin de configurer le magasin SQL Server d’archivage.</span><span class="sxs-lookup"><span data-stu-id="b4f85-119">In this case, you don’t need to configure SQL Server Archiving store.</span></span>
    
      - <span data-ttu-id="b4f85-120">Pour spécifier un nouveau SQL Server Store, cliquez sur **nouveau**puis, dans la boîte de dialogue **définir un nouveau SQL Server Store** , procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="b4f85-120">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
        
          - <span data-ttu-id="b4f85-121">Dans **FQDN SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur sur lequel vous souhaitez créer le nouveau SQL Server Store.</span><span class="sxs-lookup"><span data-stu-id="b4f85-121">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
        
          - <span data-ttu-id="b4f85-122">Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.</span><span class="sxs-lookup"><span data-stu-id="b4f85-122">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
        
          - <span data-ttu-id="b4f85-123">Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans une relation en miroir** , puis, dans numéro de port **en miroir**, spécifiez le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="b4f85-123">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

9.  <span data-ttu-id="b4f85-124">Si vous souhaitez utiliser la mise en miroir SQL Server Store, sélectionnez **activer la mise en miroir SQL Server Store**, puis procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="b4f85-124">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
      - <span data-ttu-id="b4f85-125">Pour utiliser un magasin SQL Server existant pour la mise en miroir, dans la zone de liste déroulante archivage de **SQL Server Store** , cliquez sur le nom du magasin SQL Server que vous voulez utiliser pour la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="b4f85-125">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
      - <span data-ttu-id="b4f85-126">Pour spécifier un nouveau magasin SQL Server pour la mise en miroir, cliquez sur **nouveau**puis, dans la boîte de dialogue **définir un nouveau SQL Server Store** , effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="b4f85-126">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
        
        1.  <span data-ttu-id="b4f85-127">Dans **nom de domaine complet SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur SQL sur lequel vous souhaitez créer le nouveau SQL Server Store.</span><span class="sxs-lookup"><span data-stu-id="b4f85-127">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
        
        2.  <span data-ttu-id="b4f85-128">Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.</span><span class="sxs-lookup"><span data-stu-id="b4f85-128">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
        
        3.  <span data-ttu-id="b4f85-129">Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans une relation en miroir** , puis, dans numéro de port **en miroir**, spécifiez le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="b4f85-129">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="b4f85-130">Si vous activez la mise en miroir SQL Server et souhaitez inclure un témoin de mise en miroir SQL Server (troisième instance SQL Server distincte capable de détecter l’état du serveur SQL Server principal et des instances de miroirs), sélectionnez le **témoin d’utilisation de miroirs SQL Server à activer. option de reprise automatique** , puis effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="b4f85-130">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
        
        1.  <span data-ttu-id="b4f85-131">Dans **FQDN SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur sur lequel vous souhaitez créer le nouveau témoin de mise en miroir SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b4f85-131">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
        
        2.  <span data-ttu-id="b4f85-132">Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser comme témoin de mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="b4f85-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
        
        3.  <span data-ttu-id="b4f85-133">Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans une relation en miroir** , puis, dans numéro de port **en miroir**, spécifiez le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="b4f85-133">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

10. <span data-ttu-id="b4f85-134">Pour enregistrer la configuration, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4f85-134">To save the configuration, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

