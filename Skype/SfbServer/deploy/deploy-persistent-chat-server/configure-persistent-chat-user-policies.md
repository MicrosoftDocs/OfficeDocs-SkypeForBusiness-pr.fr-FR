---
title: Configuration des stratégies utilisateur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Résumé : Lisez cette rubrique pour savoir comment créer des stratégies utilisateur initial for Persistent Chat Server dans Skype pour Business Server 2015. Les stratégies utilisateur Chat permanentes déterminent si les utilisateurs sont autorisés à accéder aux salles de conversation.'
ms.openlocfilehash: e082898d92e622827e2543316b07a8be224c56c3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225454"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="0af86-104">Configuration des stratégies utilisateur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="0af86-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0af86-105">**Résumé :** Lisez cette rubrique pour savoir comment créer des stratégies utilisateur initial for Persistent Chat Server dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0af86-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="0af86-106">Les stratégies utilisateur Chat permanentes déterminent si les utilisateurs sont autorisés à accéder aux salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="0af86-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="0af86-107">Vous pouvez gérer les stratégies d’utilisateur de serveur de conversation permanente aux niveaux suivants : globale, site ou utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0af86-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="0af86-108">Initialement, vous configurez la stratégie globale pour activer les paramètres de conversation permanente pour tous les utilisateurs de votre déploiement, puis créer des stratégies utilisateur et site supplémentaires afin de déterminer si la conversation permanente est activée pour des utilisateurs ou des sites spécifiques.</span><span class="sxs-lookup"><span data-stu-id="0af86-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="0af86-109">Cette rubrique contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="0af86-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="0af86-110">Configurer la stratégie globale</span><span class="sxs-lookup"><span data-stu-id="0af86-110">Configure the global policy</span></span>
    
- <span data-ttu-id="0af86-111">Créer une stratégie de site</span><span class="sxs-lookup"><span data-stu-id="0af86-111">Create a site policy</span></span>
    
- <span data-ttu-id="0af86-112">Créer une stratégie utilisateur</span><span class="sxs-lookup"><span data-stu-id="0af86-112">Create a user policy</span></span>
    
- <span data-ttu-id="0af86-113">Appliquer une stratégie à un utilisateur ou un groupe d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="0af86-113">Apply a policy to a user or user group</span></span>
    
> [!NOTE] 
> <span data-ttu-id="0af86-114">Conversation permanente est disponible dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0af86-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="0af86-115">La même fonctionnalité est disponible dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="0af86-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="0af86-116">Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="0af86-116">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="0af86-117">Si vous devez utiliser la conversation permanente, vos choix est pour migrer les utilisateurs ayant besoin de cette fonctionnalité aux équipes, ou pour continuer à utiliser Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0af86-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="configure-the-global-policy"></a><span data-ttu-id="0af86-118">Configurer la stratégie globale</span><span class="sxs-lookup"><span data-stu-id="0af86-118">Configure the global policy</span></span>

<span data-ttu-id="0af86-119">Pour configurer la stratégie globale :</span><span class="sxs-lookup"><span data-stu-id="0af86-119">To configure the global policy:</span></span>
  
1. <span data-ttu-id="0af86-120">À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à n’importe quel ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="0af86-120">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0af86-121">Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration serveur Business ou ouvrir une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="0af86-121">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="0af86-122">Dans Skype pour Business Server le panneau de configuration, cliquez sur **Conversation permanente**, puis cliquez sur **Stratégie de conversation permanente**.</span><span class="sxs-lookup"><span data-stu-id="0af86-122">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="0af86-123">Cliquez sur **Globale** dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="0af86-123">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="0af86-124">Dans **Modifier la stratégie de conversation permanente - Globale**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0af86-124">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="0af86-125">Dans **Nom**, spécifiez un nouveau nom pour la stratégie globale si vous ne souhaitez pas utiliser le nom par défaut « Global ».</span><span class="sxs-lookup"><span data-stu-id="0af86-125">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="0af86-126">Dans **Description**, fournissez les informations décrivant la stratégie utilisateur (par exemple, stratégie globale pour _Nom_site_central_).</span><span class="sxs-lookup"><span data-stu-id="0af86-126">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="0af86-127">Pour contrôler la conversation permanente pour tous les sites et les utilisateurs ne sont pas spécifiquement contrôlés via une stratégie de site ou d’une stratégie utilisateur, activez ou désactivez la case à cocher **Activer la conversation permanente** .</span><span class="sxs-lookup"><span data-stu-id="0af86-127">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="0af86-128">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="0af86-128">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="0af86-129">Créer une stratégie de site</span><span class="sxs-lookup"><span data-stu-id="0af86-129">Create a site policy</span></span>

