---
title: 'Lync Server 2013 : affecter une stratégie de version de client par utilisateur'
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
ms.openlocfilehash: e509427b6d2651f84b96a96c87fbe7cfd6177a7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738374"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="9b8d3-102">Affecter une stratégie de version de client par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b8d3-102">Assign a per-user client version policy in Lync Server 2013</span></span>

 


<span data-ttu-id="9b8d3-103">La stratégie de version du client est l’un des paramètres individuels d’un compte d’utilisateur que vous pouvez configurer dans le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-103">The client version policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="9b8d3-104">Le déploiement d’une ou plusieurs stratégies de version de client par utilisateur est facultatif.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-104">Deploying one or more per-user client version policies is optional.</span></span> <span data-ttu-id="9b8d3-105">Vous pouvez également déployer uniquement une stratégie de version de client de niveau global, ou des stratégies de version de client de niveau de site ou de groupe.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-105">You can also deploy only a global-level client version policy, or site-level or pool-level client version policies.</span></span> <span data-ttu-id="9b8d3-106">Si vous déployez des stratégies au niveau utilisateur, vous devez les attribuer de manière explicite aux objets User, Group ou Contact.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="9b8d3-107">S’il n’y a pas d’attribution de stratégies de niveau de site, de pool ou par utilisateur spécifiques, les clients par défaut autorisés à s’inscrire auprès de Lync Server 2013 sont ceux définis dans la stratégie de version de client de niveau global.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-107">When no specific site-level, pool-level, or per-user policy is assigned, the default clients that are allowed to register with Lync Server 2013 are those defined in the global-level client version policy.</span></span>

<span data-ttu-id="9b8d3-108">Après avoir créé au moins une stratégie de version de client par utilisateur, suivez les procédures décrites dans cette rubrique pour affecter la stratégie spécifiant les versions de clients que vous voulez autoriser à inscrire sur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-108">After creating at least one per-user client version policy, use the procedures in this topic to assign the policy that specifies the client versions that you want to allow to register with Lync Server.</span></span>

<span data-ttu-id="9b8d3-109">Pour plus d’informations sur la création de stratégies de version de client par utilisateur, voir [spécification des applications clientes qui peuvent être utilisées pour la connexion à Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="9b8d3-109">For details about creating per-user client version policies, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span></span>

## <a name="to-assign-a-per-user-client-version-policy"></a><span data-ttu-id="9b8d3-110">Pour attribuer une stratégie de version de client par utilisateur</span><span class="sxs-lookup"><span data-stu-id="9b8d3-110">To assign a per-user client version policy</span></span>

1.  <span data-ttu-id="9b8d3-111">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9b8d3-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9b8d3-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9b8d3-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9b8d3-114">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="9b8d3-115">Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="9b8d3-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="9b8d3-116">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="9b8d3-117">Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour rechercher la requête (un fichier .usf).</span><span class="sxs-lookup"><span data-stu-id="9b8d3-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="9b8d3-118">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="9b8d3-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="9b8d3-119">Cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="9b8d3-120">Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche de la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="9b8d3-121">Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).</span><span class="sxs-lookup"><span data-stu-id="9b8d3-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="9b8d3-122">Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="9b8d3-123">Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur <STRONG>Ajouter un filtre</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="9b8d3-124">Cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-124">Click **Find**.</span></span>

