---
title: Modifier les options de base de données d’archivage dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Résumé : Découvrez comment modifier les options de base de données d’archivage pour Skype Entreprise Server.'
ms.openlocfilehash: 9a2b1056b6dd5d31c8b1dda658e219c345b28278
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817694"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a><span data-ttu-id="78203-103">Modifier les options de base de données d’archivage dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="78203-103">Change Archiving database options in Skype for Business Server</span></span>

<span data-ttu-id="78203-104">**Résumé :** Découvrez comment modifier les options de base de données d’archivage pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="78203-104">**Summary:** Learn how to change archiving database options for Skype for Business Server.</span></span>
  
<span data-ttu-id="78203-105">Si vous déployez l’archivage à l’aide SQL Server stockage d’archivage pour l’un de vos utilisateurs, vous pouvez apporter les modifications suivantes au stockage de base de données :</span><span class="sxs-lookup"><span data-stu-id="78203-105">If you deploy archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>
  
- <span data-ttu-id="78203-106">Utilisez une base de données SQL Server d’archivage différente.</span><span class="sxs-lookup"><span data-stu-id="78203-106">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="78203-107">Cela inclut la base de données d’archivage principale et toute base de données que vous utilisez pour SQL Server miroir.</span><span class="sxs-lookup"><span data-stu-id="78203-107">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>
    
- <span data-ttu-id="78203-108">Basculez vers l’intégration Microsoft Exchange pour stocker les données d’archivage et les fichiers sur les serveurs Exchange.</span><span class="sxs-lookup"><span data-stu-id="78203-108">Switch to Microsoft Exchange integration to store archiving data and files on Exchange servers.</span></span> <span data-ttu-id="78203-109">Si tous vos utilisateurs sont stockés sur vos serveurs Exchange et que vous souhaitez utiliser le stockage Microsoft Exchange pour tous les utilisateurs de votre déploiement, vous devez supprimer les bases de données du magasin SQL Server de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="78203-109">If all your users are homed on your Exchange servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span> 
    
<span data-ttu-id="78203-110">Pour apporter l’une de ces modifications, vous devez exécuter le Générateur de topologies, effectuer les modifications, puis publier à nouveau la topologie.</span><span class="sxs-lookup"><span data-stu-id="78203-110">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="78203-111">Ne spécifiez pas les informations de  mise en SQL Server du magasin d’archivage ou Activer SQL Server store, sauf si vous avez des utilisateurs Skype Entreprise qui ne sont pas dossés sur des serveurs Exchange. </span><span class="sxs-lookup"><span data-stu-id="78203-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Skype for Business users who are not homed on Exchange servers.</span></span>
  
## <a name="change-archiving-database-options"></a><span data-ttu-id="78203-112">Modifier les options de la base de données d’archivage</span><span class="sxs-lookup"><span data-stu-id="78203-112">Change Archiving database options</span></span>

1. <span data-ttu-id="78203-113">Sur un ordinateur exécutant Skype Entreprise Server ou sur lequel les outils d’administration Skype Entreprise Server sont installés, connectez-vous à l’aide d’un compte membre du groupe Utilisateurs local (ou d’un compte avec des droits d’utilisateur équivalents).</span><span class="sxs-lookup"><span data-stu-id="78203-113">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="78203-114">Vous pouvez définir une topologie à l’aide d’un compte membre du groupe Utilisateurs local, mais pour publier une topologie, qui est requise pour ajouter un composant à la topologie, Vous devez utiliser un compte membre du groupe **Administrateurs** du domaine et du groupe **RTCUniversalServerAdmins,** et qui dispose des autorisations de contrôle total (c’est-à-dire, lire, écrire et modifier) sur le partage de fichiers que vous utilisez pour le magasin de fichiers Skype Entreprise Server (c’est-à-dire, pour que le Générateur de topologie puisse configurer les listes de contrôle d’accès discrétionnaire requises ou un compte avec des droits équivalents).</span><span class="sxs-lookup"><span data-stu-id="78203-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Skype for Business Server file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="78203-115">Démarrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="78203-115">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="78203-116">Dans l’arborescence de la console, accédez au pool de serveurs frontaux dans lequel vous avez déployé l’archivage, puis cliquez sur le nom du pool de serveurs frontaux dans lequel vous voulez modifier les options de base de données.</span><span class="sxs-lookup"><span data-stu-id="78203-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>
    
