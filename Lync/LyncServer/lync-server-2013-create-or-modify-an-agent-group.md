---
title: 'Lync Server 2013 : création ou modification d’un groupe d’agents'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an agent group
ms:assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205370(v=OCS.15)
ms:contentKeyID: 48185784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b60ba1c402a629c0a85b2bd99dc4819da3455660
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202880"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="594e7-102">Création ou modification d’un groupe d’agents dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="594e7-102">Create or modify an agent group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="594e7-103">_**Dernière modification de la rubrique :** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="594e7-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="594e7-104">Utilisez l’une des procédures suivantes pour créer ou modifier un groupe d’agents.</span><span class="sxs-lookup"><span data-stu-id="594e7-104">Use one of the following procedures to create or modify an agent group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="594e7-105">Un administrateur, par exemple CsVoiceAdministrator, doit activer les utilisateurs pour voix entreprise et Lync Server pour que les utilisateurs puissent être attribués à des groupes d’agents.</span><span class="sxs-lookup"><span data-stu-id="594e7-105">An Administrator—for example, CsVoiceAdministrator—must enable users for Enterprise Voice and Lync Server before the users can be assigned to agent groups.</span></span> <span data-ttu-id="594e7-106">Si vous êtes l’un des responsables des groupes Response Group délégués pour un flux de travail géré, vous pouvez créer des groupes d’agents et utiliser les groupes d’agents dans les flux de travail que vous gérez.</span><span class="sxs-lookup"><span data-stu-id="594e7-106">If you are one of the delegated Response Group Managers for a managed workflow, you can create agent groups and use the agent groups in the workflows that you manage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="594e7-107">Lorsque vous affectez des utilisateurs en tant qu’agents au groupe de réponses, informez-les que, s’ils ont activé le mode de confidentialité, ils doivent rechercher des contacts « RGS Presence Watcher » et les ajouter à leur liste de contacts.</span><span class="sxs-lookup"><span data-stu-id="594e7-107">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list.</span></span> <span data-ttu-id="594e7-108">Les agents dont le mode de confidentialité est activé, mais qui n’ont pas « RGS presence Watcher » dans leur liste de contacts, ne peuvent pas recevoir d’appels vers le groupe Response Group.</span><span class="sxs-lookup"><span data-stu-id="594e7-108">Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group.</span></span> <span data-ttu-id="594e7-109">Cela ne concerne pas les agents qui n’ont pas activé le mode de confidentialité.</span><span class="sxs-lookup"><span data-stu-id="594e7-109">Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="594e7-110">Pour créer ou modifier un groupe d’agents à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="594e7-110">To use Lync Server Control Panel to create or modify an agent group</span></span>

1.  <span data-ttu-id="594e7-111">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="594e7-111">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="594e7-112">Si vous êtes l’un des responsables des groupes Response Group délégués pour un flux de travail géré, vous pouvez créer des groupes et les utiliser dans les flux de travail que vous gérez.</span><span class="sxs-lookup"><span data-stu-id="594e7-112">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="594e7-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="594e7-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="594e7-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="594e7-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="594e7-115">Dans la barre de navigation de gauche, cliquez sur **Groupes Response Group**, puis sur **Groupe**.</span><span class="sxs-lookup"><span data-stu-id="594e7-115">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="594e7-116">Sur la page **groupe** , effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="594e7-116">On the **Group** page, do one of the following:</span></span>
    
      - <span data-ttu-id="594e7-117">Pour créer un groupe d’agents, cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="594e7-117">To create a new agent group, click **New**.</span></span> <span data-ttu-id="594e7-118">Dans le champ de recherche **Sélectionner un service** , tapez entièrement ou partiellement le nom du service **ApplicationServer** auquel vous souhaitez ajouter le groupe.</span><span class="sxs-lookup"><span data-stu-id="594e7-118">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group.</span></span> <span data-ttu-id="594e7-119">Dans la liste des services obtenue, cliquez sur le service de votre choix, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="594e7-119">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="594e7-120">Pour modifier un groupe d’agents existant, tapez entièrement ou partiellement le nom du groupe d’agents dans le champ de recherche.</span><span class="sxs-lookup"><span data-stu-id="594e7-120">To modify an existing agent group, type all or part of the name of the agent group in the search field.</span></span> <span data-ttu-id="594e7-121">Dans la liste obtenue, cliquez sur le groupe de votre choix, cliquez sur **modifier**, puis sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="594e7-121">In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="594e7-122">Dans **nom**, tapez un nom d’identification pour le groupe d’agents.</span><span class="sxs-lookup"><span data-stu-id="594e7-122">In **Name**, type an identifying name for the agent group.</span></span>

