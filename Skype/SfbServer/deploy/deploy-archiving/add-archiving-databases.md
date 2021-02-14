---
title: Ajouter des bases de données d’archivage à un déploiement existant dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Résumé : Lisez cette rubrique pour découvrir comment ajouter des bases de données d’archivage à votre déploiement Skype Entreprise Server.'
ms.openlocfilehash: f7642cb79f73ab519938ddcb680f8450347b943d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820674"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a><span data-ttu-id="67bf0-103">Ajouter des bases de données d’archivage à un déploiement existant dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="67bf0-103">Add archiving databases to an existing deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="67bf0-104">**Résumé :** Lisez cette rubrique pour découvrir comment ajouter des bases de données d’archivage à votre déploiement Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="67bf0-104">**Summary:** Read this topic to learn how to add archiving databases to your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="67bf0-105">Vous devez incorporer l’archivage dans votre topologie avant de configurer votre déploiement pour qu’il prenne en charge l’archivage.</span><span class="sxs-lookup"><span data-stu-id="67bf0-105">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="67bf0-106">Les informations de cette rubrique expliquent comment utiliser le Générateur de topologie pour :</span><span class="sxs-lookup"><span data-stu-id="67bf0-106">The information in this topic explains how to use Topology Builder to:</span></span>
  
- <span data-ttu-id="67bf0-107">Ajoutez une base de données d’archivage à votre topologie.</span><span class="sxs-lookup"><span data-stu-id="67bf0-107">Add an archiving database to your topology.</span></span>
    
- <span data-ttu-id="67bf0-108">Publiez la topologie mise à jour pour ajouter la base de données d’archivage à votre déploiement Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="67bf0-108">Publish the updated topology to add the archiving database to your Skype for Business Server deployment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="67bf0-109">Si vous souhaitez utiliser l’intégration De Microsoft Exchange pour stocker des données d’archivage et des fichiers sur des serveurs Exchange pour tous vos utilisateurs dans votre déploiement, ne spécifiez pas le magasin **d’archivage SQL Server** ou utilisez les informations de mise en miroir du **SQL Server Store.**</span><span class="sxs-lookup"><span data-stu-id="67bf0-109">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange servers for all your users in your deployment, do not specify **Archiving SQL Server store** or **Use SQL Server Store mirroring** information.</span></span>
  
### <a name="add-an-archiving-database-to-your-topology"></a><span data-ttu-id="67bf0-110">Ajouter une base de données d’archivage à votre topologie</span><span class="sxs-lookup"><span data-stu-id="67bf0-110">Add an archiving database to your topology</span></span>

1. <span data-ttu-id="67bf0-111">Sur un ordinateur exécutant Skype Entreprise Server ou sur lequel les outils d’administration Skype Entreprise Server sont installés, connectez-vous à l’aide d’un compte membre du groupe Utilisateurs local (ou d’un compte avec des droits d’utilisateur équivalents).</span><span class="sxs-lookup"><span data-stu-id="67bf0-111">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
2. <span data-ttu-id="67bf0-112">Démarrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="67bf0-112">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="67bf0-113">Dans l’arborescence de la console, accédez au pool frontal dans lequel vous souhaitez déployer l’archivage, puis cliquez sur le nom du pool frontal où vous souhaitez déployer l’archivage.</span><span class="sxs-lookup"><span data-stu-id="67bf0-113">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy archiving.</span></span>
    
4. <span data-ttu-id="67bf0-114">Dans le menu **Action**, cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="67bf0-114">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="67bf0-115">Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **Général**.</span><span class="sxs-lookup"><span data-stu-id="67bf0-115">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="67bf0-116">Faites défiler la liste jusqu’à **Archivage**.</span><span class="sxs-lookup"><span data-stu-id="67bf0-116">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="67bf0-117">Activez la case à cocher **Archivage**.</span><span class="sxs-lookup"><span data-stu-id="67bf0-117">Select the **Archiving** check box.</span></span>
    
