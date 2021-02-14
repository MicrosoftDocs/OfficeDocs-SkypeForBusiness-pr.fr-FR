---
title: Configurer des stratégies d’archivage pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Résumé : Lisez cette rubrique pour découvrir comment configurer les stratégies d’archivage initiales pour les utilisateurs de Skype Entreprise Server.'
ms.openlocfilehash: ab737305561aa20c873bbce6e0f075d17fedd0d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820854"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a><span data-ttu-id="8a329-103">Configurer des stratégies d’archivage pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8a329-103">Configure archiving policies for Skype for Business Server</span></span>
 
<span data-ttu-id="8a329-104">**Résumé :** Lisez cette rubrique pour découvrir comment configurer les stratégies d’archivage initiales pour les utilisateurs de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8a329-104">**Summary:** Read this topic to learn how to configure initial archiving policies for Skype for Business Server users.</span></span>
  
<span data-ttu-id="8a329-105">Dans Skype Entreprise Server, vous utilisez des stratégies pour activer et désactiver l’archivage des communications internes et externes pour les utilisateurs qui sont homed sur Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8a329-105">In Skype for Business Server, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="8a329-106">Les voici :</span><span class="sxs-lookup"><span data-stu-id="8a329-106">This includes the following:</span></span>
  
- <span data-ttu-id="8a329-107">Stratégie globale créée par défaut lorsque vous déployez Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8a329-107">A global policy that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="8a329-108">Stratégies facultatives au niveau du site qui spécifient la façon dont l’archivage est implémenté pour un site spécifique</span><span class="sxs-lookup"><span data-stu-id="8a329-108">Optional site-level policies that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="8a329-109">Stratégies facultatives au niveau de l’utilisateur qui spécifient la façon dont l’archivage est implémenté pour des utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="8a329-109">Optional user-level policies that specify how archiving is implemented for specific users</span></span>
    
<span data-ttu-id="8a329-110">Vous définissez initialement les stratégies d’archivage lorsque vous déployez l’archivage, mais vous pouvez modifier, ajouter et supprimer des stratégies après le déploiement.</span><span class="sxs-lookup"><span data-stu-id="8a329-110">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="8a329-111">Dans le Panneau de contrôle Skype Entreprise Server, vous  pouvez utiliser la **page** Stratégie d’archivage du groupe Archivage et surveillance pour gérer les stratégies au niveau global, du site et de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8a329-111">In Skype for Business Server Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global, site, and user levels.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8a329-112">Pour contrôler l’implémentation de l’archivage, vous devez spécifier des options, telles que l’archivage de la messagerie instantanée ou de la conférence, l’utilisation du mode critique et les options de purge.</span><span class="sxs-lookup"><span data-stu-id="8a329-112">To control the implementation of archiving, you must specify options, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="8a329-113">Par défaut, aucune option n’est activée dans la configuration de l’archivage global ou dans toute configuration d’archivage de site ou de pool.</span><span class="sxs-lookup"><span data-stu-id="8a329-113">By default no options are enabled in the global archiving configuration or any site or pool archiving configuration.</span></span> <span data-ttu-id="8a329-114">Vous devez spécifier toutes les options appropriées avant d’activer l’archivage pour les communications internes ou externes.</span><span class="sxs-lookup"><span data-stu-id="8a329-114">You should specify all appropriate options before enabling archiving for internal or external communications.</span></span> <span data-ttu-id="8a329-115">Pour plus d’informations, [voir Configurer les options d’archivage pour Skype Entreprise Server.](configure-archiving-options.md)</span><span class="sxs-lookup"><span data-stu-id="8a329-115">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8a329-116">Si vous activez l’intégration de Microsoft Exchange pour votre déploiement, les stratégies d’archive In-Place Exchange contrôlent si l’archivage est activé pour les utilisateurs qui sont homed on Exchange et dont les boîtes aux lettres sont mises en In-Place archive.</span><span class="sxs-lookup"><span data-stu-id="8a329-116">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> 
  
<span data-ttu-id="8a329-117">Pour plus d’informations sur le fonctionnement des stratégies d’archivage, notamment la hiérarchie des stratégies globales, de site et utilisateur, voir Planifier l’archivage dans [Skype Entreprise Server.](../../plan-your-deployment/archiving/archiving.md)</span><span class="sxs-lookup"><span data-stu-id="8a329-117">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="8a329-118">Pour plus d’informations sur la gestion des stratégies après le déploiement, voir Gérer les stratégies [d’archivage dans Skype Entreprise Server.](../../manage/archiving/policies.md)</span><span class="sxs-lookup"><span data-stu-id="8a329-118">For details about how to manage policies after deployment, see [Manage archiving policies in Skype for Business Server](../../manage/archiving/policies.md).</span></span>
  
## <a name="global-policy"></a><span data-ttu-id="8a329-119">Stratégie globale</span><span class="sxs-lookup"><span data-stu-id="8a329-119">Global policy</span></span>

