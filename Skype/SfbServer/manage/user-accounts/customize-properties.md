---
title: Personnaliser les propriétés de compte d’utilisateur pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Les procédures dans cette section vous permettent de modifier les propriétés de chaque compte d’utilisateur.
ms.openlocfilehash: 6f2c3a76f9047da0a5d78695518cfb8355ab82e3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826264"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a><span data-ttu-id="45259-103">Personnaliser les propriétés de compte d’utilisateur pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="45259-103">Customize user account properties for Skype for Business Server</span></span>
 
<span data-ttu-id="45259-104">Les procédures dans cette section vous permettent de modifier les propriétés de chaque compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="45259-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="45259-105">Deux opérations de base peuvent être réalisées au niveau de l’utilisateur individuel :</span><span class="sxs-lookup"><span data-stu-id="45259-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="45259-106">Configurer les options de téléphonie pour un compte d’utilisateur spécifique</span><span class="sxs-lookup"><span data-stu-id="45259-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="45259-107">Déplacer des utilisateurs vers un autre pool</span><span class="sxs-lookup"><span data-stu-id="45259-107">Move users to another pool</span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="45259-108">Configurer les options de téléphonie pour un compte d’utilisateur spécifique</span><span class="sxs-lookup"><span data-stu-id="45259-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="45259-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="45259-109"><a name="Tel_Op"> </a></span></span>

<span data-ttu-id="45259-110">Vous pouvez personnaliser les paramètres téléphoniques d’un utilisateur spécifique (tant que l’utilisateur individuel a été activé pour Skype Entreprise Server et que l’organisation prend en charge la téléphonie).</span><span class="sxs-lookup"><span data-stu-id="45259-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server and the organization supports telephony).</span></span>
  
