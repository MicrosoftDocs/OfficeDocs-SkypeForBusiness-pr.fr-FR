---
title: Stratégie de conversation permanente – Page principale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0dc18d5c-82d6-4d39-afb1-efdb3ae6d2c7
description: Vous pouvez utiliser la page Stratégie de conversation permanente du groupe Conversation permanente pour gérer les stratégies au niveau utilisateur, site, pool ou global, y compris pour configurer la stratégie globale par défaut et créer une ou plusieurs autres stratégies utilisateur et de site pour votre déploiement. Si un utilisateur est activé pour le serveur Chat permanent par stratégie, l’environnement serveur Chat permanent apparaît dans le client.
ms.openlocfilehash: ed4e8bbcb0856156148f459435b5cec857e9e223
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294171"
---
# <a name="persistent-chat-policy-main-page"></a><span data-ttu-id="35f93-104">Stratégie de conversation permanente – Page principale</span><span class="sxs-lookup"><span data-stu-id="35f93-104">Persistent Chat Policy Main Page</span></span>
 
<span data-ttu-id="35f93-105">Vous pouvez utiliser la page **Stratégie de conversation permanente** du groupe **Conversation permanente** pour gérer les stratégies au niveau utilisateur, site, pool ou global, y compris pour configurer la stratégie globale par défaut et créer une ou plusieurs autres stratégies utilisateur et de site pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="35f93-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="35f93-106">Si un utilisateur est activé pour le serveur Chat permanent par stratégie, l’environnement serveur Chat permanent apparaît dans le client.</span><span class="sxs-lookup"><span data-stu-id="35f93-106">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
> [!NOTE]
> <span data-ttu-id="35f93-107">Dans la topologie, les stratégies de site serveur de chat permanent s’appliquent globalement, le pool de chaque utilisateur, le site de chaque utilisateur ou par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="35f93-107">In the topology, Persistent Chat Server site policies apply globally, per user's pool, or per user's site, or per user.</span></span> 
  