6.  <span data-ttu-id="594e7-123">Dans **Description**, tapez la description du groupe.</span><span class="sxs-lookup"><span data-stu-id="594e7-123">In **Description**, type a description for the group.</span></span>

7.  <span data-ttu-id="594e7-124">Dans **Stratégie de participation**, sélectionnez l’une des options suivantes pour définir le comportement de connexion pour le groupe :</span><span class="sxs-lookup"><span data-stu-id="594e7-124">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
      - <span data-ttu-id="594e7-125">Sélectionnez **Informel** pour spécifier que les agents dans le groupe n’ont pas besoin de se connecter au groupe pour y accéder et de se déconnecter pour le quitter.</span><span class="sxs-lookup"><span data-stu-id="594e7-125">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="594e7-126">Les agents sont automatiquement connectés au groupe lorsqu’ils se connectent à Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="594e7-126">Agents are automatically signed in to the group when they sign in to Lync Server 2013.</span></span>
    
      - <span data-ttu-id="594e7-127">Sélectionnez **Formel** pour spécifier que les agents sont obligés de se connecter au groupe pour y accéder et de se déconnecter pour le quitter.</span><span class="sxs-lookup"><span data-stu-id="594e7-127">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="594e7-128">Lorsque vous sélectionnez cette option, les agents cliquent sur un élément de menu dans Lync pour ouvrir Internet Explorer et afficher une console de page Web pour la connexion et la déconnexion du groupe.</span><span class="sxs-lookup"><span data-stu-id="594e7-128">When you select this option, agents click a menu item in Lync to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

8.  <span data-ttu-id="594e7-129">Dans **Temps d’alerte (secondes)**, spécifiez combien de temps (en secondes) un appel doit sonner pour qu’il soit transmis à un agent disponible si l’agent auquel l’appel était initialement destiné ne peut pas y répondre (la durée par défaut est 20 secondes).</span><span class="sxs-lookup"><span data-stu-id="594e7-129">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="594e7-130">Le paramètre de durée d’alerte de l’agent ne peut pas dépasser 180 secondes.</span><span class="sxs-lookup"><span data-stu-id="594e7-130">The agent alert time setting cannot exceed 180 seconds.</span></span> <span data-ttu-id="594e7-131">Si la durée d’alerte de l’agent dépasse 180 secondes, l’application cliente rejette l’appel car le minuteur de la transaction SIP atteint le temps d’attente maximal.</span><span class="sxs-lookup"><span data-stu-id="594e7-131">If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

9.  <span data-ttu-id="594e7-132">Dans **Méthode de routage**, sélectionnez la méthode pour transmettre les appels aux agents dans le groupe comme suit :</span><span class="sxs-lookup"><span data-stu-id="594e7-132">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
      - <span data-ttu-id="594e7-133">Pour proposer un nouvel appel à l’agent qui a été inactif le plus longtemps (dont la présence est **disponible** ou **inactive** dans Lync Server le plus longtemps), cliquez sur le plus longtemps **inactif**.</span><span class="sxs-lookup"><span data-stu-id="594e7-133">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Lync Server the longest), click **Longest idle**.</span></span>
    
      - <span data-ttu-id="594e7-p109">Pour qu’un nouvel appel soit présenté à tous les agents disponibles simultanément, cliquez sur **Parallèle**. L’appel est envoyé au premier agent qui l’accepte.</span><span class="sxs-lookup"><span data-stu-id="594e7-p109">To offer a new call to all available agents at the same time, click **Parallel**. The call is sent to the first agent who accepts it.</span></span>
    
      - <span data-ttu-id="594e7-136">Pour qu’un nouvel appel soit présenté à chaque agent, à tour de rôle, cliquez sur **Tourniquet (round robin)**.</span><span class="sxs-lookup"><span data-stu-id="594e7-136">To offer a new call to each agent in turn, click **Round robin**.</span></span>
    
      - <span data-ttu-id="594e7-137">Pour qu’un nouvel appel soit toujours présenté aux agents dans l’ordre dans lequel ils apparaissent dans la liste **Agents**, cliquez sur **Série**.</span><span class="sxs-lookup"><span data-stu-id="594e7-137">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span>
    
      - <span data-ttu-id="594e7-138">Pour proposer un nouvel appel à tous les agents connectés à Lync Server 2013 et à l’application Response Group en même temps, quelle que soit leur présence actuelle, cliquez sur **surveillance**.</span><span class="sxs-lookup"><span data-stu-id="594e7-138">To offer a new call to all agents who are signed into Lync Server 2013 and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="594e7-139">Les utilisateurs de la surveillance de Lync 2010 configurés comme agents peuvent voir tous les appels en attente et répondre aux appels en attente dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="594e7-139">Lync 2010 Attendant users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="594e7-140">L’appel est envoyé au premier agent qui l’accepte, après quoi les autres utilisateurs de la surveillance de Lync 2010 ne voient plus l’appel.</span><span class="sxs-lookup"><span data-stu-id="594e7-140">The call is sent to the first agent who accepts it, after which the other Lync 2010 Attendant users no longer see the call.</span></span>

