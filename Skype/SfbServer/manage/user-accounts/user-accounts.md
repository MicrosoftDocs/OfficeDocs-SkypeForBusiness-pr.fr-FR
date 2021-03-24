---
title: Gérer les comptes d’utilisateur pour Skype Entreprise Server
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
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: Les sections de cet article décrivent comment activer, désactiver temporairement ou supprimer des utilisateurs Active Directory de Skype Entreprise Server.
ms.openlocfilehash: 0cf78b4ebe7023bc5a0f1b4af75c5d9e5a45db1b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103120"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="ebc0b-103">Gérer les comptes d’utilisateur pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ebc0b-103">Manage user accounts for Skype for Business Server</span></span>

<span data-ttu-id="ebc0b-104">Les sections de cet article décrivent comment activer, désactiver temporairement ou supprimer des utilisateurs Active Directory de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>

<span data-ttu-id="ebc0b-105">Pour plus d’informations sur la façon d’activer un utilisateur Active Directory, voir [Créer un compte d’utilisateur.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="ebc0b-105">For information on how to enable an Active Directory user, see [Create a New User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11)).</span></span> <span data-ttu-id="ebc0b-106">Pour plus d’informations sur la suppression d’un utilisateur Active Directory, voir [Supprimer un compte d’utilisateur.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="ebc0b-106">For information on how to delete an Active Directory user, see [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span></span>

<span data-ttu-id="ebc0b-107">Ces procédures doivent être effectuées pendant une fenêtre de maintenance, lorsque l’utilisation de Skype Entreprise est la plus faible.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="ebc0b-108">Les besoins de votre organisation déterminent si cette planification est quotidienne ou hebdomadaire.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span>

<span data-ttu-id="ebc0b-109">Cet article contient les procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="ebc0b-109">This article contains the following procedures:</span></span>

- [<span data-ttu-id="ebc0b-110">Pour rechercher un ou plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="ebc0b-110">To search for one or more users</span></span>](user-accounts.md#Search)

- [<span data-ttu-id="ebc0b-111">Ajouter et activer un nouvel utilisateur Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ebc0b-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)

- [<span data-ttu-id="ebc0b-112">Désactiver ou réactiver un compte d’utilisateur précédemment activé pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ebc0b-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)

- [<span data-ttu-id="ebc0b-113">Désactiver un utilisateur pour une Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="ebc0b-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)

- [<span data-ttu-id="ebc0b-114">Supprimer un compte d’utilisateur avec Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="ebc0b-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="ebc0b-115">Pour rechercher un ou plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="ebc0b-115">To search for one or more users</span></span>
<span data-ttu-id="ebc0b-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="ebc0b-116"><a name="Search"> </a></span></span>

<span data-ttu-id="ebc0b-117">Vous pouvez utiliser les résultats d’une requête de recherche pour configurer les utilisateurs Active Directory pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="ebc0b-118">Vous pouvez rechercher des utilisateurs par nom d’affichage, prénom, nom de famille, nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), adresse SIP ou URI (Uniform Resource Identifier) de ligne.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="ebc0b-119">Vous pouvez rechercher des utilisateurs à l’aide du Panneau de contrôle Skype Entreprise Server ou du logiciel en ligne Utilisateurs et ordinateurs Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="ebc0b-120">La procédure suivante décrit comment utiliser le Panneau de contrôle Skype Entreprise Server pour rechercher des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>

> [!NOTE]
> <span data-ttu-id="ebc0b-121">Dans un environnement avec une topologie de forêt centrale, les résultats de la recherche peuvent ne pas être précis lorsque vous recherchez un utilisateur par son adresse de messagerie.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="ebc0b-122">Au lieu de cela, vous pouvez rechercher des utilisateurs en spécifiant un préfixe d’adresse SIP, par exemple sip:name, ajouter un filtre de recherche et sélectionner une adresse SIP qui contient une adresse de messagerie partielle, ou utiliser l'; </span><span class="sxs-lookup"><span data-stu-id="ebc0b-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>

1. <span data-ttu-id="ebc0b-123">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="ebc0b-124">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="ebc0b-125">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-125">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="ebc0b-126">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5. <span data-ttu-id="ebc0b-127">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="ebc0b-127">(Optional) Specify additional search criteria to narrow the results:</span></span>

   <span data-ttu-id="ebc0b-128">a.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-128">a.</span></span> <span data-ttu-id="ebc0b-129">Cliquez sur la flèche déroulante située en haut à droite de l’écran, au-dessus **Résultats de la recherche**, puis sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>

   <span data-ttu-id="ebc0b-130">b.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-130">b.</span></span> <span data-ttu-id="ebc0b-131">Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>

   <span data-ttu-id="ebc0b-132">c.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-132">c.</span></span> <span data-ttu-id="ebc0b-133">Dans la liste déroulante **Égal à**, cliquez sur **Égal à** ou **Pas égal à**.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>

   <span data-ttu-id="ebc0b-134">d.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-134">d.</span></span> <span data-ttu-id="ebc0b-135">Dans la zone de texte, tapez le critère de recherche selon lequel filtrer les résultats, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6. <span data-ttu-id="ebc0b-p110">les résultats de la recherche apparaissent sous **Résultats de la recherche**. Sélectionnez dans la liste les utilisateurs sur lesquels vous voulez exécuter les tâches de configuration.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-p110">The search results appear under **Search Results**. You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="ebc0b-138">Ajouter et activer un nouvel utilisateur Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ebc0b-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="ebc0b-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="ebc0b-139"><a name="Add"> </a></span></span>

<span data-ttu-id="ebc0b-140">Après avoir activé un compte d’utilisateur dans Utilisateurs et ordinateurs Active Directory, vous pouvez utiliser le Panneau de contrôle Skype Entreprise Server pour créer et activer de nouveaux comptes d’utilisateur Skype Entreprise Server en ajoutant un utilisateur Active Directory à Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>

<span data-ttu-id="ebc0b-141">Vous pouvez également utiliser une cmdlet, en particulier [Enable-CsUser](/powershell/module/skype/enable-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="ebc0b-141">You can also use a cmdlet, specifically [Enable-CsUser](/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>

1. <span data-ttu-id="ebc0b-142">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="ebc0b-143">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="ebc0b-144">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-144">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="ebc0b-145">Cliquez sur **Activer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-145">Click **Enable users**.</span></span>

5. <span data-ttu-id="ebc0b-146">Dans la boîte de dialogue **Nouvel utilisateur Lync Server**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-146">On the **New Lync Server User** dialog, click **Add**.</span></span>

6. <span data-ttu-id="ebc0b-147">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom, du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse e-mail, du nom d’utilisateur principal ou le numéro de téléphone du compte d’utilisateur Active Directory souhaité, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7. <span data-ttu-id="ebc0b-148">Dans le tableau, sélectionnez le compte que vous souhaitez ajouter à Skype Entreprise Server, puis cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="ebc0b-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>

8. <span data-ttu-id="ebc0b-149">Affectez l’utilisateur à un pool, indiquez d’autres détails utiles et affectez les stratégies à l’utilisateur voulu, puis cliquez sur **Activer**.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="ebc0b-150">Désactiver ou réactiver un compte d’utilisateur précédemment activé pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ebc0b-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="ebc0b-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="ebc0b-151"><a name="Disable"> </a></span></span>

<span data-ttu-id="ebc0b-152">Vous pouvez utiliser la procédure suivante pour désactiver un compte d’utilisateur précédemment activé dans Skype Entreprise Server sans perdre les paramètres Skype Entreprise Server que vous avez configurés pour le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="ebc0b-153">Étant donné que vous ne perdez pas les paramètres du compte d’utilisateur Skype Entreprise Server, vous pouvez ré-activer un compte d’utilisateur précédemment activé sans avoir à reconfigurer le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

1. <span data-ttu-id="ebc0b-154">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="ebc0b-155">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="ebc0b-156">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-156">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="ebc0b-157">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez désactiver ou réactiver, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="ebc0b-158">Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez désactiver ou réactiver.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-158">In the table, click the user account that you want to disable or re-enable.</span></span>

6. <span data-ttu-id="ebc0b-159">Dans le menu **Action**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="ebc0b-159">On the **Action** menu, do one of the following:</span></span>

   - <span data-ttu-id="ebc0b-160">Pour désactiver temporairement le compte d’utilisateur pour Skype Entreprise Server, cliquez sur Désactiver temporairement **pour Lync Server.**</span><span class="sxs-lookup"><span data-stu-id="ebc0b-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>

   - <span data-ttu-id="ebc0b-161">Pour activer le compte d’utilisateur pour Skype Entreprise Server, cliquez sur **Ré-activer pour Lync Server.**</span><span class="sxs-lookup"><span data-stu-id="ebc0b-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="ebc0b-162">Utiliser Windows Powershell pour désactiver ou réactiver des comptes d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="ebc0b-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="ebc0b-163">Les comptes d’utilisateurs peuvent être temporairement désactivés, puis  réactivés par la suite, à l’aide de l';</span><span class="sxs-lookup"><span data-stu-id="ebc0b-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="ebc0b-164">Vous pouvez exécuter cette cmdlet à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ebc0b-165">Pour plus d’informations sur l’utilisation des Windows PowerShell distantes pour se connecter à Skype Entreprise Server, consultez l’article de blog « Démarrage rapide : Gestion [de Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="ebc0b-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="ebc0b-166">Le processus est le même dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-166">The process is the same in Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account"></a><span data-ttu-id="ebc0b-167">Pour désactiver un compte d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="ebc0b-167">To disable a user account</span></span>

- <span data-ttu-id="ebc0b-168">Pour désactiver temporairement un compte d’utilisateur, définissez la valeur de la propriété Enabled sur False ($False).</span><span class="sxs-lookup"><span data-stu-id="ebc0b-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="ebc0b-169">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="ebc0b-169">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="ebc0b-170">Pour ré-activer un compte d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="ebc0b-170">To re-enable a user account</span></span>

- <span data-ttu-id="ebc0b-171">Pour réactiver un compte d’utilisateur désactivé, définissez la valeur de la propriété Enabled sur True ($True).</span><span class="sxs-lookup"><span data-stu-id="ebc0b-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="ebc0b-172">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="ebc0b-172">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="ebc0b-173">Pour plus d’informations, consultez la rubrique d’aide de [l';Set-CsUser.](/powershell/module/skype/set-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ebc0b-173">For more information, see the help topic for the [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="ebc0b-174">Désactiver un utilisateur pour une Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="ebc0b-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="ebc0b-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="ebc0b-175"><a name="Disable_EV"> </a></span></span>

<span data-ttu-id="ebc0b-176">Utilisez la procédure suivante pour désactiver Voix Entreprise pour un compte d’utilisateur activé pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="ebc0b-177">Pour désactiver un compte d’utilisateur pour Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="ebc0b-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="ebc0b-178">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="ebc0b-179">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="ebc0b-180">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-180">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="ebc0b-181">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5. <span data-ttu-id="ebc0b-182">Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez activer pour Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6. <span data-ttu-id="ebc0b-183">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-183">On the **Edit** menu, click **Show details**.</span></span>

7. <span data-ttu-id="ebc0b-184">Dans la page **Modifier l’utilisateur Lync Server**, sous **Téléphonie**, cliquez sur l’option de votre choix à l’exception de **Voix Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ebc0b-185">Pour empêcher un utilisateur d’effectuer des appels audio ou vidéo à l’aide de Lync, sous **Téléphonie,** cliquez sur **Audio/Vidéo désactivé.**</span><span class="sxs-lookup"><span data-stu-id="ebc0b-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span>

8. <span data-ttu-id="ebc0b-186">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-186">Click **Commit**.</span></span>

<span data-ttu-id="ebc0b-187">L’utilisateur ne peut désormais pas utiliser la fonctionnalité Voix Entreprise’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="ebc0b-188">Informations connexes :</span><span class="sxs-lookup"><span data-stu-id="ebc0b-188">Related information:</span></span> <br/>[<span data-ttu-id="ebc0b-189">Voix Entreprise mobilité</span><span class="sxs-lookup"><span data-stu-id="ebc0b-189">Enterprise Voice and mobility</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-managing-enterprise-voice-for-users)<br/> [<span data-ttu-id="ebc0b-190">Activer les utilisateurs Voix Entreprise dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ebc0b-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="ebc0b-191">Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="ebc0b-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="ebc0b-192">Supprimer un compte d’utilisateur avec Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="ebc0b-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="ebc0b-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="ebc0b-193"><a name="Remove"> </a></span></span>

<span data-ttu-id="ebc0b-194">Vous pouvez utiliser la procédure suivante pour supprimer un compte d’utilisateur précédemment ajouté dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="ebc0b-195">La suppression d’un utilisateur entraînera la perte de tous les paramètres associés au compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="ebc0b-196">Si vous souhaitez désactiver temporairement un compte d’utilisateur à la place, consultez Désactiver ou [réactiver](user-accounts.md#Disable)un compte d’utilisateur précédemment activé pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span>

1. <span data-ttu-id="ebc0b-197">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="ebc0b-198">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="ebc0b-199">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-199">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="ebc0b-200">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez désactiver ou réactiver, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="ebc0b-201">Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-201">In the table, click the user account that you want to remove.</span></span>

6. <span data-ttu-id="ebc0b-202">Dans le menu **Action**, sélectionnez **Supprimer de Lync Server** et une boîte de dialogue apparaît.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7. <span data-ttu-id="ebc0b-203">Dans la boîte de dialogue, sélectionnez **OK** pour supprimer l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-203">From the dialog box, select **OK** to remove the user.</span></span>

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="ebc0b-204">Supprimer des comptes d’utilisateurs avec des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ebc0b-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="ebc0b-205">Vous pouvez supprimer des comptes d’utilisateurs à l’aide Disable-CsUser cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="ebc0b-206">Cette cmdlet peut être exécuté à partir de Skype Entreprise Server Management Shell ou d’une session distante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="ebc0b-207">Pour plus d’informations sur l’utilisation des Windows PowerShell distantes pour se connecter à Skype Entreprise Server, consultez l’article de blog « Démarrage rapide : Gestion [de Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="ebc0b-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="ebc0b-208">Le processus est le même dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-208">The process is the same in Skype for Business Server.</span></span>

### <a name="to-remove-a-user-account"></a><span data-ttu-id="ebc0b-209">Pour supprimer un compte d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="ebc0b-209">To remove a user account</span></span>
<span data-ttu-id="ebc0b-210">Pour supprimer un compte d’utilisateur, utilisez l’applet de commande Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="ebc0b-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="ebc0b-211">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="ebc0b-211">For example:</span></span>

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

<span data-ttu-id="ebc0b-212">Pour plus d’informations, consultez la rubrique d’aide de l';cmdlet [Disable-CsUser.](/powershell/module/skype/disable-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ebc0b-212">For more information, see the help topic for the [Disable-CsUser](/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="ebc0b-213">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ebc0b-213">See also</span></span>
<span data-ttu-id="ebc0b-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="ebc0b-214"><a name="Remove"> </a></span></span>

[<span data-ttu-id="ebc0b-215">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="ebc0b-215">Enable-CsUser</span></span>](/powershell/module/skype/enable-csuser?view=skype-ps)

[<span data-ttu-id="ebc0b-216">Disable-CsUser</span><span class="sxs-lookup"><span data-stu-id="ebc0b-216">Disable-CsUser</span></span>](/powershell/module/skype/disable-csuser?view=skype-ps)