6.  <span data-ttu-id="9b8d3-125">Cliquez sur un utilisateur dans les résultats, puis sur **Action** et sur **Attribuer des stratégies**.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="9b8d3-126">Si vous voulez appliquer la même stratégie de version de client par utilisateur à plusieurs utilisateurs, sélectionnez plusieurs utilisateurs dans les résultats de la recherche, cliquez sur <STRONG>actions</STRONG>, puis sur <STRONG>affecter des stratégies</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-126">If you want the same per-user client version policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="9b8d3-127">Dans **affecter des stratégies**, sous **stratégie de version de client**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9b8d3-127">In **Assign Policies**, under **Client version policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="9b8d3-128">Dans la mesure où il existe plusieurs stratégies que vous pouvez configurer à l’aide de la boîte de dialogue <STRONG>affecter des stratégies</STRONG> , <STRONG> &lt;l’option conserver en tant que est&gt; </STRONG> activée par défaut pour chaque stratégie dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="9b8d3-129">Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="9b8d3-130">Autorisez le serveur Lync à choisir automatiquement la stratégie de niveau global ou, si elle est définie, la stratégie de niveau du site ou la stratégie de niveau groupe.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-130">Allow Lync Server to automatically choose either the global-level policy or, if defined, the site-level policy or pool-level policy.</span></span>
    
      - <span data-ttu-id="9b8d3-131">Cliquez sur le nom d’une stratégie de version de client par utilisateur que vous avez précédemment définie sur la page de **stratégie de version du client** .</span><span class="sxs-lookup"><span data-stu-id="9b8d3-131">Click the name of a per-user client version policy you previously defined on the **Client Version Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="9b8d3-132">Pour vous aider à décider quelle stratégie attribuer, après avoir cliqué sur un nom de stratégie, cliquez sur <STRONG>Afficher</STRONG> pour afficher les droits et autorisations des utilisateurs définis dans la stratégie.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-132">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="9b8d3-133">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9b8d3-134">Attribution d’une stratégie de version de client par utilisateur à l’aide des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b8d3-134">Assigning a Per-User Client Version Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9b8d3-135">Vous pouvez affecter des stratégies de version de client par utilisateur à l’aide de l’applet de contrôle Grant-CsClientVersionPolicy.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-135">You can assign per-user client version policies by using the Grant-CsClientVersionPolicy cmdlet.</span></span> <span data-ttu-id="9b8d3-136">Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-136">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9b8d3-137">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="9b8d3-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a><span data-ttu-id="9b8d3-138">Pour attribuer une stratégie de version de client par utilisateur à un utilisateur unique</span><span class="sxs-lookup"><span data-stu-id="9b8d3-138">To assign a per-user client version policy to a single user</span></span>

  - <span data-ttu-id="9b8d3-139">La commande suivante assigne le RedmondClientVersionPolicy de la stratégie de version du client par utilisateur à l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-139">The following command assigns the per-user client version policy RedmondClientVersionPolicy to the user Ken Myer.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a><span data-ttu-id="9b8d3-140">Pour attribuer une stratégie de version de client par utilisateur à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="9b8d3-140">To assign a per-user client version policy to multiple users</span></span>

  - <span data-ttu-id="9b8d3-141">Cette commande affecte la stratégie de version de client RedmondClientVersionPolicy à tous les utilisateurs auxquels est actuellement affectée le RedmondVoicePolicy de la stratégie vocale.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-141">This command assigns the per-user client version policy RedmondClientVersionPolicy to all the users who are currently assigned the voice policy RedmondVoicePolicy.</span></span> <span data-ttu-id="9b8d3-142">Pour plus d’informations sur le paramètre de filtre utilisé dans cette commande, consultez la documentation de l’applet de commande [Get-Csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="9b8d3-142">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a><span data-ttu-id="9b8d3-143">Pour annuler l’affectation d’une stratégie de version de client par utilisateur</span><span class="sxs-lookup"><span data-stu-id="9b8d3-143">To unassign a per-user client version policy</span></span>

  - <span data-ttu-id="9b8d3-144">La commande suivante annule l’affectation d’une stratégie de version de client par utilisateur précédemment attribuée à Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-144">The following command unassigns any per-user client version policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="9b8d3-145">Après l’affectation de la stratégie par utilisateur, Ken Myer sera automatiquement géré à l’aide de la stratégie globale, de sa stratégie de site local (s’il en existe une) ou de la stratégie de portée de service attribuée à son bureau d’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-145">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy, his local site policy (if one exists), or the service-scope policy assigned to his Registrar.</span></span> <span data-ttu-id="9b8d3-146">Une stratégie d’étendue de service est prioritaire sur n’importe quelle stratégie de site, et une stratégie de site est prioritaire par rapport à la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="9b8d3-146">A service scope policy takes precedence over any site policy, and a site policy takes precedence over the global policy.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="9b8d3-147">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/gg412903\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="9b8d3-147">For more information, see the help topic for the [Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/gg412903\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b8d3-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9b8d3-148">See Also</span></span>


[<span data-ttu-id="9b8d3-149">Attribution de stratégies par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b8d3-149">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
[<span data-ttu-id="9b8d3-150">Gestion des appareils, des téléphones et des applications client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b8d3-150">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)

