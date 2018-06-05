---
title: Création ou modification d’un groupe d’agents dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: Créer ou modifier un groupe d’agents Response Group, dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 5555272fdcaa7b9a3576dc2b943eaeda064e3bb5
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568344"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business-2015"></a><span data-ttu-id="b1faf-103">Création ou modification d’un groupe d’agents dans Skype Entreprise 2015</span><span class="sxs-lookup"><span data-stu-id="b1faf-103">Create or modify an agent group in Skype for Business 2015</span></span>
 
<span data-ttu-id="b1faf-104">Créer ou modifier un groupe d’agents Response Group, dans Skype pour Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="b1faf-104">Create or modify an agent group in Response Group, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="b1faf-105">Lorsque vous créez un groupe d’agents, vous sélectionnez les agents affectés au groupe, spécifiez différents autres paramètres du groupe, comme la méthode de routage des appels, et indiquez si un agent peut se connecter au groupe et s’en déconnecter.</span><span class="sxs-lookup"><span data-stu-id="b1faf-105">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span> 
  
<span data-ttu-id="b1faf-106">Un agent qui doit se connecter ou se déconnecter du groupe qui est différent de signature s’en déconnecter Skype pour les entreprises, est appelé agent formel.</span><span class="sxs-lookup"><span data-stu-id="b1faf-106">An agent who must sign in and out of the group, which is different from signing in or out of Skype for Business, is called a formal agent.</span></span> <span data-ttu-id="b1faf-107">Les agents formels doivent être connectés au groupe pour recevoir des appels routés vers le groupe.</span><span class="sxs-lookup"><span data-stu-id="b1faf-107">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="b1faf-108">Cela peut s’avérer utile pour les agents qui répondent à temps partiel aux appels du groupe.</span><span class="sxs-lookup"><span data-stu-id="b1faf-108">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="b1faf-109">Les agents formels se connecter ou se déconnecter de leurs groupes en cliquant sur un élément de menu dans Skype pour les entreprises ouvrir le navigateur Internet Windows Internet Explorer et afficher une page Web console.</span><span class="sxs-lookup"><span data-stu-id="b1faf-109">Formal agents sign in and out of their groups by clicking a menu item in Skype for Business to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>
  
<span data-ttu-id="b1faf-110">Un agent qui ne doit pas se connecter le dans ou hors du groupe est appelé agent informel.</span><span class="sxs-lookup"><span data-stu-id="b1faf-110">An agent who does not sign in or out of the group is called an informal agent.</span></span> <span data-ttu-id="b1faf-111">Les agents informels sont automatiquement connectés au groupe lorsqu’ils se connectent à Skype pour les entreprises, et ils ne peuvent pas vous déconnecter du groupe.</span><span class="sxs-lookup"><span data-stu-id="b1faf-111">Informal agents are automatically signed in to the group when they sign in to Skype for Business, and they cannot sign out of the group.</span></span>
  
<span data-ttu-id="b1faf-112">Seuls les utilisateurs locaux peuvent être des agents.</span><span class="sxs-lookup"><span data-stu-id="b1faf-112">Only on-premises users can be agents.</span></span> <span data-ttu-id="b1faf-113">Si un agent est déplacé sur site vers online, appels Response Group ne seront pas acheminés à cet agent.</span><span class="sxs-lookup"><span data-stu-id="b1faf-113">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>
  
<span data-ttu-id="b1faf-114">Pour créer ou modifier un groupe d’agents, utilisez l’une des procédures ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="b1faf-114">Use one of the following procedures to create or modify an agent group.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b1faf-p104">Lorsque vous affectez des utilisateurs comme agents de groupe de réponse, informez-les que, si leur mode de confidentialité est activé, ils doivent rechercher des contacts « RGS Presence Watcher » et les rajouter à leur liste de contacts. Les agents dont le mode de confidentialité est activé, mais qui n’ont aucun contact « RGS Presence Watcher » dans leur liste de contacts, ne peuvent pas recevoir d’appels vers le groupe de réponse. Les agents dont le mode de confidentialité n’est pas activé ne seront pas affectés.</span><span class="sxs-lookup"><span data-stu-id="b1faf-p104">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="b1faf-118">Utiliser Skype pour Business Server Control Panel pour créer ou modifier un groupe d’agents</span><span class="sxs-lookup"><span data-stu-id="b1faf-118">To use Skype for Business Server Control Panel to create or modify an agent group</span></span>