4. <span data-ttu-id="78203-117">Dans le menu **Action**, cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="78203-117">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="78203-118">Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **Général**.</span><span class="sxs-lookup"><span data-stu-id="78203-118">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="78203-119">Faites défiler la liste jusqu’à **Archivage**.</span><span class="sxs-lookup"><span data-stu-id="78203-119">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="78203-120">Dans **Archivage**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="78203-120">In **Archiving**, do the following:</span></span>
    
   - <span data-ttu-id="78203-121">Pour choisir un autre magasin SQL Server existant, sous **Magasin SQL Server d’archivage**, dans la zone de liste déroulante, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="78203-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
    
   - <span data-ttu-id="78203-122">Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="78203-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
   - <span data-ttu-id="78203-123">Pour spécifier un nouveau magasin SQL Server, cliquez sur **Nouveau**, puis dans la boîte de dialogue **Définir un nouveau magasin SQL Server**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="78203-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
    
     - <span data-ttu-id="78203-124">Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="78203-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
     - <span data-ttu-id="78203-125">Pour spécifier une nouvelle SQL Server, cliquez sur **Nouveau,** puis dans la boîte de dialogue Définir un nouveau SQL Server **Store,** faites les choses suivantes :</span><span class="sxs-lookup"><span data-stu-id="78203-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
       - <span data-ttu-id="78203-126">Dans **SQL Server FQDN**, spécifiez le nom de SQL Server serveur sur lequel vous souhaitez créer le nouveau magasin.</span><span class="sxs-lookup"><span data-stu-id="78203-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
       - <span data-ttu-id="78203-127">Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.</span><span class="sxs-lookup"><span data-stu-id="78203-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
       - <span data-ttu-id="78203-128">Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, sélectionnez la case à cocher Cette **instance SQL se** trouve dans la relation de mise en miroir, puis, dans le numéro de **port** Miroir, spécifiez le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="78203-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="78203-129">Pour ajouter le magasin SQL Server ou choisir un autre magasin SQL Server existant pour la mise en miroir, sélectionnez **Activer la mise en miroir du magasin SQL Server**, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="78203-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
    
     - <span data-ttu-id="78203-130">Pour utiliser un magasin SQL Server existant pour la  mise en miroir, dans la zone de liste de listes de listes SQL Server miroir du magasin d’archivage, cliquez sur le nom du magasin SQL Server que vous souhaitez utiliser pour la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="78203-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
     - <span data-ttu-id="78203-131">Pour spécifier un nouveau magasin SQL Server pour la mise en miroir, cliquez sur **Nouveau,** puis dans la boîte de dialogue Définir un nouveau magasin **SQL Server,** faites l’une des choses suivantes :</span><span class="sxs-lookup"><span data-stu-id="78203-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
       <span data-ttu-id="78203-132">a.</span><span class="sxs-lookup"><span data-stu-id="78203-132">a.</span></span> <span data-ttu-id="78203-133">Dans **SQL Server FQDN**, spécifiez le FQDN du SQL Server sur lequel vous souhaitez créer le nouveau magasin SQL Server de données.</span><span class="sxs-lookup"><span data-stu-id="78203-133">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
       <span data-ttu-id="78203-134">b.</span><span class="sxs-lookup"><span data-stu-id="78203-134">b.</span></span> <span data-ttu-id="78203-135">Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser.</span><span class="sxs-lookup"><span data-stu-id="78203-135">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
       <span data-ttu-id="78203-136">c.</span><span class="sxs-lookup"><span data-stu-id="78203-136">c.</span></span> <span data-ttu-id="78203-137">Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, sélectionnez la case à cocher Cette **instance SQL se** trouve dans la relation de mise en miroir, puis, dans le numéro de **port** Miroir, spécifiez le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="78203-137">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="78203-138">Si vous activez la mise en miroir SQL Server et que vous souhaitez ajouter ou modifier un témoin de mise en miroir SQL Server (une troisième instance de SQL Server distincte qui peut détecter l’état d’état du serveur SQL Server principal et des instances miroir), sélectionnez le témoin de mise en miroir Utiliser **SQL Server** pour activer la case à cocher deover automatique, puis faites l’une des choses suivantes :</span><span class="sxs-lookup"><span data-stu-id="78203-138">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
      <span data-ttu-id="78203-139">a.</span><span class="sxs-lookup"><span data-stu-id="78203-139">a.</span></span> <span data-ttu-id="78203-140">Dans **SQL Server FQDN**, spécifiez le nom de groupe du serveur sur lequel vous souhaitez créer le témoin de mise en SQL Server de données.</span><span class="sxs-lookup"><span data-stu-id="78203-140">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
      <span data-ttu-id="78203-141">b.</span><span class="sxs-lookup"><span data-stu-id="78203-141">b.</span></span> <span data-ttu-id="78203-142">Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser comme témoin de mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="78203-142">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
      <span data-ttu-id="78203-143">c.</span><span class="sxs-lookup"><span data-stu-id="78203-143">c.</span></span> <span data-ttu-id="78203-144">Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, sélectionnez la case à cocher Cette **instance SQL se** trouve dans la relation de mise en miroir, puis, dans le numéro de **port** Miroir, spécifiez le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="78203-144">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="78203-145">Pour basculer vers l’intégration Microsoft Exchange afin de stocker les données d’archivage et les fichiers sur les serveurs Exchange (si tous les utilisateurs de votre déploiement sont stockés sur vos serveurs Exchange), supprimez toutes les informations relatives aux bases de données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="78203-145">To switch to Microsoft Exchange integration to store archiving data and files on Exchange servers (if all users in your deployment are homed on your Exchange servers), delete all information for Archiving databases.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="78203-146">Si vous avez des utilisateurs Skype Entreprise qui ne sont pas dossés sur des serveurs Exchange, ne supprimez pas les SQL Server du magasin.</span><span class="sxs-lookup"><span data-stu-id="78203-146">If you have any Skype for Business users who are not homed on Exchange servers, do not delete the SQL Server store information.</span></span> 
  
