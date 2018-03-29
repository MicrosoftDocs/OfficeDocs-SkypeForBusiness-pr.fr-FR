---
title: Personnaliser les propriétés du compte d’utilisateur de Skype pour Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Vous pouvez utiliser les procédures dans cette section pour modifier les propriétés de compte d’utilisateur individuel.
ms.openlocfilehash: fc15dac499fe5d812d5d084a919db10096e6dc56
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="customize-user-account-properties-for-skype-for-business-server-2015"></a><span data-ttu-id="3ce6f-103">Personnaliser les propriétés du compte d’utilisateur de Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3ce6f-103">Customize user account properties for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3ce6f-104">Vous pouvez utiliser les procédures dans cette section pour modifier les propriétés de compte d’utilisateur individuel.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="3ce6f-105">Il existe deux opérations de base qui peuvent être effectuées au niveau de l’utilisateur individuel :</span><span class="sxs-lookup"><span data-stu-id="3ce6f-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="3ce6f-106">Configurer les options de téléphonie pour un compte d’utilisateur spécifique</span><span class="sxs-lookup"><span data-stu-id="3ce6f-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="3ce6f-107">Déplacer des utilisateurs vers un autre pool</span><span class="sxs-lookup"><span data-stu-id="3ce6f-107">Move users to another pool </span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="3ce6f-108">Configurer les options de téléphonie pour un compte d’utilisateur spécifique</span><span class="sxs-lookup"><span data-stu-id="3ce6f-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="3ce6f-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="3ce6f-109"></span></span>

<span data-ttu-id="3ce6f-110">Vous pouvez personnaliser les paramètres de téléphonie pour un utilisateur spécifique (tant que l’utilisateur a été activé pour Skype pour Business Server 2015 et l’organisation prend en charge la téléphonie).</span><span class="sxs-lookup"><span data-stu-id="3ce6f-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server 2015 and the organization supports telephony).</span></span>
  
<span data-ttu-id="3ce6f-111">Skype pour des options de téléphonie utilisateur Business Server sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="3ce6f-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="3ce6f-112">**Audio/vidéo désactivée** L’utilisateur ne peut pas effectuer des appels avec audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="3ce6f-113">**PC à PC uniquement** L’utilisateur peut effectuer uniquement aux appels de PC à PC audio ou vidéo.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="3ce6f-114">**Voix Entreprise** L’utilisateur peut utiliser le Skype pour l’infrastructure de Business Server 2015 pour acheminer tous les appels entrants et sortants.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-114">**Enterprise Voice** The user can use the Skype for Business Server 2015 infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="3ce6f-115">L’utilisateur peut également effectuer des appels de PC à PC.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="3ce6f-116">**Contrôle d’appel distant** L’utilisateur peut utiliser le Skype pour Business Server 2015 pour contrôler le téléphone de bureau et peut aussi effectuer des appels de PC à PC.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-116">**Remote call control** The user can use Skype for Business Server 2015 to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="3ce6f-117">Pour plus d’informations sur la configuration de la téléphonie pour une organisation, voir [Déploiement de Voix Entreprise dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) et de [permettre aux utilisateurs de Voix Entreprise dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="3ce6f-118">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3ce6f-119">Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="3ce6f-120">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3ce6f-121">Dans la zone **Rechercher des utilisateurs** , tapez tout ou la première partie du nom complet, prénom, dernier nom, nom de compte Gestionnaire de comptes de sécurité (SAM), adresse SIP ou identificateur URI (Uniform Resource) du compte d’utilisateur que vous souhaitez, puis cliquez sur recherche de **de ligne **.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="3ce6f-122">Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="3ce6f-123">Dans le menu **Edition** , cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="3ce6f-124">En **téléphonie**, effectuez les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="3ce6f-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="3ce6f-125">Pour désactiver les appels audio et vidéo pour l’utilisateur, cliquez sur **Audio/vidéo désactivée**.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="3ce6f-126">Pour activer les communications audio de PC à PC de l’utilisateur, mais le contrôle d’appel distant pas ou la Voix Entreprise, cliquez sur **PC à PC uniquement**.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-126">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**.</span></span> <span data-ttu-id="3ce6f-127">Spécifiez une valeur pour **l’URI de la ligne** pour le téléphone de l’utilisateur pour les communications audio de PC à PC.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-127">Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="3ce6f-128">Pour acheminer les appels téléphoniques de l’utilisateur à l’aide de la Skype pour l’infrastructure d’entreprise selon la classe de stratégie de service, y compris la communication audio de PC à PC, cliquez sur **Voix Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="3ce6f-129">Dans l' **URI de la ligne**, spécifiez le numéro de téléphone de Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="3ce6f-130">Dans **stratégie de plan d’accès à distance** et **stratégie Voice**, spécifiez les stratégies appropriées pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="3ce6f-131">Pour spécifier les règles de normalisation pour la traduction des numéros de téléphone composés par l’utilisateur au format E.164, sélectionnez le profil d’emplacement approprié dans la **stratégie de l’emplacement**.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="3ce6f-132">Pour activer l’appel distant contrôle, ce qui permet aux utilisateurs de contrôler leur ligne de téléphone de bureau à partir de Skype pour 2015 de serveur d’entreprise effectuer des appels de PC à PC et PC à téléphone, cliquez sur **contrôle d’appel distant**.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server 2015 to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="3ce6f-133">Dans l' **URI de la ligne**, spécifiez le numéro de téléphone pour le contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="3ce6f-134">L’utilisateur doit avoir une connexion à exchange (PBX) privé de branche pour le routage d’appel et le téléphone de bureau.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="3ce6f-135">Déplacer des utilisateurs vers un autre pool</span><span class="sxs-lookup"><span data-stu-id="3ce6f-135">Move users to another pool</span></span>
<span data-ttu-id="3ce6f-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="3ce6f-136"></span></span>

