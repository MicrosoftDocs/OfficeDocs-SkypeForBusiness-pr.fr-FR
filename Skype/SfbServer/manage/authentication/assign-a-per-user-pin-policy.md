---
title: Attribuer une stratégie de code confidentiel par utilisateur dans Skype Entreprise Server
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
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 'Résumé : Stage AV and OAuth certificates for Skype for Business Server.'
ms.openlocfilehash: a5cd533dccffb878fad7d7562ded3da301fc0ce3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096830"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="103cb-103">Attribuer une stratégie de code confidentiel par utilisateur dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="103cb-103">Assign a per-user PIN policy in Skype for Business Server</span></span>

<span data-ttu-id="103cb-104">**Résumé :** Stage AV and OAuth certificates for Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="103cb-104">**Summary:** Stage AV and OAuth certificates for Skype for Business Server.</span></span>
  
<span data-ttu-id="103cb-105">La stratégie de code confidentiel des conférences téléphoniques est l’un des paramètres individuels d’un compte d’utilisateur qui peuvent être configurés dans le Panneau de configuration de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="103cb-105">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="103cb-p101">Le déploiement d’une ou plusieurs stratégies de code confidentiel par utilisateur est facultatif. Vous pouvez également déployer une stratégie de code confidentiel au niveau global ou au niveau d’un site. Si vous déployez des stratégies au niveau utilisateur, vous devez les attribuer de manière explicite aux objets User, Group ou Contact. Les droits et autorisations des utilisateurs concernant l’utilisation des codes confidentiels pour les conférences rendez-vous sont automatiquement définis sur ceux de la stratégie de code confidentiel globale si aucune stratégie par utilisateur ou au niveau d’un site spécifique n’est attribuée.</span><span class="sxs-lookup"><span data-stu-id="103cb-p101">Deploying one or more per-user PIN policies is optional. You can also deploy only a global-level PIN policy or site-level PIN policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>
  
<span data-ttu-id="103cb-110">Lorsque vous aurez créé au moins une stratégie de code confidentiel par utilisateur, suivez les procédures de cette rubrique pour attribuer la stratégie spécifiant les contraintes que le serveur doit appliquer aux codes confidentiels créés et utilisés par un utilisateur particulier.</span><span class="sxs-lookup"><span data-stu-id="103cb-110">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="103cb-111">Pour attribuer une stratégie de code confidentiel par utilisateur</span><span class="sxs-lookup"><span data-stu-id="103cb-111">To assign a per-user PIN policy</span></span>

1. <span data-ttu-id="103cb-112">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="103cb-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="103cb-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="103cb-113">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="103cb-114">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="103cb-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="103cb-115">Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="103cb-115">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="103cb-116">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="103cb-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="103cb-117">Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour localiser la requête (un fichier .usf).</span><span class="sxs-lookup"><span data-stu-id="103cb-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="103cb-118">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="103cb-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="103cb-119">a.</span><span class="sxs-lookup"><span data-stu-id="103cb-119">a.</span></span> <span data-ttu-id="103cb-120">Cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="103cb-120">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="103cb-121">b.</span><span class="sxs-lookup"><span data-stu-id="103cb-121">b.</span></span> <span data-ttu-id="103cb-122">Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="103cb-122">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="103cb-123">c.</span><span class="sxs-lookup"><span data-stu-id="103cb-123">c.</span></span> <span data-ttu-id="103cb-124">Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).</span><span class="sxs-lookup"><span data-stu-id="103cb-124">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="103cb-125">d.</span><span class="sxs-lookup"><span data-stu-id="103cb-125">d.</span></span> <span data-ttu-id="103cb-126">Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="103cb-126">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="103cb-127">Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="103cb-127">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="103cb-128">e.</span><span class="sxs-lookup"><span data-stu-id="103cb-128">e.</span></span> <span data-ttu-id="103cb-129">Cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="103cb-129">Click **Find**.</span></span>
    
6. <span data-ttu-id="103cb-130">Cliquez sur un utilisateur dans les résultats, puis sur **Action** et sur **Attribuer des stratégies**.</span><span class="sxs-lookup"><span data-stu-id="103cb-130">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="103cb-131">Si vous voulez que la même stratégie de code confidentiel par utilisateur s’applique à plusieurs utilisateurs, sélectionnez-les dans les résultats de la recherche, cliquez sur **Actions**, puis sur **Attribuer des stratégies**.</span><span class="sxs-lookup"><span data-stu-id="103cb-131">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click **Actions**, and then click **Assign policies**.</span></span> 
  
