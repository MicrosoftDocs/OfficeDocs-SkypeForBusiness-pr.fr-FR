---
title: Gérer les comptes d’utilisateurs pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: Les sections de cet article décrivent l’activation, la désactivation temporaire ou la suppression d’utilisateurs Active Directory de Skype entreprise Server.
ms.openlocfilehash: 33af0305fe25b9d7a272e89ae196923e97c4cfd3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817054"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="f808c-103">Gérer les comptes d’utilisateurs pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="f808c-103">Manage user accounts for Skype for Business Server</span></span>

<span data-ttu-id="f808c-104">Les sections de cet article décrivent l’activation, la désactivation temporaire ou la suppression d’utilisateurs Active Directory de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f808c-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>

<span data-ttu-id="f808c-105">Pour plus d’informations sur l’activation d’un utilisateur Active Directory, voir [créer un compte d’utilisateur](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="f808c-105">For information on how to enable an Active Directory user, see [Create a New User Account](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span></span> <span data-ttu-id="f808c-106">Pour plus d’informations sur la suppression d’un utilisateur Active Directory, voir [supprimer un compte d’utilisateur](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="f808c-106">For information on how to delete an Active Directory user, see [Delete a User Account](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span></span>

<span data-ttu-id="f808c-107">Ces procédures doivent être effectuées au cours d’une fenêtre de maintenance, lorsque le niveau d’utilisation de Skype entreprise est inférieur.</span><span class="sxs-lookup"><span data-stu-id="f808c-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="f808c-108">Le mode de planification quotidienne ou hebdomadaire sera déterminé selon les besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f808c-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span>

<span data-ttu-id="f808c-109">Cet article contient les procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="f808c-109">This article contains the following procedures:</span></span>

- [<span data-ttu-id="f808c-110">Pour rechercher un ou plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="f808c-110">To search for one or more users</span></span>](user-accounts.md#Search)

- [<span data-ttu-id="f808c-111">Ajout et activation d’un nouvel utilisateur de Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="f808c-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)

- [<span data-ttu-id="f808c-112">Désactivation ou réactivation d’un compte d’utilisateur précédemment activé pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="f808c-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)

- [<span data-ttu-id="f808c-113">Désactiver un utilisateur pour voix entreprise</span><span class="sxs-lookup"><span data-stu-id="f808c-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)

- [<span data-ttu-id="f808c-114">Supprimer un compte d’utilisateur avec Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="f808c-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="f808c-115">Pour rechercher un ou plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="f808c-115">To search for one or more users</span></span>
<span data-ttu-id="f808c-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="f808c-116"><a name="Search"> </a></span></span>

<span data-ttu-id="f808c-117">Vous pouvez utiliser les résultats d’une requête de recherche pour configurer les utilisateurs Active Directory pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f808c-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="f808c-118">Vous pouvez rechercher des utilisateurs par nom d’affichage, prénom, nom de famille, nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), adresse SIP ou URI (Uniform Resource Identifier) de ligne.</span><span class="sxs-lookup"><span data-stu-id="f808c-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="f808c-119">Vous pouvez rechercher des utilisateurs à l’aide du panneau de configuration Skype entreprise Server ou du composant logiciel enfichable utilisateurs et ordinateurs Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f808c-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="f808c-120">La procédure suivante vous explique comment utiliser le panneau de configuration Skype entreprise Server pour rechercher des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f808c-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>

> [!NOTE]
> <span data-ttu-id="f808c-121">Dans un environnement doté d’une topologie de forêt centrale, il est possible que les résultats de la recherche soient inexacts lorsque vous recherchez un utilisateur à l’aide de son adresse de messagerie.</span><span class="sxs-lookup"><span data-stu-id="f808c-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="f808c-122">Au lieu de cela, vous pouvez rechercher des utilisateurs en spécifiant un préfixe d’adresse SIP (par exemple, SIP : nom), ajouter un filtre de recherche et sélectionner une adresse SIP contenant une adresse de messagerie partielle ou utiliser l’applet de requête **Get-Csuser** .</span><span class="sxs-lookup"><span data-stu-id="f808c-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>

1. <span data-ttu-id="f808c-123">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f808c-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="f808c-124">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f808c-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="f808c-125">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="f808c-125">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="f808c-126">Dans la boîte de **recherche utilisateurs** , entrez tout ou la première partie du nom d’affichage, prénom, nom, nom de compte Sam, adresse SIP ou URI de ligne du compte d’utilisateur que vous souhaitez rechercher, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="f808c-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5. <span data-ttu-id="f808c-127">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="f808c-127">(Optional) Specify additional search criteria to narrow the results:</span></span>

   <span data-ttu-id="f808c-128">a.</span><span class="sxs-lookup"><span data-stu-id="f808c-128">a.</span></span> <span data-ttu-id="f808c-129">Cliquez sur la flèche de développement située dans le coin supérieur droit de l’écran au-dessus des résultats de la **recherche**, puis cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="f808c-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>

   <span data-ttu-id="f808c-130">b.</span><span class="sxs-lookup"><span data-stu-id="f808c-130">b.</span></span> <span data-ttu-id="f808c-131">Entrez la propriété User en le tapant ou en cliquant sur la flèche dans la liste déroulante pour sélectionner une propriété d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f808c-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>

   <span data-ttu-id="f808c-132">c.</span><span class="sxs-lookup"><span data-stu-id="f808c-132">c.</span></span> <span data-ttu-id="f808c-133">Dans la liste **égal à** , cliquez sur **égal à** ou **n’est pas égal à**.</span><span class="sxs-lookup"><span data-stu-id="f808c-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>

   <span data-ttu-id="f808c-134">d.</span><span class="sxs-lookup"><span data-stu-id="f808c-134">d.</span></span> <span data-ttu-id="f808c-135">Dans la zone de texte, tapez les critères de recherche que vous voulez utiliser pour filtrer les résultats de recherche, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="f808c-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6. <span data-ttu-id="f808c-136">Les résultats de la recherche apparaissent sous résultats de la **recherche**.</span><span class="sxs-lookup"><span data-stu-id="f808c-136">The search results appear under **Search Results**.</span></span> <span data-ttu-id="f808c-137">Vous pouvez sélectionner tout ou partie des utilisateurs de la liste et effectuer des tâches de configuration pour les utilisateurs sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="f808c-137">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="f808c-138">Ajout et activation d’un nouvel utilisateur de Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="f808c-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="f808c-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="f808c-139"><a name="Add"> </a></span></span>

<span data-ttu-id="f808c-140">Après avoir activé un compte d’utilisateur dans utilisateurs et ordinateurs Active Directory, vous pouvez utiliser le panneau de configuration Skype entreprise Server pour créer et activer les nouveaux comptes d’utilisateurs Skype entreprise Server en ajoutant un utilisateur Active Directory à Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f808c-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>

<span data-ttu-id="f808c-141">Vous pouvez également utiliser une applet de cmdlet, en particulier [Enable-Csuser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f808c-141">You can also use a cmdlet, specifically [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>

1. <span data-ttu-id="f808c-142">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f808c-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="f808c-143">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f808c-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="f808c-144">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="f808c-144">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="f808c-145">Cliquez sur **activer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="f808c-145">Click **Enable users**.</span></span>

5. <span data-ttu-id="f808c-146">Dans la boîte de dialogue **nouveau serveur Lync** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f808c-146">On the **New Lync Server User** dialog, click **Add**.</span></span>

6. <span data-ttu-id="f808c-147">Dans la boîte de dialogue **Rechercher des utilisateurs** , tapez tout ou la première partie du nom, le nom d’affichage, le prénom, le nom, le nom du compte Sam (Security Accounts Manager), l’adresse de messagerie, le nom d’utilisateur principal (UPN) ou le numéro de téléphone du compte d’utilisateur Active Directory souhaité, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="f808c-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7. <span data-ttu-id="f808c-148">Dans le tableau, sélectionnez le compte que vous voulez ajouter à Skype entreprise Server, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f808c-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>

8. <span data-ttu-id="f808c-149">Affectez l’utilisateur à un pool, spécifiez des détails supplémentaires et attribuez les stratégies à l’utilisateur de votre choix, puis cliquez sur **activer**.</span><span class="sxs-lookup"><span data-stu-id="f808c-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="f808c-150">Désactivation ou réactivation d’un compte d’utilisateur précédemment activé pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="f808c-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="f808c-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="f808c-151"><a name="Disable"> </a></span></span>

<span data-ttu-id="f808c-152">Vous pouvez utiliser la procédure suivante pour désactiver un compte d’utilisateur déjà activé dans Skype entreprise Server sans perdre les paramètres de Skype entreprise Server que vous avez configurés pour le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f808c-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="f808c-153">Étant donné que vous ne perdez pas les paramètres de compte d’utilisateur Skype entreprise Server, vous pouvez réactiver un compte d’utilisateur déjà activé sans avoir à reconfigurer le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f808c-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

1. <span data-ttu-id="f808c-154">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f808c-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="f808c-155">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f808c-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="f808c-156">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="f808c-156">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="f808c-157">Dans la boîte de dialogue **Rechercher des utilisateurs** , tapez tout ou la première partie du nom complet, prénom, nom, nom du compte de comptes de sécurité (Sam), adresse SIP ou URI (Uniform Resource Identifier) du compte d’utilisateur que vous souhaitez désactiver ou réactiver, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="f808c-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="f808c-158">Dans la table, cliquez sur le compte d’utilisateur que vous souhaitez désactiver ou réactiver.</span><span class="sxs-lookup"><span data-stu-id="f808c-158">In the table, click the user account that you want to disable or re-enable.</span></span>

6. <span data-ttu-id="f808c-159">Dans le menu **action** , effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f808c-159">On the **Action** menu, do one of the following:</span></span>

   - <span data-ttu-id="f808c-160">Pour désactiver temporairement le compte d’utilisateur Skype entreprise Server, cliquez sur **désactiver temporairement pour Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f808c-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>

   - <span data-ttu-id="f808c-161">Pour activer le compte d’utilisateur Skype entreprise Server, cliquez sur **réactiver pour Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f808c-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="f808c-162">Utiliser Windows PowerShell pour désactiver ou réactiver les comptes d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="f808c-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="f808c-163">Pour désactiver temporairement les comptes d’utilisateurs, vous pouvez les réactiver ultérieurement à l’aide de l’applet de dialogue **Set-Csuser** .</span><span class="sxs-lookup"><span data-stu-id="f808c-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="f808c-164">Vous pouvez exécuter cette applet de commande à partir de Skype entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f808c-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f808c-165">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype entreprise Server, voir l’article sur le blog [« démarrage rapide : gestion de Microsoft Lync Server 2010 à l’aide de Remote PowerShell »](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="f808c-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="f808c-166">Le processus est le même dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f808c-166">The process is the same in Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account"></a><span data-ttu-id="f808c-167">Pour désactiver un compte d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="f808c-167">To disable a user account</span></span>

- <span data-ttu-id="f808c-168">Pour désactiver temporairement un compte d’utilisateur, définissez la valeur de la propriété Enabled sur false ($False).</span><span class="sxs-lookup"><span data-stu-id="f808c-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="f808c-169">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f808c-169">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="f808c-170">Pour réactiver un compte d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="f808c-170">To re-enable a user account</span></span>

- <span data-ttu-id="f808c-171">Pour réactiver un compte d’utilisateur désactivé, définissez la valeur de la propriété Enabled sur true ($True).</span><span class="sxs-lookup"><span data-stu-id="f808c-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="f808c-172">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f808c-172">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="f808c-173">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Set-Csuser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f808c-173">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="f808c-174">Désactiver un utilisateur pour voix entreprise</span><span class="sxs-lookup"><span data-stu-id="f808c-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="f808c-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="f808c-175"><a name="Disable_EV"> </a></span></span>

<span data-ttu-id="f808c-176">Utilisez la procédure suivante pour désactiver Enterprise Voice pour un compte d’utilisateur activé pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f808c-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="f808c-177">Pour désactiver un compte d’utilisateur pour voix entreprise</span><span class="sxs-lookup"><span data-stu-id="f808c-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="f808c-178">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f808c-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="f808c-179">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f808c-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="f808c-180">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="f808c-180">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="f808c-181">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager), de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur à activer, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="f808c-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5. <span data-ttu-id="f808c-182">Dans la table, cliquez sur le compte d’utilisateur que vous souhaitez activer pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="f808c-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6. <span data-ttu-id="f808c-183">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="f808c-183">On the **Edit** menu, click **Show details**.</span></span>

7. <span data-ttu-id="f808c-184">Dans la page **modifier l’utilisateur de Lync Server** , sous **téléphonie**, cliquez sur une option sauf **entreprise voix**.</span><span class="sxs-lookup"><span data-stu-id="f808c-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f808c-185">Pour empêcher un utilisateur de passer des appels audio ou vidéo à l’aide de Lync, sous **téléphonie**, cliquez sur **audio/vidéo désactivé**.</span><span class="sxs-lookup"><span data-stu-id="f808c-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span>

8. <span data-ttu-id="f808c-186">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="f808c-186">Click **Commit**.</span></span>

<span data-ttu-id="f808c-187">L’utilisateur ne peut plus utiliser la fonctionnalité voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="f808c-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="f808c-188">Informations connexes :</span><span class="sxs-lookup"><span data-stu-id="f808c-188">Related information:</span></span> <br/>[<span data-ttu-id="f808c-189">Voix et mobilité entreprise</span><span class="sxs-lookup"><span data-stu-id="f808c-189">Enterprise Voice and mobility</span></span>](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [<span data-ttu-id="f808c-190">Activer les utilisateurs pour voix entreprise dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="f808c-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="f808c-191">Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="f808c-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="f808c-192">Supprimer un compte d’utilisateur avec Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="f808c-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="f808c-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="f808c-193"><a name="Remove"> </a></span></span>

<span data-ttu-id="f808c-194">Vous pouvez utiliser la procédure suivante pour supprimer un compte d’utilisateur déjà ajouté dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f808c-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="f808c-195">La suppression d’un utilisateur entraîne la perte des paramètres que vous avez configurés pour le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f808c-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="f808c-196">Si vous voulez désactiver temporairement un compte d’utilisateur, reportez-vous à [la rubrique désactiver ou réactiver un compte d’utilisateur précédemment activé pour Skype entreprise Server](user-accounts.md#Disable).</span><span class="sxs-lookup"><span data-stu-id="f808c-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span>

1. <span data-ttu-id="f808c-197">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f808c-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="f808c-198">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f808c-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="f808c-199">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="f808c-199">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="f808c-200">Dans la boîte de dialogue **Rechercher des utilisateurs** , tapez tout ou la première partie du nom complet, prénom, nom, nom du compte de comptes de sécurité (Sam), adresse SIP ou URI (Uniform Resource Identifier) du compte d’utilisateur que vous souhaitez désactiver ou réactiver, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="f808c-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="f808c-201">Dans la table, cliquez sur le compte d’utilisateur que vous voulez supprimer.</span><span class="sxs-lookup"><span data-stu-id="f808c-201">In the table, click the user account that you want to remove.</span></span>

6. <span data-ttu-id="f808c-202">Dans le menu **action** , sélectionnez **supprimer de Lync Server**et une boîte de dialogue s’affiche.</span><span class="sxs-lookup"><span data-stu-id="f808c-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7. <span data-ttu-id="f808c-203">Dans la boîte de dialogue, sélectionnez **OK** pour supprimer l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f808c-203">From the dialog box, select **OK** to remove the user.</span></span>

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="f808c-204">Supprimer des comptes d’utilisateurs avec des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f808c-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="f808c-205">Vous pouvez supprimer des comptes d’utilisateurs à l’aide de l’applet de passe Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="f808c-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="f808c-206">Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou d’une session distante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f808c-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="f808c-207">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype entreprise Server, voir l’article sur le blog [« démarrage rapide : gestion de Microsoft Lync Server 2010 à l’aide de Remote PowerShell »](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="f808c-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="f808c-208">Le processus est le même dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f808c-208">The process is the same in Skype for Business Server.</span></span>

### <a name="to-remove-a-user-account"></a><span data-ttu-id="f808c-209">Pour supprimer un compte d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="f808c-209">To remove a user account</span></span>
<span data-ttu-id="f808c-210">Pour supprimer un compte d’utilisateur, utilisez l’applet de passe Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="f808c-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="f808c-211">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f808c-211">For example:</span></span>

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

<span data-ttu-id="f808c-212">Pour plus d’informations, reportez-vous à la rubrique d’aide de l’applet de la cmdlet [Disable-Csuser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f808c-212">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="f808c-213">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f808c-213">See also</span></span>
<span data-ttu-id="f808c-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="f808c-214"><a name="Remove"> </a></span></span>

[<span data-ttu-id="f808c-215">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="f808c-215">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[<span data-ttu-id="f808c-216">Disable-CsUser</span><span class="sxs-lookup"><span data-stu-id="f808c-216">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
