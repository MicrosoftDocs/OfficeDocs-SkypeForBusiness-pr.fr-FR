---
title: Ajouter des bases de données d’archivage à un déploiement existant dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Résumé: cette rubrique vous explique comment ajouter des bases de données d’archivage à votre déploiement Skype entreprise Server.'
ms.openlocfilehash: 2110a6c82aed473fdc07e5796075aabdb50c7086
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278996"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a><span data-ttu-id="18e03-103">Ajouter des bases de données d’archivage à un déploiement existant dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="18e03-103">Add archiving databases to an existing deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="18e03-104">**Résumé:** Consultez cette rubrique pour découvrir comment ajouter des bases de données d’archivage à votre déploiement de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="18e03-104">**Summary:** Read this topic to learn how to add archiving databases to your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="18e03-105">Vous devez incorporer l’archivage dans votre topologie avant de configurer votre déploiement pour qu’il prenne en charge l’archivage.</span><span class="sxs-lookup"><span data-stu-id="18e03-105">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="18e03-106">Les informations contenues dans cet article vous expliquent comment utiliser le générateur de topologie pour:</span><span class="sxs-lookup"><span data-stu-id="18e03-106">The information in this topic explains how to use Topology Builder to:</span></span>
  
- <span data-ttu-id="18e03-107">Ajouter une base de données d’archivage à votre topologie.</span><span class="sxs-lookup"><span data-stu-id="18e03-107">Add an archiving database to your topology.</span></span>
    
- <span data-ttu-id="18e03-108">Publiez la topologie mise à jour pour ajouter la base de données d’archivage à votre déploiement de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="18e03-108">Publish the updated topology to add the archiving database to your Skype for Business Server deployment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="18e03-109">Si vous souhaitez utiliser l’intégration de Microsoft Exchange pour stocker les données et fichiers d’archivage sur les serveurs Exchange pour tous les utilisateurs de votre déploiement, ne spécifiez pas **l’archivage de SQL Server Store** ou les informations de **mise en miroir SQL Server Store** .</span><span class="sxs-lookup"><span data-stu-id="18e03-109">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange servers for all your users in your deployment, do not specify **Archiving SQL Server store** or **Use SQL Server Store mirroring** information.</span></span>
  
### <a name="add-an-archiving-database-to-your-topology"></a><span data-ttu-id="18e03-110">Ajouter une base de données d’archivage à votre topologie</span><span class="sxs-lookup"><span data-stu-id="18e03-110">Add an archiving database to your topology</span></span>

1. <span data-ttu-id="18e03-111">Sur un ordinateur exécutant Skype entreprise Server ou sur lequel sont installés les outils d’administration de Skype entreprise Server, connectez-vous à l’aide d’un compte membre du groupe utilisateurs locaux (ou d’un compte possédant des droits d’utilisateur similaires).</span><span class="sxs-lookup"><span data-stu-id="18e03-111">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
2. <span data-ttu-id="18e03-112">Démarrer le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="18e03-112">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="18e03-113">Dans l’arborescence de la console, accédez au pool frontal dans lequel vous voulez déployer l’archivage, puis cliquez sur le nom de ce pool frontal.</span><span class="sxs-lookup"><span data-stu-id="18e03-113">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy archiving.</span></span>
    
4. <span data-ttu-id="18e03-114">Dans le menu **Action**, cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="18e03-114">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="18e03-115">Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **Général**.</span><span class="sxs-lookup"><span data-stu-id="18e03-115">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="18e03-116">Faites défiler la liste jusqu’à **Archivage**.</span><span class="sxs-lookup"><span data-stu-id="18e03-116">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="18e03-117">Activez la case à cocher **Archivage**.</span><span class="sxs-lookup"><span data-stu-id="18e03-117">Select the **Archiving** check box.</span></span>
    
