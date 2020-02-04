---
title: 'Lync Server 2013 : affecter une stratégie d’emplacement par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user location policy
ms:assetid: 343f2de3-a0ae-4403-8456-6e520b579d32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520974(v=OCS.15)
ms:contentKeyID: 48183794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d3a53ae779ccc6fb19bb2d16274e007b8fc405c6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739394"
---
# <a name="assign-a-per-user-location-policy-in-lync-server-2013"></a><span data-ttu-id="f83a3-102">Affecter une stratégie d’emplacement par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f83a3-102">Assign a per-user location policy in Lync Server 2013</span></span>

 


<span data-ttu-id="f83a3-103">La stratégie d’emplacement est l’un des paramètres individuels d’un compte d’utilisateur que vous pouvez configurer dans le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f83a3-103">The location policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="f83a3-104">Le déploiement d’une ou plusieurs stratégies d’emplacement par utilisateur est facultatif.</span><span class="sxs-lookup"><span data-stu-id="f83a3-104">Deploying one or more per-user location policies is optional.</span></span> <span data-ttu-id="f83a3-105">Vous pouvez également déployer uniquement une stratégie d’emplacement de niveau global ou une stratégie d’emplacement au niveau du sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="f83a3-105">You can also deploy only a global-level location policy or subnet-level location policy.</span></span> <span data-ttu-id="f83a3-106">Si vous déployez des stratégies au niveau utilisateur, vous devez les attribuer de manière explicite aux objets User, Group ou Contact.</span><span class="sxs-lookup"><span data-stu-id="f83a3-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="f83a3-107">Amélioration de 9-1-1 (E9-1-1) les paramètres par défaut sont automatiquement définis dans la stratégie d’emplacement au niveau du globalisation lorsque aucune stratégie spécifique de niveau de sous-réseau ou par utilisateur n’est affectée.</span><span class="sxs-lookup"><span data-stu-id="f83a3-107">Enhanced 9-1-1 (E9-1-1) settings automatically default to those defined in the global-level location policy when no specific subnet-level or per-user policy is assigned.</span></span>

<span data-ttu-id="f83a3-108">Après avoir créé au moins une stratégie d’emplacement par utilisateur, suivez les procédures décrites dans cette rubrique pour affecter à la stratégie spécifiant les paramètres que le serveur doit appliquer pour les appels d’urgence placés par un utilisateur particulier.</span><span class="sxs-lookup"><span data-stu-id="f83a3-108">After creating at least one per-user location policy, use the procedures in this topic to assign to the policy that specifies the settings that you want the server to apply for emergency calls placed by a particular user.</span></span>

