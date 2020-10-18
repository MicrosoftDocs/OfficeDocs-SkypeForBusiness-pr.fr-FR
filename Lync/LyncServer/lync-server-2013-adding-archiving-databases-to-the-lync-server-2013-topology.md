---
title: 'Lync Server 2013 : ajout de bases de données d’archivage à la topologie Lync Server 2013'
description: 'Lync Server 2013 : ajout de bases de données d’archivage à la topologie Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding Archiving databases to the Lync Server 2013 topology
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48183338
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12387c06bc55775ef824c061228a68021046c113
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573040"
---
# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a><span data-ttu-id="1b15f-103">Ajout de bases de données d’archivage à la topologie Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b15f-103">Adding Archiving databases to the Lync Server 2013 topology</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b15f-104">_**Dernière modification de la rubrique :** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="1b15f-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="1b15f-105">Vous devez incorporer l’archivage dans votre topologie avant de configurer votre déploiement pour qu’il prenne en charge l’archivage.</span><span class="sxs-lookup"><span data-stu-id="1b15f-105">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="1b15f-106">Les informations contenues dans cette rubrique expliquent comment utiliser le générateur de topologie pour ajouter l’archivage à votre topologie existante.</span><span class="sxs-lookup"><span data-stu-id="1b15f-106">The information in this topic explains how to use Topology Builder to add archiving to your existing topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1b15f-107">Si vous souhaitez utiliser l’intégration de Microsoft Exchange pour stocker les données d’archivage et les fichiers sur les serveurs Exchange 2013 pour tous les utilisateurs de votre déploiement, ne spécifiez pas le <STRONG>magasin SQL Server d’archivage</STRONG> ou n’utilisez pas les informations de <STRONG>mise en miroir du magasin SQL Server</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="1b15f-107">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers for all your users in your deployment, do not specify <STRONG>Archiving SQL Server store</STRONG> or <STRONG>Use SQL Server Store mirroring</STRONG> information.</span></span>



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a><span data-ttu-id="1b15f-108">Pour ajouter la prise en charge de la base de données d’archivage à votre topologie</span><span class="sxs-lookup"><span data-stu-id="1b15f-108">To add Archiving database support to your topology</span></span>

1.  <span data-ttu-id="1b15f-109">Sur un ordinateur exécutant Lync Server 2013 ou sur lequel les outils d’administration Lync Server sont installés, ouvrez une session à l’aide d’un compte membre du groupe utilisateurs local (ou d’un compte doté de droits d’utilisateur équivalents).</span><span class="sxs-lookup"><span data-stu-id="1b15f-109">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1b15f-110">Vous pouvez définir une topologie à l’aide d’un compte membre du groupe utilisateurs local, mais pour publier une topologie, qui est requise pour ajouter un serveur à la topologie, vous devez utiliser un compte membre du groupe <STRONG>administrateurs du domaine</STRONG> et du groupe <STRONG>RTCUniversalServerAdmins</STRONG> ., et qui dispose des autorisations contrôle total (c’est-à-dire, lecture, écriture et modification) sur le partage de fichiers que vous utilisez pour le magasin de fichiers Lync Server 2013 (c’est-à-dire que le générateur de topologies peut configurer la liste de contrôle d’accès discrétionnaire (DACL) requise ou un compte avec des droits équivalents.</span><span class="sxs-lookup"><span data-stu-id="1b15f-110">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="1b15f-111">Démarrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="1b15f-111">Start Topology Builder.</span></span>

3.  <span data-ttu-id="1b15f-112">Dans l’arborescence de la console, accédez au pool frontal dans lequel vous voulez déployer l’archivage, puis cliquez sur le nom de ce pool frontal.</span><span class="sxs-lookup"><span data-stu-id="1b15f-112">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy Archiving.</span></span>

4.  <span data-ttu-id="1b15f-113">Dans le menu **Action**, cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="1b15f-113">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="1b15f-114">Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **Général**.</span><span class="sxs-lookup"><span data-stu-id="1b15f-114">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="1b15f-115">Faites défiler la liste jusqu’à **Archivage**.</span><span class="sxs-lookup"><span data-stu-id="1b15f-115">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="1b15f-116">Activez la case à cocher **Archivage**.</span><span class="sxs-lookup"><span data-stu-id="1b15f-116">Select the **Archiving** check box.</span></span>