10. <span data-ttu-id="594e7-141">Dans **Agents**, spécifiez comment vous voulez créer votre liste d’agents :</span><span class="sxs-lookup"><span data-stu-id="594e7-141">In **Agents**, specify how you want to create your agents list:</span></span>
    
      - <span data-ttu-id="594e7-142">Pour utiliser une liste d’agents personnalisée, cliquez sur **définir un groupe personnalisé d’agents**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="594e7-142">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
        
          - <span data-ttu-id="594e7-143">Pour ajouter un utilisateur au groupe d’agents, cliquez sur **Sélectionner**, puis dans le champ de recherche **Sélectionner des agents** , tapez entièrement ou partiellement le nom de l’utilisateur que vous souhaitez ajouter à ce groupe, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="594e7-143">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**.</span></span> <span data-ttu-id="594e7-144">Dans la liste des agents obtenue, cliquez sur l’utilisateur, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="594e7-144">In the resulting list of agents, click the user, and then click **OK**.</span></span>
        
          - <span data-ttu-id="594e7-145">Pour supprimer un utilisateur du groupe d’agents, dans la liste des agents, cliquez sur l’utilisateur que vous souhaitez supprimer, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="594e7-145">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
        
          - <span data-ttu-id="594e7-146">Pour modifier l’ordre dans lequel les appels sont proposés aux agents dans des groupes qui utilisent le routage à répétition alternée ou le routage en série, dans la liste des agents, cliquez sur un utilisateur, puis sur la flèche vers le haut ou la flèche vers le bas.</span><span class="sxs-lookup"><span data-stu-id="594e7-146">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span>
    
      - <span data-ttu-id="594e7-147">Pour utiliser une liste de distribution Microsoft Exchange Server en tant que groupe d’agents, cliquez sur **utiliser une liste de distribution de courrier électronique existante**, puis, dans adresse de la **liste de distribution**, tapez l’adresse de messagerie de la liste de distribution (par exemple, NetworkSupport@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="594e7-147">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
        
        <span data-ttu-id="594e7-148">Si vous utilisez une liste de distribution de courrier électronique, vous êtes soumis aux contraintes suivantes :</span><span class="sxs-lookup"><span data-stu-id="594e7-148">If you use an email distribution list, you are subject to the following constraints:</span></span>
        
          - <span data-ttu-id="594e7-p112">Vous ne pouvez pas sélectionner plusieurs listes de distribution pour le groupe d’agents. Chaque groupe prend en charge une seule liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="594e7-p112">You cannot select multiple distribution lists for the agent group. Each group supports only a single distribution list.</span></span>
        
          - <span data-ttu-id="594e7-151">Si la liste de distribution contient une ou plusieurs listes de distribution, les membres des listes de distribution imbriquées ne sont pas ajoutés à la liste d’agents.</span><span class="sxs-lookup"><span data-stu-id="594e7-151">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
        
          - <span data-ttu-id="594e7-152">Si le routage série ou tourniquet est sélectionné, le serveur offre un appel entrant à l’agent approprié en fonction de la méthode de routage et en fonction de l’ordre dans lequel les agents sont répertoriés dans la liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="594e7-152">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
        
          - <span data-ttu-id="594e7-153">Si la liste de distribution contient des utilisateurs pour lesquels Lync Server 2010 est activé mais que voix entreprise n’est pas activé, ils seront ajoutés au groupe d’agents en tant qu’agents incorrects.</span><span class="sxs-lookup"><span data-stu-id="594e7-153">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents.</span></span> <span data-ttu-id="594e7-154">Assurez-vous que voix entreprise est activé pour les comptes d’utilisateur de tous les membres de la liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="594e7-154">Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="594e7-155">Si vous utilisez une liste de distribution de courrier électronique, les appartenances masquées ou les listes masquées peuvent devenir visibles par l’administrateur ou les utilisateurs du groupe Response Group.</span><span class="sxs-lookup"><span data-stu-id="594e7-155">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span>

        
        </div>
        
        <span data-ttu-id="594e7-156">Les appartenances au groupe d’agents masquées ou les listes masquées peuvent devenir visibles comme suit :</span><span class="sxs-lookup"><span data-stu-id="594e7-156">Hidden memberships or hidden lists can become visible as follows:</span></span>
        
          - <span data-ttu-id="594e7-157">Si une liste de distribution a été configurée de sorte que l’appartenance est masquée et que l’administrateur du groupe réponse affecte la liste de distribution à la liste des agents, les utilisateurs peuvent appeler le groupe pour connaître l’identité des membres.</span><span class="sxs-lookup"><span data-stu-id="594e7-157">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span>
        
          - <span data-ttu-id="594e7-158">Si une liste de distribution a été configurée de sorte qu’elle soit masquée dans la liste d’adresses globale d’Exchange, l’administrateur de Response Group peut voir la liste de distribution et l’affecter à la liste des agents si le processus Response Group dispose des droits d’utilisateur appropriés et autorisations, même si l’administrateur ne dispose pas des droits d’utilisateur et des autorisations appropriés.</span><span class="sxs-lookup"><span data-stu-id="594e7-158">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>

11. <span data-ttu-id="594e7-159">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="594e7-159">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="594e7-160">Pour utiliser Windows PowerShell afin de créer ou de modifier un groupe d’agents</span><span class="sxs-lookup"><span data-stu-id="594e7-160">To use Windows PowerShell to create or modify an agent group</span></span>

1.  <span data-ttu-id="594e7-161">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="594e7-161">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="594e7-162">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="594e7-162">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="594e7-163">Utilisez **New-CsRgsAgentGroup** pour créer un groupe d’agents.</span><span class="sxs-lookup"><span data-stu-id="594e7-163">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="594e7-164">Utilisez **Set-CsRgsAgentGroup** pour modifier un groupe d’agents existant.</span><span class="sxs-lookup"><span data-stu-id="594e7-164">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="594e7-165">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="594e7-165">At the command line, run:</span></span>
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    <span data-ttu-id="594e7-166">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="594e7-166">For example:</span></span>
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="594e7-167">Le paramètre de durée d’alerte de l’agent ne peut pas dépasser 180 secondes.</span><span class="sxs-lookup"><span data-stu-id="594e7-167">The agent alert time setting cannot exceed 180 seconds.</span></span> <span data-ttu-id="594e7-168">Si la durée de l’alerte de l’agent est supérieure à 180 secondes, l’application cliente rejette l’appel car le minuteur de la transaction SIP atteint le temps d’attente maximal.</span><span class="sxs-lookup"><span data-stu-id="594e7-168">If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

4.  <span data-ttu-id="594e7-169">Vérifiez que le groupe d’agents est créé.</span><span class="sxs-lookup"><span data-stu-id="594e7-169">Confirm that the agent group is created.</span></span> <span data-ttu-id="594e7-170">Générer</span><span class="sxs-lookup"><span data-stu-id="594e7-170">Run:</span></span>
    
        Get-CsRgsAgentGroup -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="594e7-171">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="594e7-171">See Also</span></span>


[<span data-ttu-id="594e7-172">Supprimer un groupe d’agents dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="594e7-172">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)  


[<span data-ttu-id="594e7-173">Gestion des groupes d’agents Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="594e7-173">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)  
[<span data-ttu-id="594e7-174">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="594e7-174">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="594e7-175">New-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="594e7-175">New-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup)  
[<span data-ttu-id="594e7-176">Set-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="594e7-176">Set-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsAgentGroup)  
[<span data-ttu-id="594e7-177">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="594e7-177">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

