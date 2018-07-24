---
title: Configuration des stratégies d’archivage de Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Résumé : Lisez cette rubrique pour savoir comment configurer les stratégies d’archivage initiales pour Skype pour les utilisateurs Business Server.'
ms.openlocfilehash: 9db5d04ba04a3d840c493f5fbea42260ed87a6d4
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21003954"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a><span data-ttu-id="a7921-103">Configuration des stratégies d’archivage de Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="a7921-103">Configure archiving policies for Skype for Business Server</span></span>
 
<span data-ttu-id="a7921-104">**Résumé :** Lisez cette rubrique pour savoir comment configurer les stratégies d’archivage initiales pour Skype pour les utilisateurs Business Server.</span><span class="sxs-lookup"><span data-stu-id="a7921-104">**Summary:** Read this topic to learn how to configure initial archiving policies for Skype for Business Server users.</span></span>
  
<span data-ttu-id="a7921-105">Dans Skype pour Business Server, vous utilisez des stratégies pour activer et désactiver l’archivage des communications internes et les communications externes pour les utilisateurs qui sont hébergés sur Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="a7921-105">In Skype for Business Server, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="a7921-106">Il s’agit notamment de ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="a7921-106">This includes the following:</span></span>
  
- <span data-ttu-id="a7921-107">Une stratégie globale qui est créée par défaut lorsque vous déployez Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="a7921-107">A global policy that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="a7921-108">Stratégies facultatives au niveau site qui définissent de quelle manière l’archivage est implémenté pour un site spécifique</span><span class="sxs-lookup"><span data-stu-id="a7921-108">Optional site-level policies that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="a7921-109">Stratégies facultatives au niveau de l’utilisateur qui spécifient comment l’archivage est implémenté pour des utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="a7921-109">Optional user-level policies that specify how archiving is implemented for specific users</span></span>
    
<span data-ttu-id="a7921-110">Vous définissez les stratégies d’archivage lors du déploiement initial de l’archivage, mais vous pouvez modifier et supprimer des stratégies existantes, ou en ajouter de nouvelles, à tout moment après le déploiement.</span><span class="sxs-lookup"><span data-stu-id="a7921-110">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="a7921-111">Dans Skype pour le panneau de configuration serveur Business, vous pouvez utiliser la page **Stratégie d’archivage** du groupe **d’archivage et surveillance** pour gérer les stratégies au niveau global, site et les niveaux de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a7921-111">In Skype for Business Server Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global, site, and user levels.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a7921-112">Pour contrôler l’implémentation de l’archivage, vous devez définir certaines options, notamment spécifier si les messages instantanés ou les conférences doivent être archivés, si le mode critique est utilisé et les options de vidage.</span><span class="sxs-lookup"><span data-stu-id="a7921-112">To control the implementation of archiving, you must specify options, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="a7921-113">Par défaut, aucune option n’est activée dans la configuration de l’archivage global ni dans la configuration de l’archivage de site ou de pool.</span><span class="sxs-lookup"><span data-stu-id="a7921-113">By default no options are enabled in the global archiving configuration or any site or pool archiving configuration.</span></span> <span data-ttu-id="a7921-114">Vous devez définir toutes les options appropriées avant d’activer l’archivage des communications internes ou externes.</span><span class="sxs-lookup"><span data-stu-id="a7921-114">You should specify all appropriate options before enabling archiving for internal or external communications.</span></span> <span data-ttu-id="a7921-115">Pour plus d’informations, voir [configurer les options de Skype pour Business Server d’archivage](configure-archiving-options.md).</span><span class="sxs-lookup"><span data-stu-id="a7921-115">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a7921-116">Si vous activez l’intégration de Microsoft Exchange pour votre déploiement, le contrôle de stratégies de blocage sur Place Exchange si l’archivage est activé pour les utilisateurs qui sont hébergés sur Exchange et mettre les boîtes aux lettres en blocage sur Place.</span><span class="sxs-lookup"><span data-stu-id="a7921-116">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> 
  
