---
title: Configuration des options d’archivage pour Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: 'Résumé : Lisez cette rubrique pour savoir comment configurer les options d’archivage initiales pour Skype pour Business Server 2015. Vous définissez initialement l’archivage configurations lorsque vous déployez l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations d’après le déploiement.'
ms.openlocfilehash: 38923d436f2fc5543158dfce6f8bebde27c7c911
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-archiving-options-for-skype-for-business-server-2015"></a><span data-ttu-id="f99a9-104">Configuration des options d’archivage pour Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="f99a9-104">Configure archiving options for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f99a9-105">**Résumé :** Lisez cette rubrique pour savoir comment configurer les options d’archivage initiales pour Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f99a9-105">**Summary:** Read this topic to learn how to configure initial archiving options for Skype for Business Server 2015.</span></span> <span data-ttu-id="f99a9-106">Vous définissez initialement l’archivage configurations lorsque vous déployez l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations d’après le déploiement.</span><span class="sxs-lookup"><span data-stu-id="f99a9-106">You initially set up archiving configurations when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span>
  
<span data-ttu-id="f99a9-107">Pour configurer initiale de l’archivage des configurations, vous utilisez Skype pour le panneau de configuration de Business Server pour spécifier les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="f99a9-107">To configure initial archiving configurations, you use Skype for Business Server Control Panel to specify the following:</span></span>
  
- <span data-ttu-id="f99a9-108">Configuration au niveau global qui est créée par défaut lorsque vous déployez Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="f99a9-108">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="f99a9-109">Configurations facultatives au niveau du site qui déterminent la mise en œuvre de l’archivage d’un site spécifique</span><span class="sxs-lookup"><span data-stu-id="f99a9-109">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="f99a9-110">Configurations facultatives au niveau du pool qui spécifient comment l’archivage est implémentée pour un pool donné</span><span class="sxs-lookup"><span data-stu-id="f99a9-110">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="f99a9-111">Vous devez configurer les options pour définir les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f99a9-111">You will need to configure options for the following:</span></span>
  
- <span data-ttu-id="f99a9-112">Activer ou désactiver l’archivage</span><span class="sxs-lookup"><span data-stu-id="f99a9-112">Whether to enable or disable archiving</span></span>
    
- <span data-ttu-id="f99a9-113">Archiver ou non les sessions de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="f99a9-113">Whether to archive IM sessions</span></span>
    
- <span data-ttu-id="f99a9-114">Archiver ou non les sessions de conférence Web</span><span class="sxs-lookup"><span data-stu-id="f99a9-114">Whether to archive web conferencing sessions</span></span>
    
- <span data-ttu-id="f99a9-115">Bloquer ou non l’activité lorsque l’archivage n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="f99a9-115">Whether to block activity when archiving is not available</span></span>
    
- <span data-ttu-id="f99a9-116">Utiliser ou non l’intégration d’Exchange</span><span class="sxs-lookup"><span data-stu-id="f99a9-116">Whether to use Exchange integration</span></span>
    
- <span data-ttu-id="f99a9-117">Procédure de configuration de la purge et de l’exportation des données</span><span class="sxs-lookup"><span data-stu-id="f99a9-117">How to set up purging and exporting of data</span></span>
    
> [!NOTE]
> <span data-ttu-id="f99a9-118">Vous devez spécifier toutes les options appropriées avant d’activer l’archivage.</span><span class="sxs-lookup"><span data-stu-id="f99a9-118">You should specify all appropriate options before enabling archiving.</span></span> 
  
