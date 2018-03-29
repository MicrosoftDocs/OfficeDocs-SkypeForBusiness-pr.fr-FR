---
title: Configuration des stratégies utilisateur de conversation permanente dans Skype Entreprise Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Résumé : Lisez cette rubrique pour savoir comment créer des stratégies de l’utilisateur initial pour le serveur Chat persistant dans Skype pour Business Server 2015. Les stratégies utilisateur Chat permanentes déterminent si les utilisateurs sont autorisés à accéder aux salles de conversation.'
ms.openlocfilehash: 01ed6eb048f1949c93260c554eb58d0c76c5259f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="5e421-104">Configuration des stratégies utilisateur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5e421-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5e421-105">**Résumé :** Lisez cette rubrique pour savoir comment créer des stratégies de l’utilisateur initial pour le serveur Chat persistant dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5e421-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="5e421-106">Les stratégies utilisateur Chat permanentes déterminent si les utilisateurs sont autorisés à accéder aux salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="5e421-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="5e421-107">Vous pouvez gérer des stratégies d’utilisateur de serveur de conversation permanent aux niveaux suivants : global, site ou à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5e421-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="5e421-108">Initialement, vous configurez la stratégie globale pour activer les paramètres de conversation permanente pour tous les utilisateurs de votre déploiement, puis créer des stratégies utilisateur et site supplémentaires afin de déterminer si la conversation permanente est activée pour des utilisateurs ou des sites spécifiques.</span><span class="sxs-lookup"><span data-stu-id="5e421-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="5e421-109">Cette rubrique contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="5e421-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="5e421-110">Configurer la stratégie globale</span><span class="sxs-lookup"><span data-stu-id="5e421-110">Configure the global policy</span></span>
    
- <span data-ttu-id="5e421-111">Créer une stratégie de site</span><span class="sxs-lookup"><span data-stu-id="5e421-111">Create a site policy</span></span>
    
- <span data-ttu-id="5e421-112">Créer une stratégie utilisateur</span><span class="sxs-lookup"><span data-stu-id="5e421-112">Create a user policy</span></span>
    
- <span data-ttu-id="5e421-113">Appliquer une stratégie à un utilisateur ou un groupe d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="5e421-113">Apply a policy to a user or user group</span></span>
    
## <a name="configure-the-global-policy"></a><span data-ttu-id="5e421-114">Configurer la stratégie globale</span><span class="sxs-lookup"><span data-stu-id="5e421-114">Configure the global policy</span></span>

<span data-ttu-id="5e421-115">Pour configurer la stratégie globale :</span><span class="sxs-lookup"><span data-stu-id="5e421-115">To configure the global policy:</span></span>
  
1. <span data-ttu-id="5e421-116">À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à n’importe quel ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="5e421-116">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="5e421-117">Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration de Business Server ou ouvrir une fenêtre de navigateur et puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="5e421-117">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="5e421-118">Dans Skype pour le panneau de configuration de Business Server, cliquez sur **Conversation permanent**, puis cliquez sur **Stratégie permanente de Chat**.</span><span class="sxs-lookup"><span data-stu-id="5e421-118">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="5e421-119">Cliquez sur **Globale** dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="5e421-119">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="5e421-120">Dans **Modifier la stratégie de conversation permanente - Globale**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5e421-120">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="5e421-121">Dans **Nom**, spécifiez un nouveau nom pour la stratégie globale si vous ne souhaitez pas utiliser le nom par défaut « Global ».</span><span class="sxs-lookup"><span data-stu-id="5e421-121">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="5e421-122">Dans **Description**, fournissez des détails sur les nouveautés de la stratégie de l’utilisateur (par exemple, une stratégie globale pour _centralSiteName_).</span><span class="sxs-lookup"><span data-stu-id="5e421-122">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="5e421-123">Pour contrôler le Chat permanente pour tous les sites et les utilisateurs ne sont pas spécifiquement contrôlés par une stratégie de site ou de la stratégie de l’utilisateur, activez ou désactivez la case à cocher **Activer le Chat persistant** .</span><span class="sxs-lookup"><span data-stu-id="5e421-123">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="5e421-124">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="5e421-124">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="5e421-125">Créer une stratégie de site</span><span class="sxs-lookup"><span data-stu-id="5e421-125">Create a site policy</span></span>

<span data-ttu-id="5e421-126">Pour chaque site que vous avez déployé, vous pouvez créer une stratégie de conversation permanente spécifique au site.</span><span class="sxs-lookup"><span data-stu-id="5e421-126">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="5e421-127">La configuration de la stratégie de site remplace la stratégie globale, uniquement pour le site pour lequel elle est défini.</span><span class="sxs-lookup"><span data-stu-id="5e421-127">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="5e421-128">Pour créer une stratégie de site :</span><span class="sxs-lookup"><span data-stu-id="5e421-128">To create a site policy:</span></span>
  