8. <span data-ttu-id="18e03-118">Sous **archivage de SQL Server Store,** effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="18e03-118">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
   - <span data-ttu-id="18e03-119">Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="18e03-119">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="18e03-120">Si tous vos utilisateurs sont hébergés sur Microsoft Exchange Server 2013 ou une version ultérieure, vous pouvez archiver les communications Skype entreprise pour tous vos utilisateurs en échange.</span><span class="sxs-lookup"><span data-stu-id="18e03-120">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Skype for Business communications for all your users in Exchange.</span></span> <span data-ttu-id="18e03-121">Dans ce cas, vous n’avez pas besoin de configurer le magasin SQL Server d’archivage.</span><span class="sxs-lookup"><span data-stu-id="18e03-121">In this case, you don't need to configure SQL Server Archiving store.</span></span>
    
   - <span data-ttu-id="18e03-122">Pour spécifier un nouveau SQL Server Store, cliquez sur **nouveau**puis, dans la boîte de dialogue **définir un nouveau SQL Server Store** , procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="18e03-122">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
   - <span data-ttu-id="18e03-123">Dans **FQDN SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur sur lequel vous souhaitez créer le nouveau SQL Server Store.</span><span class="sxs-lookup"><span data-stu-id="18e03-123">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
   - <span data-ttu-id="18e03-124">Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.</span><span class="sxs-lookup"><span data-stu-id="18e03-124">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
   - <span data-ttu-id="18e03-125">Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans une relation en miroir** , puis, dans numéro de port **en miroir**, spécifiez le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="18e03-125">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
9. <span data-ttu-id="18e03-126">Si vous souhaitez utiliser la mise en miroir SQL Server Store, sélectionnez **activer la mise en miroir SQL Server Store**, puis procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="18e03-126">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
   - <span data-ttu-id="18e03-127">Pour utiliser un magasin SQL Server existant pour la mise en miroir, dans la zone de liste déroulante archivage de **SQL Server Store** , cliquez sur le nom du magasin SQL Server que vous voulez utiliser pour la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="18e03-127">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
   - <span data-ttu-id="18e03-128">Pour spécifier un nouveau magasin SQL Server pour la mise en miroir, cliquez sur **nouveau**puis, dans la boîte de dialogue **définir un nouveau SQL Server Store** , effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="18e03-128">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
     <span data-ttu-id="18e03-129">a.</span><span class="sxs-lookup"><span data-stu-id="18e03-129">a.</span></span> <span data-ttu-id="18e03-130">Dans **nom de domaine complet SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur SQL sur lequel vous souhaitez créer le nouveau SQL Server Store.</span><span class="sxs-lookup"><span data-stu-id="18e03-130">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
     <span data-ttu-id="18e03-131">b.</span><span class="sxs-lookup"><span data-stu-id="18e03-131">b.</span></span> <span data-ttu-id="18e03-132">Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.</span><span class="sxs-lookup"><span data-stu-id="18e03-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
     <span data-ttu-id="18e03-133">c.</span><span class="sxs-lookup"><span data-stu-id="18e03-133">c.</span></span> <span data-ttu-id="18e03-134">Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans une relation en miroir** , puis, dans numéro de port **en miroir**, spécifiez le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="18e03-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="18e03-135">Si vous activez la mise en miroir SQL Server et souhaitez inclure un témoin de mise en miroir SQL Server (troisième instance SQL Server distincte capable de détecter l’état du serveur SQL Server et des instances miroir principales), sélectionnez le \*\*témoin de mise en miroir SQL Server pour activer le service automatique. \*\*activez le basculement, puis effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="18e03-135">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
     <span data-ttu-id="18e03-136">a.</span><span class="sxs-lookup"><span data-stu-id="18e03-136">a.</span></span> <span data-ttu-id="18e03-137">Dans **FQDN SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur sur lequel vous souhaitez créer le nouveau témoin de mise en miroir SQL Server.</span><span class="sxs-lookup"><span data-stu-id="18e03-137">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
     <span data-ttu-id="18e03-138">b.</span><span class="sxs-lookup"><span data-stu-id="18e03-138">b.</span></span> <span data-ttu-id="18e03-139">Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser comme témoin de mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="18e03-139">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
     <span data-ttu-id="18e03-140">c.</span><span class="sxs-lookup"><span data-stu-id="18e03-140">c.</span></span> <span data-ttu-id="18e03-141">Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans une relation en miroir** , puis, dans numéro de port **en miroir**, spécifiez le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="18e03-141">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
