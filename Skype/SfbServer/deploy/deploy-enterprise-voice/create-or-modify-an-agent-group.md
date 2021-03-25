---
title: Créer ou modifier un groupe d’agents dans Skype Entreprise
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: Créez ou modifiez un groupe d’agents dans Response Group, dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 0c0e7d54008ba6affa2bae5bd3228c93e430a114
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105810"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a><span data-ttu-id="af34b-103">Créer ou modifier un groupe d’agents dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="af34b-103">Create or modify an agent group in Skype for Business</span></span>
 
<span data-ttu-id="af34b-104">Créez ou modifiez un groupe d’agents dans Response Group, dans Skype Entreprise Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="af34b-104">Create or modify an agent group in Response Group, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="af34b-105">Lorsque vous créez un groupe d’agents, vous sélectionnez les agents assignés au groupe et spécifiez divers autres paramètres du groupe. Vous pouvez ainsi sélectionner la méthode de routage des appels et spécifier si un agent peut se connecter au groupe et s’en déconnecter.</span><span class="sxs-lookup"><span data-stu-id="af34b-105">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span> 
  
<span data-ttu-id="af34b-106">Un agent qui doit se dé connecter au groupe et s’en dé connecter, ce qui est différent de la signature ou de la sortie de Skype Entreprise, est appelé agent formel.</span><span class="sxs-lookup"><span data-stu-id="af34b-106">An agent who must sign in and out of the group, which is different from signing in or out of Skype for Business, is called a formal agent.</span></span> <span data-ttu-id="af34b-107">Les agents formels doivent être connectés au groupe pour recevoir des appels acheminés vers le groupe.</span><span class="sxs-lookup"><span data-stu-id="af34b-107">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="af34b-108">Cela peut être utile pour les agents qui répondent à temps partiel aux appels du groupe.</span><span class="sxs-lookup"><span data-stu-id="af34b-108">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="af34b-109">Les agents formels se connectent et se connectent à leurs groupes en cliquant sur un élément de menu dans Skype Entreprise pour ouvrir le navigateur Internet Windows Internet Explorer et afficher une console web.</span><span class="sxs-lookup"><span data-stu-id="af34b-109">Formal agents sign in and out of their groups by clicking a menu item in Skype for Business to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>
  
<span data-ttu-id="af34b-110">Un agent qui ne se connecte pas ou ne se connecte pas au groupe est appelé agent informel.</span><span class="sxs-lookup"><span data-stu-id="af34b-110">An agent who does not sign in or out of the group is called an informal agent.</span></span> <span data-ttu-id="af34b-111">Les agents informels sont automatiquement connectés au groupe lorsqu’ils se connectent à Skype Entreprise et ne peuvent pas se résigner au groupe.</span><span class="sxs-lookup"><span data-stu-id="af34b-111">Informal agents are automatically signed in to the group when they sign in to Skype for Business, and they cannot sign out of the group.</span></span>
  
<span data-ttu-id="af34b-112">Seuls les utilisateurs locaux peuvent être des agents.</span><span class="sxs-lookup"><span data-stu-id="af34b-112">Only on-premises users can be agents.</span></span> <span data-ttu-id="af34b-113">Si un agent est déplacé de l’local vers le site en ligne, les appels Response Group ne seront pas acheminés vers cet agent.</span><span class="sxs-lookup"><span data-stu-id="af34b-113">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>
  