8.  <span data-ttu-id="1b15f-117">Sous **magasin SQL Server d’archivage,** effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1b15f-117">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
      - <span data-ttu-id="1b15f-118">Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="1b15f-118">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="1b15f-119">Si tous vos utilisateurs sont hébergés sur Microsoft Exchange Server 2013 ou version ultérieure, vous pouvez archiver les communications Lync pour tous vos utilisateurs dans Exchange.</span><span class="sxs-lookup"><span data-stu-id="1b15f-119">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Lync communications for all your users in Exchange.</span></span> <span data-ttu-id="1b15f-120">Dans ce cas, vous n’avez pas besoin de configurer le magasin d’archivage SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1b15f-120">In this case, you don’t need to configure SQL Server Archiving store.</span></span>
    
      - <span data-ttu-id="1b15f-121">Pour spécifier un nouveau magasin SQL Server, cliquez sur **nouveau**, puis dans la boîte de dialogue **définir un nouveau magasin SQL Server** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="1b15f-121">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
        
          - <span data-ttu-id="1b15f-122">Dans **nom de domaine complet SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur sur lequel vous souhaitez créer le nouveau magasin SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1b15f-122">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
        
          - <span data-ttu-id="1b15f-123">Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.</span><span class="sxs-lookup"><span data-stu-id="1b15f-123">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
        
          - <span data-ttu-id="1b15f-124">Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans la relation de mise en miroir** , puis, dans **numéro de port miroir**, spécifiez le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="1b15f-124">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

9.  <span data-ttu-id="1b15f-125">Si vous souhaitez utiliser la mise en miroir du magasin SQL Server, sélectionnez **activer la mise en miroir du magasin SQL Server**, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="1b15f-125">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
      - <span data-ttu-id="1b15f-126">Pour utiliser un magasin SQL Server existant pour la mise en miroir, dans la zone de liste déroulante **miroir du magasin SQL Server d’archivage** , cliquez sur le nom du magasin SQL Server que vous souhaitez utiliser pour la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="1b15f-126">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
      - <span data-ttu-id="1b15f-127">Pour spécifier un nouveau magasin SQL Server pour la mise en miroir, cliquez sur **nouveau**, puis dans la boîte de dialogue **définir un nouveau magasin SQL Server** , effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1b15f-127">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
        
        1.  <span data-ttu-id="1b15f-128">Dans **nom de domaine complet SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur SQL Server sur lequel vous souhaitez créer le nouveau magasin SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1b15f-128">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
        
        2.  <span data-ttu-id="1b15f-129">Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser.</span><span class="sxs-lookup"><span data-stu-id="1b15f-129">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
        
        3.  <span data-ttu-id="1b15f-130">Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans la relation de mise en miroir** , puis, dans **numéro de port miroir**, spécifiez le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="1b15f-130">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="1b15f-131">Si vous activez la mise en miroir SQL Server et que vous souhaitez inclure un témoin de mise en miroir SQL Server (une troisième instance SQL Server distincte qui peut détecter l’intégrité du serveur SQL Server et des instances miroir principales), activez la case à cocher **utiliser le témoin de mise en miroir SQL Server pour activer le basculement automatique** , puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1b15f-131">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
        
        1.  <span data-ttu-id="1b15f-132">Dans **nom de domaine complet SQL Server**, spécifiez le nom de domaine complet du serveur sur lequel vous souhaitez créer le nouveau témoin de mise en miroir SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1b15f-132">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
        
        2.  <span data-ttu-id="1b15f-133">Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser comme témoin de mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="1b15f-133">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
        
        3.  <span data-ttu-id="1b15f-134">Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans la relation de mise en miroir** , puis, dans **numéro de port miroir**, spécifiez le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="1b15f-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

10. <span data-ttu-id="1b15f-135">Pour enregistrer la configuration, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b15f-135">To save the configuration, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

