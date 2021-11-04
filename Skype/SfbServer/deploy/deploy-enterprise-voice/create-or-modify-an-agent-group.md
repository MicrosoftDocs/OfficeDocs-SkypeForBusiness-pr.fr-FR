---
title: Créer ou modifier un groupe d’agents dans Skype Entreprise
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: Créez ou modifiez un groupe d’agents dans Response Group, Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: f17b3839e483f1886e69f84b33980f5384b50066
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771559"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a>Créer ou modifier un groupe d’agents dans Skype Entreprise
 
Créez ou modifiez un groupe d’agents dans Response Group, Skype Entreprise Server Voix Entreprise.
  
Lorsque vous créez un groupe d’agents, vous sélectionnez les agents assignés au groupe et spécifiez divers autres paramètres du groupe. Vous pouvez ainsi sélectionner la méthode de routage des appels et spécifier si un agent peut se connecter au groupe et s’en déconnecter. 
  
Un agent qui doit se dé connecter au groupe et s’en dése sortie, ce qui est différent de la Skype Entreprise, est appelé agent formel. Les agents formels doivent être connectés au groupe pour recevoir des appels acheminés vers le groupe. Cela peut être utile pour les agents qui répondent à temps partiel aux appels du groupe. Les agents formels se connectent et se connectent à leurs groupes en cliquant sur un élément de menu dans Skype Entreprise pour ouvrir le navigateur Internet Windows Internet Explorer et afficher une console de page web.
  
Un agent qui ne se connecte pas ou ne se connecte pas au groupe est appelé agent informel. Les agents informels sont automatiquement connectés au groupe lorsqu’ils se connectent à Skype Entreprise et ne peuvent pas se résigner au groupe.
  
Seuls les utilisateurs locaux peuvent être des agents. Si un agent est déplacé de l’local vers le site en ligne, les appels Response Group ne seront pas acheminés vers cet agent.
  
Utilisez l’une des procédures suivantes pour créer ou modifier un groupe d’agents.
  
> [!IMPORTANT]
> Lorsque vous affectez des utilisateurs en tant qu’agents au groupe de réponses, informez-les que, s’ils ont activé le mode de confidentialité, ils doivent rechercher des contacts « RGS Presence Watcher » et les ajouter à leur liste de contacts. Les agents qui ont activé le mode de confidentialité, mais qui n’ont pas « RGS Presence Watcher » dans leur liste de contacts, ne peuvent pas recevoir d’appels au groupe Response Group. Cela ne concerne pas les agents qui n’ont pas activé le mode de confidentialité. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a>Pour utiliser Skype Entreprise Server de contrôle d’agent pour créer ou modifier un groupe d’agents

1. Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.
    
    > [!NOTE]
    > Si vous êtes l’un des responsables Response Group délégués pour un flux de travail géré, vous pouvez créer des groupes et les utiliser dans les flux de travail que vous gérez. 
  
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Groupes Response Group**, puis sur **Groupe**.
    
4. Dans la page **Groupe,** faites l’une des choses suivantes :
    
   - Pour créer un groupe d’agents, cliquez sur **Nouveau.** Dans le **champ Sélectionner un service** de recherche, tapez tout ou partie du nom du service **ApplicationServer** où vous souhaitez ajouter le groupe. Dans la liste des services obtenue, cliquez sur le service de votre choix, puis sur **OK**.
    
   - Pour modifier un groupe d’agents existant, tapez tout ou partie du nom du groupe d’agents dans le champ de recherche. Dans la liste qui en résulte, cliquez sur le groupe que vous souhaitez, cliquez sur **Modifier,** puis cliquez sur Afficher **les détails.**
    
5. Dans **Nom,** tapez un nom d’identification pour le groupe d’agents.
    
6. Dans **Description**, tapez la description du groupe.
    
7. Dans **Stratégie de participation**, sélectionnez l’une des options suivantes pour définir le comportement de connexion pour le groupe :
    
   - Sélectionnez **Informel** pour spécifier que les agents dans le groupe n’ont pas besoin de se connecter au groupe pour y accéder et de se déconnecter pour le quitter. Les agents sont automatiquement connectés au groupe lorsqu’ils se connectent à Skype Entreprise.
    
   - Sélectionnez **Formel** pour spécifier que les agents sont obligés de se connecter au groupe pour y accéder et de se déconnecter pour le quitter. Lorsque vous sélectionnez cette option, les agents cliquent sur un élément de menu dans Skype Entreprise pour ouvrir Internet Explorer et afficher une console de page web pour la connexion et la sortie du groupe.
    
8. Dans **Temps d’alerte (secondes)**, spécifiez combien de temps (en secondes) un appel doit sonner pour qu’il soit transmis à un agent disponible si l’agent auquel l’appel était initialement destiné ne peut pas y répondre (la durée par défaut est 20 secondes).
    
    > [!IMPORTANT]
    > Le paramètre de temps d’alerte de l’agent ne peut pas dépasser 180 secondes. Si le temps d’alerte de l’agent dépasse 180 secondes, l’application cliente rejette l’appel, car le minuteur de transaction SIP atteint son délai d’attente maximal. 
  