8. <span data-ttu-id="67bf0-118">Sous **Archiver SQL Server store,** faites l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="67bf0-118">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
   - <span data-ttu-id="67bf0-119">Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="67bf0-119">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="67bf0-120">Si tous vos utilisateurs sont Microsoft Exchange Server 2013 ou supérieur, vous pouvez archiver les communications Skype Entreprise pour tous vos utilisateurs dans Exchange.</span><span class="sxs-lookup"><span data-stu-id="67bf0-120">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Skype for Business communications for all your users in Exchange.</span></span> <span data-ttu-id="67bf0-121">Dans ce cas, vous n’avez pas besoin de configurer le SQL Server’archivage.</span><span class="sxs-lookup"><span data-stu-id="67bf0-121">In this case, you don't need to configure SQL Server Archiving store.</span></span>
    
   - <span data-ttu-id="67bf0-122">Pour spécifier une nouvelle SQL Server, cliquez sur **Nouveau,** puis dans la boîte de dialogue Définir un nouveau SQL Server **Store,** faites les choses suivantes :</span><span class="sxs-lookup"><span data-stu-id="67bf0-122">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
   - <span data-ttu-id="67bf0-123">Dans **SQL Server FQDN**, spécifiez le nom de SQL Server serveur sur lequel vous souhaitez créer le nouveau magasin.</span><span class="sxs-lookup"><span data-stu-id="67bf0-123">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
   - <span data-ttu-id="67bf0-124">Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.</span><span class="sxs-lookup"><span data-stu-id="67bf0-124">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
   - <span data-ttu-id="67bf0-125">Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, sélectionnez la case à cocher Cette **instance SQL se** trouve dans la relation de mise en miroir, puis, dans le numéro de **port** Miroir, spécifiez le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="67bf0-125">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
9. <span data-ttu-id="67bf0-126">Si vous souhaitez utiliser la mise en miroir SQL Server store, sélectionnez Activer SQL Server mise en miroir du **Store,** puis faites les choses suivantes :</span><span class="sxs-lookup"><span data-stu-id="67bf0-126">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
   - <span data-ttu-id="67bf0-127">Pour utiliser un magasin SQL Server existant pour la  mise en miroir, dans la zone de liste de listes de listes SQL Server miroir du magasin d’archivage, cliquez sur le nom du magasin SQL Server que vous souhaitez utiliser pour la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="67bf0-127">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
   - <span data-ttu-id="67bf0-128">Pour spécifier un nouveau magasin SQL Server pour la mise en miroir, cliquez sur **Nouveau,** puis dans la boîte de dialogue Définir un nouveau magasin **SQL Server,** faites l’une des choses suivantes :</span><span class="sxs-lookup"><span data-stu-id="67bf0-128">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
     <span data-ttu-id="67bf0-129">a.</span><span class="sxs-lookup"><span data-stu-id="67bf0-129">a.</span></span> <span data-ttu-id="67bf0-130">Dans **SQL Server FQDN**, spécifiez le FQDN du SQL Server sur lequel vous souhaitez créer le nouveau magasin SQL Server de données.</span><span class="sxs-lookup"><span data-stu-id="67bf0-130">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
     <span data-ttu-id="67bf0-131">b.</span><span class="sxs-lookup"><span data-stu-id="67bf0-131">b.</span></span> <span data-ttu-id="67bf0-132">Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser.</span><span class="sxs-lookup"><span data-stu-id="67bf0-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
     <span data-ttu-id="67bf0-133">c.</span><span class="sxs-lookup"><span data-stu-id="67bf0-133">c.</span></span> <span data-ttu-id="67bf0-134">Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, sélectionnez la case à cocher Cette **instance SQL se** trouve dans la relation de mise en miroir, puis, dans le numéro de **port** Miroir, spécifiez le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="67bf0-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="67bf0-135">Si vous activez la mise en miroir SQL Server et que vous souhaitez inclure un témoin de mise en miroir SQL Server (une troisième instance de SQL Server distincte qui peut détecter l’état d’SQL Server principal et des instances miroir), sélectionnez le témoin de mise en miroir Utiliser **SQL Server** pour activer la case à cocher deover automatique, puis faites l’une des choses suivantes :</span><span class="sxs-lookup"><span data-stu-id="67bf0-135">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
     <span data-ttu-id="67bf0-136">a.</span><span class="sxs-lookup"><span data-stu-id="67bf0-136">a.</span></span> <span data-ttu-id="67bf0-137">Dans **SQL Server FQDN**, spécifiez le nom de groupe du serveur sur lequel vous souhaitez créer le témoin de mise en SQL Server de données.</span><span class="sxs-lookup"><span data-stu-id="67bf0-137">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
     <span data-ttu-id="67bf0-138">b.</span><span class="sxs-lookup"><span data-stu-id="67bf0-138">b.</span></span> <span data-ttu-id="67bf0-139">Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser comme témoin de mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="67bf0-139">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
     <span data-ttu-id="67bf0-140">c.</span><span class="sxs-lookup"><span data-stu-id="67bf0-140">c.</span></span> <span data-ttu-id="67bf0-141">Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, sélectionnez la case à cocher Cette **instance SQL se** trouve dans la relation de mise en miroir, puis, dans le numéro de **port** Miroir, spécifiez le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="67bf0-141">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
