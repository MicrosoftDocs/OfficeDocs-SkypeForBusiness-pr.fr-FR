---
title: 'Lync Server 2013: modification des options de base de données d’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changing Archiving database options
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48183879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a98c2efc0dc956a6b8c33f2fcf065f629e5e57d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-archiving-database-options-in-lync-server-2013"></a><span data-ttu-id="8c0eb-102">Modification des options de base de données d’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c0eb-102">Changing Archiving database options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c0eb-103">_**Dernière modification de la rubrique:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8c0eb-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8c0eb-104">Si vous déployez l’archivage à l’aide du stockage SQL Server pour l’archivage pour l’un de vos utilisateurs, vous pouvez effectuer les modifications suivantes du stockage de la base de données:</span><span class="sxs-lookup"><span data-stu-id="8c0eb-104">If you deploy Archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>

  - <span data-ttu-id="8c0eb-105">Utilisez une autre base de données SQL Server pour l’archivage du stockage.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-105">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="8c0eb-106">Il s’agit de la base de données d’archivage principale et de la base de données que vous utilisez pour la mise en miroir SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-106">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>

  - <span data-ttu-id="8c0eb-107">Basculez vers l’intégration de Microsoft Exchange pour stocker les données et fichiers d’archivage sur les serveurs Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-107">Switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers.</span></span> <span data-ttu-id="8c0eb-108">Si tous vos utilisateurs sont sur votre serveur Exchange 2013 et que vous souhaitez utiliser le stockage Microsoft Exchange pour tous les utilisateurs de votre déploiement, vous devez supprimer les bases de données SQL Server Store de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-108">If all your users are homed on your Exchange 2013 servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span>

<span data-ttu-id="8c0eb-109">Pour effectuer l’une de ces modifications, vous devez exécuter le générateur de topologie, apporter les modifications, puis publier de nouveau la topologie.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-109">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="8c0eb-110">Pour cela, vous pouvez utiliser le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-110">You can use Topology Builder to do this.</span></span> <span data-ttu-id="8c0eb-111">Ne spécifiez pas **l’archivage de SQL Server Store** ou activez les informations de **mise en miroir SQL Server Store** , sauf si vous avez des utilisateurs de Lync qui ne sont pas hébergés sur des serveurs Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Lync users who are not homed on Exchange 2013 servers.</span></span>

<div>

## <a name="to-change-your-archiving-database-option"></a><span data-ttu-id="8c0eb-112">Pour modifier l’option de votre base de données d’archivage</span><span class="sxs-lookup"><span data-stu-id="8c0eb-112">To change your archiving database option</span></span>

1.  <span data-ttu-id="8c0eb-113">Sur un ordinateur exécutant Lync Server 2013 ou sur lequel sont installés les outils d’administration de Lync Server, connectez-vous à l’aide d’un compte qui est membre du groupe utilisateurs local (ou d’un compte disposant de droits d’utilisateur équivalents).</span><span class="sxs-lookup"><span data-stu-id="8c0eb-113">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8c0eb-114">Vous pouvez définir une topologie à l’aide d’un compte membre du groupe utilisateurs locaux, mais pour publier une topologie, qui est nécessaire pour ajouter un composant à la topologie, vous devez utiliser un compte membre du groupe <STRONG>administrateurs de domaine</STRONG> et de la <STRONG>RTCUniversalSer. verAdmins</STRONG> et qui dispose des autorisations de contrôle total (en lecture, écriture et modification) sur le partage de fichiers que vous utilisez pour le magasin de fichiers 2013 de Lync Server (c’est-à-dire que le générateur de topologie peut configurer les listes de contrôle d’accès discrétionnaire requises ( DACL ou un compte avec des droits équivalents.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="8c0eb-115">Démarrer le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-115">Start Topology Builder.</span></span>

3.  <span data-ttu-id="8c0eb-116">Dans l’arborescence de la console, accédez au pool de serveurs frontaux dans lequel vous avez déployé l’archivage, puis cliquez sur le nom du pool de serveurs frontaux dans lequel vous voulez modifier les options de base de données.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>

