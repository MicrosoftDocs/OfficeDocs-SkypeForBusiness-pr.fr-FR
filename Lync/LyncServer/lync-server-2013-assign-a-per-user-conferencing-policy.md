---
title: 'Lync Server 2013 : affecter une stratégie de conférence par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user conferencing policy
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521015(v=OCS.15)
ms:contentKeyID: 48184475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c4fbef02553d4ba390dcf94f96f55936e2661b1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043316"
---
# <a name="assign-a-per-user-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="cdb7c-102">Affecter une stratégie de conférence par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdb7c-102">Assign a per-user conferencing policy in Lync Server 2013</span></span>

 


<span data-ttu-id="cdb7c-103">La stratégie de conférence est l’un des paramètres individuels d’un compte d’utilisateur que vous pouvez configurer dans le panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-103">The conferencing policy is one of the individual settings of a user account that you can configure in Lync Server Control Panel.</span></span>

<span data-ttu-id="cdb7c-p101">Le déploiement d’une ou plusieurs stratégies de conférence par utilisateur est facultatif. Vous pouvez également déployer une stratégie de conférence au niveau global ou au niveau d’un site. Si vous déployez des stratégies au niveau utilisateur, vous devez les attribuer de manière explicite à des utilisateurs, des groupes ou des objets contact. Les droits et autorisations des utilisateurs de conférence sont automatiquement définis sur ceux de la stratégie de conférence globale si aucune stratégie par utilisateur ou au niveau d’un site spécifique n’est attribuée.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-p101">Deploying one or more per-user conferencing policies is optional. You can also deploy only a global-level conferencing policy or site-level conferencing policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects. Conferencing user rights and permissions automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="cdb7c-108">Lorsque vous aurez créé au moins une stratégie de conférence par utilisateur, suivez les procédures de cette rubrique pour attribuer la stratégie spécifiant les droits et autorisations que le serveur doit octroyer aux réunions organisées par un utilisateur particulier.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-108">After creating at least one per-user conferencing policy, use the procedures in this topic to assign the policy that specifies the user rights and permissions that you want the server to grant to the meetings organized by a particular user.</span></span>