<span data-ttu-id="af34b-114">Utilisez l’une des procédures suivantes pour créer ou modifier un groupe d’agents.</span><span class="sxs-lookup"><span data-stu-id="af34b-114">Use one of the following procedures to create or modify an agent group.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="af34b-115">Lorsque vous affectez des utilisateurs en tant qu’agents au groupe de réponses, informez-les que, s’ils ont activé le mode de confidentialité, ils doivent rechercher des contacts « RGS Presence Watcher » et les ajouter à leur liste de contacts.</span><span class="sxs-lookup"><span data-stu-id="af34b-115">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list.</span></span> <span data-ttu-id="af34b-116">Les agents qui ont activé le mode de confidentialité, mais qui n’ont pas « RGS Presence Watcher » dans leur liste de contacts, ne peuvent pas recevoir d’appels au groupe Response Group.</span><span class="sxs-lookup"><span data-stu-id="af34b-116">Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group.</span></span> <span data-ttu-id="af34b-117">Cela ne concerne pas les agents qui n’ont pas activé le mode de confidentialité.</span><span class="sxs-lookup"><span data-stu-id="af34b-117">Agents who do not have Privacy mode enabled are not affected.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="af34b-118">Pour utiliser le Panneau de contrôle Skype Entreprise Server pour créer ou modifier un groupe d’agents</span><span class="sxs-lookup"><span data-stu-id="af34b-118">To use Skype for Business Server Control Panel to create or modify an agent group</span></span>

1. <span data-ttu-id="af34b-119">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="af34b-119">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="af34b-120">Si vous êtes l’un des responsables Response Group délégués pour un flux de travail géré, vous pouvez créer des groupes et les utiliser dans les flux de travail que vous gérez.</span><span class="sxs-lookup"><span data-stu-id="af34b-120">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="af34b-121">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="af34b-121">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="af34b-122">Dans la barre de navigation de gauche, cliquez sur **Groupes Response Group**, puis sur **Groupe**.</span><span class="sxs-lookup"><span data-stu-id="af34b-122">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>
    
4. <span data-ttu-id="af34b-123">Dans la page **Groupe,** faites l’une des choses suivantes :</span><span class="sxs-lookup"><span data-stu-id="af34b-123">On the **Group** page, do one of the following:</span></span>
    
   - <span data-ttu-id="af34b-124">Pour créer un groupe d’agents, cliquez sur **Nouveau.**</span><span class="sxs-lookup"><span data-stu-id="af34b-124">To create a new agent group, click **New**.</span></span> <span data-ttu-id="af34b-125">Dans le **champ Sélectionner un service** de recherche, tapez tout ou partie du nom du service **ApplicationServer** où vous souhaitez ajouter le groupe.</span><span class="sxs-lookup"><span data-stu-id="af34b-125">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group.</span></span> <span data-ttu-id="af34b-126">Dans la liste des services obtenue, cliquez sur le service de votre choix, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="af34b-126">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="af34b-127">Pour modifier un groupe d’agents existant, tapez tout ou partie du nom du groupe d’agents dans le champ de recherche.</span><span class="sxs-lookup"><span data-stu-id="af34b-127">To modify an existing agent group, type all or part of the name of the agent group in the search field.</span></span> <span data-ttu-id="af34b-128">Dans la liste qui en résulte, cliquez sur le groupe que vous souhaitez, cliquez sur **Modifier,** puis cliquez sur Afficher **les détails.**</span><span class="sxs-lookup"><span data-stu-id="af34b-128">In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="af34b-129">Dans **Nom,** tapez un nom d’identification pour le groupe d’agents.</span><span class="sxs-lookup"><span data-stu-id="af34b-129">In **Name**, type an identifying name for the agent group.</span></span>
    
6. <span data-ttu-id="af34b-130">Dans **Description**, tapez la description du groupe.</span><span class="sxs-lookup"><span data-stu-id="af34b-130">In **Description**, type a description for the group.</span></span>
    
