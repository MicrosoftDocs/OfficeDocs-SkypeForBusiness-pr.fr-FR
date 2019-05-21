---
title: Personnaliser des propriétés de compte d’utilisateur pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Vous pouvez utiliser les procédures décrites dans cette section pour modifier des propriétés de compte d’utilisateur individuelles.
ms.openlocfilehash: d0e1a3ac02f5696e91e07c0f08cf0cf10e09f98e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275072"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a><span data-ttu-id="427a5-103">Personnaliser des propriétés de compte d’utilisateur pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="427a5-103">Customize user account properties for Skype for Business Server</span></span>
 
<span data-ttu-id="427a5-104">Vous pouvez utiliser les procédures décrites dans cette section pour modifier des propriétés de compte d’utilisateur individuelles.</span><span class="sxs-lookup"><span data-stu-id="427a5-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="427a5-105">Deux opérations de base peuvent être effectuées au niveau utilisateur individuel:</span><span class="sxs-lookup"><span data-stu-id="427a5-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="427a5-106">Configurer les options de téléphonie pour un compte d’utilisateur spécifique</span><span class="sxs-lookup"><span data-stu-id="427a5-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="427a5-107">Déplacer des utilisateurs vers un autre pool</span><span class="sxs-lookup"><span data-stu-id="427a5-107">Move users to another pool </span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="427a5-108">Configurer les options de téléphonie pour un compte d’utilisateur spécifique</span><span class="sxs-lookup"><span data-stu-id="427a5-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="427a5-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="427a5-109"></span></span>

<span data-ttu-id="427a5-110">Vous pouvez personnaliser les paramètres de téléphonie pour un utilisateur spécifique (tant que l’utilisateur individuel a été activé pour Skype entreprise Server et l’Organisation prend en charge la téléphonie).</span><span class="sxs-lookup"><span data-stu-id="427a5-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server and the organization supports telephony).</span></span>
  
