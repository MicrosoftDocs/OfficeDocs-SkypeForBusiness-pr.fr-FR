---
title: Personnaliser les propriétés du compte d’utilisateur pour Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Vous pouvez utiliser les procédures décrites dans cette section pour modifier les propriétés du compte d’utilisateur individuel.
ms.openlocfilehash: 8546d660d0d79f36fa37abf43fcf06dc8e863691
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20968858"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a><span data-ttu-id="a16ae-103">Personnaliser les propriétés du compte d’utilisateur pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="a16ae-103">Customize user account properties for Skype for Business Server</span></span>
 
<span data-ttu-id="a16ae-104">Vous pouvez utiliser les procédures décrites dans cette section pour modifier les propriétés du compte d’utilisateur individuel.</span><span class="sxs-lookup"><span data-stu-id="a16ae-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="a16ae-105">Il existe deux opérations de base qui peuvent être effectuées au niveau de chaque utilisateur :</span><span class="sxs-lookup"><span data-stu-id="a16ae-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="a16ae-106">Configurer les options de téléphonie pour un compte d’utilisateur spécifique</span><span class="sxs-lookup"><span data-stu-id="a16ae-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="a16ae-107">Déplacer les utilisateurs vers un autre pool</span><span class="sxs-lookup"><span data-stu-id="a16ae-107">Move users to another pool </span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="a16ae-108">Configurer les options de téléphonie pour un compte d’utilisateur spécifique</span><span class="sxs-lookup"><span data-stu-id="a16ae-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="a16ae-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="a16ae-109"></span></span>

<span data-ttu-id="a16ae-110">Vous pouvez personnaliser les paramètres de téléphonie pour un utilisateur spécifique (tant que l’utilisateur a été activé pour Skype pour Business Server et l’organisation prend en charge la téléphonie).</span><span class="sxs-lookup"><span data-stu-id="a16ae-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server and the organization supports telephony).</span></span>
  