1. <span data-ttu-id="5e421-129">À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à n’importe quel ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="5e421-129">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="5e421-130">Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration de Business Server ou ouvrir une fenêtre de navigateur et puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="5e421-130">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="5e421-131">Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.</span><span class="sxs-lookup"><span data-stu-id="5e421-131">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="5e421-132">Cliquez sur **Créer**, puis sur **Stratégie de site**.</span><span class="sxs-lookup"><span data-stu-id="5e421-132">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="5e421-133">Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit s’appliquer.</span><span class="sxs-lookup"><span data-stu-id="5e421-133">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="5e421-134">Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5e421-134">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="5e421-135">Dans **Nom**, spécifiez un nom pour la nouvelle stratégie de site (par exemple, « Redmond »).</span><span class="sxs-lookup"><span data-stu-id="5e421-135">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="5e421-136">Dans **Description**, entrez des informations décrivant la stratégie de site (par exemple, « Stratégie de salle de conversation pour Redmond »).</span><span class="sxs-lookup"><span data-stu-id="5e421-136">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="5e421-137">Pour contrôler la conversation permanente pour tous les sites qui ne sont pas contrôlés spécifiquement par le biais d’une stratégie de site, activez ou désactivez la case à cocher **Activer la conversation permanente**.</span><span class="sxs-lookup"><span data-stu-id="5e421-137">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="5e421-138">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="5e421-138">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="5e421-139">Créer une stratégie utilisateur</span><span class="sxs-lookup"><span data-stu-id="5e421-139">Create a user policy</span></span>

<span data-ttu-id="5e421-140">Vous pouvez créer des stratégies propres à l’utilisateur qui remplacent la stratégie globale et les stratégies de tout site auquel appartient l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5e421-140">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="5e421-141">Pour créer une stratégie utilisateur :</span><span class="sxs-lookup"><span data-stu-id="5e421-141">To create a user policy:</span></span>
  
1. <span data-ttu-id="5e421-142">À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à n’importe quel ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="5e421-142">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="5e421-143">Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration de Business Server ou ouvrir une fenêtre de navigateur et puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="5e421-143">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="5e421-144">Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.</span><span class="sxs-lookup"><span data-stu-id="5e421-144">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="5e421-145">Cliquez sur **Créer**, puis sur **Stratégie utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="5e421-145">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="5e421-146">Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5e421-146">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="5e421-147">Dans **Nom**, spécifiez un nom pour la nouvelle stratégie utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5e421-147">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="5e421-148">Dans **Description**, fournissez des détails sur les nouveautés de la stratégie de l’utilisateur (par exemple, Chat persistant de stratégie pour un utilisateur spécifique).</span><span class="sxs-lookup"><span data-stu-id="5e421-148">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="5e421-149">Pour contrôler le Chat permanente pour tous les utilisateurs qui ne sont pas spécifiquement contrôlées par une stratégie utilisateur, activez ou désactivez la case à cocher **Activer le Chat persistant** .</span><span class="sxs-lookup"><span data-stu-id="5e421-149">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="5e421-150">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="5e421-150">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="5e421-151">Appliquer une stratégie à un compte d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="5e421-151">Apply a policy to a user account</span></span>

<span data-ttu-id="5e421-152">Après avoir créé les stratégies, vous pouvez les appliquer à un compte d’utilisateur, comme suit :</span><span class="sxs-lookup"><span data-stu-id="5e421-152">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="5e421-153">À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à n’importe quel ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="5e421-153">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="5e421-154">Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration de Business Server ou ouvrir une fenêtre de navigateur et puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="5e421-154">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="5e421-155">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur à configurer.</span><span class="sxs-lookup"><span data-stu-id="5e421-155">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="5e421-156">Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="5e421-156">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="5e421-157">Dans **Modifier un Skype pour l’utilisateur de serveur d’entreprise** sous **stratégie de Chat persistant**, sélectionnez la stratégie d’utilisateur Chat permanent que vous souhaitez appliquer.</span><span class="sxs-lookup"><span data-stu-id="5e421-157">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5e421-158">La ** \<automatique\> ** les paramètres s’appliquent à la stratégie par défaut en cours.</span><span class="sxs-lookup"><span data-stu-id="5e421-158">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="5e421-159">Le serveur les applique automatiquement.</span><span class="sxs-lookup"><span data-stu-id="5e421-159">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="5e421-160">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="5e421-160">Click **Commit**.</span></span>
    

