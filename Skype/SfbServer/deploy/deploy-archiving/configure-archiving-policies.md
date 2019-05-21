---
title: Configuration de stratégies d’archivage pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Résumé: cette rubrique vous explique comment configurer les stratégies d’archivage initial pour les utilisateurs de Skype entreprise Server.'
ms.openlocfilehash: 9d4fc7bd27440688f981ac9d05b1e47750ad7867
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286559"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a><span data-ttu-id="2a216-103">Configuration de stratégies d’archivage pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2a216-103">Configure archiving policies for Skype for Business Server</span></span>
 
<span data-ttu-id="2a216-104">**Résumé:** Pour plus d’informations sur la configuration des stratégies d’archivage initial pour les utilisateurs de Skype entreprise Server, reportez-vous à cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="2a216-104">**Summary:** Read this topic to learn how to configure initial archiving policies for Skype for Business Server users.</span></span>
  
<span data-ttu-id="2a216-105">Dans Skype entreprise Server, vous utilisez des stratégies pour activer et désactiver l’archivage des communications internes et des communications externes pour les utilisateurs qui sont hébergés sur Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="2a216-105">In Skype for Business Server, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="2a216-106">Il s’agit notamment de ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="2a216-106">This includes the following:</span></span>
  
- <span data-ttu-id="2a216-107">Politique globale créée par défaut lors du déploiement de Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2a216-107">A global policy that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="2a216-108">Stratégies facultatives au niveau site qui définissent de quelle manière l’archivage est implémenté pour un site spécifique</span><span class="sxs-lookup"><span data-stu-id="2a216-108">Optional site-level policies that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="2a216-109">Stratégies de niveau utilisateur facultatives qui spécifient la façon dont l’archivage est implémenté pour des utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="2a216-109">Optional user-level policies that specify how archiving is implemented for specific users</span></span>
    
<span data-ttu-id="2a216-110">Vous définissez les stratégies d’archivage lors du déploiement initial de l’archivage, mais vous pouvez modifier et supprimer des stratégies existantes, ou en ajouter de nouvelles, à tout moment après le déploiement.</span><span class="sxs-lookup"><span data-stu-id="2a216-110">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="2a216-111">Dans le panneau de configuration Skype entreprise Server, vous pouvez utiliser la page de **stratégie** d’archivage du groupe **archivage et surveillance** pour gérer les stratégies aux niveaux global, site et utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2a216-111">In Skype for Business Server Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global, site, and user levels.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2a216-112">Pour contrôler l’implémentation de l’archivage, vous devez définir certaines options, notamment spécifier si les messages instantanés ou les conférences doivent être archivés, si le mode critique est utilisé et les options de vidage.</span><span class="sxs-lookup"><span data-stu-id="2a216-112">To control the implementation of archiving, you must specify options, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="2a216-113">Par défaut, aucune option n’est activée dans la configuration de l’archivage global ni dans la configuration de l’archivage de site ou de pool.</span><span class="sxs-lookup"><span data-stu-id="2a216-113">By default no options are enabled in the global archiving configuration or any site or pool archiving configuration.</span></span> <span data-ttu-id="2a216-114">Vous devez définir toutes les options appropriées avant d’activer l’archivage des communications internes ou externes.</span><span class="sxs-lookup"><span data-stu-id="2a216-114">You should specify all appropriate options before enabling archiving for internal or external communications.</span></span> <span data-ttu-id="2a216-115">Pour plus d’informations, reportez-vous à [configurer les options d’archivage de Skype entreprise Server](configure-archiving-options.md).</span><span class="sxs-lookup"><span data-stu-id="2a216-115">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2a216-116">Si vous activez l’intégration de Microsoft Exchange pour votre déploiement, Exchange stratégies de conservation inaltérable déterminent si l’archivage est activé pour les utilisateurs hébergés sur Exchange et que leurs boîtes aux lettres sont placées dans la conservation inaltérable.</span><span class="sxs-lookup"><span data-stu-id="2a216-116">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> 
  