<span data-ttu-id="f83a3-109">Pour obtenir la liste de tous les paramètres de stratégie d’emplacement disponibles, voir [définition de la stratégie d’emplacement pour Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="f83a3-109">For a list of all available location policy settings, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="f83a3-110">Pour plus d’informations sur la création de stratégies d’emplacement, voir [créer des stratégies d’emplacement dans Lync Server 2013](lync-server-2013-create-location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f83a3-110">For details about creating location policies, see [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md).</span></span>

## <a name="to-assign-a-per-user-location-policy-with-the-lync-server-control-panel"></a><span data-ttu-id="f83a3-111">Pour attribuer une stratégie d’emplacement par utilisateur à l’aide du panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f83a3-111">To assign a per-user location policy with the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f83a3-112">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f83a3-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f83a3-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f83a3-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f83a3-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f83a3-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f83a3-115">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="f83a3-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="f83a3-116">Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="f83a3-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="f83a3-117">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="f83a3-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="f83a3-118">Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour rechercher la requête (un fichier .usf).</span><span class="sxs-lookup"><span data-stu-id="f83a3-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="f83a3-119">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="f83a3-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="f83a3-120">Cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="f83a3-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="f83a3-121">Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche de la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="f83a3-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="f83a3-122">Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).</span><span class="sxs-lookup"><span data-stu-id="f83a3-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="f83a3-123">Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="f83a3-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="f83a3-124">Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur <STRONG>Ajouter un filtre</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f83a3-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="f83a3-125">Cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="f83a3-125">Click **Find**.</span></span>

6.  <span data-ttu-id="f83a3-126">Cliquez sur un utilisateur dans les résultats, puis sur **Action** et sur **Attribuer des stratégies**.</span><span class="sxs-lookup"><span data-stu-id="f83a3-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="f83a3-127">Si vous voulez appliquer la même stratégie d’emplacement par utilisateur à plusieurs utilisateurs, sélectionnez plusieurs utilisateurs dans les résultats de la recherche, cliquez sur <STRONG>actions</STRONG>, puis sur <STRONG>affecter des stratégies</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f83a3-127">If you want the same per-user location policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="f83a3-128">Dans **affecter des stratégies**, sous **stratégie d’emplacement**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f83a3-128">In **Assign Policies**, under **Location policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="f83a3-129">Dans la mesure où il existe plusieurs stratégies que vous pouvez configurer à l’aide de la boîte de dialogue <STRONG>affecter des stratégies</STRONG> , <STRONG> &lt;l’option conserver en tant que est&gt; </STRONG> activée par défaut pour chaque stratégie dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="f83a3-129">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="f83a3-130">Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.</span><span class="sxs-lookup"><span data-stu-id="f83a3-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="f83a3-131">Autorisez Lync Server 2013 à choisir automatiquement la stratégie de niveau global ou, s’il est défini, la stratégie de niveau de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="f83a3-131">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the subnet-level policy.</span></span>
    
      - <span data-ttu-id="f83a3-132">Cliquez sur le nom d’une stratégie d’emplacement par utilisateur que vous avez précédemment définie en exécutant l’applet **de cmdlet New-CsLocationPolicy** .</span><span class="sxs-lookup"><span data-stu-id="f83a3-132">Click the name of a per-user location policy you previously defined by running the **New-CsLocationPolicy** cmdlet.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="f83a3-133">Pour vous aider à décider de la stratégie que vous voulez attribuer, après avoir cliqué sur un nom de stratégie, cliquez sur <STRONG>Afficher</STRONG> pour afficher les droits d’utilisateur et les autorisations définis dans la stratégie.</span><span class="sxs-lookup"><span data-stu-id="f83a3-133">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="f83a3-134">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f83a3-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-location-policy-by-using-lync-server-management-shell-cmdlets"></a><span data-ttu-id="f83a3-135">Attribution d’une stratégie d’emplacement par utilisateur à l’aide des applets de cmdlet Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="f83a3-135">Assigning a Per-User Location Policy by Using Lync Server Management Shell Cmdlets</span></span>

<span data-ttu-id="f83a3-136">Vous pouvez affecter des stratégies d’emplacement par utilisateur à l’aide de l’applet de passe Grant-CsLocationPolicy.</span><span class="sxs-lookup"><span data-stu-id="f83a3-136">You can assign per-user location policies by using the Grant-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="f83a3-137">Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f83a3-137">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f83a3-138">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="f83a3-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-location-policy-to-a-single-user"></a><span data-ttu-id="f83a3-139">Pour attribuer une stratégie d’emplacement par utilisateur à un utilisateur unique</span><span class="sxs-lookup"><span data-stu-id="f83a3-139">To assign a per-user location policy to a single user</span></span>

  - <span data-ttu-id="f83a3-140">La commande suivante affecte le RedmondLocationPolicy de stratégie d’emplacement par utilisateur à l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="f83a3-140">The following command assigns the per-user location policy RedmondLocationPolicy to the user Ken Myer.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## <a name="to-assign-a-per-user-location-policy-to-multiple-users"></a><span data-ttu-id="f83a3-141">Pour affecter une stratégie d’emplacement par utilisateur à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="f83a3-141">To assign a per-user location policy to multiple users</span></span>

  - <span data-ttu-id="f83a3-142">Cette commande affecte le AccountingDepartmentLocationPolicy de stratégie d’emplacement par utilisateur à tous les utilisateurs qui travaillent pour le service de comptabilité.</span><span class="sxs-lookup"><span data-stu-id="f83a3-142">This command assigns the per-user location policy AccountingDepartmentLocationPolicy to all the users who work for the Accounting department.</span></span> <span data-ttu-id="f83a3-143">Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, voir la documentation relative à l’applet de commande [Get-Csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="f83a3-143">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## <a name="to-unassign-a-per-user-location-policy"></a><span data-ttu-id="f83a3-144">Pour annuler l’affectation d’une stratégie d’emplacement par utilisateur</span><span class="sxs-lookup"><span data-stu-id="f83a3-144">To unassign a per-user location policy</span></span>

  - <span data-ttu-id="f83a3-145">La commande suivante annule l’attribution d’une stratégie d’emplacement par utilisateur précédemment attribuée à Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="f83a3-145">The following command unassigns any per-user location policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="f83a3-146">Une fois l’affectation de la stratégie par utilisateur annulée, Ken Myer sera automatiquement géré en utilisant la stratégie globale ou, le cas échéant, sa stratégie de site local.</span><span class="sxs-lookup"><span data-stu-id="f83a3-146">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="f83a3-147">Une stratégie de site est prioritaire sur la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="f83a3-147">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="f83a3-148">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/gg413049\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="f83a3-148">For more information, see the help topic for the [Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/gg413049\(v=ocs.15\)) cmdlet.</span></span>

