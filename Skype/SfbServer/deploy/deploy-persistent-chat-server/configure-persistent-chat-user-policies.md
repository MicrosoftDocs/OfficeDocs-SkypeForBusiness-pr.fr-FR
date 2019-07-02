---
title: Configuration des stratégies utilisateur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Résumé: pour plus d’informations sur la création de stratégies utilisateur initiales pour le serveur de conversation persistant dans Skype entreprise Server 2015, consultez la rubrique suivante. Les stratégies utilisateur de conversation permanente déterminent si les utilisateurs sont autorisés à accéder aux salles de conversation.'
ms.openlocfilehash: 3f2a55f3a411fc3020ebe9af57d456f00dd74ef4
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418122"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="3ca48-104">Configuration des stratégies utilisateur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="3ca48-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3ca48-105">**Résumé:** Pour plus d’informations sur la création de stratégies utilisateur initiales pour le serveur de chat permanent dans Skype entreprise Server 2015, lisez cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="3ca48-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="3ca48-106">Les stratégies utilisateur de conversation permanente déterminent si les utilisateurs sont autorisés à accéder aux salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="3ca48-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="3ca48-107">Vous pouvez gérer les stratégies d’utilisateur de chat permanent aux niveaux suivants: global, site ou utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3ca48-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="3ca48-108">Initialement, vous configurez la stratégie globale pour activer les paramètres de conversation permanente pour tous les utilisateurs de votre déploiement, puis créer des stratégies utilisateur et site supplémentaires afin de déterminer si la conversation permanente est activée pour des utilisateurs ou des sites spécifiques.</span><span class="sxs-lookup"><span data-stu-id="3ca48-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="3ca48-109">Cette rubrique contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="3ca48-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="3ca48-110">Configurer la stratégie globale</span><span class="sxs-lookup"><span data-stu-id="3ca48-110">Configure the global policy</span></span>
    
- <span data-ttu-id="3ca48-111">Créer une stratégie de site</span><span class="sxs-lookup"><span data-stu-id="3ca48-111">Create a site policy</span></span>
    
- <span data-ttu-id="3ca48-112">Créer une stratégie utilisateur</span><span class="sxs-lookup"><span data-stu-id="3ca48-112">Create a user policy</span></span>
    
- <span data-ttu-id="3ca48-113">Appliquer une stratégie à un utilisateur ou un groupe d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="3ca48-113">Apply a policy to a user or user group</span></span>
    