<span data-ttu-id="2a216-117">Pour plus d’informations sur le fonctionnement des stratégies d’archivage, y compris la hiérarchie des stratégies globales, de site et d’utilisateur, reportez-vous à la rubrique [planification de l’archivage dans Skype entreprise Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="2a216-117">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="2a216-118">Pour plus d’informations sur la gestion des stratégies après le déploiement, voir [gérer les stratégies d’archivage dans Skype entreprise Server](../../manage/archiving/policies.md).</span><span class="sxs-lookup"><span data-stu-id="2a216-118">For details about how to manage policies after deployment, see [Manage archiving policies in Skype for Business Server](../../manage/archiving/policies.md).</span></span>
  
## <a name="global-policy"></a><span data-ttu-id="2a216-119">Stratégie globale</span><span class="sxs-lookup"><span data-stu-id="2a216-119">Global policy</span></span>

<span data-ttu-id="2a216-120">Lorsque vous déployez vos serveurs frontaux, Skype entreprise Server crée une stratégie globale d’archivage.</span><span class="sxs-lookup"><span data-stu-id="2a216-120">When you deploy your Front End Servers, Skype for Business Server creates a global policy for archiving.</span></span> <span data-ttu-id="2a216-121">Par défaut, l’archivage est désactivé dans la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="2a216-121">By default, archiving is disabled in the global policy.</span></span> <span data-ttu-id="2a216-122">La stratégie globale contrôle l’activation de l’archivage pour les communications internes et externes pour votre déploiement complet, sauf si vous configurez des stratégies de site ou d’utilisateur qui remplacent la stratégie globale ou si vous utilisez l’intégration de Microsoft Exchange pour tout ou partie de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="2a216-122">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="2a216-123">Si vous utilisez l’intégration de Microsoft Exchange, la stratégie global ne s’applique pas aux utilisateurs hébergés sur Exchange et ayant recours à des boîtes aux lettres en conservation inaltérable.</span><span class="sxs-lookup"><span data-stu-id="2a216-123">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange and have the mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a><span data-ttu-id="2a216-124">Configurer la politique globale de l’archivage pour les bases de données d’archivage de Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2a216-124">Configure the global policy for archiving for Skype for Business Server archiving databases</span></span>

1. <span data-ttu-id="2a216-125">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="2a216-125">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2a216-126">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="2a216-126">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="2a216-127">Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **stratégie**d’archivage.</span><span class="sxs-lookup"><span data-stu-id="2a216-127">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="2a216-128">Dans la page **Stratégie d’archivage**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="2a216-128">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="2a216-129">Dans **Modifier la stratégie d’archivage - Globale**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="2a216-129">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="2a216-130">Dans **Nom**, si vous ne souhaitez pas utiliser le nom par défaut Global, spécifiez un nouveau nom pour la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="2a216-130">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span> 
    
   - <span data-ttu-id="2a216-131">Dans **Description**, entrez les informations relatives à la stratégie (par exemple, stratégie générale pour *divisionName* ).</span><span class="sxs-lookup"><span data-stu-id="2a216-131">In **Description**, provide information about what the policy is (for example, Global policy for  *divisionName*  .</span></span>
    
   - <span data-ttu-id="2a216-132">Afin de contrôler l’archivage des communications internes pour tous les sites et utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie de site ou une stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications internes**.</span><span class="sxs-lookup"><span data-stu-id="2a216-132">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="2a216-133">Afin de contrôler l’archivage des communications externes pour tous les sites et utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie de site ou une stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications externes**.</span><span class="sxs-lookup"><span data-stu-id="2a216-133">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="2a216-134">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="2a216-134">Click **Commit**.</span></span>
    
## <a name="site-policies"></a><span data-ttu-id="2a216-135">Stratégies de site</span><span class="sxs-lookup"><span data-stu-id="2a216-135">Site policies</span></span>

<span data-ttu-id="2a216-136">Vous pouvez activer ou désactiver l’archivage pour des sites spécifiques en créant une stratégie d’archivage pour chacun de ces sites.</span><span class="sxs-lookup"><span data-stu-id="2a216-136">You can enable or disable archiving for specific sites by creating an archiving policy for each of those sites.</span></span> <span data-ttu-id="2a216-137">Une stratégie de site remplace la stratégie globale, mais les stratégies utilisateur remplacent les stratégies de site.</span><span class="sxs-lookup"><span data-stu-id="2a216-137">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="2a216-138">Les stratégies d’archivage ne s’appliquent que si vous n’utilisez pas l’intégration de Microsoft Exchange ou, si vous utilisez l’intégration de Microsoft Exchange, mais que certains utilisateurs ne sont pas hébergés sur Exchange et que leurs boîtes aux lettres sont placées sur le blocage sur place.</span><span class="sxs-lookup"><span data-stu-id="2a216-138">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="create-an-archiving-policy-for-a-site"></a><span data-ttu-id="2a216-139">Créer une stratégie d’archivage pour un site</span><span class="sxs-lookup"><span data-stu-id="2a216-139">Create an archiving policy for a site</span></span>

1. <span data-ttu-id="2a216-140">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="2a216-140">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2a216-141">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="2a216-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="2a216-142">Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **stratégie**d’archivage.</span><span class="sxs-lookup"><span data-stu-id="2a216-142">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="2a216-143">Pour plus d’informations sur le fonctionnement des stratégies d’archivage, y compris la hiérarchie des stratégies globales, de site et d’utilisateur, reportez-vous à la rubrique [planification de l’archivage dans Skype entreprise Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="2a216-143">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
    
4. <span data-ttu-id="2a216-144">Cliquez sur **Créer**, puis sur **Stratégie de site**.</span><span class="sxs-lookup"><span data-stu-id="2a216-144">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="2a216-145">Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit s’appliquer.</span><span class="sxs-lookup"><span data-stu-id="2a216-145">In **Select a site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="2a216-146">Dans **Nouvelle stratégie d’archivage**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="2a216-146">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="2a216-147">Dans **Nom**, spécifiez le nom pour la stratégie de site.</span><span class="sxs-lookup"><span data-stu-id="2a216-147">In **Name**, specify the name for the site policy.</span></span> 
    
   - <span data-ttu-id="2a216-148">Dans **Description**, entrez des informations décrivant la stratégie de site (par exemple, stratégie de site pour Redmond).</span><span class="sxs-lookup"><span data-stu-id="2a216-148">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
   - <span data-ttu-id="2a216-149">Pour contrôler l’archivage des communications internes pour le site spécifié, activez ou désactivez la case à cocher **Archiver les communications internes**.</span><span class="sxs-lookup"><span data-stu-id="2a216-149">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="2a216-150">Pour contrôler l’archivage des communications externes pour le site spécifié, activez ou désactivez la case à cocher **Archiver les communications externes**.</span><span class="sxs-lookup"><span data-stu-id="2a216-150">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>
    
7. <span data-ttu-id="2a216-151">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="2a216-151">Click **Commit**.</span></span>
    
## <a name="user-policies"></a><span data-ttu-id="2a216-152">Stratégies utilisateur</span><span class="sxs-lookup"><span data-stu-id="2a216-152">User policies</span></span>

<span data-ttu-id="2a216-153">Vous pouvez activer ou désactiver l’archivage pour des utilisateurs spécifiques en créant et en configurant une stratégie d’archivage pour les utilisateurs, puis en appliquant la stratégie à des utilisateurs spécifiques ou à des groupes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="2a216-153">You can enable or disable archiving for specific users by creating and configuring an archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="2a216-154">Les stratégies utilisateur remplacent les stratégies globales ou de site.</span><span class="sxs-lookup"><span data-stu-id="2a216-154">User policies override any global policy or site policies.</span></span> <span data-ttu-id="2a216-155">Les stratégies d’archivage ne s’appliquent que si vous n’utilisez pas l’intégration de Microsoft Exchange ou, si vous utilisez l’intégration de Microsoft Exchange, mais que certains utilisateurs ne sont pas hébergés sur Exchange et que leurs boîtes aux lettres sont placées sur le blocage sur place.</span><span class="sxs-lookup"><span data-stu-id="2a216-155">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a><span data-ttu-id="2a216-156">Configurer une stratégie d’archivage pour les utilisateurs hébergés sur Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2a216-156">Configure an archiving policy for users homed on Skype for Business Server</span></span>

1. <span data-ttu-id="2a216-157">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="2a216-157">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2a216-158">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="2a216-158">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="2a216-159">Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **stratégie**d’archivage.</span><span class="sxs-lookup"><span data-stu-id="2a216-159">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="2a216-160">Cliquez sur **Créer**, puis sur **Stratégie utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="2a216-160">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="2a216-161">Dans **Nouvelle stratégie d’archivage**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="2a216-161">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="2a216-162">Dans **Nom**, spécifiez le nom de la stratégie utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2a216-162">In **Name**, specify the name for the user policy.</span></span> 
    
   - <span data-ttu-id="2a216-163">Dans **Description**, entrez des informations décrivant la stratégie utilisateur (par exemple, stratégie utilisateur pour le service juridique).</span><span class="sxs-lookup"><span data-stu-id="2a216-163">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
   - <span data-ttu-id="2a216-164">Pour contrôler l’archivage des communications internes de la stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications internes**.</span><span class="sxs-lookup"><span data-stu-id="2a216-164">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="2a216-165">Pour contrôler l’archivage des communications externes de la stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications externes**.</span><span class="sxs-lookup"><span data-stu-id="2a216-165">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="2a216-166">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="2a216-166">Click **Commit**.</span></span>
    
<span data-ttu-id="2a216-167">Une stratégie utilisateur ne s’applique qu’aux utilisateurs auxquels vous affectez la stratégie.</span><span class="sxs-lookup"><span data-stu-id="2a216-167">A user policy applies only to users to whom you assign the policy.</span></span>
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a><span data-ttu-id="2a216-168">Appliquer une stratégie d’archivage de Skype entreprise Server à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="2a216-168">Apply a Skype for Business Server archiving policy to a user</span></span>

1. <span data-ttu-id="2a216-169">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="2a216-169">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2a216-170">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="2a216-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="2a216-171">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.</span><span class="sxs-lookup"><span data-stu-id="2a216-171">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="2a216-172">Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="2a216-172">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="2a216-173">Dans **modifier l’utilisateur de Skype entreprise Server** sous **stratégie**d’archivage, sélectionnez la stratégie de l’utilisateur d’archivage que vous voulez appliquer.</span><span class="sxs-lookup"><span data-stu-id="2a216-173">In **Edit Skype for Business Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2a216-174">Les \*\* \<paramètres\> automatiques\*\* appliquent les paramètres d’installation du serveur par défaut.</span><span class="sxs-lookup"><span data-stu-id="2a216-174">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="2a216-175">Ces paramètres sont appliqués automatiquement par le serveur.</span><span class="sxs-lookup"><span data-stu-id="2a216-175">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="2a216-176">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="2a216-176">Click **Commit**.</span></span>
    