8. <span data-ttu-id="78203-147">Pour enregistrer la configuration, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="78203-147">To save the configuration, click **OK**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="78203-148">Les modifications apportées dans le Générateur de topologie ne prennent effet qu’une fois que vous avez publié la nouvelle topologie.</span><span class="sxs-lookup"><span data-stu-id="78203-148">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="78203-149">Pour plus d’informations, voir Ajouter des bases de données d’archivage à un déploiement [existant dans Skype Entreprise Server.](../../deploy/deploy-archiving/add-archiving-databases.md)</span><span class="sxs-lookup"><span data-stu-id="78203-149">For details, see [Add archiving databases to an existing deployment in Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md).</span></span> 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a><span data-ttu-id="78203-150">Modifier l’emplacement de la base de données d’archivage à l’aide Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="78203-150">Change the location of the Archiving database by using Windows PowerShell</span></span>

<span data-ttu-id="78203-151">Dans la plupart des cas, vous n’aurez pas besoin de modifier l’emplacement de la base de données d’archivage, qui est spécifié lors de l’installation du serveur d’archivage.</span><span class="sxs-lookup"><span data-stu-id="78203-151">In most cases, you will not need to change the location of the Archiving database, which is specified when you install Archiving Server.</span></span> <span data-ttu-id="78203-152">Toutefois, si une défaillance matérielle ou un autre problème doit se produire,  vous pouvez pointer le serveur d’archivage vers une nouvelle base de données à l’aide de l';</span><span class="sxs-lookup"><span data-stu-id="78203-152">However, if a hardware failure or other problem should occur, you can point Archiving Server to a new database by using the **Set-CsArchivingServer** cmdlet.</span></span>
  
<span data-ttu-id="78203-153">L’exemple suivant modifie l’emplacement de la base de données d’archivage pour le serveur d’archivage ArchivingServer:atl-cs-001.contoso.com Archiving Server.</span><span class="sxs-lookup"><span data-stu-id="78203-153">The following example changes the location of the Archiving database for the ArchivingServer:atl-cs-001.contoso.com Archiving Server.</span></span> <span data-ttu-id="78203-154">Dans cet exemple, la nouvelle base de données se trouve à l’emplacement ArchivingDatabase:atl-sql-001.contoso.com :</span><span class="sxs-lookup"><span data-stu-id="78203-154">In this example, the new database is located at ArchivingDatabase:atl-sql-001.contoso.com:</span></span>
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


