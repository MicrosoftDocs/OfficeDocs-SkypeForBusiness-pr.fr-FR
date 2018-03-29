---
title: Gérer les comptes d’utilisateurs de Skype pour Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: Les sections de cet article décrivent comment activer, désactiver temporairement ou supprimer des utilisateurs d’Active Directory de Skype pour Business Server 2015.
ms.openlocfilehash: bd09687a6a2d2f3d1e8dcfe13b7f8aa64648e56b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-user-accounts-for-skype-for-business-server-2015"></a><span data-ttu-id="50940-103">Gérer les comptes d’utilisateurs de Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="50940-103">Manage user accounts for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="50940-104">Les sections de cet article décrivent comment activer, désactiver temporairement ou supprimer des utilisateurs d’Active Directory de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="50940-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="50940-105">Pour plus d’informations sur l’activation d’un utilisateur Active Directory, voir [créer un nouveau compte d’utilisateur](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="50940-105">For information on how to enable an Active Directory user, see [Create a New User Account](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span></span> <span data-ttu-id="50940-106">Pour plus d’informations sur la façon de supprimer un utilisateur d’Active Directory, voir [suppression d’un compte d’utilisateur](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="50940-106">For information on how to delete an Active Directory user, see [Delete a User Account](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span></span>
  
<span data-ttu-id="50940-107">Ces procédures doivent être effectuées au cours d’une période de maintenance, lorsque Skype pour l’utilisation d’entreprise est le plus bas.</span><span class="sxs-lookup"><span data-stu-id="50940-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="50940-108">Si cela est effectué sur une planification quotidienne ou hebdomadaire sera déterminé par les besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="50940-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span> 
  
<span data-ttu-id="50940-109">Cet article contient les procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="50940-109">This article contains the following procedures:</span></span>
  
- [<span data-ttu-id="50940-110">Pour rechercher un ou plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="50940-110">To search for one or more users</span></span>](user-accounts.md#Search)
    
- [<span data-ttu-id="50940-111">Ajouter et activer un nouveau Skype pour l’utilisateur de Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="50940-111">Add and enable a new Skype for Business Server 2015 user</span></span>](user-accounts.md#Add)
    
- [<span data-ttu-id="50940-112">Désactiver ou réactiver un compte d’utilisateur précédemment activé pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="50940-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)
    
- [<span data-ttu-id="50940-113">Désactiver un utilisateur de Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="50940-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)
    
- [<span data-ttu-id="50940-114">Supprimer un compte d’utilisateur avec le Skype pour Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="50940-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)
    
## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="50940-115">Pour rechercher un ou plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="50940-115">To search for one or more users</span></span>
<span data-ttu-id="50940-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="50940-116"></span></span>

<span data-ttu-id="50940-117">Les résultats d’une requête de recherche vous permet de configurer des utilisateurs Active Directory pour Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="50940-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server 2015.</span></span> <span data-ttu-id="50940-118">Vous pouvez rechercher des utilisateurs par nom d’affichage, prénom, nom de famille, nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), adresse SIP ou URI (Uniform Resource Identifier) de ligne.</span><span class="sxs-lookup"><span data-stu-id="50940-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>
  
<span data-ttu-id="50940-119">Vous pouvez rechercher des utilisateurs à l’aide de la Skype pour Business Server du Panneau de configuration ou les utilisateurs Active Directory et le composant logiciel enfichable ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="50940-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="50940-120">La procédure suivante décrit comment utiliser Skype pour le panneau de configuration de Business Server pour rechercher des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="50940-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="50940-121">Dans un environnement avec une topologie à forêt centrale, résultats de la recherche soient pas précis lorsque vous recherchez un utilisateur par adresse de messagerie de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="50940-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="50940-122">Au lieu de cela, vous pouvez rechercher des utilisateurs en spécifiant un préfixe d’adresse SIP, par exemple sip : nom, ajouter un filtre de recherche et sélectionnez une adresse SIP qui contient une adresse partielle ou utiliser l’applet de commande **Get-CSUser** .</span><span class="sxs-lookup"><span data-stu-id="50940-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>
  
1. <span data-ttu-id="50940-123">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="50940-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="50940-124">Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="50940-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="50940-125">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="50940-125">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="50940-126">Dans la boîte de **recherche utilisateurs** , tapez tout ou la première partie de l’affichage nom, le prénom, le nom, le nom de compte SAM, SIP d’adresse ou ligne URI du compte d’utilisateur que vous souhaitez rechercher, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="50940-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>
    
5. <span data-ttu-id="50940-127">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="50940-127">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="50940-128">a.</span><span class="sxs-lookup"><span data-stu-id="50940-128">a.</span></span> <span data-ttu-id="50940-129">Cliquez sur le bouton flèche dans le coin supérieur droit de l’écran située au-dessus des **résultats de recherche**, puis cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="50940-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>
    
   <span data-ttu-id="50940-130">b.</span><span class="sxs-lookup"><span data-stu-id="50940-130">b.</span></span> <span data-ttu-id="50940-131">Entrez la propriété de l’utilisateur en tapant ou en cliquant sur la flèche dans la liste déroulante pour sélectionner une propriété de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="50940-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>
    
   <span data-ttu-id="50940-132">c.</span><span class="sxs-lookup"><span data-stu-id="50940-132">c.</span></span> <span data-ttu-id="50940-133">Dans la liste **égal à** , cliquez sur **égal** ou **non égal à**.</span><span class="sxs-lookup"><span data-stu-id="50940-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>
    
   <span data-ttu-id="50940-134">d.</span><span class="sxs-lookup"><span data-stu-id="50940-134">d.</span></span> <span data-ttu-id="50940-135">Dans la zone de texte, tapez les critères de recherche que vous souhaitez utiliser pour filtrer les résultats de la recherche, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="50940-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>
    
6. <span data-ttu-id="50940-136">Les résultats de la recherche s’affichent sous **Résultats de la recherche**.</span><span class="sxs-lookup"><span data-stu-id="50940-136">The search results appear under **Search Results**.</span></span> <span data-ttu-id="50940-137">Vous pouvez sélectionner tout ou partie des utilisateurs dans la liste et effectuer des tâches de configuration sur les utilisateurs que vous sélectionnez.</span><span class="sxs-lookup"><span data-stu-id="50940-137">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>
    
## <a name="add-and-enable-a-new-skype-for-business-server-2015-user"></a><span data-ttu-id="50940-138">Ajouter et activer un nouveau Skype pour l’utilisateur de Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="50940-138">Add and enable a new Skype for Business Server 2015 user</span></span>
<span data-ttu-id="50940-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="50940-139"></span></span>

<span data-ttu-id="50940-140">Après l’activation d’un compte d’utilisateur dans Active Directory utilisateurs et ordinateurs, vous pouvez utiliser Skype pour le panneau de configuration de Business Server pour créer et activer le nouveau Skype pour les comptes d’utilisateur Business Server 2015 en ajoutant un utilisateur Active Directory à Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="50940-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server 2015 user accounts by adding an Active Directory user to Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="50940-141">Vous pouvez également utiliser une applet de commande, spécifiquement [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="50940-141">You can also use a cmdlet, specifically [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>
  
1. <span data-ttu-id="50940-142">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="50940-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="50940-143">Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="50940-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="50940-144">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="50940-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="50940-145">Cliquez sur **Activer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="50940-145">Click **Enable users**.</span></span>
    
5. <span data-ttu-id="50940-146">Dans la boîte de dialogue **Nouvel utilisateur de serveur Lync** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="50940-146">On the **New Lync Server User** dialog, click **Add**.</span></span>
    
6. <span data-ttu-id="50940-147">Dans la boîte de **recherche utilisateurs** , tapez tout ou la première partie du nom, afficher le nom, prénom, nom, nom de compte Gestionnaire de comptes de sécurité (SAM), adresse de messagerie, nom d’utilisateur Principal (UPN) ou numéro de téléphone du compte d’utilisateur Active Directory que vous souhaitez , puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="50940-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>
    
7. <span data-ttu-id="50940-148">Dans le tableau, sélectionnez le compte que vous souhaitez ajouter à Skype pour Business Server 2015, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="50940-148">In the table, select the account you want to add to Skype for Business Server 2015, and then click **OK**.</span></span>
    
8. <span data-ttu-id="50940-149">Assigner l’utilisateur à un pool, spécifier des détails supplémentaires et affecter à l’utilisateur que vous souhaitez que les stratégies et puis cliquez sur **Activer**.</span><span class="sxs-lookup"><span data-stu-id="50940-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>
    
## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="50940-150">Désactiver ou réactiver un compte d’utilisateur précédemment activé pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="50940-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="50940-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="50940-151"></span></span>

<span data-ttu-id="50940-152">Vous pouvez utiliser la procédure suivante pour désactiver un compte d’utilisateur précédemment activé dans Skype pour Business Server sans perdre la Skype pour les paramètres de serveur de l’entreprise que vous avez configurée pour le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="50940-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="50940-153">Étant donné que vous ne perdez pas le Skype pour les paramètres de compte d’utilisateur Business Server, vous pouvez réactiver un compte d’utilisateur précédemment activé à nouveau sans avoir à reconfigurer le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="50940-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span> 
  
1. <span data-ttu-id="50940-154">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="50940-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="50940-155">Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="50940-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="50940-156">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="50940-156">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="50940-157">Dans la boîte de **recherche utilisateurs** , tapez tout ou la première partie du nom complet, prénom, nom, nom de compte Gestionnaire de comptes de sécurité (SAM), adresse SIP ou ligne identificateur URI (Uniform Resource) du compte d’utilisateur que vous souhaitez désactiver ou réactiver, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="50940-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="50940-158">Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez désactiver ou réactiver.</span><span class="sxs-lookup"><span data-stu-id="50940-158">In the table, click the user account that you want to disable or re-enable.</span></span>
    
6. <span data-ttu-id="50940-159">Dans le menu **Action** , effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="50940-159">On the **Action** menu, do one of the following:</span></span>
    
   - <span data-ttu-id="50940-160">Pour désactiver temporairement le compte d’utilisateur pour Skype pour Business Server, cliquez sur **désactiver temporairement pour Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="50940-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>
    
   - <span data-ttu-id="50940-161">Pour activer le compte d’utilisateur Skype pour Business Server, cliquez sur **réactiver pour Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="50940-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>
    
### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="50940-162">Utiliser Windows Powershell pour désactiver ou réactiver les comptes d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="50940-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="50940-163">Comptes d’utilisateurs peuvent être temporairement désactivés et puis ensuite réactivés, à l’aide de l’applet de commande **Set-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="50940-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="50940-164">Vous pouvez exécuter cette applet de commande depuis le Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50940-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="50940-165">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter sur Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="50940-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="50940-166">Le processus est le même dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="50940-166">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-disable-a-user-account"></a><span data-ttu-id="50940-167">Pour désactiver un compte d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="50940-167">To disable a user account</span></span>

- <span data-ttu-id="50940-168">Pour désactiver temporairement un compte d’utilisateur, la valeur de la propriété Enabled la valeur False ($False).</span><span class="sxs-lookup"><span data-stu-id="50940-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="50940-169">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="50940-169">For example:</span></span>
    
  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="50940-170">Pour réactiver un compte d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="50940-170">To re-enable a user account</span></span>

- <span data-ttu-id="50940-171">Pour réactiver un compte d’utilisateur désactivé, la valeur de la propriété Enabled la valeur True ($True).</span><span class="sxs-lookup"><span data-stu-id="50940-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="50940-172">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="50940-172">For example:</span></span>
    
  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="50940-173">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="50940-173">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>
  
## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="50940-174">Désactiver un utilisateur de Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="50940-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="50940-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="50940-175"></span></span>

<span data-ttu-id="50940-176">La procédure suivante permet de désactiver la Voix Entreprise pour un compte d’utilisateur est activé pour Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="50940-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server 2015.</span></span>
  
### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="50940-177">Pour désactiver un compte d’utilisateur de Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="50940-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="50940-178">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="50940-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="50940-179">Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="50940-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="50940-180">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="50940-180">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="50940-181">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager), de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur à activer, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="50940-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="50940-182">Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez activer pour les Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="50940-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="50940-183">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="50940-183">On the **Edit** menu, click **Show details**.</span></span>
    
7. <span data-ttu-id="50940-184">Dans la page **Modifier l’utilisateur Lync Server** , **téléphonie**, cliquez sur une option autre que la **Voix Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="50940-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="50940-185">Pour empêcher un utilisateur d’effectuer des appels audio ou vidéo à l’aide de Lync, sous **téléphonie**, cliquez sur **Audio/vidéo désactivée**.</span><span class="sxs-lookup"><span data-stu-id="50940-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span> 
  
8. <span data-ttu-id="50940-186">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="50940-186">Click **Commit**.</span></span>
    
<span data-ttu-id="50940-187">L’utilisateur est désormais impossible d’utiliser la fonctionnalité Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="50940-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="50940-188">Obtenir des informations connexes :</span><span class="sxs-lookup"><span data-stu-id="50940-188">Related information:</span></span> <br/>[<span data-ttu-id="50940-189">Voix Entreprise et la mobilité</span><span class="sxs-lookup"><span data-stu-id="50940-189">Enterprise Voice and mobility</span></span>](http://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [<span data-ttu-id="50940-190">Permettre aux utilisateurs de Voix Entreprise dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="50940-190">Enable users for Enterprise Voice in Skype for Business Server 2015</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="50940-191">Skype pour Business Server 2015 Management Shell</span><span class="sxs-lookup"><span data-stu-id="50940-191">Skype for Business Server 2015 Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="50940-192">Supprimer un compte d’utilisateur avec le Skype pour Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="50940-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="50940-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="50940-193"></span></span>

<span data-ttu-id="50940-194">Vous pouvez utiliser la procédure suivante pour supprimer un compte d’utilisateur précédemment ajouté dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="50940-194">You can use the following procedure to remove a previously added user account in Skype for Business Server 2015.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="50940-195">Suppression d’un utilisateur provoque la perte des paramètres que vous avez configurée pour le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="50940-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="50940-196">Si vous voulez temporairement désactiver un compte d’utilisateur à la place, consultez [désactiver ou réactiver un compte d’utilisateur précédemment activé pour Skype pour Business Server](user-accounts.md#Disable).</span><span class="sxs-lookup"><span data-stu-id="50940-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span> 
  
1. <span data-ttu-id="50940-197">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="50940-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="50940-198">Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="50940-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="50940-199">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="50940-199">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="50940-200">Dans la boîte de **recherche utilisateurs** , tapez tout ou la première partie du nom complet, prénom, nom, nom de compte Gestionnaire de comptes de sécurité (SAM), adresse SIP ou ligne identificateur URI (Uniform Resource) du compte d’utilisateur que vous souhaitez désactiver ou réactiver, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="50940-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="50940-201">Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="50940-201">In the table, click the user account that you want to remove.</span></span>
    
6. <span data-ttu-id="50940-202">Dans le menu **Action** , sélectionnez **Supprimer de Lync Server**et une boîte de dialogue zone s’affiche.</span><span class="sxs-lookup"><span data-stu-id="50940-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>
    
7. <span data-ttu-id="50940-203">À partir de la boîte de dialogue, cliquez sur **OK** pour supprimer l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="50940-203">From the dialog box, select **OK** to remove the user.</span></span>
    
### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="50940-204">Supprimer des comptes d’utilisateurs avec les applets de commande Windows Powershell</span><span class="sxs-lookup"><span data-stu-id="50940-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="50940-205">Vous pouvez supprimer des comptes d’utilisateurs à l’aide de l’applet de commande Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="50940-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="50940-206">Cette applet de commande peut être exécuté à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50940-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="50940-207">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter sur Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="50940-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="50940-208">Le processus est le même dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="50940-208">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-user-account"></a><span data-ttu-id="50940-209">Pour supprimer un compte d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="50940-209">To remove a user account</span></span>
<span data-ttu-id="50940-210">Pour supprimer un compte d’utilisateur, utilisez l’applet de commande Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="50940-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="50940-211">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="50940-211">For example:</span></span>
    
  ```
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.
    
<span data-ttu-id="50940-212">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="50940-212">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="50940-213">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="50940-213">See also</span></span>
<span data-ttu-id="50940-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="50940-214"></span></span>

#### 

[<span data-ttu-id="50940-215">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="50940-215">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)
  
[<span data-ttu-id="50940-216">Désactiver-CsUser</span><span class="sxs-lookup"><span data-stu-id="50940-216">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)

