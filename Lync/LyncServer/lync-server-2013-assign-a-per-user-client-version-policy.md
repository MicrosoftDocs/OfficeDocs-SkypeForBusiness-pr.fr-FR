---
title: 'Lync Server 2013 : affecter une stratégie de version de client par utilisateur'
description: 'Lync Server 2013 : affectez une stratégie de version de client par utilisateur.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user client version policy
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48185868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ec2fcbf9c005806a97dfbdceb22095fe0ff8f33
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559976"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="01be4-103">Affecter une stratégie de version de client par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01be4-103">Assign a per-user client version policy in Lync Server 2013</span></span>

 


<span data-ttu-id="01be4-104">La stratégie de version du client est l’un des paramètres individuels d’un compte d’utilisateur que vous pouvez configurer dans le panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="01be4-104">The client version policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="01be4-105">Le déploiement d’une ou plusieurs stratégies de version du client par utilisateur est facultatif.</span><span class="sxs-lookup"><span data-stu-id="01be4-105">Deploying one or more per-user client version policies is optional.</span></span> <span data-ttu-id="01be4-106">Vous pouvez également ne déployer qu’une stratégie de version du client au niveau global, ou encore déployer des stratégies de version du client au niveau du site ou du pool.</span><span class="sxs-lookup"><span data-stu-id="01be4-106">You can also deploy only a global-level client version policy, or site-level or pool-level client version policies.</span></span> <span data-ttu-id="01be4-107">Si vous déployez des stratégies au niveau utilisateur, vous devez les attribuer de manière explicite aux objets User, Group ou Contact.</span><span class="sxs-lookup"><span data-stu-id="01be4-107">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="01be4-108">Lorsqu’aucune stratégie spécifique au niveau du site, du pool ou par utilisateur n’est affectée, les clients par défaut autorisés à s’inscrire auprès de Lync Server 2013 sont ceux définis dans la stratégie de version du client au niveau global.</span><span class="sxs-lookup"><span data-stu-id="01be4-108">When no specific site-level, pool-level, or per-user policy is assigned, the default clients that are allowed to register with Lync Server 2013 are those defined in the global-level client version policy.</span></span>

<span data-ttu-id="01be4-109">Après avoir créé au moins une stratégie de version de client par utilisateur, utilisez les procédures de cette rubrique pour affecter la stratégie qui spécifie les versions du client que vous souhaitez autoriser à s’inscrire auprès de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="01be4-109">After creating at least one per-user client version policy, use the procedures in this topic to assign the policy that specifies the client versions that you want to allow to register with Lync Server.</span></span>

<span data-ttu-id="01be4-110">Pour plus d’informations sur la création de stratégies de version de client par utilisateur, voir [spécification des applications clientes pouvant être utilisées pour se connecter à Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="01be4-110">For details about creating per-user client version policies, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span></span>

## <a name="to-assign-a-per-user-client-version-policy"></a><span data-ttu-id="01be4-111">Pour affecter une stratégie de version du client par utilisateur</span><span class="sxs-lookup"><span data-stu-id="01be4-111">To assign a per-user client version policy</span></span>

1.  <span data-ttu-id="01be4-112">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="01be4-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="01be4-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="01be4-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="01be4-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="01be4-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="01be4-115">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="01be4-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="01be4-116">Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="01be4-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="01be4-117">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="01be4-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="01be4-118">Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour localiser la requête (un fichier .usf).</span><span class="sxs-lookup"><span data-stu-id="01be4-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="01be4-119">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="01be4-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="01be4-120">Cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="01be4-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="01be4-121">Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="01be4-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="01be4-122">Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).</span><span class="sxs-lookup"><span data-stu-id="01be4-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="01be4-123">Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="01be4-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="01be4-124">Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur <STRONG>Ajouter un filtre</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="01be4-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="01be4-125">Cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="01be4-125">Click **Find**.</span></span>