<span data-ttu-id="8a329-120">Lorsque vous déployez vos serveurs frontux, Skype Entreprise Server crée une stratégie globale pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="8a329-120">When you deploy your Front End Servers, Skype for Business Server creates a global policy for archiving.</span></span> <span data-ttu-id="8a329-121">Par défaut, l’archivage est désactivé dans la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="8a329-121">By default, archiving is disabled in the global policy.</span></span> <span data-ttu-id="8a329-122">La stratégie globale contrôle si l’archivage est activé pour les communications internes et externes pour l’ensemble de votre déploiement, sauf si vous avez mis en place des stratégies de site ou d’utilisateur, qui remplacent la stratégie globale, ou si vous utilisez l’intégration de Microsoft Exchange pour une partie ou la totalité de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8a329-122">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="8a329-123">Si vous utilisez l’intégration Microsoft Exchange, la stratégie globale ne s’applique pas aux utilisateurs qui sont homed on Exchange et dont les boîtes aux lettres sont In-Place en attente.</span><span class="sxs-lookup"><span data-stu-id="8a329-123">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange and have the mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a><span data-ttu-id="8a329-124">Configurer la stratégie globale pour l’archivage des bases de données d’archivage Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8a329-124">Configure the global policy for archiving for Skype for Business Server archiving databases</span></span>