7. <span data-ttu-id="af34b-131">Dans **Stratégie de participation**, sélectionnez l’une des options suivantes pour définir le comportement de connexion pour le groupe :</span><span class="sxs-lookup"><span data-stu-id="af34b-131">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
   - <span data-ttu-id="af34b-132">Sélectionnez **Informel** pour spécifier que les agents dans le groupe n’ont pas besoin de se connecter au groupe pour y accéder et de se déconnecter pour le quitter.</span><span class="sxs-lookup"><span data-stu-id="af34b-132">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="af34b-133">Les agents sont automatiquement connectés au groupe lorsqu’ils se connectent à Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="af34b-133">Agents are automatically signed in to the group when they sign in to Skype for Business.</span></span>
    
   - <span data-ttu-id="af34b-134">Sélectionnez **Formel** pour spécifier que les agents sont obligés de se connecter au groupe pour y accéder et de se déconnecter pour le quitter.</span><span class="sxs-lookup"><span data-stu-id="af34b-134">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="af34b-135">Lorsque vous sélectionnez cette option, les agents cliquent sur un élément de menu dans Skype Entreprise pour ouvrir Internet Explorer et afficher une console de page web pour la connexion et la sortie du groupe.</span><span class="sxs-lookup"><span data-stu-id="af34b-135">When you select this option, agents click a menu item in Skype for Business to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>
    
8. <span data-ttu-id="af34b-136">Dans **Temps d’alerte (secondes)**, spécifiez combien de temps (en secondes) un appel doit sonner pour qu’il soit transmis à un agent disponible si l’agent auquel l’appel était initialement destiné ne peut pas y répondre (la durée par défaut est 20 secondes).</span><span class="sxs-lookup"><span data-stu-id="af34b-136">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="af34b-137">Le paramètre de temps d’alerte de l’agent ne peut pas dépasser 180 secondes.</span><span class="sxs-lookup"><span data-stu-id="af34b-137">The agent alert time setting cannot exceed 180 seconds.</span></span> <span data-ttu-id="af34b-138">Si le temps d’alerte de l’agent dépasse 180 secondes, l’application cliente rejette l’appel, car le minuteur de transaction SIP atteint son délai d’attente maximal.</span><span class="sxs-lookup"><span data-stu-id="af34b-138">If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
9. <span data-ttu-id="af34b-139">Dans **Méthode de routage**, sélectionnez la méthode pour transmettre les appels aux agents dans le groupe comme suit :</span><span class="sxs-lookup"><span data-stu-id="af34b-139">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
   - <span data-ttu-id="af34b-140">Pour proposer d’abord un nouvel appel à l’agent qui a été inactif le plus longtemps (a été le plus longtemps en présence de **Disponible** ou **Inactif** dans Skype Entreprise), cliquez sur Le plus long **inactif**.</span><span class="sxs-lookup"><span data-stu-id="af34b-140">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Skype for Business the longest), click **Longest idle**.</span></span> 
    
   - <span data-ttu-id="af34b-p110">Pour qu’un nouvel appel soit présenté à tous les agents disponibles simultanément, cliquez sur **Parallèle**. L’appel est envoyé au premier agent qui l’accepte.</span><span class="sxs-lookup"><span data-stu-id="af34b-p110">To offer a new call to all available agents at the same time, click **Parallel**. The call is sent to the first agent who accepts it.</span></span>
    
   - <span data-ttu-id="af34b-143">Pour qu’un nouvel appel soit présenté à chaque agent, à tour de rôle, cliquez sur **Tourniquet (round robin)**.</span><span class="sxs-lookup"><span data-stu-id="af34b-143">To offer a new call to each agent in turn, click **Round robin**.</span></span> 
    
   - <span data-ttu-id="af34b-144">Pour qu’un nouvel appel soit toujours présenté aux agents dans l’ordre dans lequel ils apparaissent dans la liste **Agents**, cliquez sur **Série**.</span><span class="sxs-lookup"><span data-stu-id="af34b-144">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span> 
    
   - <span data-ttu-id="af34b-145">Pour proposer un nouvel appel à tous les agents qui sont signés dans Skype Entreprise et l’application Response Group en même temps, quelle que soit leur présence actuelle, cliquez sur **Attendant**.</span><span class="sxs-lookup"><span data-stu-id="af34b-145">To offer a new call to all agents who are signed into Skype for Business and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="af34b-146">Les utilisateurs configurés en tant qu’agents peuvent voir tous les appels en attente et répondre aux appels en attente dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="af34b-146">Users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="af34b-147">L’appel est envoyé au premier agent qui l’accepte, après quoi les autres agents ne voient plus l’appel.</span><span class="sxs-lookup"><span data-stu-id="af34b-147">The call is sent to the first agent who accepts it, after which the other agents no longer see the call.</span></span>
    