6.  <span data-ttu-id="01be4-126">Cliquez sur un utilisateur dans les résultats, puis sur **Action** et sur **Attribuer des stratégies**.</span><span class="sxs-lookup"><span data-stu-id="01be4-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="01be4-127">Si vous voulez que la même stratégie de version du client par utilisateur s’applique à plusieurs utilisateurs, sélectionnez plusieurs utilisateurs dans les résultats de la recherche, puis cliquez sur <STRONG>Actions</STRONG> et sur <STRONG>Attribuer des stratégies</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="01be4-127">If you want the same per-user client version policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="01be4-128">Dans **Attribuer des stratégies**, sous **Stratégie de version du client**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="01be4-128">In **Assign Policies**, under **Client version policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="01be4-129">Étant donné qu’il existe plusieurs stratégies que vous pouvez configurer à l’aide de la boîte de dialogue <STRONG>affecter les stratégies</STRONG> , l’option <STRONG> &lt; conserver en tant que est &gt; </STRONG> sélectionnée par défaut pour chaque stratégie dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="01be4-129">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="01be4-130">Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.</span><span class="sxs-lookup"><span data-stu-id="01be4-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="01be4-131">Autoriser Lync Server à choisir automatiquement la stratégie au niveau global ou, si elle est définie, la stratégie au niveau du site ou la stratégie au niveau du pool.</span><span class="sxs-lookup"><span data-stu-id="01be4-131">Allow Lync Server to automatically choose either the global-level policy or, if defined, the site-level policy or pool-level policy.</span></span>
    
      - <span data-ttu-id="01be4-132">Cliquez sur le nom d’une stratégie de version du client par utilisateur que vous avez précédemment définie sur la page **Stratégie de version du client**.</span><span class="sxs-lookup"><span data-stu-id="01be4-132">Click the name of a per-user client version policy you previously defined on the **Client Version Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="01be4-133">Pour vous aider à décider quelle stratégie attribuer, après avoir cliqué sur un nom de stratégie, cliquez sur <STRONG>Afficher</STRONG> pour afficher les droits et autorisations des utilisateurs définis dans la stratégie.</span><span class="sxs-lookup"><span data-stu-id="01be4-133">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="01be4-134">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01be4-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="01be4-135">Affectation d’une stratégie de version de client de Per-User à l’aide d’applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="01be4-135">Assigning a Per-User Client Version Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="01be4-136">Vous pouvez affecter des stratégies de version du client par utilisateur en utilisant la cmdlet Grant-CsClientVersionPolicy cmdlet.</span><span class="sxs-lookup"><span data-stu-id="01be4-136">You can assign per-user client version policies by using the Grant-CsClientVersionPolicy cmdlet.</span></span> <span data-ttu-id="01be4-137">Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01be4-137">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="01be4-138">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="01be4-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a><span data-ttu-id="01be4-139">Pour affecter une stratégie de version du client par utilisateur à un seul utilisateur</span><span class="sxs-lookup"><span data-stu-id="01be4-139">To assign a per-user client version policy to a single user</span></span>

  - <span data-ttu-id="01be4-140">La commande suivante affecte la stratégie de version du client par utilisateur RedmondClientVersionPolicy à l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="01be4-140">The following command assigns the per-user client version policy RedmondClientVersionPolicy to the user Ken Myer.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a><span data-ttu-id="01be4-141">Pour affecter une stratégie de version du client par utilisateur à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="01be4-141">To assign a per-user client version policy to multiple users</span></span>

  - <span data-ttu-id="01be4-142">Cette commande affecte la stratégie de version du client par utilisateur RedmondClientVersionPolicy à tous les utilisateurs actuellement affectés à la stratégie vocale RedmondVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="01be4-142">This command assigns the per-user client version policy RedmondClientVersionPolicy to all the users who are currently assigned the voice policy RedmondVoicePolicy.</span></span> <span data-ttu-id="01be4-143">Pour plus d’informations sur le paramètre Filter utilisé dans cette commande, reportez-vous à la documentation de la cmdlet [Get-Csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="01be4-143">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a><span data-ttu-id="01be4-144">Pour annuler l’affectation d’une stratégie de version du client par utilisateur</span><span class="sxs-lookup"><span data-stu-id="01be4-144">To unassign a per-user client version policy</span></span>

  - <span data-ttu-id="01be4-p106">La commande suivante annule l’affectation de toute stratégie de version du client par utilisateur affectée à Ken Myer. Une fois l’affectation de la stratégie par utilisateur annulée, Ken Myer sera automatiquement géré en utilisant la stratégie globale, sa stratégie de site locale (le cas échéant), ou la stratégie d’étendue de service affectée à son serveur d’inscription. Une stratégie d’étendue de service est prioritaire sur les stratégies de site, et une stratégie de site est prioritaire sur la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="01be4-p106">The following command unassigns any per-user client version policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy, his local site policy (if one exists), or the service-scope policy assigned to his Registrar. A service scope policy takes precedence over any site policy, and a site policy takes precedence over the global policy.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="01be4-148">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/gg412903\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="01be4-148">For more information, see the help topic for the [Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/gg412903\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="01be4-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="01be4-149">See Also</span></span>


[<span data-ttu-id="01be4-150">Affectation de stratégies par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01be4-150">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
[<span data-ttu-id="01be4-151">Gestion des appareils, des téléphones et des applications clientes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01be4-151">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)