<span data-ttu-id="45259-111">Les options de téléphonie utilisateur Skype Entreprise Server sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="45259-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="45259-112">**Audio/vidéo désactivé** L’utilisateur ne peut pas effectuer d’appels avec l’audio et la vidéo.</span><span class="sxs-lookup"><span data-stu-id="45259-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="45259-113">**PC à PC uniquement** L’utilisateur peut uniquement effectuer des appels audio ou vidéo de PC à PC.</span><span class="sxs-lookup"><span data-stu-id="45259-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="45259-114">**Voix Entreprise** L’utilisateur peut utiliser l’infrastructure Skype Entreprise Server pour router tous les appels entrants et sortants.</span><span class="sxs-lookup"><span data-stu-id="45259-114">**Enterprise Voice** The user can use the Skype for Business Server infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="45259-115">L’utilisateur peut aussi effectuer des appels de PC à PC.</span><span class="sxs-lookup"><span data-stu-id="45259-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="45259-116">**Contrôle d’appel distant** L’utilisateur peut utiliser Skype Entreprise Server pour contrôler le téléphone de bureau et peut également effectuer des appels de PC à PC.</span><span class="sxs-lookup"><span data-stu-id="45259-116">**Remote call control** The user can use Skype for Business Server to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="45259-117">Pour plus d’informations sur la configuration de la téléphonie pour une organisation, voir Enable [users for Voix Entreprise in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and Deploy Voix Entreprise in Skype for Business Server [in](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) the Deployment documentation.</span><span class="sxs-lookup"><span data-stu-id="45259-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="45259-118">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="45259-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="45259-119">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="45259-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="45259-120">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="45259-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="45259-121">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur souhaité, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="45259-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="45259-122">Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="45259-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="45259-123">Dans le menu **Edition**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="45259-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="45259-124">Dans **Téléphonie**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="45259-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="45259-125">Pour désactiver les appels audio et vidéo pour l’utilisateur, cliquez sur **Audio/vidéo désactivé**.</span><span class="sxs-lookup"><span data-stu-id="45259-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="45259-p102">Pour activer les communications audio de PC à PC pour l’utilisateur, mais pas le contrôle d’appel distant ou Voix Entreprise, cliquez sur **De PC à PC uniquement**. Spécifiez une valeur d’**URI de ligne** pour le téléphone dont se sert l’utilisateur pour les communications audio de PC à PC.</span><span class="sxs-lookup"><span data-stu-id="45259-p102">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**. Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="45259-128">Pour router les appels téléphoniques de l’utilisateur à l’aide de l’infrastructure Skype Entreprise conformément à la classe de stratégie de service, y compris la communication audio de PC à PC, cliquez sur **Voix Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="45259-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="45259-129">Dans **URI de ligne**, spécifiez le numéro de téléphone pour Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="45259-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="45259-130">Dans **Stratégie de plan de numérotation** et **Stratégie de la voix**, spécifiez les stratégies appropriées pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="45259-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="45259-131">Afin de spécifier des règles de normalisation pour la traduction des numéros de téléphone composés par l’utilisateur au format E.164, sélectionnez le profil d’emplacement approprié dans **Stratégie d’emplacement**.</span><span class="sxs-lookup"><span data-stu-id="45259-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="45259-132">Pour activer le contrôle d’appel distant, qui permet aux utilisateurs de contrôler leur ligne téléphonique de bureau à partir de Skype Entreprise Server pour effectuer des appels de PC à PC et des appels de PC à téléphone, cliquez sur Contrôle d’appel **distant.**</span><span class="sxs-lookup"><span data-stu-id="45259-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="45259-133">Dans **URI de ligne**, spécifiez le numéro de téléphone pour le contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="45259-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="45259-134">L’utilisateur doit disposer d’un téléphone de bureau et d’une connexion d’autocommutateur privé (PBX) pour le routage des appels.</span><span class="sxs-lookup"><span data-stu-id="45259-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="45259-135">Déplacer des utilisateurs vers un autre pool</span><span class="sxs-lookup"><span data-stu-id="45259-135">Move users to another pool</span></span>
<span data-ttu-id="45259-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="45259-136"><a name="Move_Users"> </a></span></span>

<span data-ttu-id="45259-137">Vous pouvez utiliser le Panneau de contrôle Skype Entreprise Server pour affecter des utilisateurs à un serveur ou pool spécifique.</span><span class="sxs-lookup"><span data-stu-id="45259-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="45259-138">Le déplacement de tous les utilisateurs existants d’un pool source exécutant Lync Server 2010 ou une antérieure vers un pool de destination Skype Entreprise Server dans un environnement Active Directory complexe peut entraîner une réplication Active Directory plus lente.</span><span class="sxs-lookup"><span data-stu-id="45259-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="45259-139">Pour éviter cela, vous pouvez utiliser des filtres de recherche pour déplacer séparément des utilisateurs de pools exécutant Lync Server 2010 ou une antérieure, ou utiliser Skype Entreprise Server Management Shell pour déplacer des utilisateurs avec des cmdlets.</span><span class="sxs-lookup"><span data-stu-id="45259-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="45259-140">En outre, la fonctionnalité de filtrage fonctionne avec les utilisateurs de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="45259-140">Also, the filter functionality works with Skype for Business Server users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="45259-141">Pour déplacer les utilisateurs sélectionnés vers un autre serveur ou pool</span><span class="sxs-lookup"><span data-stu-id="45259-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="45259-142">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="45259-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="45259-143">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="45259-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="45259-144">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="45259-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="45259-145">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur souhaité, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="45259-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="45259-146">Dans le tableau, sélectionnez un ou plusieurs utilisateurs dans la liste.</span><span class="sxs-lookup"><span data-stu-id="45259-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="45259-147">Dans le menu **Action**, cliquez sur **Déplacer les utilisateurs sélectionnés vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="45259-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="45259-148">Dans **Déplacer des utilisateurs**, sélectionnez dans le champ **Pool de serveurs d’inscriptions de destination** le pool vers lequel vous souhaitez déplacer les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="45259-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="45259-149">(Optionnel) Si le serveur ou pool de destination n’est pas disponible, activez la case à cocher **Forcer**.</span><span class="sxs-lookup"><span data-stu-id="45259-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="45259-p106">Si vous activez la case à cocher **Forcer**, le compte d’utilisateur est déplacé, mais toutes les données associées sont supprimées (par exemple, les conférences planifiées par l’utilisateur). Si vous n’activez pas cette case à cocher, le compte et les données associées sont déplacés.</span><span class="sxs-lookup"><span data-stu-id="45259-p106">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled). If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="45259-152">Pour déplacer tous les utilisateurs d’un seul serveur ou pool vers un autre serveur ou pool</span><span class="sxs-lookup"><span data-stu-id="45259-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="45259-153">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="45259-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="45259-154">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="45259-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="45259-155">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="45259-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="45259-156">Dans le menu **Action**, cliquez sur **Déplacer tous les utilisateurs vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="45259-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="45259-157">Dans **Déplacer des utilisateurs**, sélectionnez le pool contenant les comptes d’utilisateurs que vous souhaitez déplacer à l’aide de l’option **Pool de serveurs d’inscriptions source**.</span><span class="sxs-lookup"><span data-stu-id="45259-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="45259-158">Dans **Pool de serveurs d’inscriptions de destination**, sélectionnez le pool vers lequel vous souhaitez déplacer les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="45259-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="45259-159">(Optionnel) Si le serveur ou pool de destination n’est pas disponible, activez la case à cocher **Forcer**.</span><span class="sxs-lookup"><span data-stu-id="45259-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="45259-p107">Si vous activez la case à cocher **Forcer**, le compte d’utilisateur est déplacé, mais toutes les données associées sont supprimées (par exemple, les conférences planifiées par l’utilisateur). Si vous n’activez pas cette case à cocher, le compte et les données associées sont déplacés.</span><span class="sxs-lookup"><span data-stu-id="45259-p107">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled). If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="45259-162">Pour déplacer des utilisateurs d’un pool vers un autre pool à l’aide d’un filtre</span><span class="sxs-lookup"><span data-stu-id="45259-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="45259-163">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="45259-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="45259-164">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="45259-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="45259-165">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="45259-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="45259-166">Dans **la recherche d’utilisateur,** cliquez **sur Rechercher,** puis sur **Ajouter un filtre.**</span><span class="sxs-lookup"><span data-stu-id="45259-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="45259-167">Dans les critères de recherche, sélectionnez **Pool de serveurs d’inscriptions**, **Égal à**, **Nom de domaine complet du pool actuel**, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="45259-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="45259-168">Dans le menu **Action**, cliquez sur **Déplacer tous les utilisateurs vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="45259-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="45259-169">Lorsqu’un filtre est appliqué à un ensemble d’utilisateurs existant, l’option **Déplacer tous les utilisateurs vers le pool** s’applique au sous-ensemble filtré des utilisateurs, et non à **tous** les utilisateurs possibles.</span><span class="sxs-lookup"><span data-stu-id="45259-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="45259-170">Dans **Déplacer des utilisateurs**, sélectionnez le pool contenant les comptes d’utilisateur que vous souhaitez déplacer à l’aide de l’option **Pool de serveurs d’inscriptions source**.</span><span class="sxs-lookup"><span data-stu-id="45259-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="45259-171">Dans **Pool de serveurs d’inscriptions de destination**, sélectionnez le pool vers lequel vous souhaitez déplacer les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="45259-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="45259-172">(Optionnel) Si le serveur ou pool de destination n’est pas disponible, activez la case à cocher **Forcer**.</span><span class="sxs-lookup"><span data-stu-id="45259-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="45259-p108">Si vous activez la case à cocher **Forcer**, le compte d’utilisateur est déplacé, mais toutes les données associées sont supprimées (par exemple, les conférences planifiées par l’utilisateur et les contacts). Si vous n’activez pas cette case à cocher, le compte et les données associées sont déplacés.</span><span class="sxs-lookup"><span data-stu-id="45259-p108">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts). If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="45259-175">Pour déplacer des utilisateurs d’un pool vers un autre à l’aide des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="45259-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="45259-176">Selon la façon dont vous exécutez les commandes Windows PowerShell (localement ou à distance), vous devez vous connecter en tant que membre des rôles d’administration Skype Entreprise Server corrects comme suit :</span><span class="sxs-lookup"><span data-stu-id="45259-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server administrative roles as follows:</span></span>
    
   <span data-ttu-id="45259-177">a.</span><span class="sxs-lookup"><span data-stu-id="45259-177">a.</span></span> <span data-ttu-id="45259-178">Si vous exécutez les commandes sur l’ordinateur local (par exemple, vous vous connectez directement à un serveur frontal) : connectez-vous à l’ordinateur sur lequel Skype Entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans déléguer les **autorisations** d’installation.</span><span class="sxs-lookup"><span data-stu-id="45259-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="45259-179">b.</span><span class="sxs-lookup"><span data-stu-id="45259-179">b.</span></span> <span data-ttu-id="45259-180">Si vous exécutez les commandes à distance sur un autre ordinateur (par exemple, vous vous connectez à votre ordinateur et exécutez les commandes à distance sur un serveur frontal Standard Edition) : à partir d’un compte d’utilisateur affecté au rôle CsUserAdministrator ou au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="45259-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="45259-181">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype** Entreprise, puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="45259-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="45259-182">Pour déplacer des utilisateurs individuels, utilisez la cmdlet Move-CsUser comme suit :</span><span class="sxs-lookup"><span data-stu-id="45259-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="45259-183">Où l’utilisateur à déplacer est Pilar Ackerman, lequel sera déplacé depuis le pool d’accueil qui lui est actuellement affecté vers le pool pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="45259-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="45259-184">Pour déplacer un grand nombre d’utilisateurs, utilisez des filtres avec la cmdlet **Get-CsUser** et passez l’ensemble d’utilisateurs obtenu à **Move-CsUser** :</span><span class="sxs-lookup"><span data-stu-id="45259-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="45259-185">Les commandes associées de **Get-CsUser** et de **Move-CsUser** peuvent aboutir au résultat suivant :</span><span class="sxs-lookup"><span data-stu-id="45259-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


