---
title: 'Lync Server 2013: affecter une stratégie d’archivage par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f82b2398002a1c2536c9a57b18f9276a9d138903
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838758"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="67f00-102">Affecter une stratégie d’archivage par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67f00-102">Assign a per-user archiving policy in Lync Server 2013</span></span>

 


<span data-ttu-id="67f00-103">La stratégie d’archivage est l’un des paramètres individuels d’un compte d’utilisateur que vous pouvez configurer dans le panneau de configuration de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="67f00-103">The archiving policy is one of the individual settings of a user account that you can configure in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="67f00-104">Le déploiement d’une ou plusieurs stratégies d’archivage par utilisateur est facultatif.</span><span class="sxs-lookup"><span data-stu-id="67f00-104">Deploying one or more per-user archiving policies is optional.</span></span> <span data-ttu-id="67f00-105">Vous pouvez également déployer uniquement une stratégie d’archivage au niveau mondial ou une stratégie d’archivage au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="67f00-105">You can also deploy only a global-level archiving policy or site-level archiving policy.</span></span> <span data-ttu-id="67f00-106">Si vous déployez des stratégies au niveau utilisateur, vous devez les attribuer de manière explicite aux objets User, Group ou Contact.</span><span class="sxs-lookup"><span data-stu-id="67f00-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="67f00-107">Les exigences d’archivage définies automatiquement par défaut par celles définies dans la stratégie de conférence au niveau global s’il n’y a pas d’attribution de stratégies de niveau de site ou d’utilisateur spécifiques.</span><span class="sxs-lookup"><span data-stu-id="67f00-107">Archiving requirements automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="67f00-108">Après avoir créé au moins une stratégie d’archivage par utilisateur, suivez les procédures décrites dans cette rubrique pour affecter la stratégie qui détermine de manière appropriée si les communications internes d’un utilisateur particulier ou les deux sont archivées par le serveur.</span><span class="sxs-lookup"><span data-stu-id="67f00-108">After creating at least one per-user archiving policy, use the procedures in this topic to assign the policy that appropriately specifies whether a particular user’s internal communications, external communications, or both, will be archived by the server.</span></span>

<span data-ttu-id="67f00-109">Pour plus d’informations sur la création de stratégies d’archivage par utilisateur, reportez-vous à la rubrique [création d’une stratégie d’archivage dans Lync Server 2013 pour activer ou désactiver l’archivage des communications internes ou externes pour des sites ou des utilisateurs spécifiques](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md).</span><span class="sxs-lookup"><span data-stu-id="67f00-109">For details about creating per-user archiving policies, see [Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of Internal or external communications for specific sites or users](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md).</span></span>

## <a name="to-assign-a-per-user-archiving-policy"></a><span data-ttu-id="67f00-110">Pour attribuer une stratégie d’archivage par utilisateur</span><span class="sxs-lookup"><span data-stu-id="67f00-110">To assign a per-user archiving policy</span></span>

1.  <span data-ttu-id="67f00-111">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="67f00-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="67f00-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="67f00-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="67f00-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="67f00-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="67f00-114">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="67f00-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="67f00-115">Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="67f00-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="67f00-116">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="67f00-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="67f00-117">Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour rechercher la requête (un fichier .usf).</span><span class="sxs-lookup"><span data-stu-id="67f00-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="67f00-118">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="67f00-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="67f00-119">Cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="67f00-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="67f00-120">Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche de la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="67f00-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="67f00-121">Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).</span><span class="sxs-lookup"><span data-stu-id="67f00-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="67f00-122">Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="67f00-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="67f00-123">Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur <STRONG>Ajouter un filtre</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="67f00-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="67f00-124">Cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="67f00-124">Click **Find**.</span></span>

