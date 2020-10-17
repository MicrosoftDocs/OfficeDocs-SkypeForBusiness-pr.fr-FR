---
title: 'Lync Server 2013 : modification des options de base de données d’archivage'
description: 'Lync Server 2013 : modification des options de base de données d’archivage.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing Archiving database options
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48183879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a3751be63e17688ad9258b9773a1a5397b67952
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543580"
---
# <a name="changing-archiving-database-options-in-lync-server-2013"></a><span data-ttu-id="d5098-103">Modification des options de base de données d’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5098-103">Changing Archiving database options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5098-104">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d5098-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d5098-105">Si vous déployez l’archivage à l’aide du stockage SQL Server pour l’archivage du stockage pour l’un de vos utilisateurs, vous pouvez réaliser les modifications suivantes au stockage de la base de données :</span><span class="sxs-lookup"><span data-stu-id="d5098-105">If you deploy Archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>

  - <span data-ttu-id="d5098-106">Utiliser une autre base de données SQL Server pour l’archivage du stockage.</span><span class="sxs-lookup"><span data-stu-id="d5098-106">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="d5098-107">Cela inclut la base de données d’archivage principale et toute base de données que vous utilisez pour la mise en miroir SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d5098-107">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>

  - <span data-ttu-id="d5098-108">Basculez vers l’intégration de Microsoft Exchange pour stocker les données d’archivage et les fichiers sur les serveurs Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="d5098-108">Switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers.</span></span> <span data-ttu-id="d5098-109">Si tous vos utilisateurs sont hébergés sur vos serveurs Exchange 2013 et que vous souhaitez utiliser le stockage Microsoft Exchange pour tous les utilisateurs de votre déploiement, vous devez supprimer les bases de données du magasin SQL Server de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="d5098-109">If all your users are homed on your Exchange 2013 servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span>

<span data-ttu-id="d5098-110">Pour effectuer l’une ou l’autre de ces modifications, vous devez exécuter le générateur de topologie, effectuer les modifications, puis publier à nouveau la topologie.</span><span class="sxs-lookup"><span data-stu-id="d5098-110">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="d5098-111">Pour ce faire, vous pouvez utiliser le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="d5098-111">You can use Topology Builder to do this.</span></span> <span data-ttu-id="d5098-112">Ne spécifiez pas le **magasin SQL Server d’archivage** ou activez les informations de **mise en miroir du magasin SQL Server** , sauf si vous avez des utilisateurs Lync qui ne sont pas hébergés sur des serveurs Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="d5098-112">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Lync users who are not homed on Exchange 2013 servers.</span></span>

<div>

## <a name="to-change-your-archiving-database-option"></a><span data-ttu-id="d5098-113">Pour modifier vos options de base de données d’archivage</span><span class="sxs-lookup"><span data-stu-id="d5098-113">To change your archiving database option</span></span>

1.  <span data-ttu-id="d5098-114">Sur un ordinateur exécutant Lync Server 2013 ou sur lequel les outils d’administration Lync Server sont installés, ouvrez une session à l’aide d’un compte membre du groupe utilisateurs local (ou d’un compte doté de droits d’utilisateur équivalents).</span><span class="sxs-lookup"><span data-stu-id="d5098-114">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d5098-115">Vous pouvez définir une topologie à l’aide d’un compte membre du groupe utilisateurs local, mais pour publier une topologie, qui est requise pour ajouter un composant à la topologie, vous devez utiliser un compte membre du groupe <STRONG>administrateurs du domaine</STRONG> et du groupe <STRONG>RTCUniversalServerAdmins</STRONG> ., et qui dispose des autorisations contrôle total (c’est-à-dire, lecture, écriture et modification) sur le partage de fichiers que vous utilisez pour le magasin de fichiers Lync Server 2013 (c’est-à-dire que le générateur de topologies peut configurer les listes de contrôle d’accès discrétionnaire (DACL) requises ou un compte avec des droits équivalents.</span><span class="sxs-lookup"><span data-stu-id="d5098-115">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="d5098-116">Démarrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="d5098-116">Start Topology Builder.</span></span>

3.  <span data-ttu-id="d5098-117">Dans l’arborescence de la console, accédez au pool de serveurs frontaux dans lequel vous avez déployé l’archivage, puis cliquez sur le nom du pool de serveurs frontaux dans lequel vous voulez modifier les options de base de données.</span><span class="sxs-lookup"><span data-stu-id="d5098-117">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>

