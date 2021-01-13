---
title: Stratégie de conversation permanente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: Vous pouvez utiliser la page Stratégie de conversation permanente du groupe conversation permanente pour gérer les stratégies au niveau global, pool, site ou utilisateur, y compris la configuration de la stratégie globale par défaut et la création d’une ou de plusieurs stratégies utilisateur et de site supplémentaires pour votre déploiement. Si le serveur de conversation permanente est activé pour un utilisateur par une stratégie, l’environnement de serveur de conversation permanente apparaît dans son client.
ms.openlocfilehash: e7148530f571a46937ee8d8a3bf44315ac692eb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819294"
---
# <a name="persistent-chat-policy"></a><span data-ttu-id="62408-104">Stratégie de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="62408-104">Persistent Chat Policy</span></span>
 
<span data-ttu-id="62408-105">Vous pouvez utiliser la **page**  Stratégie de conversation permanente du groupe conversation permanente pour gérer les stratégies au niveau global, pool, site ou utilisateur, y compris la configuration de la stratégie globale par défaut et la création d’une ou de plusieurs stratégies utilisateur et de site supplémentaires pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="62408-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="62408-106">Si le serveur de conversation permanente est activé pour un utilisateur par une stratégie, l’environnement de serveur de conversation permanente apparaît dans son client.</span><span class="sxs-lookup"><span data-stu-id="62408-106">If Persistent Chat Server is enabled for a user by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
<span data-ttu-id="62408-107">La stratégie globale est créée automatiquement lorsque vous déployez un serveur de conversation permanente et elle peut être configurée, mais pas supprimée.</span><span class="sxs-lookup"><span data-stu-id="62408-107">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="62408-108">Étant donné que la stratégie globale s’applique à tous les utilisateurs, elle n’a pas besoin d’être définie par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="62408-108">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="62408-109">Vous pouvez créer et configurer plusieurs stratégies de site et d’utilisateur qui, avec la stratégie globale, activent les utilisateurs pour le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="62408-109">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="62408-110">Les stratégies de serveur de conversation permanente de pool et de site remplacent la stratégie globale du serveur de conversation permanente, mais uniquement pour les utilisateurs de ce site.</span><span class="sxs-lookup"><span data-stu-id="62408-110">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="62408-111">Les stratégies utilisateur supplantent les stratégies utilisateur, de pool et globales pour les utilisateurs auxquels la stratégie utilisateur est assignée.</span><span class="sxs-lookup"><span data-stu-id="62408-111">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="62408-112">Pour configurer et utiliser le serveur de conversation permanente, vous devez d’abord utiliser le Générateur de topologie pour ajouter la prise en charge du serveur de conversation permanente à la topologie, puis publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="62408-112">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="62408-113">Pour plus d’informations, voir [Add Persistent Chat Server to your Skype for Business Server 2015 topology.](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)</span><span class="sxs-lookup"><span data-stu-id="62408-113">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="62408-114">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="62408-114">Tasks that you can perform</span></span>