<span data-ttu-id="a16ae-111">Skype pour les options de téléphonie utilisateur Business Server sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="a16ae-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="a16ae-112">**Audio/vidéo désactivé** L’utilisateur ne peut pas émettre des appels avec audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="a16ae-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="a16ae-113">**PC à PC uniquement** L’utilisateur peut effectuer uniquement aux appels de PC à PC audio ou vidéo.</span><span class="sxs-lookup"><span data-stu-id="a16ae-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="a16ae-114">**Voix entreprise** L’utilisateur peut utiliser le Skype pour infrastructure Business Server pour acheminer tous les appels entrants et sortants.</span><span class="sxs-lookup"><span data-stu-id="a16ae-114">**Enterprise Voice** The user can use the Skype for Business Server infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="a16ae-115">L’utilisateur peut aussi passer des appels de PC à PC.</span><span class="sxs-lookup"><span data-stu-id="a16ae-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="a16ae-116">**Contrôle d’appel distant** L’utilisateur peut utiliser Skype pour Business Server pour contrôler le téléphone de bureau et peut aussi passer des appels de PC à PC.</span><span class="sxs-lookup"><span data-stu-id="a16ae-116">**Remote call control** The user can use Skype for Business Server to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="a16ae-117">Pour plus d’informations sur la configuration de téléphonie dans une organisation, voir [Activer les utilisateurs pour Enterprise Voice dans Skype pour Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) et le [Déploiement d’Enterprise Voice dans Skype pour Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="a16ae-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="a16ae-118">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="a16ae-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a16ae-119">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="a16ae-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="a16ae-120">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="a16ae-121">Dans la zone **Rechercher des utilisateurs** , tapez tout ou la première partie du nom complet, prénom, dernier nom, nom de compte Gestionnaire de comptes de sécurité (SAM), adresse SIP ou au trait identificateur URI (Uniform Resource) du compte d’utilisateur que vous souhaitez, puis cliquez sur **Rechercher **.</span><span class="sxs-lookup"><span data-stu-id="a16ae-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="a16ae-122">Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="a16ae-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="a16ae-123">Dans le menu **Edition** , cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="a16ae-124">En **téléphonie**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a16ae-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="a16ae-125">Pour désactiver les appels audio et vidéo pour l’utilisateur, cliquez sur **Audio/vidéo désactivé**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="a16ae-126">Pour activer les communications audio de PC à PC pour l’utilisateur, mais pas le contrôle d’appel ou un Enterprise Voice, cliquez sur **PC à PC uniquement**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-126">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**.</span></span> <span data-ttu-id="a16ae-127">Spécifiez une valeur pour **URI de ligne** pour le téléphone de l’utilisateur pour les communications audio de PC à PC.</span><span class="sxs-lookup"><span data-stu-id="a16ae-127">Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="a16ae-128">Pour acheminer les appels téléphoniques de l’utilisateur à l’aide de la Skype pour l’infrastructure d’entreprise, conformément à la classe de stratégie de service, y compris les communications audio de PC à PC, cliquez sur **Enterprise Voice**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="a16ae-129">Dans **URI de ligne**, spécifiez le numéro de téléphone pour Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="a16ae-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="a16ae-130">Dans **stratégie de plan de numérotation** et **la stratégie de voix**, spécifiez les stratégies appropriées pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a16ae-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="a16ae-131">Pour spécifier les règles de normalisation pour traduire les numéros de téléphone composés par l’utilisateur au format E.164, sélectionnez le profil d’emplacement approprié dans la **stratégie d’emplacement**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="a16ae-132">Pour permettre d’appel distant contrôle, qui permet aux utilisateurs de contrôler la ligne de leur téléphone de bureau à partir de Skype pour émettre des appels de PC à PC et PC à téléphone Business Server, cliquez sur **le contrôle d’appel distant**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="a16ae-133">Dans **URI de ligne**, spécifiez le numéro de téléphone pour le contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="a16ae-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="a16ae-134">L’utilisateur doit avoir une connexion à exchange (PBX) autocommutateur privé pour le routage des appels et le téléphone de bureau.</span><span class="sxs-lookup"><span data-stu-id="a16ae-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="a16ae-135">Déplacer les utilisateurs vers un autre pool</span><span class="sxs-lookup"><span data-stu-id="a16ae-135">Move users to another pool</span></span>
<span data-ttu-id="a16ae-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="a16ae-136"></span></span>

<span data-ttu-id="a16ae-137">Vous pouvez utiliser Skype pour Business Server Control Panel pour affecter des utilisateurs à un serveur spécifique ou un pool.</span><span class="sxs-lookup"><span data-stu-id="a16ae-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="a16ae-138">Déplacement de tous les utilisateurs existants à partir d’un pool source exécutant Lync Server 2010 ou version antérieure vers un Skype pour le pool de destination Business Server dans un environnement Active Directory complexe peut entraîner la réplication Active Directory plus lente.</span><span class="sxs-lookup"><span data-stu-id="a16ae-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="a16ae-139">Pour éviter ce problème, vous pouvez utiliser des filtres de recherche pour déplacer des utilisateurs à partir des pools qui exécutent Lync Server 2010 ou précédemment séparément, ou vous pouvez utiliser Skype pour Business Server Management Shell pour déplacer des utilisateurs avec les applets de commande.</span><span class="sxs-lookup"><span data-stu-id="a16ae-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="a16ae-140">En outre, la fonctionnalité de filtre fonctionne avec Skype pour les utilisateurs Business Server.</span><span class="sxs-lookup"><span data-stu-id="a16ae-140">Also, the filter functionality works with Skype for Business Server users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="a16ae-141">Pour déplacer les utilisateurs sélectionnés vers un autre serveur ou un pool</span><span class="sxs-lookup"><span data-stu-id="a16ae-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="a16ae-142">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="a16ae-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a16ae-143">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="a16ae-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="a16ae-144">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="a16ae-145">Dans la zone **Rechercher des utilisateurs** , tapez tout ou la première partie du nom complet, prénom, dernier nom, nom de compte Gestionnaire de comptes de sécurité (SAM), adresse SIP ou au trait identificateur URI (Uniform Resource) du compte d’utilisateur que vous souhaitez, puis cliquez sur **Rechercher **.</span><span class="sxs-lookup"><span data-stu-id="a16ae-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="a16ae-146">Dans le tableau, sélectionnez un ou plusieurs utilisateurs dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a16ae-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="a16ae-147">Dans le menu **Action** , cliquez sur **déplacer les utilisateurs sélectionnés vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="a16ae-148">Dans **Déplacer des utilisateurs**, sélectionnez le pool que vous souhaitez déplacer les utilisateurs dans le **pool de serveurs d’inscriptions de Destination**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="a16ae-149">(Facultatif) Si le serveur de destination ou le pool n’est pas disponible, activez la case à cocher **forcer** .</span><span class="sxs-lookup"><span data-stu-id="a16ae-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="a16ae-150">Si vous sélectionnez **Force**, le compte d’utilisateur est déplacé, mais toutes les données utilisateur associé sont supprimées (par exemple, l’utilisateur a planifié des conférences).</span><span class="sxs-lookup"><span data-stu-id="a16ae-150">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="a16ae-151">Si vous n’activez pas le, le compte et les données associées sont déplacées.</span><span class="sxs-lookup"><span data-stu-id="a16ae-151">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="a16ae-152">Pour déplacer tous les utilisateurs d’un serveur ou pool vers un autre serveur ou un pool</span><span class="sxs-lookup"><span data-stu-id="a16ae-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="a16ae-153">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="a16ae-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a16ae-154">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="a16ae-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="a16ae-155">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="a16ae-156">Dans le menu **Action** , cliquez sur **déplacer tous les utilisateurs vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="a16ae-157">Dans **Déplacer des utilisateurs**, sélectionnez le pool contenant les comptes d’utilisateur que vous souhaitez déplacer dans un **pool de serveurs d’inscriptions Source**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="a16ae-158">Dans le **pool de serveurs d’inscriptions de Destination**, sélectionnez le pool que vous souhaitez déplacer les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a16ae-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="a16ae-159">(Facultatif) Si le serveur de destination ou le pool n’est pas disponible, activez la case à cocher **forcer** .</span><span class="sxs-lookup"><span data-stu-id="a16ae-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="a16ae-160">Si vous sélectionnez **Force**, le compte d’utilisateur est déplacé, mais toutes les données utilisateur associé sont supprimées (par exemple, l’utilisateur a planifié des conférences).</span><span class="sxs-lookup"><span data-stu-id="a16ae-160">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="a16ae-161">Si vous n’activez pas le, le compte et les données associées sont déplacées.</span><span class="sxs-lookup"><span data-stu-id="a16ae-161">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="a16ae-162">Pour déplacer des utilisateurs d’un pool vers un autre pool à l’aide d’un filtre</span><span class="sxs-lookup"><span data-stu-id="a16ae-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="a16ae-163">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="a16ae-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a16ae-164">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="a16ae-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="a16ae-165">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="a16ae-166">Dans la **Recherche d’un utilisateur**, cliquez sur **Rechercher**, puis cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="a16ae-167">Dans les critères de recherche, sélectionnez **Pool de serveurs d’inscriptions**, sélectionnez **égal à**, sélectionnez **Actif nom complet du Pool**, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="a16ae-168">Dans le menu **Action** , cliquez sur **déplacer tous les utilisateurs vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a16ae-169">Lorsqu’un filtre est appliqué à un ensemble existant d’utilisateurs, l’option **déplacer tous les utilisateurs vers le pool** est dans le contexte du sous-ensemble d’utilisateurs, **tous les** utilisateurs possibles pas filtré.</span><span class="sxs-lookup"><span data-stu-id="a16ae-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="a16ae-170">Dans **Déplacer des utilisateurs**, sélectionnez le pool contenant les comptes d’utilisateur que vous souhaitez déplacer dans un **pool de serveurs d’inscriptions Source**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="a16ae-171">Dans le **pool de serveurs d’inscriptions de Destination**, sélectionnez le pool dans lequel vous souhaitez déplacer les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a16ae-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="a16ae-172">(Facultatif) Si le serveur de destination ou le pool n’est pas disponible, activez la case à cocher **forcer** .</span><span class="sxs-lookup"><span data-stu-id="a16ae-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="a16ae-173">Si vous sélectionnez **Force**, le compte d’utilisateur est déplacé, mais toutes les données utilisateur associé sont supprimées (par exemple, l’utilisateur a planifié des conférences et les contacts).</span><span class="sxs-lookup"><span data-stu-id="a16ae-173">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts).</span></span> <span data-ttu-id="a16ae-174">Si vous n’activez pas le, le compte et les données associées sont déplacées.</span><span class="sxs-lookup"><span data-stu-id="a16ae-174">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="a16ae-175">Pour déplacer les utilisateurs d’un pool vers un autre à l’aide des applets de commande Windows Powershell</span><span class="sxs-lookup"><span data-stu-id="a16ae-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="a16ae-176">Selon si vous exécutez les commandes Windows PowerShell (c'est-à-dire, localement ou à distance), vous devez ouvrir une session en tant que membre de la Skype correcte des rôles d’administration Business Server comme suit :</span><span class="sxs-lookup"><span data-stu-id="a16ae-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server administrative roles as follows:</span></span>
    
   <span data-ttu-id="a16ae-177">a.</span><span class="sxs-lookup"><span data-stu-id="a16ae-177">a.</span></span> <span data-ttu-id="a16ae-178">Si vous exécutez les commandes sur l’ordinateur local (par exemple, vous connecter directement à un serveur frontal) : ouvrez une session sur l’ordinateur où Skype pour Business Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou disposant des nécessaires droits d’utilisateur tels que décrits dans **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="a16ae-179">b.</span><span class="sxs-lookup"><span data-stu-id="a16ae-179">b.</span></span> <span data-ttu-id="a16ae-180">Si vous exécutez les commandes à distance sur un autre ordinateur (par exemple, vous ouvrez une session sur votre ordinateur et exécutez les commandes à distance sur un serveur Standard Edition serveur frontal) : à partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou le CsAdministrator Role, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="a16ae-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a16ae-181">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour les entreprises**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a16ae-182">Pour déplacer des utilisateurs individuels, utilisez l’applet de commande Move-CsUser comme suit :</span><span class="sxs-lookup"><span data-stu-id="a16ae-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="a16ae-183">Où l’utilisateur à déplacer est l’utilisateur Pilar Ackerman et l’utilisateur sera déplacé à partir de leur pool d’accueil actuellement affecté vers le pool pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="a16ae-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="a16ae-184">Pour déplacer un grand nombre d’utilisateurs, utilisez des filtres avec l’applet de commande **Get-CsUser** et passez l’ensemble d’utilisateurs obtenu vers **Move-CsUser**:</span><span class="sxs-lookup"><span data-stu-id="a16ae-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="a16ae-185">Cela peuvent entraîner les commandes combinées des **Get-CsUser** et **Move-CsUser** :</span><span class="sxs-lookup"><span data-stu-id="a16ae-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


