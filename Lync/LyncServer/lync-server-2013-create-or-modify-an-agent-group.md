---
title: 'Lync Server 2013 : créer ou modifier un groupe d’agents'
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
ms.openlocfilehash: 99fed5bf80979ef807f45ce7e5ecdc8e8a16329b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="2f1b3-102">Créer ou modifier un groupe d’agents dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f1b3-102">Create or modify an agent group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f1b3-103">_**Dernière modification de la rubrique :** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="2f1b3-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="2f1b3-104">Pour créer ou modifier un groupe d’agents, utilisez l’une des procédures ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-104">Use one of the following procedures to create or modify an agent group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2f1b3-105">Un administrateur (par exemple, CsVoiceAdministrator) doit permettre aux utilisateurs d’Enterprise Voice et de Lync Server d’affecter les utilisateurs à des groupes d’agents.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-105">An Administrator—for example, CsVoiceAdministrator—must enable users for Enterprise Voice and Lync Server before the users can be assigned to agent groups.</span></span> <span data-ttu-id="2f1b3-106">Si vous êtes l’un des gestionnaires de groupe de réponse déléguée pour un flux de travail géré, vous pouvez créer des groupes d’agents et utiliser les groupes d’agents dans les flux de travail que vous gérez.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-106">If you are one of the delegated Response Group Managers for a managed workflow, you can create agent groups and use the agent groups in the workflows that you manage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2f1b3-p102">Lorsque vous affectez des utilisateurs comme agents de groupe de réponse, informez-les que, si leur mode de confidentialité est activé, ils doivent rechercher des contacts « RGS Presence Watcher » et les rajouter à leur liste de contacts. Les agents dont le mode de confidentialité est activé, mais qui n’ont aucun contact « RGS Presence Watcher » dans leur liste de contacts, ne peuvent pas recevoir d’appels vers le groupe de réponse. Les agents dont le mode de confidentialité n’est pas activé ne seront pas affectés.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-p102">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="2f1b3-110">Pour utiliser le panneau de configuration de Lync Server pour créer ou modifier un groupe d’agents</span><span class="sxs-lookup"><span data-stu-id="2f1b3-110">To use Lync Server Control Panel to create or modify an agent group</span></span>

1.  <span data-ttu-id="2f1b3-111">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre de l’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-111">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2f1b3-112">Si vous faites partie des responsables de groupes Response Group délégués pour un flux de travail géré, vous pouvez créer des groupes et les utiliser dans les flux de travail que vous gérez.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-112">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="2f1b3-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2f1b3-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2f1b3-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2f1b3-115">Dans la barre de navigation de gauche, cliquez sur **Groupes Response Group**, puis cliquez sur **Groupe**.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-115">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="2f1b3-116">Dans la page **Groupe**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="2f1b3-116">On the **Group** page, do one of the following:</span></span>
    
      - <span data-ttu-id="2f1b3-p104">Pour créer un groupe d’agents, cliquez sur **Nouveau**. Dans le champ de recherche **Sélectionner un service**, tapez entièrement ou partiellement le nom du service **ApplicationServer** à ajouter au groupe. Dans la liste des services obtenus, cliquez sur le service de votre choix, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-p104">To create a new agent group, click **New**. In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group. In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="2f1b3-p105">Pour modifier un groupe d’agents existant, tapez entièrement ou partiellement le nom du groupe d’agents dans le champ de recherche. Dans la liste obtenue, cliquez sur le groupe de votre choix, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-p105">To modify an existing agent group, type all or part of the name of the agent group in the search field. In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="2f1b3-122">Dans **Nom**, tapez un nom d’identification pour le groupe d’agents.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-122">In **Name**, type an identifying name for the agent group.</span></span>

6.  <span data-ttu-id="2f1b3-123">Dans **Description**, tapez la description du groupe.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-123">In **Description**, type a description for the group.</span></span>

7.  <span data-ttu-id="2f1b3-124">Dans **Stratégie de participation**, sélectionnez l’une des options ci-dessous pour définir le comportement de connexion du groupe :</span><span class="sxs-lookup"><span data-stu-id="2f1b3-124">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
      - <span data-ttu-id="2f1b3-125">Sélectionnez **Informel** pour spécifier que les agents du groupe n’ont pas besoin de se connecter au groupe ou de s’en déconnecter.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-125">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="2f1b3-126">Les agents sont automatiquement connectés au groupe lorsqu’ils se connectent à Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-126">Agents are automatically signed in to the group when they sign in to Lync Server 2013.</span></span>
    
      - <span data-ttu-id="2f1b3-127">Sélectionnez **Formel** pour spécifier que les agents du groupe doivent se connecter au groupe et s’en déconnecter.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-127">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="2f1b3-128">Lorsque vous sélectionnez cette option, l’agent clique sur un élément de menu dans Lync pour ouvrir Internet Explorer et afficher une console de pages Web pour vous connecter et se déconnecter du groupe.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-128">When you select this option, agents click a menu item in Lync to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