1. <span data-ttu-id="b1faf-119">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administrateur prédéfinis qui prennent en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="b1faf-119">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b1faf-120">Si vous faites partie des responsables de groupes Response Group délégués pour un flux de travail géré, vous pouvez créer des groupes et les utiliser dans les flux de travail que vous gérez.</span><span class="sxs-lookup"><span data-stu-id="b1faf-120">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="b1faf-121">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="b1faf-121">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b1faf-122">Dans la barre de navigation de gauche, cliquez sur **Groupes Response Group**, puis cliquez sur **Groupe**.</span><span class="sxs-lookup"><span data-stu-id="b1faf-122">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>
    
4. <span data-ttu-id="b1faf-123">Dans la page **Groupe**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="b1faf-123">On the **Group** page, do one of the following:</span></span>
    
   - <span data-ttu-id="b1faf-p105">Pour créer un groupe d’agents, cliquez sur **Nouveau**. Dans le champ de recherche **Sélectionner un service**, tapez entièrement ou partiellement le nom du service **ApplicationServer** à ajouter au groupe. Dans la liste des services obtenus, cliquez sur le service de votre choix, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1faf-p105">To create a new agent group, click **New**. In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group. In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="b1faf-p106">Pour modifier un groupe d’agents existant, tapez entièrement ou partiellement le nom du groupe d’agents dans le champ de recherche. Dans la liste obtenue, cliquez sur le groupe de votre choix, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="b1faf-p106">To modify an existing agent group, type all or part of the name of the agent group in the search field. In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="b1faf-129">Dans **Nom**, tapez un nom d’identification pour le groupe d’agents.</span><span class="sxs-lookup"><span data-stu-id="b1faf-129">In **Name**, type an identifying name for the agent group.</span></span>
    
6. <span data-ttu-id="b1faf-130">Dans **Description**, tapez la description du groupe.</span><span class="sxs-lookup"><span data-stu-id="b1faf-130">In **Description**, type a description for the group.</span></span>
    
7. <span data-ttu-id="b1faf-131">Dans **Stratégie de participation**, sélectionnez l’une des options ci-dessous pour définir le comportement de connexion du groupe :</span><span class="sxs-lookup"><span data-stu-id="b1faf-131">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
   - <span data-ttu-id="b1faf-132">Sélectionnez **Informel** pour spécifier que les agents du groupe n’ont pas besoin de se connecter au groupe ou de s’en déconnecter.</span><span class="sxs-lookup"><span data-stu-id="b1faf-132">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="b1faf-133">Les agents sont automatiquement connectés au groupe lorsqu’ils se connectent à Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="b1faf-133">Agents are automatically signed in to the group when they sign in to Skype for Business.</span></span>
    
   - <span data-ttu-id="b1faf-134">Sélectionnez **Formel** pour spécifier que les agents du groupe doivent se connecter au groupe et s’en déconnecter.</span><span class="sxs-lookup"><span data-stu-id="b1faf-134">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="b1faf-135">Lorsque vous sélectionnez cette option, les agents, cliquez sur un élément de menu dans Skype pour les entreprises, ouvrez Internet Explorer et afficher une console de page Web pour la signature et s’en déconnecter du groupe.</span><span class="sxs-lookup"><span data-stu-id="b1faf-135">When you select this option, agents click a menu item in Skype for Business to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>
    