9. Dans **Méthode de routage**, sélectionnez la méthode pour transmettre les appels aux agents dans le groupe comme suit :
    
   - Pour d’abord proposer un nouvel appel à l’agent qui a été inactif le plus longtemps (a été la présence de **Disponible** ou **Inactif** dans Skype Entreprise le plus long), cliquez sur Le plus long **inactif**. 
    
   - Pour qu’un nouvel appel soit présenté à tous les agents disponibles simultanément, cliquez sur **Parallèle**. L’appel est envoyé au premier agent qui l’accepte.
    
   - Pour qu’un nouvel appel soit présenté à chaque agent, à tour de rôle, cliquez sur **Tourniquet (round robin)**. 
    
   - Pour qu’un nouvel appel soit toujours présenté aux agents dans l’ordre dans lequel ils apparaissent dans la liste **Agents**, cliquez sur **Série**. 
    
   - Pour proposer un nouvel appel à tous les agents qui sont en même temps Skype Entreprise et l’application Response Group, quelle que soit leur présence actuelle, cliquez sur **Attendant**. Les utilisateurs configurés en tant qu’agents peuvent voir tous les appels en attente et répondre aux appels en attente dans n’importe quel ordre. L’appel est envoyé au premier agent qui l’accepte, après quoi les autres agents ne voient plus l’appel.
    
10. Dans **Agents**, spécifiez comment vous voulez créer votre liste d’agents :
    
    - Pour utiliser une liste personnalisée d’agents, cliquez sur Définir un groupe personnalisé **d’agents** et faites l’une des choses suivantes :
    
    - Pour ajouter un utilisateur au groupe d’agents,  cliquez sur Sélectionner, puis dans le champ De recherche Sélectionner des agents, tapez tout ou partie du nom de l’utilisateur que vous souhaitez ajouter à ce groupe, puis cliquez sur **Rechercher.** Dans la liste des agents qui en résulte, cliquez sur l’utilisateur, puis sur **OK.**
    
    - Pour supprimer un utilisateur du groupe d’agents, dans la liste des agents, cliquez sur l’utilisateur à supprimer, puis cliquez sur **Supprimer.**
    
    - Pour modifier l’ordre dans lequel les appels sont proposés aux agents dans les groupes qui utilisent le routage round robin ou le routage en série, dans la liste des agents, cliquez sur un utilisateur, puis cliquez sur la flèche vers le haut ou vers le bas. 
    
    - Pour utiliser une liste de distribution Microsoft Exchange Server en tant que groupe d’agents, cliquez sur Utiliser une liste de **distribution** de courrier électronique existante, puis, dans l’adresse de la liste de **distribution,** tapez l’adresse e-mail de la liste de distribution (par exemple, NetworkSupport@contoso.com).
    
      Si vous utilisez une liste de distribution de courrier électronique, vous êtes soumis aux contraintes suivantes :
    
      - Vous ne pouvez pas sélectionner plusieurs listes de distribution pour le groupe d’agents. Chaque groupe prend en charge une seule liste de distribution.
    
      - Si la liste de distribution contient une ou plusieurs listes de distribution, les membres des listes de distribution imbriquées ne sont pas ajoutés à la liste d’agents.
    
      - Si le routage série ou round robin est sélectionné, le serveur propose un appel entrant à l’agent approprié en fonction de la méthode de routage et de l’ordre dans lequel les agents sont répertoriés dans la liste de distribution.
    
      - Si la liste de distribution contient des utilisateurs pour lesquels Lync Server 2010 est activé, mais que Voix Entreprise n’est pas activé, ils sont ajoutés au groupe d’agents en tant qu’agents d’exécution. Assurez-vous que tous les membres de la liste de distribution Voix Entreprise activés pour leurs comptes d’utilisateur.
    
    > [!IMPORTANT]
    > Si vous utilisez une liste de distribution de courrier électronique, les appartenances masquées ou les listes masquées peuvent devenir visibles pour l’administrateur ou les utilisateurs Response Group. 
  
    Les appartenances au groupe d’agents masquées ou les listes masquées peuvent devenir visibles comme suit :
    
     - Si une liste de distribution a été configurée pour que l’appartenance soit masquée et que l’administrateur Response Group affecte la liste de distribution à la liste des agents, les utilisateurs peuvent appeler le groupe pour savoir qui sont les membres. 
    
     - Si une liste de distribution a été configurée de sorte qu’elle soit masquée dans la liste d’adresses globale de Exchange, l’administrateur Response Group peut être en mesure d’en voir la liste de distribution et de l’affecter à la liste des agents si le processus Response Group dispose des droits et autorisations d’utilisateur appropriés, même si l’administrateur ne dispose pas des droits et autorisations d’utilisateur appropriés.
    
11. Cliquez sur **Valider**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a>Pour utiliser Skype Entreprise Server Management Shell pour créer ou modifier un groupe d’agents

1. Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.
    
2. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
3. Utilisez **New-CsRgsAgentGroup** pour créer un groupe d’agents. Utilisez **Set-CsRgsAgentGroup pour** modifier un groupe d’agents existant. À partir de la ligne de commande, exécutez la commande suivante :
    
   ```powershell
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    Par exemple :
    
   ```powershell
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > Le paramètre de temps d’alerte de l’agent ne peut pas dépasser 180 secondes. Si le temps d’alerte de l’agent est supérieur à 180 secondes, l’application cliente rejette l’appel, car le minuteur de transaction SIP atteint son délai d’attente maximal. 
  
4. Confirmez que le groupe d’agents est créé. Exécutez :  
    
   ```powershell
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a>Voir aussi

[Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps)
  
[New-CsRgsAgentGroup](/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[Set-CsRgsAgentGroup](/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[Get-CsRgsAgentGroup](/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)