<span data-ttu-id="cdb7c-109">Pour obtenir la liste de tous les paramètres de stratégie de conférence disponibles, consultez la rubrique [référence des paramètres de stratégie de conférence pour Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="cdb7c-109">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<span data-ttu-id="cdb7c-110">Pour plus d’informations sur la création de stratégies de conférence, voir [Create or Modify a Conferencing Policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="cdb7c-110">For details about creating conferencing policies, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span>

## <a name="to-assign-a-per-user-conferencing-policy"></a><span data-ttu-id="cdb7c-111">Pour attribuer une stratégie de conférence par utilisateur</span><span class="sxs-lookup"><span data-stu-id="cdb7c-111">To assign a per-user conferencing policy</span></span>

1.  <span data-ttu-id="cdb7c-112">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cdb7c-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cdb7c-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cdb7c-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cdb7c-115">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="cdb7c-116">Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="cdb7c-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="cdb7c-117">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="cdb7c-118">Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour localiser la requête (un fichier .usf).</span><span class="sxs-lookup"><span data-stu-id="cdb7c-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="cdb7c-119">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="cdb7c-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="cdb7c-120">Cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="cdb7c-121">Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="cdb7c-122">Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).</span><span class="sxs-lookup"><span data-stu-id="cdb7c-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="cdb7c-123">Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="cdb7c-124">Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur <STRONG>Ajouter un filtre</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="cdb7c-125">Cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-125">Click **Find**.</span></span>

6.  <span data-ttu-id="cdb7c-126">Cliquez sur un utilisateur dans les résultats, puis sur **Action** et sur **Attribuer des stratégies**.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="cdb7c-127">Si vous voulez que la même stratégie de conférence par utilisateur s’applique à plusieurs utilisateurs, sélectionnez-les dans les résultats de la recherche, cliquez sur <STRONG>Actions</STRONG>, puis sur <STRONG>Attribuer des stratégies</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-127">If you want the same per-user conferencing policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="cdb7c-128">Dans **Attribuer des stratégies**, sous **Stratégie de conférence**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="cdb7c-128">In **Assign Policies**, under **Conferencing policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="cdb7c-129">Étant donné qu’il existe plusieurs stratégies que vous pouvez configurer dans <STRONG>affecter des stratégies</STRONG>, <STRONG> &lt;garder en&gt; tant que est</STRONG> sélectionnée par défaut pour chaque stratégie dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-129">Because there are multiple policies that you can configure in <STRONG>Assign Policies</STRONG>, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="cdb7c-130">Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="cdb7c-131">Sélectionnez \*\* \<automatique\> \*\* pour permettre à Lync Server 2013 de choisir automatiquement la stratégie au niveau global ou, si elle est définie, la stratégie au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-131">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="cdb7c-132">Cliquez sur le nom d’une stratégie de conférence par utilisateur que vous avez précédemment définie dans la page **Stratégie de conférence**.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-132">Click the name of a per-user conferencing policy you previously defined on the **Conferencing Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="cdb7c-133">Pour vous aider à décider quelle stratégie attribuer, après avoir cliqué sur un nom de stratégie, cliquez sur <STRONG>Afficher</STRONG> pour afficher les droits et autorisations des utilisateurs définis dans la stratégie.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-133">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="cdb7c-134">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-conferencing-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="cdb7c-135">Affectation d’une stratégie de conférence par utilisateur à l’aide d’applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cdb7c-135">Assigning a Per-User Conferencing Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="cdb7c-136">Les stratégies de conférence par utilisateur peuvent être affectées à l’aide de Windows PowerShell et de la cmdlet Grant-CsConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-136">Per-user conferencing policies can be assigned by using Windows PowerShell and the Grant-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="cdb7c-137">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-137">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="cdb7c-138">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-conferencing-policy-to-a-single-user"></a><span data-ttu-id="cdb7c-139">Pour affecter une stratégie de conférence par utilisateur à un seul utilisateur</span><span class="sxs-lookup"><span data-stu-id="cdb7c-139">To assign a per-user conferencing policy to a single user</span></span>

  - <span data-ttu-id="cdb7c-140">La commande suivante affecte la stratégie de conférence par utilisateur RedmondConferencingPolicy à l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-140">The following command assigns the per-user conferencing policy RedmondConferencingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## <a name="to-assign-a-per-user-conferencing-policy-to-multiple-users"></a><span data-ttu-id="cdb7c-141">Pour affecter une stratégie de conférence par utilisateur à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="cdb7c-141">To assign a per-user conferencing policy to multiple users</span></span>

  - <span data-ttu-id="cdb7c-142">Cette commande affecte la stratégie de conférence par utilisateur HRConferencingPolicy à tous les utilisateurs qui travaillent pour le service des ressources humaines.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-142">This command assigns the per-user conferencing policy HRConferencingPolicy to all the users who work for the Human Resources department.</span></span> <span data-ttu-id="cdb7c-143">Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, reportez-vous à la documentation de la cmdlet [Get-Csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="cdb7c-143">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## <a name="to-unassign-a-per-user-conferencing-policy"></a><span data-ttu-id="cdb7c-144">Pour annuler l’affectation d’une stratégie de conférence par utilisateur</span><span class="sxs-lookup"><span data-stu-id="cdb7c-144">To unassign a per-user conferencing policy</span></span>

  - <span data-ttu-id="cdb7c-p106">La commande suivante annule l’affectation d’une stratégie de conférence par utilisateur précédemment affectée à Ken Myer. Lorsque cette stratégie par utilisateur n’est plus affectée à Ken Myer, celui-ci est automatiquement géré par la stratégie globale ou, le cas échéant, par la stratégie de site locale associée. La stratégie de site est prioritaire sur la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="cdb7c-p106">The following command unassigns any per-user conferencing policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="cdb7c-148">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="cdb7c-148">For more information, see the help topic for the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="cdb7c-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cdb7c-149">See Also</span></span>


[<span data-ttu-id="cdb7c-150">Création ou modification d’une stratégie de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdb7c-150">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)  


[<span data-ttu-id="cdb7c-151">Affectation de stratégies par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdb7c-151">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