8. <span data-ttu-id="b1faf-136">Dans **Temps d’alerte (secondes)**, spécifiez la durée (en secondes) pendant laquelle un appel doit sonner pour qu’il soit transmis à un agent disponible si l’agent auquel l’appel était destiné initialement ne peut pas y répondre (la durée par défaut est de 20 secondes).</span><span class="sxs-lookup"><span data-stu-id="b1faf-136">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b1faf-p109">Le paramètre de temps d’alerte d’agent ne peut pas dépasser 180 secondes. S’il dépasse 180 secondes, l’application cliente refusera l’appel, car la durée d’attente de la transaction SIP (Session Initiation Protocol) sera dépassée.</span><span class="sxs-lookup"><span data-stu-id="b1faf-p109">The agent alert time setting cannot exceed 180 seconds. If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
9. <span data-ttu-id="b1faf-139">Dans **Méthode de routage**, sélectionnez la méthode de transmission des appels aux agents dans le groupe, comme suit :</span><span class="sxs-lookup"><span data-stu-id="b1faf-139">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
   - <span data-ttu-id="b1faf-140">Pour présenter un nouvel appel d’abord à l’agent qui a été inactif le plus longtemps (dispose la présence était **disponible** ou **inactif/Inactive** dans Skype pour les entreprises la plus longue), cliquez sur **plus long inactif**.</span><span class="sxs-lookup"><span data-stu-id="b1faf-140">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Skype for Business the longest), click **Longest idle**.</span></span> 
    
   - <span data-ttu-id="b1faf-p110">Pour qu’un nouvel appel soit présenté simultanément à tous les agents disponibles, cliquez sur **Parallèle**. L’appel est envoyé au premier agent qui l’accepte.</span><span class="sxs-lookup"><span data-stu-id="b1faf-p110">To offer a new call to all available agents at the same time, click **Parallel**. The call is sent to the first agent who accepts it.</span></span>
    
   - <span data-ttu-id="b1faf-143">Pour qu’un nouvel appel soit présenté à tour de rôle à chaque agent, cliquez sur **Tourniquet (round robin)**.</span><span class="sxs-lookup"><span data-stu-id="b1faf-143">To offer a new call to each agent in turn, click **Round robin**.</span></span> 
    
   - <span data-ttu-id="b1faf-144">Pour qu’un nouvel appel soit toujours présenté aux agents dans l’ordre dans lequel ils s’affichent dans la liste **Agents**, cliquez sur **Série**.</span><span class="sxs-lookup"><span data-stu-id="b1faf-144">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span> 
    
   - <span data-ttu-id="b1faf-145">Pour proposer un nouvel appel à tous les agents qui sont connecté Skype pour les entreprises et l’application Response Group en même temps, indépendamment de leur présence en cours, cliquez sur **standard**.</span><span class="sxs-lookup"><span data-stu-id="b1faf-145">To offer a new call to all agents who are signed into Skype for Business and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="b1faf-146">Les utilisateurs configurés comme agents peuvent voir tous les appels en attente et y répondre, dans l’ordre qui leur convient.</span><span class="sxs-lookup"><span data-stu-id="b1faf-146">Users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="b1faf-147">L’appel est envoyé au premier agent qui l’accepte, et les autres agents ne peuvent alors plus voir l’appel.</span><span class="sxs-lookup"><span data-stu-id="b1faf-147">The call is sent to the first agent who accepts it, after which the other agents no longer see the call.</span></span>
    
10. <span data-ttu-id="b1faf-148">Dans **Agents**, spécifiez la méthode de création de votre liste d’agents :</span><span class="sxs-lookup"><span data-stu-id="b1faf-148">In **Agents**, specify how you want to create your agents list:</span></span>
    
   - <span data-ttu-id="b1faf-149">Pour utiliser une liste d’agents personnalisée, cliquez sur **Définir un groupe personnalisé d’agents**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="b1faf-149">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
    
   - <span data-ttu-id="b1faf-p112">Pour ajouter un utilisateur au groupe d’agents, cliquez sur **Sélectionner**, puis dans le champ de recherche **Sélectionner des agents**, tapez l’intégralité ou le début du nom de l’utilisateur à ajouter à ce groupe, puis cliquez sur **Rechercher**. Dans la liste des agents obtenus, sélectionnez l’utilisateur, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1faf-p112">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**. In the resulting list of agents, click the user, and then click **OK**.</span></span>
    
   - <span data-ttu-id="b1faf-152">Pour supprimer un utilisateur du groupe d’agents, dans la liste des agents, cliquez sur l’utilisateur à supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b1faf-152">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
    
   - <span data-ttu-id="b1faf-153">Pour modifier l’ordre dans lequel les appels sont présentés aux agents dans des groupes utilisant des fonctions de routage en série ou à tour de rôle (tourniquet), dans la liste des agents, sélectionnez un utilisateur, puis cliquez sur la flèche vers le haut ou le bas.</span><span class="sxs-lookup"><span data-stu-id="b1faf-153">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span> 
    
   - <span data-ttu-id="b1faf-154">Pour utiliser une liste de distribution Microsoft Exchange Server comme groupe d’agents, cliquez sur **Utiliser une liste de distribution de courrier électronique existante**, puis tapez l’adresse de messagerie de la liste de distribution (par exemple, NetworkSupport@contoso.com) dans **Adresse de la liste de distribution**.</span><span class="sxs-lookup"><span data-stu-id="b1faf-154">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
    
     <span data-ttu-id="b1faf-155">Si vous utilisez une liste de distribution de courrier électronique, vous êtes soumis aux contraintes suivantes :</span><span class="sxs-lookup"><span data-stu-id="b1faf-155">If you use an email distribution list, you are subject to the following constraints:</span></span>
    
     - <span data-ttu-id="b1faf-p113">Vous ne pouvez pas sélectionner plusieurs listes de distribution pour le groupe d’agents. Chaque groupe prend en charge une seule liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="b1faf-p113">You cannot select multiple distribution lists for the agent group. Each group supports only a single distribution list.</span></span>
    
     - <span data-ttu-id="b1faf-158">Si la liste de distribution contient une ou plusieurs listes de distribution, les membres des listes de distribution imbriquées ne sont pas ajoutés à la liste d’agents.</span><span class="sxs-lookup"><span data-stu-id="b1faf-158">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
    
     - <span data-ttu-id="b1faf-159">Si le routage série ou le routage à tour de rôle (tourniquet) est sélectionné, le serveur présente un appel entrant à l’agent approprié selon la méthode de routage sélectionnée et dans l’ordre d’affichage des agents dans la liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="b1faf-159">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
    
     - <span data-ttu-id="b1faf-p114">Si la liste de distribution contient des utilisateurs pour lesquels Lync Server 2010 est activé mais pas Voix Entreprise, ces utilisateurs sont ajoutés au groupe d’agent comme agents dysfonctionnels. Assurez-vous que Voix Entreprise est activé pour le compte d’utilisateurs de tous les membres de la liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="b1faf-p114">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents. Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b1faf-162">Si vous utilisez une liste de distribution de courrier électronique, les appartenances masquées ou les listes masquées peuvent devenir visibles aux utilisateurs ou administrateur de Response Group.</span><span class="sxs-lookup"><span data-stu-id="b1faf-162">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span> 
  
    <span data-ttu-id="b1faf-163">Les appartenances au groupe d’agents masquées ou les listes masquées peuvent devenir visibles, comme suit :</span><span class="sxs-lookup"><span data-stu-id="b1faf-163">Hidden memberships or hidden lists can become visible as follows:</span></span>
    
     - <span data-ttu-id="b1faf-164">Si une liste de distribution a été configurée de sorte que l’appartenance est masquée et l’administrateur de groupe de réponse affecte la liste de distribution à la liste d’agents, les utilisateurs peuvent appeler le groupe permettant de savoir quels sont les membres.</span><span class="sxs-lookup"><span data-stu-id="b1faf-164">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span> 
    
     - <span data-ttu-id="b1faf-165">Si une liste de distribution a été configurée afin qu’il est masqué dans la liste d’adresses globale Exchange, l’administrateur de Response Group peut être en mesure de voir la distribution de liste et l’assigner à la liste d’agents si le processus de Response Group possède les droits d’utilisateur appropriés et autorisations, même si l’administrateur n’a pas les droits d’utilisateur appropriés et les autorisations.</span><span class="sxs-lookup"><span data-stu-id="b1faf-165">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>
    