4.  <span data-ttu-id="d5098-118">Dans le menu **Action**, cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="d5098-118">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="d5098-119">Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **Général**.</span><span class="sxs-lookup"><span data-stu-id="d5098-119">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="d5098-120">Faites défiler la liste jusqu’à **Archivage**.</span><span class="sxs-lookup"><span data-stu-id="d5098-120">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="d5098-121">Dans **Archivage**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d5098-121">In **Archiving**, do the following:</span></span>
    
      - <span data-ttu-id="d5098-122">Pour choisir un autre magasin SQL Server existant, sous **Magasin SQL Server d’archivage**, dans la zone de liste déroulante, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d5098-122">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
        
          - <span data-ttu-id="d5098-123">Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="d5098-123">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
        
          - <span data-ttu-id="d5098-124">Pour spécifier un nouveau magasin SQL Server, cliquez sur **Nouveau**, puis dans la boîte de dialogue **Définir un nouveau magasin SQL Server**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d5098-124">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
            
              - <span data-ttu-id="d5098-125">Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="d5098-125">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
            
              - <span data-ttu-id="d5098-126">Pour spécifier un nouveau magasin SQL Server, cliquez sur **nouveau**, puis dans la boîte de dialogue **définir un nouveau magasin SQL Server** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d5098-126">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
                
                  - <span data-ttu-id="d5098-127">Dans **nom de domaine complet SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur sur lequel vous souhaitez créer le nouveau magasin SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d5098-127">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
                
                  - <span data-ttu-id="d5098-128">Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.</span><span class="sxs-lookup"><span data-stu-id="d5098-128">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
                
                  - <span data-ttu-id="d5098-129">Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans la relation de mise en miroir** , puis, dans **numéro de port miroir**, spécifiez le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="d5098-129">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="d5098-130">Pour ajouter le magasin SQL Server ou choisir un autre magasin SQL Server existant pour la mise en miroir, sélectionnez **Activer la mise en miroir du magasin SQL Server**, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d5098-130">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
        
          - <span data-ttu-id="d5098-131">Pour utiliser un magasin SQL Server existant pour la mise en miroir, dans la zone de liste déroulante **miroir du magasin SQL Server d’archivage** , cliquez sur le nom du magasin SQL Server que vous souhaitez utiliser pour la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="d5098-131">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
        
          - <span data-ttu-id="d5098-132">Pour spécifier un nouveau magasin SQL Server pour la mise en miroir, cliquez sur **nouveau**, puis dans la boîte de dialogue **définir un nouveau magasin SQL Server** , effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="d5098-132">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
            
            1.  <span data-ttu-id="d5098-133">Dans **nom de domaine complet SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur SQL Server sur lequel vous souhaitez créer le nouveau magasin SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d5098-133">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
            
            2.  <span data-ttu-id="d5098-134">Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser.</span><span class="sxs-lookup"><span data-stu-id="d5098-134">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
            
            3.  <span data-ttu-id="d5098-135">Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans la relation de mise en miroir** , puis, dans **numéro de port miroir**, spécifiez le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="d5098-135">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
        
          - <span data-ttu-id="d5098-136">Si vous activez la mise en miroir SQL Server et que vous souhaitez ajouter ou modifier un témoin de mise en miroir SQL Server (une troisième instance de SQL Server qui peut détecter l’intégrité du serveur SQL Server et des instances miroir principales), activez la case à cocher **utiliser le témoin de mise en miroir SQL Server pour activer le basculement automatique** , puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="d5098-136">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
            
            1.  <span data-ttu-id="d5098-137">Dans **nom de domaine complet SQL Server**, spécifiez le nom de domaine complet du serveur sur lequel vous souhaitez créer le nouveau témoin de mise en miroir SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d5098-137">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
            
            2.  <span data-ttu-id="d5098-138">Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser comme témoin de mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="d5098-138">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
            
            3.  <span data-ttu-id="d5098-139">Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans la relation de mise en miroir** , puis, dans **numéro de port miroir**, spécifiez le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="d5098-139">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="d5098-140">Pour passer à l’intégration de Microsoft Exchange afin de stocker les données d’archivage et les fichiers sur les serveurs Exchange 2013 (si tous les utilisateurs de votre déploiement sont hébergés sur vos serveurs Exchange 2013), supprimez toutes les informations pour les bases de données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="d5098-140">To switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers (if all users in your deployment are homed on your Exchange 2013 servers), delete all information for Archiving databases.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d5098-141">Si vous avez des utilisateurs Lync qui ne sont pas hébergés sur des serveurs Exchange 2013, ne supprimez pas les informations du magasin SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d5098-141">If you have any Lync users who are not homed on Exchange 2013 servers, do not delete the SQL Server store information.</span></span>

    
    </div>

8.  <span data-ttu-id="d5098-142">Pour enregistrer la configuration, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5098-142">To save the configuration, click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d5098-143">Les modifications que vous effectuez dans le générateur de topologie ne prennent effet que lorsque vous publiez la nouvelle topologie.</span><span class="sxs-lookup"><span data-stu-id="d5098-143">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="d5098-144">Pour plus d’informations, reportez-vous <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">à la rubrique publication de la topologie mise à jour pour ajouter des bases de données d’archivage dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="d5098-144">For details, see <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Publishing the updated topology to add Archiving databases in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