> [!NOTE] 
> <span data-ttu-id="3ca48-114">La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3ca48-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="3ca48-115">La même fonctionnalité est disponible dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3ca48-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="3ca48-116">Pour plus d’informations, reportez-vous à la rubrique mise [en route de Microsoft teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="3ca48-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="3ca48-117">Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3ca48-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="configure-the-global-policy"></a><span data-ttu-id="3ca48-118">Configurer la stratégie globale</span><span class="sxs-lookup"><span data-stu-id="3ca48-118">Configure the global policy</span></span>

<span data-ttu-id="3ca48-119">Pour configurer la stratégie globale :</span><span class="sxs-lookup"><span data-stu-id="3ca48-119">To configure the global policy:</span></span>
  
1. <span data-ttu-id="3ca48-120">À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à n’importe quel ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="3ca48-120">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3ca48-121">Dans le menu **Démarrer** , sélectionnez le panneau de configuration Skype entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="3ca48-121">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="3ca48-122">Dans le panneau de configuration Skype entreprise Server, cliquez sur **conversation permanente**, puis sur **stratégie de conversation persistante**.</span><span class="sxs-lookup"><span data-stu-id="3ca48-122">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="3ca48-123">Cliquez sur **Globale** dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="3ca48-123">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="3ca48-124">Dans **Modifier la stratégie de conversation permanente - Globale**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="3ca48-124">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="3ca48-125">Dans **Nom**, spécifiez un nouveau nom pour la stratégie globale si vous ne souhaitez pas utiliser le nom par défaut « Global ».</span><span class="sxs-lookup"><span data-stu-id="3ca48-125">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="3ca48-126">Dans **Description**, indiquez les détails relatifs à la stratégie de l’utilisateur (par exemple, la stratégie globale pour _centralSiteName_).</span><span class="sxs-lookup"><span data-stu-id="3ca48-126">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="3ca48-127">Pour contrôler les discussions permanentes pour tous les sites et les utilisateurs qui ne sont pas spécifiquement contrôlés par le biais d’une stratégie de site ou d’un utilisateur, cochez ou décochez la case **activer les discussions permanentes** .</span><span class="sxs-lookup"><span data-stu-id="3ca48-127">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="3ca48-128">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="3ca48-128">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="3ca48-129">Créer une stratégie de site</span><span class="sxs-lookup"><span data-stu-id="3ca48-129">Create a site policy</span></span>

<span data-ttu-id="3ca48-130">Pour chaque site déployé, vous pouvez créer une stratégie de conversation persistante spécifique au site.</span><span class="sxs-lookup"><span data-stu-id="3ca48-130">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="3ca48-131">La configuration de la stratégie de site remplace la stratégie globale, uniquement pour le site pour lequel elle est définie.</span><span class="sxs-lookup"><span data-stu-id="3ca48-131">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="3ca48-132">Pour créer une stratégie de site:</span><span class="sxs-lookup"><span data-stu-id="3ca48-132">To create a site policy:</span></span>
  
1. <span data-ttu-id="3ca48-133">À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="3ca48-133">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3ca48-134">Dans le menu **Démarrer** , sélectionnez le panneau de configuration Skype entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="3ca48-134">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="3ca48-135">Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.</span><span class="sxs-lookup"><span data-stu-id="3ca48-135">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="3ca48-136">Cliquez sur **Créer**, puis sur **Stratégie de site**.</span><span class="sxs-lookup"><span data-stu-id="3ca48-136">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="3ca48-137">Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit s’appliquer.</span><span class="sxs-lookup"><span data-stu-id="3ca48-137">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="3ca48-138">Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="3ca48-138">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="3ca48-139">Dans **Nom**, spécifiez un nom pour la nouvelle stratégie de site (par exemple, « Redmond »).</span><span class="sxs-lookup"><span data-stu-id="3ca48-139">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="3ca48-140">Dans **Description**, entrez des informations décrivant la stratégie de site (par exemple, « Stratégie de salle de conversation pour Redmond »).</span><span class="sxs-lookup"><span data-stu-id="3ca48-140">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="3ca48-141">Pour contrôler la conversation permanente pour tous les sites qui ne sont pas contrôlés spécifiquement par le biais d’une stratégie de site, activez ou désactivez la case à cocher **Activer la conversation permanente**.</span><span class="sxs-lookup"><span data-stu-id="3ca48-141">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="3ca48-142">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="3ca48-142">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="3ca48-143">Créer une stratégie utilisateur</span><span class="sxs-lookup"><span data-stu-id="3ca48-143">Create a user policy</span></span>

<span data-ttu-id="3ca48-144">Vous pouvez créer des stratégies spécifiques à l’utilisateur qui remplacent la stratégie globale et les stratégies de site auxquelles l’utilisateur appartient.</span><span class="sxs-lookup"><span data-stu-id="3ca48-144">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="3ca48-145">Pour créer une stratégie d’utilisateur:</span><span class="sxs-lookup"><span data-stu-id="3ca48-145">To create a user policy:</span></span>
  
1. <span data-ttu-id="3ca48-146">À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="3ca48-146">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3ca48-147">Dans le menu **Démarrer** , sélectionnez le panneau de configuration Skype entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="3ca48-147">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="3ca48-148">Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.</span><span class="sxs-lookup"><span data-stu-id="3ca48-148">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="3ca48-149">Cliquez sur **Créer**, puis sur **Stratégie utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="3ca48-149">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="3ca48-150">Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="3ca48-150">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="3ca48-151">Dans **Nom**, spécifiez un nom pour la nouvelle stratégie utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3ca48-151">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="3ca48-152">Dans **Description**, indiquez les détails relatifs à la stratégie de l’utilisateur (par exemple, la stratégie de conversation permanente pour un utilisateur spécifique).</span><span class="sxs-lookup"><span data-stu-id="3ca48-152">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="3ca48-153">Pour contrôler la conversation permanente de tous les utilisateurs qui ne sont pas spécifiquement contrôlés par le biais d’une stratégie utilisateur, activez ou désactivez la case à cocher **activer les discussions permanentes** .</span><span class="sxs-lookup"><span data-stu-id="3ca48-153">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="3ca48-154">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="3ca48-154">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="3ca48-155">Appliquer une stratégie à un compte d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="3ca48-155">Apply a policy to a user account</span></span>

<span data-ttu-id="3ca48-156">Lorsque vous créez des stratégies, vous pouvez les appliquer à un compte d’utilisateur en procédant comme suit:</span><span class="sxs-lookup"><span data-stu-id="3ca48-156">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="3ca48-157">À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="3ca48-157">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3ca48-158">Dans le menu **Démarrer** , sélectionnez le panneau de configuration Skype entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="3ca48-158">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="3ca48-159">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur à configurer.</span><span class="sxs-lookup"><span data-stu-id="3ca48-159">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="3ca48-160">Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="3ca48-160">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="3ca48-161">Dans **modifier l’utilisateur de Skype entreprise Server** sous **stratégie de chat persistante**, sélectionnez la stratégie d’utilisateur de conversation permanente que vous voulez appliquer.</span><span class="sxs-lookup"><span data-stu-id="3ca48-161">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3ca48-162">Les \*\* \<paramètres\> automatiques\*\* appliquent la stratégie d’effectivité par défaut.</span><span class="sxs-lookup"><span data-stu-id="3ca48-162">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="3ca48-163">Ces paramètres sont appliqués automatiquement par le serveur.</span><span class="sxs-lookup"><span data-stu-id="3ca48-163">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="3ca48-164">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="3ca48-164">Click **Commit**.</span></span>
    