1. <span data-ttu-id="8a329-125">À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="8a329-125">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8a329-126">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8a329-126">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="8a329-127">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**.</span><span class="sxs-lookup"><span data-stu-id="8a329-127">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="8a329-128">Dans la page **Stratégie d’archivage**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="8a329-128">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="8a329-129">Dans **Modifier la stratégie d’archivage - Globale**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="8a329-129">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="8a329-130">Dans **Nom**, si vous ne souhaitez pas utiliser le nom par défaut Global, spécifiez un nouveau nom pour la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="8a329-130">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span> 
    
   - <span data-ttu-id="8a329-131">Dans **description,** fournissez des informations sur la stratégie (par exemple, stratégie globale pour  *divisionName*  .</span><span class="sxs-lookup"><span data-stu-id="8a329-131">In **Description**, provide information about what the policy is (for example, Global policy for  *divisionName*  .</span></span>
    
   - <span data-ttu-id="8a329-132">Afin de contrôler l’archivage des communications internes pour tous les sites et utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie de site ou une stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications internes**.</span><span class="sxs-lookup"><span data-stu-id="8a329-132">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="8a329-133">Afin de contrôler l’archivage des communications externes pour tous les sites et utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie de site ou une stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications externes**.</span><span class="sxs-lookup"><span data-stu-id="8a329-133">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="8a329-134">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="8a329-134">Click **Commit**.</span></span>
    
## <a name="site-policies"></a><span data-ttu-id="8a329-135">Stratégies de site</span><span class="sxs-lookup"><span data-stu-id="8a329-135">Site policies</span></span>

<span data-ttu-id="8a329-136">Vous pouvez activer ou désactiver l’archivage pour des sites spécifiques en créant une stratégie d’archivage pour chacun de ces sites.</span><span class="sxs-lookup"><span data-stu-id="8a329-136">You can enable or disable archiving for specific sites by creating an archiving policy for each of those sites.</span></span> <span data-ttu-id="8a329-137">Une stratégie de site remplace la stratégie globale, mais les stratégies utilisateur remplacent les stratégies de site.</span><span class="sxs-lookup"><span data-stu-id="8a329-137">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="8a329-138">Les stratégies d’archivage s’appliquent uniquement si vous n’utilisez pas l’intégration Microsoft Exchange ou, si vous utilisez l’intégration Microsoft Exchange, mais que certains utilisateurs ne sont pas dos à exchange et dont les boîtes aux lettres sont mises en In-Place.</span><span class="sxs-lookup"><span data-stu-id="8a329-138">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="create-an-archiving-policy-for-a-site"></a><span data-ttu-id="8a329-139">Créer une stratégie d’archivage pour un site</span><span class="sxs-lookup"><span data-stu-id="8a329-139">Create an archiving policy for a site</span></span>

1. <span data-ttu-id="8a329-140">À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="8a329-140">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8a329-141">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8a329-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="8a329-142">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**.</span><span class="sxs-lookup"><span data-stu-id="8a329-142">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="8a329-143">Pour plus d’informations sur le fonctionnement des stratégies d’archivage, notamment la hiérarchie des stratégies globales, de site et utilisateur, voir Planifier l’archivage dans [Skype Entreprise Server.](../../plan-your-deployment/archiving/archiving.md)</span><span class="sxs-lookup"><span data-stu-id="8a329-143">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
    
4. <span data-ttu-id="8a329-144">Cliquez sur **Nouveau**, puis sur **Stratégie de site**.</span><span class="sxs-lookup"><span data-stu-id="8a329-144">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="8a329-145">Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit s’appliquer.</span><span class="sxs-lookup"><span data-stu-id="8a329-145">In **Select a site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="8a329-146">Dans **Nouvelle stratégie d’archivage**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="8a329-146">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="8a329-147">Dans **Nom**, spécifiez le nom pour la stratégie de site.</span><span class="sxs-lookup"><span data-stu-id="8a329-147">In **Name**, specify the name for the site policy.</span></span> 
    
   - <span data-ttu-id="8a329-148">Dans **Description**, entrez des informations décrivant la stratégie de site (par exemple, stratégie de site pour Redmond).</span><span class="sxs-lookup"><span data-stu-id="8a329-148">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
   - <span data-ttu-id="8a329-149">Pour contrôler l’archivage des communications internes pour le site spécifié, activez ou désactivez la case à cocher **Archiver les communications internes**.</span><span class="sxs-lookup"><span data-stu-id="8a329-149">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="8a329-150">Pour contrôler l’archivage des communications externes pour le site spécifié, activez ou désactivez la case à cocher **Archiver les communications externes**.</span><span class="sxs-lookup"><span data-stu-id="8a329-150">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>
    
7. <span data-ttu-id="8a329-151">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="8a329-151">Click **Commit**.</span></span>
    
## <a name="user-policies"></a><span data-ttu-id="8a329-152">Stratégies utilisateur</span><span class="sxs-lookup"><span data-stu-id="8a329-152">User policies</span></span>

<span data-ttu-id="8a329-153">Vous pouvez activer ou désactiver l’archivage pour des utilisateurs spécifiques en créant et en configurant une stratégie d’archivage pour les utilisateurs, puis en appliquant la stratégie à des utilisateurs ou groupes d’utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="8a329-153">You can enable or disable archiving for specific users by creating and configuring an archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="8a329-154">Les stratégies utilisateur remplacent les stratégies globales ou de site.</span><span class="sxs-lookup"><span data-stu-id="8a329-154">User policies override any global policy or site policies.</span></span> <span data-ttu-id="8a329-155">Les stratégies d’archivage s’appliquent uniquement si vous n’utilisez pas l’intégration Microsoft Exchange ou, si vous utilisez l’intégration Microsoft Exchange, mais que certains utilisateurs ne sont pas dos à exchange et dont les boîtes aux lettres sont mises en In-Place.</span><span class="sxs-lookup"><span data-stu-id="8a329-155">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a><span data-ttu-id="8a329-156">Configurer une stratégie d’archivage pour les utilisateurs sur Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8a329-156">Configure an archiving policy for users homed on Skype for Business Server</span></span>

1. <span data-ttu-id="8a329-157">À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="8a329-157">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8a329-158">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8a329-158">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="8a329-159">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**.</span><span class="sxs-lookup"><span data-stu-id="8a329-159">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="8a329-160">Cliquez sur **Nouvelle**, puis sur **Stratégie utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="8a329-160">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="8a329-161">Dans **Nouvelle stratégie d’archivage**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="8a329-161">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="8a329-162">Dans **Nom**, spécifiez le nom de la stratégie utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8a329-162">In **Name**, specify the name for the user policy.</span></span> 
    
   - <span data-ttu-id="8a329-163">Dans **Description**, entrez des informations décrivant la stratégie utilisateur (par exemple, stratégie utilisateur pour le service juridique).</span><span class="sxs-lookup"><span data-stu-id="8a329-163">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
   - <span data-ttu-id="8a329-164">Pour contrôler l’archivage des communications internes de la stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications internes**.</span><span class="sxs-lookup"><span data-stu-id="8a329-164">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="8a329-165">Pour contrôler l’archivage des communications externes de la stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications externes**.</span><span class="sxs-lookup"><span data-stu-id="8a329-165">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="8a329-166">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="8a329-166">Click **Commit**.</span></span>
    
<span data-ttu-id="8a329-167">Une stratégie utilisateur ne s’applique qu’aux utilisateurs auxquels vous affectez la stratégie.</span><span class="sxs-lookup"><span data-stu-id="8a329-167">A user policy applies only to users to whom you assign the policy.</span></span>
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a><span data-ttu-id="8a329-168">Appliquer une stratégie d’archivage Skype Entreprise Server à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="8a329-168">Apply a Skype for Business Server archiving policy to a user</span></span>

1. <span data-ttu-id="8a329-169">À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="8a329-169">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8a329-170">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8a329-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="8a329-171">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.</span><span class="sxs-lookup"><span data-stu-id="8a329-171">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="8a329-172">Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="8a329-172">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="8a329-173">Dans **Modifier l’utilisateur Skype Entreprise Server sous** stratégie d’archivage, sélectionnez la stratégie d’utilisateur d’archivage à appliquer. </span><span class="sxs-lookup"><span data-stu-id="8a329-173">In **Edit Skype for Business Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8a329-174">Les **\<Automatic\>** paramètres appliquent les paramètres d’installation du serveur par défaut.</span><span class="sxs-lookup"><span data-stu-id="8a329-174">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="8a329-175">Ces paramètres sont appliqués automatiquement par le serveur.</span><span class="sxs-lookup"><span data-stu-id="8a329-175">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="8a329-176">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="8a329-176">Click **Commit**.</span></span>
    