8.  <span data-ttu-id="2f1b3-129">Dans **Temps d’alerte (secondes)**, spécifiez la durée (en secondes) pendant laquelle un appel doit sonner pour qu’il soit transmis à un agent disponible si l’agent auquel l’appel était destiné initialement ne peut pas y répondre (la durée par défaut est de 20 secondes).</span><span class="sxs-lookup"><span data-stu-id="2f1b3-129">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2f1b3-p108">Le paramètre de temps d’alerte d’agent ne peut pas dépasser 180 secondes. S’il dépasse 180 secondes, l’application cliente refusera l’appel, car la durée d’attente de la transaction SIP (Session Initiation Protocol) sera dépassée.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-p108">The agent alert time setting cannot exceed 180 seconds. If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

9.  <span data-ttu-id="2f1b3-132">Dans **Méthode de routage**, sélectionnez la méthode de transmission des appels aux agents dans le groupe, comme suit :</span><span class="sxs-lookup"><span data-stu-id="2f1b3-132">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
      - <span data-ttu-id="2f1b3-133">Pour vous permettre d’appeler tout d’abord l’agent qui est resté inactif le plus longtemps (a été **disponible** ou **inactif** dans Lync Server le plus longtemps), cliquez sur **inactif**le plus longtemps.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-133">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Lync Server the longest), click **Longest idle**.</span></span>
    
      - <span data-ttu-id="2f1b3-p109">Pour qu’un nouvel appel soit présenté simultanément à tous les agents disponibles, cliquez sur **Parallèle**. L’appel est envoyé au premier agent qui l’accepte.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-p109">To offer a new call to all available agents at the same time, click **Parallel**. The call is sent to the first agent who accepts it.</span></span>
    
      - <span data-ttu-id="2f1b3-136">Pour qu’un nouvel appel soit présenté à tour de rôle à chaque agent, cliquez sur **Tourniquet (round robin)**.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-136">To offer a new call to each agent in turn, click **Round robin**.</span></span>
    
      - <span data-ttu-id="2f1b3-137">Pour qu’un nouvel appel soit toujours présenté aux agents dans l’ordre dans lequel ils s’affichent dans la liste **Agents**, cliquez sur **Série**.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-137">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span>
    
      - <span data-ttu-id="2f1b3-138">Pour effectuer un nouvel appel vers tous les agents connectés à Lync Server 2013 et l’application de groupe de réponse en même temps, quelle que soit leur présence actuelle, cliquez sur **surveillant**.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-138">To offer a new call to all agents who are signed into Lync Server 2013 and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="2f1b3-139">Les utilisateurs de la surveillance de Lync 2010 configurés en tant qu’agents peuvent voir tous les appels en attente et répondre aux appels en attente dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-139">Lync 2010 Attendant users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="2f1b3-140">L’appel est envoyé au premier agent qui l’a accepté, à l’issue duquel les autres utilisateurs de Lync 2010 attendant ne verront plus l’appel.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-140">The call is sent to the first agent who accepts it, after which the other Lync 2010 Attendant users no longer see the call.</span></span>