<span data-ttu-id="a7921-117">Pour plus d’informations sur les stratégies de l’archivage fonctionne, notamment la hiérarchie des globale, de site et stratégies d’utilisateur, voir [planifier l’archivage dans Skype pour Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="a7921-117">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="a7921-118">Pour plus d’informations sur la gestion des stratégies après le déploiement, voir [Gérer les stratégies d’archivage de Skype pour Business Server](../../manage/archiving/policies.md).</span><span class="sxs-lookup"><span data-stu-id="a7921-118">For details about how to manage policies after deployment, see [Manage archiving policies in Skype for Business Server](../../manage/archiving/policies.md).</span></span>
  
## <a name="global-policy"></a><span data-ttu-id="a7921-119">Stratégie globale</span><span class="sxs-lookup"><span data-stu-id="a7921-119">Global policy</span></span>

<span data-ttu-id="a7921-120">Lorsque vous déployez vos serveurs frontaux, Skype pour Business Server crée une stratégie globale pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="a7921-120">When you deploy your Front End Servers, Skype for Business Server creates a global policy for archiving.</span></span> <span data-ttu-id="a7921-121">Par défaut, l’archivage est désactivé dans la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="a7921-121">By default, archiving is disabled in the global policy.</span></span> <span data-ttu-id="a7921-122">Contrôle de la stratégie globale si l’archivage est activé pour les communications internes et externes pour votre déploiement entière, sauf si vous définissez des stratégies de site ou d’utilisateur, qui remplace la stratégie globale, ou si vous utilisez l’intégration de Microsoft Exchange pour tout ou partie des vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a7921-122">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="a7921-123">Si vous utilisez l’intégration de Microsoft Exchange, la stratégie globale ne s’applique pas à tous les utilisateurs hébergés sur Exchange et mettre les boîtes aux lettres en blocage sur Place.</span><span class="sxs-lookup"><span data-stu-id="a7921-123">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange and have the mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a><span data-ttu-id="a7921-124">Configurer la stratégie globale pour l’archivage pour Skype pour les bases de données d’archivage Business Server</span><span class="sxs-lookup"><span data-stu-id="a7921-124">Configure the global policy for archiving for Skype for Business Server archiving databases</span></span>

1. <span data-ttu-id="a7921-125">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="a7921-125">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a7921-126">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="a7921-126">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="a7921-127">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**.</span><span class="sxs-lookup"><span data-stu-id="a7921-127">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="a7921-128">Dans la page **Stratégie d’archivage**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="a7921-128">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="a7921-129">Dans **Modifier la stratégie d’archivage - Globale**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a7921-129">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="a7921-130">Dans **Nom**, si vous ne souhaitez pas utiliser le nom par défaut Global, spécifiez un nouveau nom pour la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="a7921-130">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span> 
    
   - <span data-ttu-id="a7921-131">Dans **Description**, fournissez les informations sur les nouveautés de la stratégie (par exemple, stratégie globale de *Nom_division* .</span><span class="sxs-lookup"><span data-stu-id="a7921-131">In **Description**, provide information about what the policy is (for example, Global policy for  *divisionName*  .</span></span>
    
   - <span data-ttu-id="a7921-132">Afin de contrôler l’archivage des communications internes pour tous les sites et utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie de site ou une stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications internes**.</span><span class="sxs-lookup"><span data-stu-id="a7921-132">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="a7921-133">Afin de contrôler l’archivage des communications externes pour tous les sites et utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie de site ou une stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications externes**.</span><span class="sxs-lookup"><span data-stu-id="a7921-133">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="a7921-134">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="a7921-134">Click **Commit**.</span></span>
    
## <a name="site-policies"></a><span data-ttu-id="a7921-135">Stratégies de site</span><span class="sxs-lookup"><span data-stu-id="a7921-135">Site policies</span></span>

<span data-ttu-id="a7921-136">Vous pouvez activer ou désactiver l’archivage pour des sites spécifiques en créant une stratégie d’archivage pour chacun de ces sites.</span><span class="sxs-lookup"><span data-stu-id="a7921-136">You can enable or disable archiving for specific sites by creating an archiving policy for each of those sites.</span></span> <span data-ttu-id="a7921-137">Une stratégie de site remplace la stratégie globale, mais les stratégies utilisateur remplacent les stratégies de site.</span><span class="sxs-lookup"><span data-stu-id="a7921-137">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="a7921-138">Stratégies d’archivage s’appliquent uniquement si vous n’utilisez pas l’intégration de Microsoft Exchange ou, si vous n’utilisez pas l’intégration de Microsoft Exchange, mais mettre les quelques utilisateurs qui ne sont pas hébergés sur Exchange et à leurs boîtes aux lettres en blocage sur Place.</span><span class="sxs-lookup"><span data-stu-id="a7921-138">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="create-an-archiving-policy-for-a-site"></a><span data-ttu-id="a7921-139">Créer une stratégie d’archivage pour un site</span><span class="sxs-lookup"><span data-stu-id="a7921-139">Create an archiving policy for a site</span></span>

1. <span data-ttu-id="a7921-140">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="a7921-140">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a7921-141">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="a7921-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="a7921-142">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**.</span><span class="sxs-lookup"><span data-stu-id="a7921-142">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="a7921-143">Pour plus d’informations sur les stratégies de l’archivage fonctionne, notamment la hiérarchie des globale, de site et stratégies d’utilisateur, voir [planifier l’archivage dans Skype pour Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="a7921-143">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
    
4. <span data-ttu-id="a7921-144">Cliquez sur **Créer**, puis sur **Stratégie de site**.</span><span class="sxs-lookup"><span data-stu-id="a7921-144">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="a7921-145">Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit s’appliquer.</span><span class="sxs-lookup"><span data-stu-id="a7921-145">In **Select a site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="a7921-146">Dans **Nouvelle stratégie d’archivage**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a7921-146">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="a7921-147">Dans **Nom**, spécifiez le nom pour la stratégie de site.</span><span class="sxs-lookup"><span data-stu-id="a7921-147">In **Name**, specify the name for the site policy.</span></span> 
    
   - <span data-ttu-id="a7921-148">Dans **Description**, entrez des informations décrivant la stratégie de site (par exemple, stratégie de site pour Redmond).</span><span class="sxs-lookup"><span data-stu-id="a7921-148">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
   - <span data-ttu-id="a7921-149">Pour contrôler l’archivage des communications internes pour le site spécifié, activez ou désactivez la case à cocher **Archiver les communications internes**.</span><span class="sxs-lookup"><span data-stu-id="a7921-149">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="a7921-150">Pour contrôler l’archivage des communications externes pour le site spécifié, activez ou désactivez la case à cocher **Archiver les communications externes**.</span><span class="sxs-lookup"><span data-stu-id="a7921-150">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>
    
7. <span data-ttu-id="a7921-151">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="a7921-151">Click **Commit**.</span></span>
    
## <a name="user-policies"></a><span data-ttu-id="a7921-152">Stratégies utilisateur</span><span class="sxs-lookup"><span data-stu-id="a7921-152">User policies</span></span>

<span data-ttu-id="a7921-153">Vous pouvez activer ou désactiver l’archivage pour des utilisateurs spécifiques en créant et en configurant une stratégie d’archivage pour les utilisateurs, puis en appliquant la stratégie à des utilisateurs spécifiques ou à des groupes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a7921-153">You can enable or disable archiving for specific users by creating and configuring an archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="a7921-154">Les stratégies utilisateur remplacent les stratégies globales ou de site.</span><span class="sxs-lookup"><span data-stu-id="a7921-154">User policies override any global policy or site policies.</span></span> <span data-ttu-id="a7921-155">Stratégies d’archivage s’appliquent uniquement si vous n’utilisez pas l’intégration de Microsoft Exchange ou, si vous n’utilisez pas l’intégration de Microsoft Exchange, mais mettre les quelques utilisateurs qui ne sont pas hébergés sur Exchange et à leurs boîtes aux lettres en blocage sur Place.</span><span class="sxs-lookup"><span data-stu-id="a7921-155">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a><span data-ttu-id="a7921-156">Configurer une stratégie d’archivage pour les utilisateurs hébergés sur Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="a7921-156">Configure an archiving policy for users homed on Skype for Business Server</span></span>

1. <span data-ttu-id="a7921-157">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="a7921-157">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a7921-158">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="a7921-158">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="a7921-159">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**.</span><span class="sxs-lookup"><span data-stu-id="a7921-159">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="a7921-160">Cliquez sur **Créer**, puis sur **Stratégie utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="a7921-160">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="a7921-161">Dans **Nouvelle stratégie d’archivage**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a7921-161">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="a7921-162">Dans **Nom**, spécifiez le nom de la stratégie utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a7921-162">In **Name**, specify the name for the user policy.</span></span> 
    
   - <span data-ttu-id="a7921-163">Dans **Description**, entrez des informations décrivant la stratégie utilisateur (par exemple, stratégie utilisateur pour le service juridique).</span><span class="sxs-lookup"><span data-stu-id="a7921-163">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
   - <span data-ttu-id="a7921-164">Pour contrôler l’archivage des communications internes de la stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications internes**.</span><span class="sxs-lookup"><span data-stu-id="a7921-164">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="a7921-165">Pour contrôler l’archivage des communications externes de la stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications externes**.</span><span class="sxs-lookup"><span data-stu-id="a7921-165">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="a7921-166">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="a7921-166">Click **Commit**.</span></span>
    
<span data-ttu-id="a7921-167">Une stratégie utilisateur ne s’applique qu’aux utilisateurs auxquels vous affectez la stratégie.</span><span class="sxs-lookup"><span data-stu-id="a7921-167">A user policy applies only to users to whom you assign the policy.</span></span>
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a><span data-ttu-id="a7921-168">Appliquer un Skype pour Business Server stratégie à un utilisateur d’archivage</span><span class="sxs-lookup"><span data-stu-id="a7921-168">Apply a Skype for Business Server archiving policy to a user</span></span>

1. <span data-ttu-id="a7921-169">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="a7921-169">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a7921-170">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="a7921-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="a7921-171">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.</span><span class="sxs-lookup"><span data-stu-id="a7921-171">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="a7921-172">Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="a7921-172">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="a7921-173">Dans **Modifier les Skype pour utilisateur Business Server** sous **stratégie d’archivage**, sélectionnez la stratégie utilisateur d’archivage que vous souhaitez appliquer.</span><span class="sxs-lookup"><span data-stu-id="a7921-173">In **Edit Skype for Business Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a7921-174">Le ** \<automatique\> ** paramètres s’appliquent les paramètres d’installation de serveur par défaut.</span><span class="sxs-lookup"><span data-stu-id="a7921-174">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="a7921-175">Le serveur les applique automatiquement.</span><span class="sxs-lookup"><span data-stu-id="a7921-175">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="a7921-176">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="a7921-176">Click **Commit**.</span></span>
    