10. <span data-ttu-id="67bf0-142">Pour enregistrer la configuration, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="67bf0-142">To save the configuration, click **OK**.</span></span>
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a><span data-ttu-id="67bf0-143">Publier la topologie mise à jour pour ajouter une base de données d’archivage à votre déploiement</span><span class="sxs-lookup"><span data-stu-id="67bf0-143">Publish the updated topology to add an archiving database to your deployment</span></span>

1. <span data-ttu-id="67bf0-144">Sur un ordinateur qui exécute Skype Entreprise Server ou sur lequel les outils d’administration Skype Entreprise Server sont installés, connectez-vous à l’aide d’un compte membre du groupe Utilisateurs local (ou d’un compte avec des droits d’utilisateur équivalents).</span><span class="sxs-lookup"><span data-stu-id="67bf0-144">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="67bf0-145">Vous pouvez définir une topologie à l’aide d’un compte membre du groupe Utilisateurs local, mais pour publier une topologie, qui est requis pour ajouter un serveur à la topologie, vous devez utiliser un compte membre du groupe **Administrateurs** du domaine et du groupe **RTCUniversalServerAdmins,** qui dispose d’autorisations de contrôle total (lecture, écriture et modification) sur le partage de fichiers que vous utilisez pour le magasin de fichiers Skype Entreprise Server (afin que le Générateur de topologie puisse configurer la liste de contrôle d’accès discrétionnaire requise ou un compte avec des droits équivalents).</span><span class="sxs-lookup"><span data-stu-id="67bf0-145">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file share that you are using for the Skype for Business Server file store (so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="67bf0-146">Ouvrez la topologie que vous avez créée dans la section précédente à l’aide du Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="67bf0-146">Open the topology you created in the previous section using Topology Builder.</span></span>
    
3. <span data-ttu-id="67bf0-147">Dans l’arborescence de la console, cliquez avec le bouton droit sur **Skype Entreprise Server,** puis cliquez sur **Publier la topologie.**</span><span class="sxs-lookup"><span data-stu-id="67bf0-147">In the console tree, right-click **Skype for Business Server**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="67bf0-148">Dans la page **Publier la topologie**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="67bf0-148">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="67bf0-149">Dans la page **Créer des bases de données**, vérifiez que la base de données est sélectionnée, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="67bf0-149">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="67bf0-150">Si vous ne disposez pas des autorisations appropriées pour créer des bases de données, vous pouvez annuler la sélection de la base de données et laisser une autre personne dotée des autorisations nécessaires la créer.</span><span class="sxs-lookup"><span data-stu-id="67bf0-150">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="67bf0-151">> seules les bases de données sur des serveurs SQL dédiés peuvent être installées à l’aide du Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="67bf0-151">> Only databases on dedicated SQL Servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="67bf0-152">Les bases de données situées sur des serveurs SQL Server colocalisés avec d’autres composants serveur doivent être installées via une installation locale sur l’ordinateur concerné.</span><span class="sxs-lookup"><span data-stu-id="67bf0-152">Databases on SQL Servers that are collocated with other server components must be installed by running local setup on that computer.</span></span> 
  
6. <span data-ttu-id="67bf0-153">Sur la page **Assistant Publication terminé**, assurez-vous que la topologie a été publiée comme il se doit, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="67bf0-153">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="67bf0-154">Une fois la topologie publiée, vous devez configurer les options et les stratégies relatives à l’archivage pour permettre l’archivage du contenu.</span><span class="sxs-lookup"><span data-stu-id="67bf0-154">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="67bf0-155">Pour plus d’informations, voir [Configure archiving options for Skype for Business Server](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server](configure-archiving-policies.md).</span><span class="sxs-lookup"><span data-stu-id="67bf0-155">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server](configure-archiving-policies.md).</span></span> 
  