10. <span data-ttu-id="2f1b3-141">Dans **Agents**, spécifiez la méthode de création de votre liste d’agents :</span><span class="sxs-lookup"><span data-stu-id="2f1b3-141">In **Agents**, specify how you want to create your agents list:</span></span>
    
      - <span data-ttu-id="2f1b3-142">Pour utiliser une liste d’agents personnalisée, cliquez sur **Définir un groupe personnalisé d’agents**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="2f1b3-142">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
        
          - <span data-ttu-id="2f1b3-p111">Pour ajouter un utilisateur au groupe d’agents, cliquez sur **Sélectionner**, puis dans le champ de recherche **Sélectionner des agents**, tapez l’intégralité ou le début du nom de l’utilisateur à ajouter à ce groupe, puis cliquez sur **Rechercher**. Dans la liste des agents obtenus, sélectionnez l’utilisateur, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-p111">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**. In the resulting list of agents, click the user, and then click **OK**.</span></span>
        
          - <span data-ttu-id="2f1b3-145">Pour supprimer un utilisateur du groupe d’agents, dans la liste des agents, cliquez sur l’utilisateur à supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-145">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
        
          - <span data-ttu-id="2f1b3-146">Pour modifier l’ordre dans lequel les appels sont présentés aux agents dans des groupes utilisant des fonctions de routage en série ou à tour de rôle (tourniquet), dans la liste des agents, sélectionnez un utilisateur, puis cliquez sur la flèche vers le haut ou le bas.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-146">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span>
    
      - <span data-ttu-id="2f1b3-147">Pour utiliser une liste de distribution Microsoft Exchange Server comme groupe d’agents, cliquez sur **Utiliser une liste de distribution de courrier électronique existante**, puis tapez l’adresse de messagerie de la liste de distribution (par exemple, NetworkSupport@contoso.com) dans **Adresse de la liste de distribution**.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-147">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
        
        <span data-ttu-id="2f1b3-148">Si vous utilisez une liste de distribution de courrier électronique, vous êtes soumis aux contraintes suivantes :</span><span class="sxs-lookup"><span data-stu-id="2f1b3-148">If you use an email distribution list, you are subject to the following constraints:</span></span>
        
          - <span data-ttu-id="2f1b3-p112">Vous ne pouvez pas sélectionner plusieurs listes de distribution pour le groupe d’agents. Chaque groupe prend en charge une seule liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-p112">You cannot select multiple distribution lists for the agent group. Each group supports only a single distribution list.</span></span>
        
          - <span data-ttu-id="2f1b3-151">Si la liste de distribution contient une ou plusieurs listes de distribution, les membres des listes de distribution imbriquées ne sont pas ajoutés à la liste d’agents.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-151">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
        
          - <span data-ttu-id="2f1b3-152">Si le routage série ou le routage à tour de rôle (tourniquet) est sélectionné, le serveur présente un appel entrant à l’agent approprié selon la méthode de routage sélectionnée et dans l’ordre d’affichage des agents dans la liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-152">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
        
          - <span data-ttu-id="2f1b3-p113">Si la liste de distribution contient des utilisateurs pour lesquels Lync Server 2010 est activé mais pas Voix Entreprise, ces utilisateurs sont ajoutés au groupe d’agent comme agents dysfonctionnels. Assurez-vous que Voix Entreprise est activé pour le compte d’utilisateurs de tous les membres de la liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-p113">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents. Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="2f1b3-155">Si vous utilisez une liste de distribution de courrier électronique, il est possible que les appartenances ou les listes masquées soient visibles pour l’administrateur du groupe de réponse ou les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-155">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span>

        
        </div>
        
        <span data-ttu-id="2f1b3-156">Les appartenances au groupe d’agents masquées ou les listes masquées peuvent devenir visibles, comme suit :</span><span class="sxs-lookup"><span data-stu-id="2f1b3-156">Hidden memberships or hidden lists can become visible as follows:</span></span>
        
          - <span data-ttu-id="2f1b3-157">Si une liste de distribution a été configurée de telle sorte que l’appartenance est masquée et que l’administrateur du groupe de réponse affecte la liste de distribution à la liste des agents, les utilisateurs peuvent appeler le groupe pour savoir qui en est les membres.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-157">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span>
        
          - <span data-ttu-id="2f1b3-158">Si une liste de distribution a été configurée de façon à être cachée dans la liste d’adresses globale Exchange, l’administrateur du groupe de réponse peut voir la liste de distribution et l’affecter à la liste des agents si le processus de groupe de réponse dispose des droits d’utilisateur appropriés et les autorisations, même si l’administrateur ne possède pas les droits d’utilisateur et les autorisations appropriés.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-158">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>

11. <span data-ttu-id="2f1b3-159">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-159">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="2f1b3-160">Pour utiliser Windows PowerShell pour créer ou modifier un groupe d’agents</span><span class="sxs-lookup"><span data-stu-id="2f1b3-160">To use Windows PowerShell to create or modify an agent group</span></span>

1.  <span data-ttu-id="2f1b3-161">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre de l’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-161">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="2f1b3-162">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-162">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2f1b3-163">Utilisez **New-CsRgsAgentGroup** pour créer un groupe d’agents.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-163">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="2f1b3-164">Utilisez **Set-CsRgsAgentGroup** pour modifier un groupe d’agents existant.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-164">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="2f1b3-165">Dans la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="2f1b3-165">At the command line, run:</span></span>
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    <span data-ttu-id="2f1b3-166">Exemple :</span><span class="sxs-lookup"><span data-stu-id="2f1b3-166">For example:</span></span>
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2f1b3-p115">Le paramètre de temps d’alerte d’agent ne peut pas dépasser 180 secondes. S’il dépasse 180 secondes, l’application cliente refusera l’appel, car la durée d’attente de la transaction SIP (Session Initiation Protocol) sera dépassée.</span><span class="sxs-lookup"><span data-stu-id="2f1b3-p115">The agent alert time setting cannot exceed 180 seconds. If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

4.  <span data-ttu-id="2f1b3-p116">Confirmez la création du groupe d’agents. Exécutez :</span><span class="sxs-lookup"><span data-stu-id="2f1b3-p116">Confirm that the agent group is created. Run:</span></span>
    
        Get-CsRgsAgentGroup -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2f1b3-171">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2f1b3-171">See Also</span></span>


[<span data-ttu-id="2f1b3-172">Supprimer un groupe d’agents dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f1b3-172">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)  


[<span data-ttu-id="2f1b3-173">Gestion des groupes d’agents de Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f1b3-173">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)  
[<span data-ttu-id="2f1b3-174">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="2f1b3-174">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="2f1b3-175">Nouveau-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="2f1b3-175">New-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup)  
[<span data-ttu-id="2f1b3-176">Set-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="2f1b3-176">Set-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsAgentGroup)  
[<span data-ttu-id="2f1b3-177">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="2f1b3-177">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