7. <span data-ttu-id="103cb-132">Dans **Attribuer des stratégies**, sous **Stratégie de code confidentiel**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="103cb-132">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="103cb-133">Étant donné que vous pouvez configurer plusieurs  stratégies à l’aide de la boîte de dialogue Attribuer des stratégies, cette option est sélectionnée par défaut pour chaque stratégie de **\<Keep as is\>** la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="103cb-133">Because there are multiple policies that you can configure by using the **Assign Policies** dialog box, **\<Keep as is\>** is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="103cb-134">Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.</span><span class="sxs-lookup"><span data-stu-id="103cb-134">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>
  
   - <span data-ttu-id="103cb-135">Autoriser Skype Entreprise Server à choisir automatiquement la stratégie de niveau global ou, si elle est définie, la stratégie au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="103cb-135">Allow Skype for Business Server to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
   - <span data-ttu-id="103cb-136">Cliquez sur le nom d’une stratégie de code confidentiel par utilisateur que vous avez définie dans la page **Stratégie de code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="103cb-136">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
    
     > [!TIP]
     > <span data-ttu-id="103cb-137">Pour vous aider à décider quelle stratégie attribuer, après avoir cliqué sur un nom de stratégie, cliquez sur **Afficher** pour afficher les droits et autorisations des utilisateurs définis dans la stratégie.</span><span class="sxs-lookup"><span data-stu-id="103cb-137">To help you decide the policy you want to assign, after you click a policy name, click **View** to view the user rights and permissions defined in the policy.</span></span>
  
8. <span data-ttu-id="103cb-138">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="103cb-138">When you are finished, click **OK**.</span></span>
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="103cb-139">Affectation d’une stratégie Per-User de code confidentiel à l’aide Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="103cb-139">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="103cb-140">Vous pouvez affecter des stratégies de code confidentiel par utilisateur à l’Windows PowerShell et à l’cmdlet **Grant-CsPinPolicy.**</span><span class="sxs-lookup"><span data-stu-id="103cb-140">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="103cb-141">Vous pouvez exécuter cette applet de commande à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="103cb-141">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="103cb-142">Pour plus d’informations sur l’utilisation des Windows PowerShell distantes pour se connecter à Skype Entreprise Server, consultez l’article de blog « Démarrage rapide : gestion de [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="103cb-142">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="103cb-143">Le processus est le même dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="103cb-143">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="103cb-144">Pour affecter une stratégie de code confidentiel par utilisateur à un seul utilisateur</span><span class="sxs-lookup"><span data-stu-id="103cb-144">To assign a per-user PIN policy to a single user</span></span>

- <span data-ttu-id="103cb-145">La commande suivante affecte la stratégie de code confidentiel par utilisateur RedmondPinPolicy à l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="103cb-145">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="103cb-146">Pour affecter une stratégie de code confidentiel par utilisateur à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="103cb-146">To assign a per-user PIN policy to multiple users</span></span>

- <span data-ttu-id="103cb-147">La commande suivante affecte la stratégie de code confidentiel par utilisateur RedmondUsersPinPolicy à tous les utilisateurs travaillant dans la ville de Redmond.</span><span class="sxs-lookup"><span data-stu-id="103cb-147">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="103cb-148">Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, voir [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="103cb-148">For details about the LdapFilter parameter used in this command, see [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```PowerShell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="103cb-149">Pour annuler l’affectation d’une stratégie de code confidentiel par utilisateur</span><span class="sxs-lookup"><span data-stu-id="103cb-149">To unassign a per-user PIN policy</span></span>

- <span data-ttu-id="103cb-p110">La commande suivante annule l’affectation d’une stratégie de code confidentiel par utilisateur précédemment affectée à Ken Myer. Une fois l’affectation de la stratégie par utilisateur annulée, Ken Myer sera automatiquement géré en utilisant la stratégie globale ou, le cas échéant, sa stratégie de site local. Une stratégie de site est prioritaire sur la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="103cb-p110">The following command unassigns any per-user PIN policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

<span data-ttu-id="103cb-153">Pour plus d’informations, [voir Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="103cb-153">For details, see [Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="103cb-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="103cb-154">See also</span></span>

[<span data-ttu-id="103cb-155">Créer une stratégie de code confidentiel dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="103cb-155">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)