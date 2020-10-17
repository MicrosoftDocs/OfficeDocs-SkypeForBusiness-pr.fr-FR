---
title: 'Lync Server 2013 : affecter une stratégie de conversation permanente par utilisateur'
description: 'Lync Server 2013 : affectez une stratégie de conversation permanente par utilisateur.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user Persistent Chat policy
ms:assetid: e22168f2-fde1-4f0a-b194-1fc881436822
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721908(v=OCS.15)
ms:contentKeyID: 49733842
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 637f1947fff7f4e919e5f9c252c047b2d0e60392
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563600"
---
# <a name="assign-a-per-user-persistent-chat-policy-in-lync-server-2013"></a><span data-ttu-id="08868-103">Affectation d’une stratégie de conversation permanente par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08868-103">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>

 


<span data-ttu-id="08868-104">Vous pouvez affecter une stratégie de conversation permanente par utilisateur avec le panneau de configuration Lync Server 2013 ou Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="08868-104">You can assign a per-user persistent chat policy with either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="08868-105">Pour plus d’informations sur la création de stratégies utilisateur pour le serveur de conversation permanente, voir [Create a User Policy for persistent chat in Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="08868-105">For details on creating user policies for Persistent Chat Server, see [Create a user policy for Persistent Chat in Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-with-lync-server-control-panel"></a><span data-ttu-id="08868-106">Pour affecter une stratégie de conversation permanente par utilisateur à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="08868-106">To assign a per-user persistent chat policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="08868-107">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="08868-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="08868-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="08868-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="08868-109">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="08868-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="08868-110">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="08868-110">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="08868-111">Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="08868-111">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="08868-112">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="08868-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="08868-113">Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour localiser la requête (un fichier .usf).</span><span class="sxs-lookup"><span data-stu-id="08868-113">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="08868-114">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="08868-114">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="08868-115">Cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="08868-115">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="08868-116">Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="08868-116">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="08868-117">Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).</span><span class="sxs-lookup"><span data-stu-id="08868-117">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="08868-118">Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="08868-118">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="08868-119">Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur <STRONG>Ajouter un filtre</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="08868-119">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="08868-120">Cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="08868-120">Click **Find**.</span></span>

6.  <span data-ttu-id="08868-121">Cliquez sur un utilisateur dans les résultats, puis sur **Action** et sur **Attribuer des stratégies**.</span><span class="sxs-lookup"><span data-stu-id="08868-121">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="08868-122">Si vous voulez que la même stratégie de conversation permanente par utilisateur s’applique à plusieurs utilisateurs, sélectionnez plusieurs utilisateurs dans les résultats de la recherche, puis cliquez sur <STRONG>actions</STRONG>et sur <STRONG>attribuer des stratégies</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="08868-122">If you want the same per-user persistent Chat policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="08868-123">Dans **attribuer des stratégies**, sous **stratégie de conversation permanente**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="08868-123">In **Assign Policies**, under **Persistent Chat policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="08868-124">Étant donné qu’il existe plusieurs stratégies que vous pouvez configurer à l’aide de la boîte de dialogue <STRONG>affecter les stratégies</STRONG> , l’option <STRONG> &lt; conserver en tant que est &gt; </STRONG> sélectionnée par défaut pour chaque stratégie dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="08868-124">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="08868-125">Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.</span><span class="sxs-lookup"><span data-stu-id="08868-125">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="08868-126">Sélectionnez cette option **\<Automatic\>** pour autoriser Lync Server 2013 à choisir automatiquement la stratégie au niveau global ou, si elle est définie, la stratégie au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="08868-126">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="08868-127">Cliquez sur le nom d’une stratégie de conversation permanente par utilisateur que vous avez précédemment définie dans la page **stratégie de conversation permanente** .</span><span class="sxs-lookup"><span data-stu-id="08868-127">Click the name of a per-user Persistent Chat policy you previously defined on the **Persistent Chat Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="08868-128">Pour vous aider à décider quelle stratégie attribuer, après avoir cliqué sur un nom de stratégie, cliquez sur <STRONG>Afficher</STRONG> pour afficher les droits et autorisations des utilisateurs définis dans la stratégie.</span><span class="sxs-lookup"><span data-stu-id="08868-128">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="08868-129">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="08868-129">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-persistent-chat-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="08868-130">Affectation d’une stratégie de conversation permanente Per-User à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="08868-130">Assigning a Per-User Persistent Chat Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="08868-131">Vous pouvez également affecter des stratégies de conversation permanente par utilisateur à l’aide de la cmdlet **Grant-CsPersistentChatPolicy** .</span><span class="sxs-lookup"><span data-stu-id="08868-131">You can also assign per-user persistent chat policies by using the **Grant-CsPersistentChatPolicy** cmdlet.</span></span> <span data-ttu-id="08868-132">Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08868-132">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="08868-133">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="08868-133">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-to-a-single-user"></a><span data-ttu-id="08868-134">Pour affecter une stratégie de conversation permanente par utilisateur à un seul utilisateur</span><span class="sxs-lookup"><span data-stu-id="08868-134">To assign a per-user persistent chat policy to a single user</span></span>

  - <span data-ttu-id="08868-135">La commande suivante affecte la stratégie de conversation persistante par utilisateur RedmondPersistentChatPolicy à l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="08868-135">The following command assigns the per-user Persistent Chat policy RedmondPersistentChatPolicy to the user Ken Myer.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## <a name="to-assign-a-per-user-persistent-chat-policy-to-multiple-users"></a><span data-ttu-id="08868-136">Pour affecter une stratégie de conversation permanente par utilisateur à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="08868-136">To assign a per-user persistent chat policy to multiple users</span></span>

  - <span data-ttu-id="08868-137">Cette commande affecte la stratégie de conversation persistante par utilisateur RedmondUsersPersistentChatPolicy à tous les utilisateurs qui travaillent pour le service informatique.</span><span class="sxs-lookup"><span data-stu-id="08868-137">This command assigns the per-user Persistent Chat policy RedmondUsersPersistentChatPolicy to all the users who work for the IT department.</span></span> <span data-ttu-id="08868-138">Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, reportez-vous à la documentation de la cmdlet [Get-Csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="08868-138">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## <a name="to-unassign-a-per-user-persistent-chat-policy"></a><span data-ttu-id="08868-139">Pour annuler l’affectation d’une stratégie de conversation permanente par utilisateur</span><span class="sxs-lookup"><span data-stu-id="08868-139">To unassign a per-user persistent chat policy</span></span>

  - <span data-ttu-id="08868-140">La commande suivante annule l’affectation d’une stratégie de conversation permanente par utilisateur précédemment affectée à Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="08868-140">The following command unassigns any per-user Persistent Chat policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="08868-141">Lorsque cette stratégie par utilisateur n’est plus assignée à Ken Myer, celui-ci est géré automatiquement par la stratégie globale ou, le cas échéant, par la stratégie de site locale associée.</span><span class="sxs-lookup"><span data-stu-id="08868-141">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="08868-142">La stratégie de site est prioritaire sur la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="08868-142">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="08868-143">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/library/jj204907\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="08868-143">For more information, see the help topic for the [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/library/jj204907\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="08868-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="08868-144">See Also</span></span>


[<span data-ttu-id="08868-145">Créer une stratégie utilisateur pour la conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08868-145">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