6.  <span data-ttu-id="67f00-125">Cliquez sur un utilisateur dans les résultats, puis sur **Action** et sur **Attribuer des stratégies**.</span><span class="sxs-lookup"><span data-stu-id="67f00-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="67f00-126">Si vous voulez appliquer la même stratégie d’archivage par utilisateur à plusieurs utilisateurs, sélectionnez plusieurs utilisateurs dans les résultats de la recherche, cliquez sur <STRONG>actions</STRONG>, puis sur <STRONG>affecter des stratégies</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="67f00-126">If you want the same per-user archiving policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="67f00-127">Dans **affecter des stratégies**, sous **stratégie**d’archivage, effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="67f00-127">In **Assign Policies**, under **Archiving policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="67f00-128">Dans la mesure où il existe plusieurs stratégies que vous pouvez configurer à l’aide de la boîte de dialogue <STRONG>affecter des stratégies</STRONG> , <STRONG> &lt;l’option conserver en tant que est&gt; </STRONG> activée par défaut pour chaque stratégie dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="67f00-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="67f00-129">Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.</span><span class="sxs-lookup"><span data-stu-id="67f00-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="67f00-130">Autorisez Lync Server 2013 à choisir automatiquement la stratégie de niveau global ou, s’il est défini, la stratégie au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="67f00-130">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="67f00-131">Cliquez sur le nom d’une stratégie d’archivage par utilisateur que vous avez précédemment définie dans la page **stratégie** d’archivage.</span><span class="sxs-lookup"><span data-stu-id="67f00-131">Click the name of a per-user archiving policy you previously defined on the **Archiving Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="67f00-132">Pour vous aider à décider de la stratégie que vous voulez attribuer, après avoir cliqué sur un nom de stratégie, cliquez sur <STRONG>Afficher</STRONG> pour afficher les droits d’utilisateur et les autorisations définis dans la stratégie.</span><span class="sxs-lookup"><span data-stu-id="67f00-132">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="67f00-133">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="67f00-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="67f00-134">Attribution d’une stratégie d’archivage par utilisateur à l’aide des applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="67f00-134">Assigning a Per-User Archiving Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="67f00-135">Vous pouvez attribuer des stratégies d’archivage par utilisateur à l’aide de Windows PowerShell et de l’applet **de passe Grant-CsArchivingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="67f00-135">You can assign per-user archiving policies by using Windows PowerShell and the **Grant-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="67f00-136">Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67f00-136">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="67f00-137">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».</span><span class="sxs-lookup"><span data-stu-id="67f00-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a><span data-ttu-id="67f00-138">Pour attribuer une stratégie d’archivage par utilisateur à un utilisateur unique</span><span class="sxs-lookup"><span data-stu-id="67f00-138">To assign a per-user archiving policy to a single user</span></span>

  - <span data-ttu-id="67f00-139">La commande suivante assigne la stratégie d’archivage par utilisateur RedmondArchivingPolicy à l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="67f00-139">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a><span data-ttu-id="67f00-140">Pour attribuer une stratégie d’archivage par utilisateur à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="67f00-140">To assign a per-user archiving policy to multiple users</span></span>

  - <span data-ttu-id="67f00-141">Cette commande affecte le RedmondArchivingPolicy de stratégie d’archivage par utilisateur à tous les utilisateurs disposant de comptes hébergés sur le pool d’inscriptions atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="67f00-141">This command assigns the per-user archiving policy RedmondArchivingPolicy to all the users who have accounts homed on the Registrar pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="67f00-142">Pour plus d’informations sur le paramètre de filtre utilisé dans cette commande, consultez la documentation de l’applet de commande [Get-Csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="67f00-142">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a><span data-ttu-id="67f00-143">Pour annuler l’affectation d’une stratégie d’archivage par utilisateur</span><span class="sxs-lookup"><span data-stu-id="67f00-143">To unassign a per-user archiving policy</span></span>

  - <span data-ttu-id="67f00-144">La commande suivante réattribue toutes les stratégies d’archivage par utilisateur précédemment affectées à Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="67f00-144">The following command unassigns any per-user archiving policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="67f00-145">Une fois l’affectation de la stratégie par utilisateur annulée, Ken Myer sera automatiquement géré en utilisant la stratégie globale ou, le cas échéant, sa stratégie de site local.</span><span class="sxs-lookup"><span data-stu-id="67f00-145">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="67f00-146">Une stratégie de site est prioritaire sur la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="67f00-146">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="67f00-147">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Grant-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/gg398475\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="67f00-147">For more information, see the help topic for the [Grant-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/gg398475\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="67f00-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="67f00-148">See Also</span></span>


[<span data-ttu-id="67f00-149">Création d’une stratégie d’archivage dans Lync Server 2013 pour activer ou désactiver l’archivage des communications internes ou externes pour des sites ou des utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="67f00-149">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of Internal or external communications for specific sites or users</span></span>](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md)  


[<span data-ttu-id="67f00-150">Attribution de stratégies par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67f00-150">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