<span data-ttu-id="0af86-130">Pour chaque site que vous avez déployé, vous pouvez créer une stratégie de conversation permanente spécifiques au site.</span><span class="sxs-lookup"><span data-stu-id="0af86-130">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="0af86-131">La configuration de la stratégie de site remplace la stratégie globale, uniquement pour le site pour lequel elle est définie.</span><span class="sxs-lookup"><span data-stu-id="0af86-131">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="0af86-132">Pour créer une stratégie de site :</span><span class="sxs-lookup"><span data-stu-id="0af86-132">To create a site policy:</span></span>
  
1. <span data-ttu-id="0af86-133">À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="0af86-133">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0af86-134">Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration serveur Business ou ouvrir une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="0af86-134">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="0af86-135">Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.</span><span class="sxs-lookup"><span data-stu-id="0af86-135">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="0af86-136">Cliquez sur **Créer**, puis sur **Stratégie de site**.</span><span class="sxs-lookup"><span data-stu-id="0af86-136">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="0af86-137">Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit s’appliquer.</span><span class="sxs-lookup"><span data-stu-id="0af86-137">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="0af86-138">Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0af86-138">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="0af86-139">Dans **Nom**, spécifiez un nom pour la nouvelle stratégie de site (par exemple, « Redmond »).</span><span class="sxs-lookup"><span data-stu-id="0af86-139">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="0af86-140">Dans **Description**, entrez des informations décrivant la stratégie de site (par exemple, « Stratégie de salle de conversation pour Redmond »).</span><span class="sxs-lookup"><span data-stu-id="0af86-140">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="0af86-141">Pour contrôler la conversation permanente pour tous les sites qui ne sont pas contrôlés spécifiquement par le biais d’une stratégie de site, activez ou désactivez la case à cocher **Activer la conversation permanente**.</span><span class="sxs-lookup"><span data-stu-id="0af86-141">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="0af86-142">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="0af86-142">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="0af86-143">Créer une stratégie utilisateur</span><span class="sxs-lookup"><span data-stu-id="0af86-143">Create a user policy</span></span>

<span data-ttu-id="0af86-144">Vous pouvez créer des stratégies spécifiques à l’utilisateur qui remplacent la stratégie globale et les stratégies de site auquel appartient l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0af86-144">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="0af86-145">Pour créer une stratégie utilisateur :</span><span class="sxs-lookup"><span data-stu-id="0af86-145">To create a user policy:</span></span>
  
1. <span data-ttu-id="0af86-146">À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="0af86-146">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0af86-147">Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration serveur Business ou ouvrir une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="0af86-147">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="0af86-148">Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.</span><span class="sxs-lookup"><span data-stu-id="0af86-148">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="0af86-149">Cliquez sur **Créer**, puis sur **Stratégie utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="0af86-149">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="0af86-150">Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0af86-150">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="0af86-151">Dans **Nom**, spécifiez un nom pour la nouvelle stratégie utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0af86-151">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="0af86-152">Dans **Description**, fournissez les informations décrivant la stratégie utilisateur (par exemple, stratégie de conversation permanente pour utilisateur spécifique).</span><span class="sxs-lookup"><span data-stu-id="0af86-152">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="0af86-153">Pour contrôler la conversation permanente pour tous les utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie utilisateur, activez ou désactivez la case à cocher **Activer la conversation permanente** .</span><span class="sxs-lookup"><span data-stu-id="0af86-153">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="0af86-154">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="0af86-154">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="0af86-155">Appliquer une stratégie à un compte d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="0af86-155">Apply a policy to a user account</span></span>

<span data-ttu-id="0af86-156">Une fois que vous créez des stratégies, vous pouvez appliquer les à un compte d’utilisateur comme suit :</span><span class="sxs-lookup"><span data-stu-id="0af86-156">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="0af86-157">À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="0af86-157">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0af86-158">Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration serveur Business ou ouvrir une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="0af86-158">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="0af86-159">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur à configurer.</span><span class="sxs-lookup"><span data-stu-id="0af86-159">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="0af86-160">Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="0af86-160">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="0af86-161">Dans **Modifier les Skype pour l’utilisateur Business Server** sous **stratégie de conversation permanente**, sélectionnez la stratégie d’utilisateur de conversation permanente que vous souhaitez appliquer.</span><span class="sxs-lookup"><span data-stu-id="0af86-161">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0af86-162">Le \*\* \<automatique\> \*\* paramètres s’appliquent à la stratégie par défaut en cours.</span><span class="sxs-lookup"><span data-stu-id="0af86-162">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="0af86-163">Ces paramètres sont appliqués automatiquement par le serveur.</span><span class="sxs-lookup"><span data-stu-id="0af86-163">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="0af86-164">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="0af86-164">Click **Commit**.</span></span>
    