4.  <span data-ttu-id="8c0eb-117">Dans le menu **Action**, cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-117">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="8c0eb-118">Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **Général**.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-118">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="8c0eb-119">Faites défiler la liste jusqu’à **Archivage**.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-119">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="8c0eb-120">Dans **Archivage**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="8c0eb-120">In **Archiving**, do the following:</span></span>
    
      - <span data-ttu-id="8c0eb-121">Pour choisir un autre magasin SQL Server existant, sous **Magasin SQL Server d’archivage**, dans la zone de liste déroulante, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="8c0eb-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
        
          - <span data-ttu-id="8c0eb-122">Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
        
          - <span data-ttu-id="8c0eb-123">Pour spécifier un nouveau magasin SQL Server, cliquez sur **Nouveau**, puis dans la boîte de dialogue **Définir un nouveau magasin SQL Server**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="8c0eb-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
            
              - <span data-ttu-id="8c0eb-124">Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
            
              - <span data-ttu-id="8c0eb-125">Pour spécifier un nouveau SQL Server Store, cliquez sur **nouveau**puis, dans la boîte de dialogue **définir un nouveau SQL Server Store** , procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="8c0eb-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
                
                  - <span data-ttu-id="8c0eb-126">Dans **FQDN SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur sur lequel vous souhaitez créer le nouveau SQL Server Store.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
                
                  - <span data-ttu-id="8c0eb-127">Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
                
                  - <span data-ttu-id="8c0eb-128">Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans une relation en miroir** , puis, dans numéro de port **en miroir**, spécifiez le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="8c0eb-129">Pour ajouter le magasin SQL Server ou choisir un autre magasin SQL Server existant pour la mise en miroir, sélectionnez **Activer la mise en miroir du magasin SQL Server**, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="8c0eb-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
        
          - <span data-ttu-id="8c0eb-130">Pour utiliser un magasin SQL Server existant pour la mise en miroir, dans la zone de liste déroulante archivage de **SQL Server Store** , cliquez sur le nom du magasin SQL Server que vous voulez utiliser pour la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
        
          - <span data-ttu-id="8c0eb-131">Pour spécifier un nouveau magasin SQL Server pour la mise en miroir, cliquez sur **nouveau**puis, dans la boîte de dialogue **définir un nouveau SQL Server Store** , effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="8c0eb-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
            
            1.  <span data-ttu-id="8c0eb-132">Dans **nom de domaine complet SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur SQL sur lequel vous souhaitez créer le nouveau SQL Server Store.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-132">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
            
            2.  <span data-ttu-id="8c0eb-133">Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-133">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
            
            3.  <span data-ttu-id="8c0eb-134">Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans une relation en miroir** , puis, dans numéro de port **en miroir**, spécifiez le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
        
          - <span data-ttu-id="8c0eb-135">Si vous activez la mise en miroir SQL Server et voulez ajouter ou modifier un témoin de mise en miroir SQL Server (troisième instance SQL Server distincte capable de détecter l’état du serveur SQL Server principal et des instances miroir), sélectionnez le **témoin de mise en miroir SQL Server. activez l’option reprise automatique** , puis effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="8c0eb-135">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
            
            1.  <span data-ttu-id="8c0eb-136">Dans **FQDN SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur sur lequel vous souhaitez créer le nouveau témoin de mise en miroir SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-136">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
            
            2.  <span data-ttu-id="8c0eb-137">Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser comme témoin de mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-137">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
            
            3.  <span data-ttu-id="8c0eb-138">Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans une relation en miroir** , puis, dans numéro de port **en miroir**, spécifiez le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-138">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="8c0eb-139">Pour basculer vers l’intégration de Microsoft Exchange pour stocker les données et fichiers d’archivage sur les serveurs Exchange 2013 (si tous les utilisateurs de votre déploiement sont hébergés sur vos serveurs Exchange 2013), supprimez toutes les informations pour l’archivage des bases de données.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-139">To switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers (if all users in your deployment are homed on your Exchange 2013 servers), delete all information for Archiving databases.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8c0eb-140">Si vous avez des utilisateurs de Lync qui ne sont pas hébergés sur des serveurs Exchange 2013, ne supprimez pas les informations du Windows Store SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-140">If you have any Lync users who are not homed on Exchange 2013 servers, do not delete the SQL Server store information.</span></span>

    
    </div>

8.  <span data-ttu-id="8c0eb-141">Pour enregistrer la configuration, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-141">To save the configuration, click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8c0eb-142">Les modifications que vous apportez dans le générateur de topologie ne s’appliquent pas tant que vous n’avez pas publié la nouvelle topologie.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-142">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="8c0eb-143">Pour plus d’informations, reportez-vous <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">à la rubrique publication de la topologie mise à jour pour ajouter des bases de données d’archivage dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="8c0eb-143">For details, see <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Publishing the updated topology to add Archiving databases in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