<span data-ttu-id="f99a9-119">Pour plus d’informations sur la façon de configurations d’archivage sont mises en oeuvre, y compris les options que vous pouvez spécifier et la hiérarchie de l’archivage des configurations, reportez-vous à [planification d’archivage dans Skype pour Business Server 2015](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="f99a9-119">For details about how archiving configurations are implemented, including which options you can specify and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="f99a9-120">Pour plus d’informations sur la façon de gérer les configurations après le déploiement à l’aide du Panneau de configuration ou à l’aide de Windows PowerShell, voir [Gérer les options d’archivage dans Skype pour Business Server 2015](../../manage/archiving/options.md).</span><span class="sxs-lookup"><span data-stu-id="f99a9-120">For details about how to manage configurations after deployment by using the Control Panel or by using Windows PowerShell, see [Manage archiving options in Skype for Business Server 2015](../../manage/archiving/options.md).</span></span>
  
## <a name="configure-global-level-archiving-options"></a><span data-ttu-id="f99a9-121">Configurer les options d’archivage au niveau global</span><span class="sxs-lookup"><span data-stu-id="f99a9-121">Configure global level archiving options</span></span>

<span data-ttu-id="f99a9-122">Lorsque vous ajoutez l’archivage de votre topologie et que vous publiez la topologie, Skype pour Business Server crée une configuration globale pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="f99a9-122">When you add archiving to your topology and publish the topology, Skype for Business Server creates a global configuration for archiving.</span></span> <span data-ttu-id="f99a9-123">Par défaut, aucune option d’archivage n’est activées dans la configuration globale.</span><span class="sxs-lookup"><span data-stu-id="f99a9-123">By default, no archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="f99a9-124">La configuration globale du contrôle quelles options sont activées pour votre déploiement complet, sauf si vous définissez des configurations de site ou d’un pool, qui remplace la configuration globale.</span><span class="sxs-lookup"><span data-stu-id="f99a9-124">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>
  
<span data-ttu-id="f99a9-125">Pour configurer les options d’archivage au niveau global</span><span class="sxs-lookup"><span data-stu-id="f99a9-125">To configure archiving options at the global level:</span></span>
  
1. <span data-ttu-id="f99a9-126">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f99a9-126">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f99a9-127">Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="f99a9-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="f99a9-128">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="f99a9-128">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="f99a9-129">Sur la page **Configuration de l’archivage**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="f99a9-129">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="f99a9-130">Dans **Modifier le paramètre d’archivage - Global**, dans la zone de liste déroulante **Paramètre d’archivage**, sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="f99a9-130">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="f99a9-131">**Désactiver l’archivage**</span><span class="sxs-lookup"><span data-stu-id="f99a9-131">**Disable archiving**</span></span>
    
   - <span data-ttu-id="f99a9-132">**Archiver les sessions de messagerie instantanée**</span><span class="sxs-lookup"><span data-stu-id="f99a9-132">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="f99a9-133">**Archiver les sessions de messagerie instantanée et de conférence web**</span><span class="sxs-lookup"><span data-stu-id="f99a9-133">**Archive IM and web conferencing sessions**</span></span>
    
6. <span data-ttu-id="f99a9-134">Également sur la page **Modifier l’archivage paramètre - Global** , effectuez le des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f99a9-134">Also on the **Edit Archiving Setting - Global** page, do the following:</span></span>
    
   - <span data-ttu-id="f99a9-135">Pour bloquer toute activité si l’archivage n’est pas disponible, cochez la case **Bloquer les sessions de messagerie instantanée ou de conférence web en cas d’échec de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="f99a9-135">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="f99a9-136">Pour utiliser Microsoft Exchange Server pour stocker les données d’archivage, cliquez sur la case à cocher **intégration de Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="f99a9-136">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="f99a9-137">Pour activer la fonctionnalité de vidage des données, cochez la case **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f99a9-137">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="f99a9-138">Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis indiquez le nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="f99a9-138">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="f99a9-139">Pour limiter le vidage aux données d’archivage exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.</span><span class="sxs-lookup"><span data-stu-id="f99a9-139">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="f99a9-140">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="f99a9-140">Click **Commit**.</span></span>
    
## <a name="configure-site-level-archiving-options"></a><span data-ttu-id="f99a9-141">Configurer les options d’archivage au niveau du site</span><span class="sxs-lookup"><span data-stu-id="f99a9-141">Configure site level archiving options</span></span>

<span data-ttu-id="f99a9-142">Vous pouvez préciser les options d’archivage d’un site spécifique.</span><span class="sxs-lookup"><span data-stu-id="f99a9-142">You can specify archiving options for a specific site.</span></span> <span data-ttu-id="f99a9-143">Une configuration de site ne remplace la configuration globale que pour le site spécifié dans la configuration du site.</span><span class="sxs-lookup"><span data-stu-id="f99a9-143">A site configuration overrides the global configuration, but only for the site specified in the site configuration.</span></span> 
  
1. <span data-ttu-id="f99a9-144">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f99a9-144">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f99a9-145">Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="f99a9-145">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="f99a9-146">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="f99a9-146">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="f99a9-147">Sur la page **Configuration de l’archivage**, cliquez sur **Nouveau**, puis sur **Configuration du site**.</span><span class="sxs-lookup"><span data-stu-id="f99a9-147">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>
    
5. <span data-ttu-id="f99a9-148">Dans **Sélectionner un site**, choisissez le site à configurer pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="f99a9-148">In **Select a Site**, select the site to be configured for archiving.</span></span>
    
6. <span data-ttu-id="f99a9-149">Dans **Nouveau paramètre d’archivage**, dans la liste déroulante **Paramètre d’archivage**, effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="f99a9-149">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="f99a9-150">Afin d’activer l’archivage seulement pour les sessions de messagerie instantanée, cliquez sur **Archiver les sessions de messagerie instantanée**.</span><span class="sxs-lookup"><span data-stu-id="f99a9-150">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="f99a9-151">Afin d’activer l’archivage à la fois pour les sessions de messagerie instantanée et les conférences, cliquez sur **Archiver les sessions de messagerie instantanée et de conférence Web**.</span><span class="sxs-lookup"><span data-stu-id="f99a9-151">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="f99a9-152">Afin de désactiver l’archivage pour une stratégie, cliquez sur **Désactiver l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="f99a9-152">To disable archiving for the policy, click **Disable archiving**.</span></span>
    
7. <span data-ttu-id="f99a9-153">Par ailleurs, dans **Créer un paramètre d’archivage**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f99a9-153">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="f99a9-154">Pour bloquer toute activité si l’archivage n’est pas disponible, cochez la case **Bloquer les sessions de messagerie instantanée ou de conférence web en cas d’échec de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="f99a9-154">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="f99a9-155">Pour utiliser Microsoft Exchange Server pour stocker les données d’archivage, cliquez sur la case à cocher **intégration de Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="f99a9-155">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="f99a9-156">Pour activer la fonctionnalité de vidage des données, cochez la case **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f99a9-156">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="f99a9-157">Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis indiquez le nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="f99a9-157">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="f99a9-158">Pour limiter le vidage aux données d’archivage exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.</span><span class="sxs-lookup"><span data-stu-id="f99a9-158">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="f99a9-159">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="f99a9-159">Click **Commit**.</span></span>
    
## <a name="configure-pool-level-archiving-options"></a><span data-ttu-id="f99a9-160">Configurer les options d’archivage au niveau du pool</span><span class="sxs-lookup"><span data-stu-id="f99a9-160">Configure pool level archiving options</span></span>

<span data-ttu-id="f99a9-p106">Vous pouvez préciser les options d’archivage d’un pool spécifique. Une configuration de pool ne remplace la configuration globale et la configuration du site que pour le pool spécifié dans la configuration du pool.</span><span class="sxs-lookup"><span data-stu-id="f99a9-p106">You can specify archiving options for a specific pool. A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>
  
1. <span data-ttu-id="f99a9-163">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f99a9-163">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f99a9-164">Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="f99a9-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="f99a9-165">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="f99a9-165">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="f99a9-166">Sur la page **Configuration de l’archivage**, cliquez sur **Nouveau**, puis sur **Configuration du pool**.</span><span class="sxs-lookup"><span data-stu-id="f99a9-166">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>
    
5. <span data-ttu-id="f99a9-167">Dans **Sélectionner un service**, sélectionnez le pool à configurer pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="f99a9-167">In **Select a Service**, select the pool to be configured for archiving.</span></span>
    
6. <span data-ttu-id="f99a9-168">Dans **Créer un paramètre d’archivage**, dans la liste déroulante **Paramètre d’archivage**, sélectionnez l’une des options d’archivage suivantes :</span><span class="sxs-lookup"><span data-stu-id="f99a9-168">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="f99a9-169">**Désactiver l’archivage**</span><span class="sxs-lookup"><span data-stu-id="f99a9-169">**Disable archiving**</span></span>
    
   - <span data-ttu-id="f99a9-170">**Archiver les sessions de messagerie instantanée**</span><span class="sxs-lookup"><span data-stu-id="f99a9-170">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="f99a9-171">**Archiver les sessions de messagerie instantanée et de conférence web**</span><span class="sxs-lookup"><span data-stu-id="f99a9-171">**Archive IM and web conferencing sessions**</span></span>
    
7. <span data-ttu-id="f99a9-172">Dans la page **Créer un paramètre d’archivage**, effectuez également l’opération suivante :</span><span class="sxs-lookup"><span data-stu-id="f99a9-172">Also in **New Archiving Setting** page, do the following:</span></span>
    
   - <span data-ttu-id="f99a9-173">Pour bloquer toute activité si l’archivage n’est pas disponible, cochez la case **Bloquer les sessions de messagerie instantanée ou de conférence Web en cas d’échec de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="f99a9-173">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="f99a9-174">Pour utiliser Microsoft Exchange Server pour stocker les données d’archivage, cliquez sur la case à cocher **intégration de Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="f99a9-174">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="f99a9-175">Pour activer la fonctionnalité de vidage des données, cochez la case **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f99a9-175">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="f99a9-176">Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis indiquez le nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="f99a9-176">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="f99a9-177">Pour limiter le vidage aux données d’archivage exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.</span><span class="sxs-lookup"><span data-stu-id="f99a9-177">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="f99a9-178">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="f99a9-178">Click **Commit**.</span></span>
    