<span data-ttu-id="35f93-108">La stratégie globale est créée automatiquement lorsque vous déployez le serveur Chat permanent et qu’elle peut être configurée, mais pas supprimée.</span><span class="sxs-lookup"><span data-stu-id="35f93-108">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="35f93-109">Dans la mesure où la stratégie globale s’applique à tous les utilisateurs, elle ne doit pas être définie par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="35f93-109">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="35f93-110">Vous pouvez créer et configurer plusieurs stratégies de site et utilisateurs qui, conjointement avec la stratégie globale, permettent aux utilisateurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="35f93-110">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="35f93-111">Les stratégies de serveur de chat permanent de pool et de site remplacent la stratégie de serveur de chat permanent global, mais uniquement pour les utilisateurs de ce site.</span><span class="sxs-lookup"><span data-stu-id="35f93-111">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="35f93-112">Les stratégies utilisateur remplacent les stratégies utilisateur, de pool et globales pour les utilisateurs auxquels la stratégie utilisateur est affectée.</span><span class="sxs-lookup"><span data-stu-id="35f93-112">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="35f93-113">Pour configurer et utiliser le serveur de chat permanent, vous devez d’abord utiliser le générateur de topologie pour ajouter la prise en charge du serveur de chat permanent à la topologie, puis publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="35f93-113">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="35f93-114">Pour plus d’informations, reportez-vous [à la rubrique ajouter un serveur Chat permanent à votre topologie 2015 Skype entreprise Server](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="35f93-114">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="35f93-115">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="35f93-115">Tasks that you can perform</span></span>

<span data-ttu-id="35f93-116">Dans la page **Stratégie de conversation permanente**, vous pouvez effectuer les tâches suivantes : autorisation et gestion de la stratégie de serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="35f93-116">You can perform the following tasks on the **Persistent Chat Policy** page: enable and manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="35f93-117">Pour configurer la stratégie globale pour la conversation permanente</span><span class="sxs-lookup"><span data-stu-id="35f93-117">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="35f93-118">À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="35f93-118">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="35f93-119">Dans le menu **Démarrer** , sélectionnez le panneau de configuration Skype entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="35f93-119">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="35f93-120">Dans le panneau de configuration Skype entreprise Server, cliquez sur **conversation permanente**, puis sur **stratégie de conversation persistante**.</span><span class="sxs-lookup"><span data-stu-id="35f93-120">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="35f93-121">Cliquez sur **Globale** dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="35f93-121">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="35f93-122">Dans **Modifier la stratégie de conversation permanente - Globale**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="35f93-122">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="35f93-123">Dans **Nom**, spécifiez un nouveau nom pour la stratégie globale si vous ne souhaitez pas utiliser le nom par défaut « Global ».</span><span class="sxs-lookup"><span data-stu-id="35f93-123">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="35f93-124">Dans **Description**, indiquez les détails relatifs à la stratégie de l’utilisateur (par exemple, la stratégie globale pour _centralSiteName_).</span><span class="sxs-lookup"><span data-stu-id="35f93-124">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="35f93-125">Pour contrôler les discussions permanentes pour tous les sites et les utilisateurs qui ne sont pas spécifiquement contrôlés par le biais d’une stratégie de site ou d’un utilisateur, cochez ou décochez la case **activer les discussions permanentes** .</span><span class="sxs-lookup"><span data-stu-id="35f93-125">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="35f93-126">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="35f93-126">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="35f93-127">Pour créer une stratégie de conversation permanente pour un site</span><span class="sxs-lookup"><span data-stu-id="35f93-127">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="35f93-128">Pour chaque site déployé, vous pouvez créer une stratégie de conversation persistante spécifique au site.</span><span class="sxs-lookup"><span data-stu-id="35f93-128">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="35f93-129">La configuration de la stratégie de site remplace la stratégie globale, uniquement pour le site pour lequel elle est définie.</span><span class="sxs-lookup"><span data-stu-id="35f93-129">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="35f93-130">À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="35f93-130">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="35f93-131">Dans le menu **Démarrer** , sélectionnez le panneau de configuration Skype entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="35f93-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="35f93-132">Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.</span><span class="sxs-lookup"><span data-stu-id="35f93-132">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="35f93-133">Cliquez sur **Créer**, puis sur **Stratégie de site**.</span><span class="sxs-lookup"><span data-stu-id="35f93-133">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="35f93-134">Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit s’appliquer.</span><span class="sxs-lookup"><span data-stu-id="35f93-134">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="35f93-135">Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="35f93-135">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="35f93-136">Dans **Nom**, spécifiez un nom pour la nouvelle stratégie de site (par exemple, « Redmond »).</span><span class="sxs-lookup"><span data-stu-id="35f93-136">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="35f93-137">Dans **Description**, entrez des informations décrivant la stratégie de site (par exemple, « Stratégie de salle de conversation pour Redmond »).</span><span class="sxs-lookup"><span data-stu-id="35f93-137">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="35f93-138">Pour contrôler la conversation permanente pour tous les sites qui ne sont pas contrôlés spécifiquement par le biais d’une stratégie de site, activez ou désactivez la case à cocher **Activer la conversation permanente**.</span><span class="sxs-lookup"><span data-stu-id="35f93-138">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="35f93-139">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="35f93-139">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="35f93-140">Pour créer une stratégie utilisateur pour la discussion permanente</span><span class="sxs-lookup"><span data-stu-id="35f93-140">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="35f93-141">Le panneau de configuration Skype entreprise Server vous permet de définir des stratégies utilisateur qui peuvent être affectées à \*\*\*\* des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="35f93-141">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="35f93-142">La stratégie utilisateur remplace les stratégies globales et de site, mais uniquement pour les utilisateurs spécifiques auxquels la stratégie utilisateur est affectée.</span><span class="sxs-lookup"><span data-stu-id="35f93-142">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="35f93-143">À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="35f93-143">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="35f93-144">Dans le menu **Démarrer** , sélectionnez le panneau de configuration Skype entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="35f93-144">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="35f93-145">Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.</span><span class="sxs-lookup"><span data-stu-id="35f93-145">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="35f93-146">Cliquez sur **Créer**, puis sur **Stratégie utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="35f93-146">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="35f93-147">Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="35f93-147">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="35f93-148">Dans **Nom**, spécifiez un nom pour la nouvelle stratégie utilisateur.</span><span class="sxs-lookup"><span data-stu-id="35f93-148">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="35f93-149">Dans **Description**, indiquez les détails relatifs à la stratégie de l’utilisateur (par exemple, la stratégie de conversation permanente pour un utilisateur spécifique).</span><span class="sxs-lookup"><span data-stu-id="35f93-149">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="35f93-150">Pour contrôler la conversation permanente de tous les utilisateurs qui ne sont pas spécifiquement contrôlés par le biais d’une stratégie utilisateur, activez ou désactivez la case à cocher **activer les discussions permanentes** .</span><span class="sxs-lookup"><span data-stu-id="35f93-150">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="35f93-151">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="35f93-151">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="35f93-152">Pour appliquer une stratégie utilisateur de conversation permanente à un compte d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="35f93-152">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="35f93-153">Si un utilisateur a été activé pour Skype entreprise, vous pouvez appliquer les stratégies appropriées à des utilisateurs spécifiques pour les activer ou les désactiver pour le serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="35f93-153">If a user has been enabled for Skype for Business, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="35f93-154">Suivez la procédure décrite dans cette rubrique pour appliquer une stratégie d’utilisateur de conversation permanente créée précédemment à un ou plusieurs comptes d’utilisateurs ou groupes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="35f93-154">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="35f93-155">À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="35f93-155">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="35f93-156">Dans le menu **Démarrer** , sélectionnez le panneau de configuration Skype entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="35f93-156">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="35f93-157">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur à configurer.</span><span class="sxs-lookup"><span data-stu-id="35f93-157">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="35f93-158">Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="35f93-158">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="35f93-159">Dans **modifier l’utilisateur de Lync Server** sous **stratégie de chat persistante**, sélectionnez la stratégie d’utilisateur de conversation permanente que vous voulez appliquer.</span><span class="sxs-lookup"><span data-stu-id="35f93-159">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="35f93-160">Les \*\* \<paramètres\> automatiques\*\* appliquent la stratégie d’effectivité par défaut.</span><span class="sxs-lookup"><span data-stu-id="35f93-160">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="35f93-161">Ces paramètres sont appliqués automatiquement par le serveur.</span><span class="sxs-lookup"><span data-stu-id="35f93-161">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="35f93-162">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="35f93-162">Click **Commit**.</span></span>
    