10. <span data-ttu-id="18e03-142">Pour enregistrer la configuration, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="18e03-142">To save the configuration, click **OK**.</span></span>
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a><span data-ttu-id="18e03-143">Publier la topologie mise à jour pour ajouter une base de données d’archivage à votre déploiement</span><span class="sxs-lookup"><span data-stu-id="18e03-143">Publish the updated topology to add an archiving database to your deployment</span></span>

1. <span data-ttu-id="18e03-144">Sur un ordinateur exécutant Skype entreprise Server ou sur lequel sont installés les outils d’administration de Skype entreprise Server, connectez-vous à l’aide d’un compte qui est membre du groupe utilisateurs local (ou d’un compte disposant de droits d’utilisateur équivalents).</span><span class="sxs-lookup"><span data-stu-id="18e03-144">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="18e03-145">Vous pouvez définir une topologie à l’aide d’un compte membre du groupe utilisateurs locaux, mais pour publier une topologie, qui est nécessaire pour ajouter un serveur à la topologie, vous devez utiliser un compte membre du groupe **administrateurs de domaine** et de la **RTCUniversalServer. Groupe administrateurs** et qui dispose des autorisations contrôle total (lecture, écriture et modification) sur le partage de fichiers que vous utilisez pour le stockage de fichiers Skype entreprise Server (de sorte que le générateur de topologie puisse configurer la liste de contrôle d’accès discrétionnaire (DACL) requise ou un compte avec des droits équivalents.</span><span class="sxs-lookup"><span data-stu-id="18e03-145">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file share that you are using for the Skype for Business Server file store (so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="18e03-146">Ouvrez la topologie que vous avez créée dans la section précédente à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="18e03-146">Open the topology you created in the previous section using Topology Builder.</span></span>
    
3. <span data-ttu-id="18e03-147">Dans l’arborescence de la console, cliquez avec le bouton droit sur **Skype entreprise Server**, puis cliquez sur **publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="18e03-147">In the console tree, right-click **Skype for Business Server**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="18e03-148">Dans la page **Publier la topologie**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="18e03-148">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="18e03-149">Dans la page **Créer des bases de données**, vérifiez que la base de données est sélectionnée, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="18e03-149">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="18e03-150">Si vous ne disposez pas des autorisations appropriées pour créer des bases de données, vous pouvez annuler la sélection de la base de données et laisser une autre personne dotée des autorisations nécessaires la créer.</span><span class="sxs-lookup"><span data-stu-id="18e03-150">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="18e03-151">> uniquement les bases de données sur les serveurs SQL dédiés peuvent être installées à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="18e03-151">> Only databases on dedicated SQL Servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="18e03-152">Les bases de données situées sur des serveurs SQL colocalisés avec d’autres composants serveur doivent être installées via une installation locale sur l’ordinateur concerné.</span><span class="sxs-lookup"><span data-stu-id="18e03-152">Databases on SQL Servers that are collocated with other server components must be installed by running local setup on that computer.</span></span> 
  
6. <span data-ttu-id="18e03-153">Dans la page **Assistant Publication terminé**, assurez-vous que la topologie a été publiée correctement, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="18e03-153">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="18e03-154">Une fois la topologie publiée, vous devez configurer les options et les stratégies relatives à l’archivage pour permettre l’archivage du contenu.</span><span class="sxs-lookup"><span data-stu-id="18e03-154">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="18e03-155">Pour plus d’informations, reportez-vous à la rubrique [Configuration des options d’archivage de Skype entreprise Server](configure-archiving-options.md) et [Configuration des stratégies d’archivage de Skype entreprise Server](configure-archiving-policies.md).</span><span class="sxs-lookup"><span data-stu-id="18e03-155">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server](configure-archiving-policies.md).</span></span> 
  