11. <span data-ttu-id="b1faf-166">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="b1faf-166">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="b1faf-167">Utiliser Skype pour Business Server Management Shell pour créer ou modifier un groupe d’agents</span><span class="sxs-lookup"><span data-stu-id="b1faf-167">To use Skype for Business Server Management Shell to create or modify an agent group</span></span>

1. <span data-ttu-id="b1faf-168">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administrateur prédéfinis qui prennent en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="b1faf-168">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="b1faf-169">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="b1faf-169">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b1faf-170">**New-CsRgsAgentGroup** permet de créer un nouveau groupe d’agents.</span><span class="sxs-lookup"><span data-stu-id="b1faf-170">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="b1faf-171">**Set-CsRgsAgentGroup** permet de modifier un groupe d’agents.</span><span class="sxs-lookup"><span data-stu-id="b1faf-171">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="b1faf-172">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b1faf-172">At the command line, run:</span></span>
    
   ```
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    <span data-ttu-id="b1faf-173">Exemple :</span><span class="sxs-lookup"><span data-stu-id="b1faf-173">For example:</span></span>
    
   ```
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="b1faf-p116">Le paramètre de temps d’alerte d’agent ne peut pas dépasser 180 secondes. S’il dépasse 180 secondes, l’application cliente refusera l’appel, car la durée d’attente de la transaction SIP (Session Initiation Protocol) sera dépassée.</span><span class="sxs-lookup"><span data-stu-id="b1faf-p116">The agent alert time setting cannot exceed 180 seconds. If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
4. <span data-ttu-id="b1faf-p117">Confirmez la création du groupe d’agents. Exécutez :</span><span class="sxs-lookup"><span data-stu-id="b1faf-p117">Confirm that the agent group is created. Run:</span></span>
    
   ```
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a><span data-ttu-id="b1faf-178">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b1faf-178">See also</span></span>

[<span data-ttu-id="b1faf-179">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="b1faf-179">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
  
[<span data-ttu-id="b1faf-180">New-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="b1faf-180">New-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="b1faf-181">Set-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="b1faf-181">Set-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="b1faf-182">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="b1faf-182">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)