<span data-ttu-id="427a5-111">Les options de téléphonie de l’utilisateur Skype entreprise Server incluent les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="427a5-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="427a5-112">**Audio/vidéo désactivé** L’utilisateur ne peut pas passer d’appels à l’aide de l’audio et de la vidéo.</span><span class="sxs-lookup"><span data-stu-id="427a5-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="427a5-113">**PC à PC uniquement** L’utilisateur peut passer des appels audio ou vidéo de PC à PC.</span><span class="sxs-lookup"><span data-stu-id="427a5-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="427a5-114">**Voix entreprise** L’utilisateur peut utiliser l’infrastructure du serveur Skype entreprise pour acheminer tous les appels entrants et sortants.</span><span class="sxs-lookup"><span data-stu-id="427a5-114">**Enterprise Voice** The user can use the Skype for Business Server infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="427a5-115">L’utilisateur peut également passer des appels de PC à PC.</span><span class="sxs-lookup"><span data-stu-id="427a5-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="427a5-116">**Contrôle d’appel distant** L’utilisateur peut utiliser Skype entreprise Server pour contrôler le téléphone de bureau et peut également passer des appels de PC à PC.</span><span class="sxs-lookup"><span data-stu-id="427a5-116">**Remote call control** The user can use Skype for Business Server to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="427a5-117">Pour plus d’informations sur la configuration de la téléphonie pour une organisation, reportez-vous à la rubrique [activer les utilisateurs d’Enterprise Voice dans Skype entreprise Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) et [déployer Enterprise Voice dans Skype entreprise Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="427a5-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="427a5-118">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="427a5-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="427a5-119">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="427a5-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="427a5-120">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="427a5-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="427a5-121">Dans la boîte de dialogue **Rechercher des utilisateurs** , entrez tout ou la première partie du nom complet, prénom, nom, nom du compte de comptes de sécurité, adresse SIP ou URI (Uniform Resource Identifier) du compte d’utilisateur que vous souhaitez, puis cliquez sur \*\*Rechercher. \*\*.</span><span class="sxs-lookup"><span data-stu-id="427a5-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="427a5-122">Dans la table, cliquez sur le compte d’utilisateur que vous voulez modifier.</span><span class="sxs-lookup"><span data-stu-id="427a5-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="427a5-123">Dans le menu **édition** , cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="427a5-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="427a5-124">En **téléphonie**, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="427a5-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="427a5-125">Pour désactiver les appels audio et vidéo pour l’utilisateur, cliquez sur **audio/vidéo désactivé**.</span><span class="sxs-lookup"><span data-stu-id="427a5-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="427a5-126">Pour activer les communications audio de PC à ordinateur pour l’utilisateur, mais pas le contrôle d’appel distant ni la voix entreprise, cliquez sur **PC à PC uniquement**.</span><span class="sxs-lookup"><span data-stu-id="427a5-126">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**.</span></span> <span data-ttu-id="427a5-127">Spécifiez une valeur pour **URI ligne** pour le téléphone utilisée par l’utilisateur pour les communications audio de PC à PC.</span><span class="sxs-lookup"><span data-stu-id="427a5-127">Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="427a5-128">Pour acheminer les appels téléphoniques de l’utilisateur à l’aide de l’infrastructure Skype entreprise conformément à la classe de la politique de service, y compris la communication audio de PC à PC, cliquez sur **voix entreprise**.</span><span class="sxs-lookup"><span data-stu-id="427a5-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="427a5-129">Dans **URI de ligne**, spécifiez le numéro de téléphone d’entreprise voix.</span><span class="sxs-lookup"><span data-stu-id="427a5-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="427a5-130">Dans **politique de plan** de numérotation et de **stratégie vocale**, spécifiez les stratégies appropriées pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="427a5-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="427a5-131">Pour spécifier les règles de normalisation pour la traduction des numéros de téléphone numérotés par l’utilisateur au format E. 164, sélectionnez le profil d’emplacement approprié dans la **politique d’emplacement**.</span><span class="sxs-lookup"><span data-stu-id="427a5-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="427a5-132">Pour activer le contrôle d’appel distant, qui permet aux utilisateurs de contrôler leur ligne téléphonique de bureau dans Skype entreprise Server afin de passer des appels de PC à PC et des appels de PC à téléphone, cliquez sur **contrôle d’appel distant**.</span><span class="sxs-lookup"><span data-stu-id="427a5-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="427a5-133">Dans **URI de ligne**, spécifiez le numéro de téléphone du contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="427a5-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="427a5-134">Pour le routage des appels, l’utilisateur doit avoir un téléphone de bureau et une connexion PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="427a5-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="427a5-135">Déplacer des utilisateurs vers un autre pool</span><span class="sxs-lookup"><span data-stu-id="427a5-135">Move users to another pool</span></span>
<span data-ttu-id="427a5-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="427a5-136"></span></span>

<span data-ttu-id="427a5-137">Vous pouvez utiliser le panneau de configuration Skype entreprise Server pour attribuer des utilisateurs à un serveur ou un pool spécifique.</span><span class="sxs-lookup"><span data-stu-id="427a5-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="427a5-138">Le déplacement de tous les utilisateurs existants à partir d’un pool de sources qui exécute Lync Server 2010 ou une version antérieure vers un pool de destination Skype entreprise Server dans un environnement Active Directory complexe peut ralentir la réplication Active Directory.</span><span class="sxs-lookup"><span data-stu-id="427a5-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="427a5-139">Pour éviter ce problème, vous pouvez utiliser des filtres de recherche pour déplacer des utilisateurs de pools exécutant Lync Server 2010 ou une version antérieure séparément, ou vous pouvez utiliser Skype entreprise Server Management Shell pour déplacer des utilisateurs avec des cmdlets.</span><span class="sxs-lookup"><span data-stu-id="427a5-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="427a5-140">Par ailleurs, la fonctionnalité filtre fonctionne avec les utilisateurs de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="427a5-140">Also, the filter functionality works with Skype for Business Server users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="427a5-141">Pour déplacer des utilisateurs sélectionnés vers un autre serveur ou pool</span><span class="sxs-lookup"><span data-stu-id="427a5-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="427a5-142">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="427a5-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="427a5-143">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="427a5-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="427a5-144">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="427a5-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="427a5-145">Dans la boîte de dialogue **Rechercher des utilisateurs** , entrez tout ou la première partie du nom complet, prénom, nom, nom du compte de comptes de sécurité, adresse SIP ou URI (Uniform Resource Identifier) du compte d’utilisateur que vous souhaitez, puis cliquez sur \*\*Rechercher. \*\*.</span><span class="sxs-lookup"><span data-stu-id="427a5-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="427a5-146">Dans le tableau, sélectionnez un utilisateur ou des utilisateurs spécifiques dans la liste.</span><span class="sxs-lookup"><span data-stu-id="427a5-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="427a5-147">Dans le menu **action** , cliquez sur **déplacer les utilisateurs sélectionnés vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="427a5-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="427a5-148">Dans **déplacer les utilisateurs**, sélectionnez le groupe dans lequel vous souhaitez déplacer les utilisateurs dans le **pool d’inscriptions de destination**.</span><span class="sxs-lookup"><span data-stu-id="427a5-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="427a5-149">Facultatif Si le serveur de destination ou le pool n’est pas disponible, activez la case à cocher **forcer** .</span><span class="sxs-lookup"><span data-stu-id="427a5-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="427a5-150">Si vous sélectionnez l’option **force**, le compte d’utilisateur est déplacé, mais les données utilisateur associées sont supprimées (par exemple, conférences que l’utilisateur a planifiées).</span><span class="sxs-lookup"><span data-stu-id="427a5-150">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="427a5-151">Si vous ne la sélectionnez pas, le compte et les données associées sont déplacés.</span><span class="sxs-lookup"><span data-stu-id="427a5-151">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="427a5-152">Pour déplacer tous les utilisateurs d’un serveur ou d’un pool vers un autre serveur ou pool</span><span class="sxs-lookup"><span data-stu-id="427a5-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="427a5-153">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="427a5-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="427a5-154">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="427a5-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="427a5-155">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="427a5-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="427a5-156">Dans le menu **action** , cliquez sur **déplacer tous les utilisateurs vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="427a5-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="427a5-157">Dans **déplacer les utilisateurs**, sélectionnez le groupe qui contient les comptes d’utilisateurs que vous voulez déplacer dans le **pool d’inscriptions sources**.</span><span class="sxs-lookup"><span data-stu-id="427a5-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="427a5-158">Dans la **liste de bureaux**d’enregistrement de destination, sélectionnez le groupe auquel vous voulez déplacer les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="427a5-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="427a5-159">Facultatif Si le serveur de destination ou le pool n’est pas disponible, activez la case à cocher **forcer** .</span><span class="sxs-lookup"><span data-stu-id="427a5-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="427a5-160">Si vous sélectionnez l’option **force**, le compte d’utilisateur est déplacé, mais les données utilisateur associées sont supprimées (par exemple, conférences que l’utilisateur a planifiées).</span><span class="sxs-lookup"><span data-stu-id="427a5-160">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="427a5-161">Si vous ne la sélectionnez pas, le compte et les données associées sont déplacés.</span><span class="sxs-lookup"><span data-stu-id="427a5-161">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="427a5-162">Pour déplacer des utilisateurs d’un groupe vers un autre à l’aide d’un filtre</span><span class="sxs-lookup"><span data-stu-id="427a5-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="427a5-163">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="427a5-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="427a5-164">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="427a5-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="427a5-165">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="427a5-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="427a5-166">Dans la **recherche d’utilisateur**, cliquez sur **Rechercher**, puis sur Ajouter un **filtre**.</span><span class="sxs-lookup"><span data-stu-id="427a5-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="427a5-167">Dans les critères de recherche, sélectionnez **pool de bureaux**d’enregistrement, sélectionnez **égal à**, sélectionnez **nom de domaine complet du pool actuel**, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="427a5-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="427a5-168">Dans le menu **action** , cliquez sur **déplacer tous les utilisateurs vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="427a5-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="427a5-169">Lorsque vous appliquez un filtre à un ensemble d’utilisateurs existant, l’option **déplacer tous les utilisateurs vers le pool** est dans le contexte du sous-ensemble filtré d’utilisateurs, et non de **tous** les utilisateurs possibles.</span><span class="sxs-lookup"><span data-stu-id="427a5-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="427a5-170">Dans **déplacer les utilisateurs**, sélectionnez le groupe qui contient les comptes d’utilisateurs que vous voulez déplacer dans le **pool d’inscriptions sources**.</span><span class="sxs-lookup"><span data-stu-id="427a5-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="427a5-171">Dans la **liste de bureaux**d’enregistrement de destination, sélectionnez le pool dans lequel vous voulez déplacer les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="427a5-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="427a5-172">Facultatif Si le serveur de destination ou le pool n’est pas disponible, activez la case à cocher **forcer** .</span><span class="sxs-lookup"><span data-stu-id="427a5-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="427a5-173">Si vous sélectionnez l’option **force**, le compte d’utilisateur est déplacé, mais toutes les données utilisateur associées sont supprimées (par exemple, les conférences que l’utilisateur a planifiées et les contacts).</span><span class="sxs-lookup"><span data-stu-id="427a5-173">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts).</span></span> <span data-ttu-id="427a5-174">Si vous ne la sélectionnez pas, le compte et les données associées sont déplacés.</span><span class="sxs-lookup"><span data-stu-id="427a5-174">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="427a5-175">Pour déplacer des utilisateurs d’un pool à un autre à l’aide des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="427a5-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="427a5-176">En fonction de la manière dont vous exécutez les commandes Windows PowerShell (c’est-à-dire, localement ou à distance), vous devez vous connecter en tant que membre des rôles d’administrateur de Skype entreprise Server appropriés comme suit:</span><span class="sxs-lookup"><span data-stu-id="427a5-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server administrative roles as follows:</span></span>
    
   <span data-ttu-id="427a5-177">a.</span><span class="sxs-lookup"><span data-stu-id="427a5-177">a.</span></span> <span data-ttu-id="427a5-178">Si vous exécutez les commandes sur l’ordinateur local (par exemple, si vous vous connectez directement à un serveur frontal): Connectez-vous à l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec la configuration nécessaire. droits d’utilisateur, tels que décrits dans **autorisations de configuration de délégué**.</span><span class="sxs-lookup"><span data-stu-id="427a5-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="427a5-179">b.</span><span class="sxs-lookup"><span data-stu-id="427a5-179">b.</span></span> <span data-ttu-id="427a5-180">Si vous exécutez les commandes à distance sur un autre ordinateur (par exemple, si vous ouvrez une session sur votre ordinateur et exécutez les commandes à distance sur un serveur frontal Standard Edition): à partir d’un compte d’utilisateur affecté au rôle CsUserAdministrator ou à CsAdministrator pour vous connecter à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="427a5-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="427a5-181">Démarrer Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="427a5-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="427a5-182">Pour déplacer des utilisateurs uniques, utilisez l’applet de passe Move-CsUser en procédant comme suit:</span><span class="sxs-lookup"><span data-stu-id="427a5-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="427a5-183">Lorsque l’utilisateur se déplace, c’est l’utilisateur Pilar Arès, et l’utilisateur est déplacé de sa liste de ressources personnelles actuellement affectées au pool pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="427a5-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="427a5-184">Pour déplacer un grand nombre d’utilisateurs, utilisez des filtres avec l’applet de passe **Get-Csuser** et transmettez le jeu d’utilisateurs obtenu à **Move-Csuser**:</span><span class="sxs-lookup"><span data-stu-id="427a5-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="427a5-185">Les commandes combinées de **Get-Csuser** et **Move-Csuser** peuvent être à l’origine:</span><span class="sxs-lookup"><span data-stu-id="427a5-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


