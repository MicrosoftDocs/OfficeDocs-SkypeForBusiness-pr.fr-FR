---
title: 'Lync Server 2013 : affecter une stratégie de code confidentiel par utilisateur'
description: 'Lync Server 2013 : affectez une stratégie de code confidentiel par utilisateur.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user PIN policy
ms:assetid: d8211c64-0b63-4193-a074-673da7d14287
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182594(v=OCS.15)
ms:contentKeyID: 48185475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b1148a015ba9b2c173f6e23ceeb4d3b37c6ac55
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563590"
---
# <a name="assign-a-per-user-pin-policy-in-lync-server-2013"></a><span data-ttu-id="8c29d-103">Affectation d’une stratégie de code confidentiel par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c29d-103">Assign a per-user PIN policy in Lync Server 2013</span></span>

 


<span data-ttu-id="8c29d-104">La stratégie de code confidentiel (PIN) de conférence rendez-vous est l’un des paramètres individuels d’un compte d’utilisateur qui peut être configuré dans le panneau de configuration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8c29d-104">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="8c29d-p101">Le déploiement d’une ou plusieurs stratégies de code confidentiel par utilisateur est facultatif. Vous pouvez également déployer une stratégie de code confidentiel au niveau global ou au niveau d’un site. Si vous déployez des stratégies au niveau utilisateur, vous devez les attribuer de manière explicite aux objets User, Group ou Contact. Les droits et autorisations des utilisateurs concernant l’utilisation des codes confidentiels pour les conférences rendez-vous sont automatiquement définis sur ceux de la stratégie de code confidentiel globale si aucune stratégie par utilisateur ou au niveau d’un site spécifique n’est attribuée.</span><span class="sxs-lookup"><span data-stu-id="8c29d-p101">Deploying one or more per-user PIN policies is optional. You can also deploy only a global-level PIN policy or site-level PIN policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="8c29d-109">Lorsque vous aurez créé au moins une stratégie de code confidentiel par utilisateur, suivez les procédures de cette rubrique pour attribuer la stratégie spécifiant les contraintes que le serveur doit appliquer aux codes confidentiels créés et utilisés par un utilisateur particulier.</span><span class="sxs-lookup"><span data-stu-id="8c29d-109">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>

