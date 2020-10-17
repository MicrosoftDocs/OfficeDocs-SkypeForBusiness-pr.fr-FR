---
title: 'Lync Server 2013 : affecter une stratégie d’archivage par utilisateur'
description: 'Lync Server 2013 : affectez une stratégie d’archivage par utilisateur.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c81d7e426f16c298196aba733d720a92d0854bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559990"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="81dce-103">Affectation d’une stratégie d’archivage par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81dce-103">Assign a per-user archiving policy in Lync Server 2013</span></span>

 


<span data-ttu-id="81dce-104">La stratégie d’archivage est l’un des paramètres individuels d’un compte d’utilisateur que vous pouvez configurer dans le panneau de configuration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81dce-104">The archiving policy is one of the individual settings of a user account that you can configure in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="81dce-p101">Le déploiement d’une ou de plusieurs stratégies d’archivage par utilisateur est facultatif. Vous pouvez également déployer une stratégie d’archivage uniquement au niveau global ou au niveau d’un site. Si vous déployez des stratégies au niveau utilisateur, vous devez les attribuer de manière explicite aux objets User, Group ou Contact. Les conditions requises pour l’archivage sont automatiquement définies par défaut sur celles de la stratégie de conférence de niveau global si aucune stratégie par utilisateur ou au niveau d’un site spécifique n’est attribuée.</span><span class="sxs-lookup"><span data-stu-id="81dce-p101">Deploying one or more per-user archiving policies is optional. You can also deploy only a global-level archiving policy or site-level archiving policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. Archiving requirements automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="81dce-109">Après avoir créé au moins une stratégie d’archivage par utilisateur, utilisez les procédures de cette rubrique pour attribuer la stratégie qui précise de manière appropriée si les communications internes, les communications externes d’un utilisateur particulier ou les deux seront archivées par le serveur.</span><span class="sxs-lookup"><span data-stu-id="81dce-109">After creating at least one per-user archiving policy, use the procedures in this topic to assign the policy that appropriately specifies whether a particular user’s internal communications, external communications, or both, will be archived by the server.</span></span>

<span data-ttu-id="81dce-110">Pour plus d’informations sur la création de stratégies d’archivage par utilisateur, reportez-vous à la rubrique [création d’une stratégie d’archivage dans Lync Server 2013 pour activer ou désactiver l’archivage des communications internes ou externes pour des sites ou des utilisateurs spécifiques](lync-server-2013-create-archiving-policy-sites-users.md).</span><span class="sxs-lookup"><span data-stu-id="81dce-110">For details about creating per-user archiving policies, see [Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of Internal or external communications for specific sites or users](lync-server-2013-create-archiving-policy-sites-users.md).</span></span>

## <a name="to-assign-a-per-user-archiving-policy"></a><span data-ttu-id="81dce-111">Pour attribuer une stratégie d’archivage par utilisateur</span><span class="sxs-lookup"><span data-stu-id="81dce-111">To assign a per-user archiving policy</span></span>

1.  <span data-ttu-id="81dce-112">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="81dce-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="81dce-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="81dce-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="81dce-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="81dce-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="81dce-115">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="81dce-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="81dce-116">Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="81dce-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="81dce-117">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="81dce-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="81dce-118">Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour localiser la requête (un fichier .usf).</span><span class="sxs-lookup"><span data-stu-id="81dce-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="81dce-119">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="81dce-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="81dce-120">Cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="81dce-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="81dce-121">Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="81dce-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="81dce-122">Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).</span><span class="sxs-lookup"><span data-stu-id="81dce-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="81dce-123">Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="81dce-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="81dce-124">Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur <STRONG>Ajouter un filtre</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="81dce-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="81dce-125">Cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="81dce-125">Click **Find**.</span></span>