10. <span data-ttu-id="af34b-148">Dans **Agents**, spécifiez comment vous voulez créer votre liste d’agents :</span><span class="sxs-lookup"><span data-stu-id="af34b-148">In **Agents**, specify how you want to create your agents list:</span></span>
    
    - <span data-ttu-id="af34b-149">Pour utiliser une liste personnalisée d’agents, cliquez sur Définir un groupe personnalisé **d’agents** et faites l’une des choses suivantes :</span><span class="sxs-lookup"><span data-stu-id="af34b-149">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
    
    - <span data-ttu-id="af34b-150">Pour ajouter un utilisateur au groupe d’agents,  cliquez sur Sélectionner, puis dans le champ De recherche Sélectionner des agents, tapez tout ou partie du nom de l’utilisateur que vous souhaitez ajouter à ce groupe, puis cliquez sur **Rechercher.**</span><span class="sxs-lookup"><span data-stu-id="af34b-150">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**.</span></span> <span data-ttu-id="af34b-151">Dans la liste des agents qui en résulte, cliquez sur l’utilisateur, puis sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="af34b-151">In the resulting list of agents, click the user, and then click **OK**.</span></span>
    
    - <span data-ttu-id="af34b-152">Pour supprimer un utilisateur du groupe d’agents, dans la liste des agents, cliquez sur l’utilisateur à supprimer, puis cliquez sur **Supprimer.**</span><span class="sxs-lookup"><span data-stu-id="af34b-152">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
    
    - <span data-ttu-id="af34b-153">Pour modifier l’ordre dans lequel les appels sont proposés aux agents dans les groupes qui utilisent le routage round robin ou le routage en série, dans la liste des agents, cliquez sur un utilisateur, puis cliquez sur la flèche vers le haut ou vers le bas.</span><span class="sxs-lookup"><span data-stu-id="af34b-153">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span> 
    
    - <span data-ttu-id="af34b-154">Pour utiliser une liste de distribution Microsoft Exchange Server en tant que groupe d’agents, cliquez sur Utiliser une liste de distribution de courrier électronique existante, puis, dans l’adresse de la liste de **distribution,** tapez l’adresse e-mail de la liste de distribution (par exemple, NetworkSupport@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="af34b-154">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
    
      <span data-ttu-id="af34b-155">Si vous utilisez une liste de distribution de courrier électronique, vous êtes soumis aux contraintes suivantes :</span><span class="sxs-lookup"><span data-stu-id="af34b-155">If you use an email distribution list, you are subject to the following constraints:</span></span>
    
      - <span data-ttu-id="af34b-p113">Vous ne pouvez pas sélectionner plusieurs listes de distribution pour le groupe d’agents. Chaque groupe prend en charge une seule liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="af34b-p113">You cannot select multiple distribution lists for the agent group. Each group supports only a single distribution list.</span></span>
    
      - <span data-ttu-id="af34b-158">Si la liste de distribution contient une ou plusieurs listes de distribution, les membres des listes de distribution imbriquées ne sont pas ajoutés à la liste d’agents.</span><span class="sxs-lookup"><span data-stu-id="af34b-158">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
    
      - <span data-ttu-id="af34b-159">Si le routage série ou round robin est sélectionné, le serveur propose un appel entrant à l’agent approprié en fonction de la méthode de routage et de l’ordre dans lequel les agents sont répertoriés dans la liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="af34b-159">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
    
      - <span data-ttu-id="af34b-160">Si la liste de distribution contient des utilisateurs pour lesquels Lync Server 2010 est activé, mais Voix Entreprise n’est pas activé, ils sont ajoutés au groupe d’agents en tant qu’agents d’exécution.</span><span class="sxs-lookup"><span data-stu-id="af34b-160">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents.</span></span> <span data-ttu-id="af34b-161">Assurez-vous que tous les membres de la liste de distribution Voix Entreprise activés pour leurs comptes d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="af34b-161">Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="af34b-162">Si vous utilisez une liste de distribution de courrier électronique, les appartenances masquées ou les listes masquées peuvent devenir visibles pour l’administrateur ou les utilisateurs Response Group.</span><span class="sxs-lookup"><span data-stu-id="af34b-162">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span> 
  
    <span data-ttu-id="af34b-163">Les appartenances au groupe d’agents masquées ou les listes masquées peuvent devenir visibles comme suit :</span><span class="sxs-lookup"><span data-stu-id="af34b-163">Hidden memberships or hidden lists can become visible as follows:</span></span>
    
     - <span data-ttu-id="af34b-164">Si une liste de distribution a été configurée pour que l’appartenance soit masquée et que l’administrateur Response Group affecte la liste de distribution à la liste des agents, les utilisateurs peuvent appeler le groupe pour savoir qui sont les membres.</span><span class="sxs-lookup"><span data-stu-id="af34b-164">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span> 
    
     - <span data-ttu-id="af34b-165">Si une liste de distribution a été configurée de sorte qu’elle soit masquée dans la liste d’adresses globale Exchange, l’administrateur Response Group peut être en mesure de voir la liste de distribution et de l’affecter à la liste des agents si le processus Response Group dispose des droits et autorisations d’utilisateur appropriés, même si l’administrateur ne dispose pas des droits et autorisations d’utilisateur appropriés.</span><span class="sxs-lookup"><span data-stu-id="af34b-165">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>
    
11. <span data-ttu-id="af34b-166">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="af34b-166">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="af34b-167">Pour utiliser Skype Entreprise Server Management Shell pour créer ou modifier un groupe d’agents</span><span class="sxs-lookup"><span data-stu-id="af34b-167">To use Skype for Business Server Management Shell to create or modify an agent group</span></span>

1. <span data-ttu-id="af34b-168">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="af34b-168">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="af34b-169">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="af34b-169">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="af34b-170">Utilisez **New-CsRgsAgentGroup** pour créer un groupe d’agents.</span><span class="sxs-lookup"><span data-stu-id="af34b-170">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="af34b-171">Utilisez **Set-CsRgsAgentGroup pour** modifier un groupe d’agents existant.</span><span class="sxs-lookup"><span data-stu-id="af34b-171">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="af34b-172">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="af34b-172">At the command line, run:</span></span>
    
   ```powershell
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    <span data-ttu-id="af34b-173">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="af34b-173">For example:</span></span>
    
   ```powershell
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="af34b-174">Le paramètre de temps d’alerte de l’agent ne peut pas dépasser 180 secondes.</span><span class="sxs-lookup"><span data-stu-id="af34b-174">The agent alert time setting cannot exceed 180 seconds.</span></span> <span data-ttu-id="af34b-175">Si le temps d’alerte de l’agent est supérieur à 180 secondes, l’application cliente rejette l’appel, car le minuteur de transaction SIP atteint son délai d’attente maximal.</span><span class="sxs-lookup"><span data-stu-id="af34b-175">If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
4. <span data-ttu-id="af34b-176">Confirmez que le groupe d’agents est créé.</span><span class="sxs-lookup"><span data-stu-id="af34b-176">Confirm that the agent group is created.</span></span> <span data-ttu-id="af34b-177">Exécutez :  </span><span class="sxs-lookup"><span data-stu-id="af34b-177">Run:</span></span>
    
   ```powershell
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a><span data-ttu-id="af34b-178">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="af34b-178">See also</span></span>

[<span data-ttu-id="af34b-179">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="af34b-179">Get-CsService</span></span>](/powershell/module/skype/get-csservice?view=skype-ps)
  
[<span data-ttu-id="af34b-180">New-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="af34b-180">New-CsRgsAgentGroup</span></span>](/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="af34b-181">Set-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="af34b-181">Set-CsRgsAgentGroup</span></span>](/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="af34b-182">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="af34b-182">Get-CsRgsAgentGroup</span></span>](/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)