<span data-ttu-id="3ce6f-137">Vous pouvez utiliser Skype pour Business Server du Panneau de configuration pour affecter des utilisateurs à un serveur spécifique ou d’un pool.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="3ce6f-138">Déplacement de tous les utilisateurs existants à partir d’un pool de source Lync Server 2010 est en cours d’exécution ou version antérieure vers un Skype pour le pool de destination 2015 de serveur d’entreprise dans un environnement Active Directory complexe peut entraîner la réplication Active Directory plus lente.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server 2015 destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="3ce6f-139">Pour éviter cela, vous pouvez utiliser des filtres de recherche pour déplacer des utilisateurs à partir de pools de Lync Server 2010 sont en cours d’exécution ou précédemment séparément, ou vous pouvez utiliser Skype pour Business Server Management Shell pour déplacer des utilisateurs avec les applets de commande.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="3ce6f-140">En outre, la fonctionnalité de filtre fonctionne avec Skype pour les utilisateurs de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-140">Also, the filter functionality works with Skype for Business Server 2015 users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="3ce6f-141">Pour déplacer les utilisateurs sélectionnés vers un autre serveur ou un pool</span><span class="sxs-lookup"><span data-stu-id="3ce6f-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="3ce6f-142">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3ce6f-143">Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="3ce6f-144">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3ce6f-145">Dans la zone **Rechercher des utilisateurs** , tapez tout ou la première partie du nom complet, prénom, dernier nom, nom de compte Gestionnaire de comptes de sécurité (SAM), adresse SIP ou identificateur URI (Uniform Resource) du compte d’utilisateur que vous souhaitez, puis cliquez sur recherche de **de ligne **.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="3ce6f-146">Dans le tableau, sélectionnez un ou plusieurs utilisateurs dans la liste.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="3ce6f-147">Dans le menu **Action** , cliquez sur **déplacer les utilisateurs sélectionnés au pool**.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="3ce6f-148">**Déplacer des utilisateurs**, sélectionnez le pool que vous souhaitez déplacer les utilisateurs dans le **pool de Destination registrar**.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="3ce6f-149">(Facultatif) Si le pool ou le serveur de destination n’est pas disponible, activez la case à cocher **forcer** .</span><span class="sxs-lookup"><span data-stu-id="3ce6f-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="3ce6f-150">Si vous sélectionnez **Force**, le compte d’utilisateur est déplacé, mais toutes les données utilisateur associé sont supprimées (par exemple, les conférences que l’utilisateur a planifié).</span><span class="sxs-lookup"><span data-stu-id="3ce6f-150">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="3ce6f-151">Si vous ne le sélectionnez pas, le compte et les données associées sont déplacées.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-151">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="3ce6f-152">Pour déplacer tous les utilisateurs à partir d’un serveur ou un pool à un autre serveur ou un pool</span><span class="sxs-lookup"><span data-stu-id="3ce6f-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="3ce6f-153">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3ce6f-154">Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="3ce6f-155">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3ce6f-156">Dans le menu **Action** , cliquez sur **déplacer tous les utilisateurs au pool**.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="3ce6f-157">**Déplacer des utilisateurs**, sélectionnez le pool qui contient les comptes d’utilisateur que vous souhaitez déplacer dans le **pool de registrar de Source**.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="3ce6f-158">**Pool de registrar de Destination**, sélectionnez le pool que vous souhaitez déplacer les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="3ce6f-159">(Facultatif) Si le pool ou le serveur de destination n’est pas disponible, activez la case à cocher **forcer** .</span><span class="sxs-lookup"><span data-stu-id="3ce6f-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="3ce6f-160">Si vous sélectionnez **Force**, le compte d’utilisateur est déplacé, mais toutes les données utilisateur associé sont supprimées (par exemple, les conférences que l’utilisateur a planifié).</span><span class="sxs-lookup"><span data-stu-id="3ce6f-160">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="3ce6f-161">Si vous ne le sélectionnez pas, le compte et les données associées sont déplacées.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-161">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="3ce6f-162">Pour déplacer des utilisateurs à partir d’un pool à un autre pool à l’aide d’un filtre</span><span class="sxs-lookup"><span data-stu-id="3ce6f-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="3ce6f-163">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3ce6f-164">Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="3ce6f-165">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3ce6f-166">Dans la **Recherche de l’utilisateur**, cliquez sur **Rechercher**, puis cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="3ce6f-167">Dans les critères de recherche, sélectionnez **Pool de Registrar**sélectionnez **égal à**, sélectionnez le **FQDN de Pool en cours**et puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="3ce6f-168">Dans le menu **Action** , cliquez sur **déplacer tous les utilisateurs au pool**.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3ce6f-169">Lorsqu’un filtre est appliqué à un jeu existant d’utilisateurs, l’option **déplacer tous les utilisateurs au pool** est dans le contexte du sous-ensemble filtré des utilisateurs, pas **tous les** utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="3ce6f-170">**Déplacer des utilisateurs**, sélectionnez le pool qui contient les comptes d’utilisateur que vous souhaitez déplacer dans le **pool de registrar de Source**.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="3ce6f-171">**Pool de registrar de Destination**, sélectionnez le pool dans lequel vous souhaitez déplacer les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="3ce6f-172">(Facultatif) Si le pool ou le serveur de destination n’est pas disponible, activez la case à cocher **forcer** .</span><span class="sxs-lookup"><span data-stu-id="3ce6f-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="3ce6f-173">Si vous sélectionnez **Force**, le compte d’utilisateur est déplacé, mais toutes les données utilisateur associé sont supprimées (par exemple, les conférences que l’utilisateur a planifié et contacts).</span><span class="sxs-lookup"><span data-stu-id="3ce6f-173">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts).</span></span> <span data-ttu-id="3ce6f-174">Si vous ne le sélectionnez pas, le compte et les données associées sont déplacées.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-174">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="3ce6f-175">Déplacer des utilisateurs à partir d’un pool à un autre à l’aide des applets de commande Windows Powershell</span><span class="sxs-lookup"><span data-stu-id="3ce6f-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="3ce6f-176">En fonction de la façon dont vous exécutez les commandes Windows PowerShell (c'est-à-dire, localement ou à distance), vous devez ouvrir une session en tant que membre de la Skype correct pour les rôles d’administration de Business Server 2015 comme suit :</span><span class="sxs-lookup"><span data-stu-id="3ce6f-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server 2015 administrative roles as follows:</span></span>
    
   <span data-ttu-id="3ce6f-177">a.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-177">a.</span></span> <span data-ttu-id="3ce6f-178">Si vous exécutez les commandes sur l’ordinateur local (par exemple, vous connecter directement à un serveur frontal) : ouvrez une session sur l’ordinateur où est installé Skype pour Business Server Management Shell en tant que membre du groupe RTCUniversalServerAdmins ou disposant des nécessaires droits d’utilisateur comme décrit dans **Déléguer les autorisations de configuration**.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="3ce6f-179">b.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-179">b.</span></span> <span data-ttu-id="3ce6f-180">Si vous exécutez les commandes à distance sur un autre ordinateur (par exemple, vous ouvrez une session sur votre ordinateur et exécuter des commandes à distance sur un Standard Edition serveur frontal) : à partir d’un compte d’utilisateur affecté au rôle CsUserAdministrator ou le CsAdministrator rôle, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3ce6f-181">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="3ce6f-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="3ce6f-182">Pour déplacer des utilisateurs individuels, utilisez l’applet de commande Move-CsUser comme suit :</span><span class="sxs-lookup"><span data-stu-id="3ce6f-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="3ce6f-183">Où correspond à l’utilisateur de déplacer l’utilisateur Pilar Ackerman et que l’utilisateur va de leur pool de domicile actuellement affectée à la pool01.contoso.net de pool</span><span class="sxs-lookup"><span data-stu-id="3ce6f-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="3ce6f-184">Pour déplacer un grand nombre d’utilisateurs, utilisez des filtres avec l’applet de commande **Get-CsUser** et passer de l’ensemble résultant des utilisateurs à **Move-CsUser**:</span><span class="sxs-lookup"><span data-stu-id="3ce6f-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="3ce6f-185">Cela peuvent entraîner les commandes combinées de **Get-CsUser** et **Move-CsUser** :</span><span class="sxs-lookup"><span data-stu-id="3ce6f-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