6.  <span data-ttu-id="81dce-126">Cliquez sur un utilisateur dans les résultats, puis sur **Action** et sur **Attribuer des stratégies**.</span><span class="sxs-lookup"><span data-stu-id="81dce-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="81dce-127">Si vous voulez que la même stratégie d’archivage par utilisateur s’applique à plusieurs utilisateurs, sélectionnez-les dans les résultats de la recherche, cliquez sur <STRONG>Actions</STRONG>, puis sur <STRONG>Attribuer des stratégies</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="81dce-127">If you want the same per-user archiving policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="81dce-128">Dans **Attribuer des stratégies**, sous **Stratégie d’archivage**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="81dce-128">In **Assign Policies**, under **Archiving policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="81dce-129">Étant donné qu’il existe plusieurs stratégies que vous pouvez configurer à l’aide de la boîte de dialogue <STRONG>affecter les stratégies</STRONG> , l’option <STRONG> &lt; conserver en tant que est &gt; </STRONG> sélectionnée par défaut pour chaque stratégie dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="81dce-129">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="81dce-130">Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.</span><span class="sxs-lookup"><span data-stu-id="81dce-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="81dce-131">Autoriser Lync Server 2013 à choisir automatiquement la stratégie au niveau global ou, si elle est définie, la stratégie au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="81dce-131">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="81dce-132">Cliquez sur le nom d’une stratégie d’archivage par utilisateur que vous avez précédemment définie dans la page **Stratégie d’archivage**.</span><span class="sxs-lookup"><span data-stu-id="81dce-132">Click the name of a per-user archiving policy you previously defined on the **Archiving Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="81dce-133">Pour vous aider à décider de la stratégie à attribuer, après avoir cliqué sur le nom d’une stratégie, cliquez sur <STRONG>Afficher</STRONG> pour afficher les droits et les autorisations associés à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="81dce-133">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="81dce-134">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="81dce-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="81dce-135">Affectation d’une stratégie d’archivage de Per-User à l’aide d’applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="81dce-135">Assigning a Per-User Archiving Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="81dce-136">Vous pouvez attribuer des stratégies d’archivage par utilisateur à l’aide de Windows PowerShell et de la cmdlet **Grant-applet csarchivingpolicy** .</span><span class="sxs-lookup"><span data-stu-id="81dce-136">You can assign per-user archiving policies by using Windows PowerShell and the **Grant-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="81dce-137">Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81dce-137">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="81dce-138">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="81dce-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a><span data-ttu-id="81dce-139">Pour affecter une stratégie d’archivage par utilisateur à un seul utilisateur</span><span class="sxs-lookup"><span data-stu-id="81dce-139">To assign a per-user archiving policy to a single user</span></span>

  - <span data-ttu-id="81dce-140">La commande suivante assigne la stratégie d’archivage par utilisateur RedmondArchivingPolicy à l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="81dce-140">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a><span data-ttu-id="81dce-141">Pour affecter une stratégie d’archivage par utilisateur à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="81dce-141">To assign a per-user archiving policy to multiple users</span></span>

  - <span data-ttu-id="81dce-142">Cette commande assigne la stratégie d’archivage par utilisateur RedmondArchivingPolicy à tous les utilisateurs qui ont un compte hébergé sur le pool de serveurs d’inscriptions atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="81dce-142">This command assigns the per-user archiving policy RedmondArchivingPolicy to all the users who have accounts homed on the Registrar pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="81dce-143">Pour plus d’informations sur le paramètre Filter utilisé dans cette commande, reportez-vous à la documentation de la cmdlet [Get-Csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="81dce-143">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a><span data-ttu-id="81dce-144">Pour annuler l’affectation d’une stratégie d’archivage par utilisateur</span><span class="sxs-lookup"><span data-stu-id="81dce-144">To unassign a per-user archiving policy</span></span>

  - <span data-ttu-id="81dce-p106">La commande suivante annule l’assignation d’une stratégie d’archivage par utilisateur précédemment affectée à Ken Myer. Lorsque cette stratégie par utilisateur n’est plus assignée à Ken Myer, celui-ci est géré automatiquement par la stratégie globale ou, le cas échéant, par la stratégie de site locale associée. La stratégie de site est prioritaire sur la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="81dce-p106">The following command unassigns any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="81dce-148">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Grant-applet csarchivingpolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="81dce-148">For more information, see the help topic for the [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="81dce-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="81dce-149">See Also</span></span>


[<span data-ttu-id="81dce-150">Création d’une stratégie d’archivage dans Lync Server 2013 pour activer ou désactiver l’archivage des communications internes ou externes pour des sites ou utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="81dce-150">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for specific sites or users</span></span>](lync-server-2013-create-archiving-policy-sites-users.md)  


[<span data-ttu-id="81dce-151">Affectation de stratégies par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81dce-151">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