<span data-ttu-id="8c29d-110">Pour plus d’informations sur la création de stratégies de code confidentiel de conférence rendez-vous par utilisateur, voir [Create or Modify Dial-in Conferencing pin Settings in Lync Server 2013 pour un site ou un groupe d’utilisateurs](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span><span class="sxs-lookup"><span data-stu-id="8c29d-110">For details about creating per-user dial-in conferencing PIN policies, see [Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span></span>

## <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="8c29d-111">Pour attribuer une stratégie de code confidentiel par utilisateur</span><span class="sxs-lookup"><span data-stu-id="8c29d-111">To assign a per-user PIN policy</span></span>

1.  <span data-ttu-id="8c29d-112">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="8c29d-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8c29d-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8c29d-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8c29d-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8c29d-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8c29d-115">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="8c29d-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="8c29d-116">Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="8c29d-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="8c29d-117">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="8c29d-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="8c29d-118">Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour localiser la requête (un fichier .usf).</span><span class="sxs-lookup"><span data-stu-id="8c29d-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="8c29d-119">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="8c29d-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="8c29d-120">Cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="8c29d-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="8c29d-121">Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="8c29d-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="8c29d-122">Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).</span><span class="sxs-lookup"><span data-stu-id="8c29d-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="8c29d-123">Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="8c29d-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="8c29d-124">Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur <STRONG>Ajouter un filtre</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="8c29d-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="8c29d-125">Cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="8c29d-125">Click **Find**.</span></span>

6.  <span data-ttu-id="8c29d-126">Cliquez sur un utilisateur dans les résultats, puis sur **Action** et sur **Attribuer des stratégies**.</span><span class="sxs-lookup"><span data-stu-id="8c29d-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="8c29d-127">Si vous voulez que la même stratégie de code confidentiel par utilisateur s’applique à plusieurs utilisateurs, sélectionnez-les dans les résultats de la recherche, cliquez sur <STRONG>Actions</STRONG>, puis sur <STRONG>Attribuer des stratégies</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="8c29d-127">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="8c29d-128">Dans **Attribuer des stratégies**, sous **Stratégie de code confidentiel**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="8c29d-128">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="8c29d-129">Étant donné qu’il existe plusieurs stratégies que vous pouvez configurer à l’aide de la boîte de dialogue <STRONG>affecter les stratégies</STRONG> , l’option <STRONG> &lt; conserver en tant que est &gt; </STRONG> sélectionnée par défaut pour chaque stratégie dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="8c29d-129">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="8c29d-130">Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.</span><span class="sxs-lookup"><span data-stu-id="8c29d-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="8c29d-131">Autoriser Lync Server 2013 à choisir automatiquement la stratégie au niveau global ou, si elle est définie, la stratégie au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="8c29d-131">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="8c29d-132">Cliquez sur le nom d’une stratégie de code confidentiel par utilisateur que vous avez définie dans la page **Stratégie de code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="8c29d-132">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="8c29d-133">Pour vous aider à décider quelle stratégie attribuer, après avoir cliqué sur un nom de stratégie, cliquez sur <STRONG>Afficher</STRONG> pour afficher les droits et autorisations des utilisateurs définis dans la stratégie.</span><span class="sxs-lookup"><span data-stu-id="8c29d-133">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="8c29d-134">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c29d-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8c29d-135">Affectation d’une stratégie de code confidentiel Per-User à l’aide d’applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c29d-135">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8c29d-136">Vous pouvez affecter des stratégies de code confidentiel par utilisateur à l’aide de Windows PowerShell et de la cmdlet **Grant-applet cspinpolicy** .</span><span class="sxs-lookup"><span data-stu-id="8c29d-136">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="8c29d-137">Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c29d-137">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8c29d-138">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="8c29d-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="8c29d-139">Pour affecter une stratégie de code confidentiel par utilisateur à un seul utilisateur</span><span class="sxs-lookup"><span data-stu-id="8c29d-139">To assign a per-user PIN policy to a single user</span></span>

  - <span data-ttu-id="8c29d-140">La commande suivante affecte la stratégie de code confidentiel par utilisateur RedmondPinPolicy à l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="8c29d-140">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"

## <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="8c29d-141">Pour affecter une stratégie de code confidentiel par utilisateur à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="8c29d-141">To assign a per-user PIN policy to multiple users</span></span>

  - <span data-ttu-id="8c29d-142">La commande suivante affecte la stratégie de code confidentiel par utilisateur RedmondUsersPinPolicy à tous les utilisateurs travaillant dans la ville de Redmond.</span><span class="sxs-lookup"><span data-stu-id="8c29d-142">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="8c29d-143">Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, consultez la rubrique [Get-Csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="8c29d-143">For details about the LdapFilter parameter used in this command, see [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

## <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="8c29d-144">Pour annuler l’affectation d’une stratégie de code confidentiel par utilisateur</span><span class="sxs-lookup"><span data-stu-id="8c29d-144">To unassign a per-user PIN policy</span></span>

  - <span data-ttu-id="8c29d-p106">La commande suivante annule l’affectation d’une stratégie de code confidentiel par utilisateur précédemment affectée à Ken Myer. Une fois l’affectation de la stratégie par utilisateur annulée, Ken Myer sera automatiquement géré en utilisant la stratégie globale ou, le cas échéant, sa stratégie de site local. Une stratégie de site est prioritaire sur la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="8c29d-p106">The following command unassigns any per-user PIN policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="8c29d-148">Pour plus d’informations, consultez la rubrique [Grant-applet cspinpolicy](https://technet.microsoft.com/library/gg398871\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="8c29d-148">For details, see [Grant-CsPinPolicy](https://technet.microsoft.com/library/gg398871\(v=ocs.15\)).</span></span>

## <a name="see-also"></a><span data-ttu-id="8c29d-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8c29d-149">See Also</span></span>


[<span data-ttu-id="8c29d-150">Créer une stratégie de code confidentiel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c29d-150">Create a new PIN policy in Lync Server 2013</span></span>](lync-server-2013-create-a-new-pin-policy.md)  


[<span data-ttu-id="8c29d-151">Affectation de stratégies par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c29d-151">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