<span data-ttu-id="62408-115">Vous pouvez effectuer les tâches suivantes dans la page Stratégie de **conversation** permanente : activer la stratégie de serveur de conversation permanente . gérer la stratégie de serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="62408-115">You can perform the following tasks on the **Persistent Chat Policy** page: enable Persistent Chat Server policy; manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="62408-116">Pour configurer la stratégie globale pour la conversation permanente</span><span class="sxs-lookup"><span data-stu-id="62408-116">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="62408-117">À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="62408-117">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="62408-118">Dans le menu **Démarrer,** sélectionnez le Panneau de contrôle Skype Entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="62408-118">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="62408-119">Dans le Panneau de contrôle Skype Entreprise Server, cliquez sur **Conversation** permanente, puis sur **Stratégie de conversation permanente.**</span><span class="sxs-lookup"><span data-stu-id="62408-119">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="62408-120">Cliquez sur **Globale** dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="62408-120">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="62408-121">Dans **Modifier la stratégie de conversation permanente - Globale**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="62408-121">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="62408-122">Dans **Nom**, spécifiez un nouveau nom pour la stratégie globale si vous ne souhaitez pas utiliser le nom par défaut Globale.</span><span class="sxs-lookup"><span data-stu-id="62408-122">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="62408-123">Dans **Description,** fournissez des détails sur la stratégie utilisateur (par exemple, stratégie globale pour  _centralSiteName_).</span><span class="sxs-lookup"><span data-stu-id="62408-123">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="62408-124">Pour contrôler la conversation permanente pour tous les sites et utilisateurs qui ne  sont pas spécifiquement contrôlés par le biais d’une stratégie de site ou d’une stratégie utilisateur, activez ou activez la case à cocher Activer la conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="62408-124">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="62408-125">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="62408-125">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="62408-126">Pour créer une stratégie de conversation permanente pour un site</span><span class="sxs-lookup"><span data-stu-id="62408-126">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="62408-127">Pour chaque site que vous avez déployé, vous pouvez créer une stratégie de conversation permanente spécifique au site.</span><span class="sxs-lookup"><span data-stu-id="62408-127">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="62408-128">La configuration de la stratégie du site supplante la stratégie globale, uniquement pour le site pour lequel elle est définie.</span><span class="sxs-lookup"><span data-stu-id="62408-128">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="62408-129">À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="62408-129">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="62408-130">Dans le menu **Démarrer,** sélectionnez le Panneau de contrôle Skype Entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="62408-130">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="62408-131">Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.</span><span class="sxs-lookup"><span data-stu-id="62408-131">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="62408-132">Cliquez sur **Nouveau**, puis sur **Stratégie de site**.</span><span class="sxs-lookup"><span data-stu-id="62408-132">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="62408-133">Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit s’appliquer.</span><span class="sxs-lookup"><span data-stu-id="62408-133">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="62408-134">Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="62408-134">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="62408-135">Dans **Nom**, spécifiez un nom pour la nouvelle stratégie de site (par exemple, Redmond).</span><span class="sxs-lookup"><span data-stu-id="62408-135">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="62408-136">Dans **Description**, entrez des informations décrivant la stratégie de site (par exemple, stratégie de salle de conversation pour Redmond).</span><span class="sxs-lookup"><span data-stu-id="62408-136">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="62408-137">Pour contrôler la conversation permanente pour tous les sites qui ne sont pas spécifiquement contrôlés par le biais d’une stratégie de site, activez ou activez la case à cocher Activer la **conversation** permanente.</span><span class="sxs-lookup"><span data-stu-id="62408-137">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="62408-138">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="62408-138">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="62408-139">Pour créer une stratégie utilisateur pour la conversation permanente</span><span class="sxs-lookup"><span data-stu-id="62408-139">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="62408-140">Dans le Panneau de contrôle Skype Entreprise Server, vous définissez des stratégies utilisateur qui peuvent être affectées à des utilisateurs dans **Les utilisateurs.**</span><span class="sxs-lookup"><span data-stu-id="62408-140">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="62408-141">La stratégie utilisateur supplante les stratégies globale et de site, mais uniquement pour les utilisateurs pour lesquels la stratégie utilisateur est appliquée.</span><span class="sxs-lookup"><span data-stu-id="62408-141">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="62408-142">À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="62408-142">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="62408-143">Dans le menu **Démarrer,** sélectionnez le Panneau de contrôle Skype Entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="62408-143">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="62408-144">Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.</span><span class="sxs-lookup"><span data-stu-id="62408-144">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="62408-145">Cliquez sur **Nouvelle**, puis sur **Stratégie utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="62408-145">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="62408-146">Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="62408-146">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="62408-147">Dans **Nom**, spécifiez un nom pour la nouvelle stratégie utilisateur.</span><span class="sxs-lookup"><span data-stu-id="62408-147">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="62408-148">Dans **Description,** fournissez des détails sur la stratégie utilisateur (par exemple, stratégie de conversation permanente pour un utilisateur spécifique).</span><span class="sxs-lookup"><span data-stu-id="62408-148">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="62408-149">Pour contrôler la conversation permanente pour tous les utilisateurs qui ne sont pas spécifiquement contrôlés par le biais d’une stratégie utilisateur, activez ou activez la case à cocher Activer la **conversation** permanente.</span><span class="sxs-lookup"><span data-stu-id="62408-149">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="62408-150">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="62408-150">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="62408-151">Pour appliquer une stratégie d’utilisateur de conversation permanente à un compte d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="62408-151">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="62408-152">Si un utilisateur a été activé pour Skype Entreprise Server, vous pouvez appliquer des stratégies appropriées à des utilisateurs spécifiques pour les activer ou les désactiver pour le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="62408-152">If a user has been enabled for Skype for Business Server, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="62408-153">Utilisez la procédure de cette rubrique pour appliquer une stratégie d’utilisateur de conversation permanente créée précédemment à un ou plusieurs comptes d’utilisateurs ou groupes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="62408-153">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="62408-154">À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="62408-154">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="62408-155">Dans le menu **Démarrer,** sélectionnez le Panneau de contrôle Skype Entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="62408-155">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="62408-156">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.</span><span class="sxs-lookup"><span data-stu-id="62408-156">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="62408-157">Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="62408-157">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="62408-158">Dans **Modifier l’utilisateur Lync Server sous** **stratégie** de conversation permanente, sélectionnez la stratégie utilisateur de conversation permanente à appliquer.</span><span class="sxs-lookup"><span data-stu-id="62408-158">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="62408-159">Les **\<Automatic\>** paramètres appliquent la stratégie effective par défaut.</span><span class="sxs-lookup"><span data-stu-id="62408-159">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="62408-160">Ces paramètres sont appliqués automatiquement par le serveur.</span><span class="sxs-lookup"><span data-stu-id="62408-160">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="62408-161">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="62408-161">Click **Commit**.</span></span>
    

