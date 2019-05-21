---
title: Créer ou modifier un groupe d’agents dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: Créez ou modifiez un groupe d’agents dans Response Group dans Skype entreprise Server Voice.
ms.openlocfilehash: 0481e8048245908c757cf0dd1ecaed5d69291cb3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286203"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a>Créer ou modifier un groupe d’agents dans Skype entreprise
 
Créez ou modifiez un groupe d’agents dans Response Group dans Skype entreprise Server Voice.
  
Lorsque vous créez un groupe d’agents, vous sélectionnez les agents affectés au groupe, spécifiez différents autres paramètres du groupe, comme la méthode de routage des appels, et indiquez si un agent peut se connecter au groupe et s’en déconnecter. 
  
Un agent qui doit se connecter ou se déconnecter du groupe, qui est différent de la connexion ou de la déconnexion de Skype entreprise, est appelé agent formel. Les agents formels doivent être connectés au groupe pour recevoir des appels routés vers le groupe. Cela peut s’avérer utile pour les agents qui répondent à temps partiel aux appels du groupe. Les agents formels se connectent à leur groupe en cliquant sur un élément de menu dans Skype entreprise pour ouvrir le navigateur Internet de Windows Internet Explorer et afficher une console de pages Web.
  
Un agent qui ne se connecte pas ou n’utilise pas le groupe est appelé agent informel. Les agents informels sont automatiquement connectés au groupe lorsqu’ils se connectent à Skype entreprise et ne peuvent pas se déconnecter du groupe.
  
Seuls les utilisateurs locaux peuvent être des agents. Si un agent est déplacé de local vers en ligne, les appels de groupe de réponse ne seront pas routés vers cet agent.
  
Pour créer ou modifier un groupe d’agents, utilisez l’une des procédures ci-dessous.
  
> [!IMPORTANT]
> Lorsque vous affectez des utilisateurs comme agents de groupe de réponse, informez-les que, si leur mode de confidentialité est activé, ils doivent rechercher des contacts « RGS Presence Watcher » et les rajouter à leur liste de contacts. Les agents dont le mode de confidentialité est activé, mais qui n’ont aucun contact « RGS Presence Watcher » dans leur liste de contacts, ne peuvent pas recevoir d’appels vers le groupe de réponse. Les agents dont le mode de confidentialité n’est pas activé ne seront pas affectés. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a>Pour utiliser le panneau de configuration Skype entreprise Server pour créer ou modifier un groupe d’agents

1. Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre de l’un des rôles d’administration prédéfinis prenant en charge Response Group.
    
    > [!NOTE]
    > Si vous faites partie des responsables de groupes Response Group délégués pour un flux de travail géré, vous pouvez créer des groupes et les utiliser dans les flux de travail que vous gérez. 
  
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Groupes Response Group**, puis cliquez sur **Groupe**.
    
4. Dans la page **Groupe**, effectuez l’une des opérations suivantes :
    
   - Pour créer un groupe d’agents, cliquez sur **Nouveau**. Dans le champ de recherche **Sélectionner un service**, tapez entièrement ou partiellement le nom du service **ApplicationServer** à ajouter au groupe. Dans la liste des services obtenus, cliquez sur le service de votre choix, puis sur **OK**.
    
   - Pour modifier un groupe d’agents existant, tapez entièrement ou partiellement le nom du groupe d’agents dans le champ de recherche. Dans la liste obtenue, cliquez sur le groupe de votre choix, cliquez sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Nom**, tapez un nom d’identification pour le groupe d’agents.
    
6. Dans **Description**, tapez la description du groupe.
    
7. Dans **Stratégie de participation**, sélectionnez l’une des options ci-dessous pour définir le comportement de connexion du groupe :
    
   - Sélectionnez **Informel** pour spécifier que les agents du groupe n’ont pas besoin de se connecter au groupe ou de s’en déconnecter. Les agents sont automatiquement connectés au groupe lorsqu’ils se connectent à Skype entreprise.
    
   - Sélectionnez **Formel** pour spécifier que les agents du groupe doivent se connecter au groupe et s’en déconnecter. Lorsque vous sélectionnez cette option, l’agent clique sur un élément de menu dans Skype entreprise pour ouvrir Internet Explorer et afficher une console de pages Web pour vous connecter et se déconnecter du groupe.
    
8. Dans **Temps d’alerte (secondes)**, spécifiez la durée (en secondes) pendant laquelle un appel doit sonner pour qu’il soit transmis à un agent disponible si l’agent auquel l’appel était destiné initialement ne peut pas y répondre (la durée par défaut est de 20 secondes).
    
    > [!IMPORTANT]
    > Le paramètre de temps d’alerte d’agent ne peut pas dépasser 180 secondes. S’il dépasse 180 secondes, l’application cliente refusera l’appel, car la durée d’attente de la transaction SIP (Session Initiation Protocol) sera dépassée. 
  
9. Dans **Méthode de routage**, sélectionnez la méthode de transmission des appels aux agents dans le groupe, comme suit :
    
   - Pour vous permettre d’appeler tout d’abord l’agent qui est resté inactif le plus longtemps (a été **disponible** ou inactif dans Skype entreprise le plus longtemps), cliquez sur plus **longtemps**. **** 
    
   - Pour qu’un nouvel appel soit présenté simultanément à tous les agents disponibles, cliquez sur **Parallèle**. L’appel est envoyé au premier agent qui l’accepte.
    
   - Pour qu’un nouvel appel soit présenté à tour de rôle à chaque agent, cliquez sur **Tourniquet (round robin)**. 
    
   - Pour qu’un nouvel appel soit toujours présenté aux agents dans l’ordre dans lequel ils s’affichent dans la liste **Agents**, cliquez sur **Série**. 
    
   - Pour effectuer un nouvel appel vers tous les agents qui sont connectés à Skype entreprise et l’application Response Group en même temps, quelle que soit leur présence actuelle, cliquez sur **surveillant**. Les utilisateurs configurés comme agents peuvent voir tous les appels en attente et y répondre, dans l’ordre qui leur convient. L’appel est envoyé au premier agent qui l’accepte, et les autres agents ne peuvent alors plus voir l’appel.
    
10. Dans **Agents**, spécifiez la méthode de création de votre liste d’agents :
    
    - Pour utiliser une liste d’agents personnalisée, cliquez sur **Définir un groupe personnalisé d’agents**, puis effectuez l’une des opérations suivantes :
    
    - Pour ajouter un utilisateur au groupe d’agents, cliquez sur **Sélectionner**, puis dans le champ de recherche **Sélectionner des agents**, tapez l’intégralité ou le début du nom de l’utilisateur à ajouter à ce groupe, puis cliquez sur **Rechercher**. Dans la liste des agents obtenus, sélectionnez l’utilisateur, puis cliquez sur **OK**.
    
    - Pour supprimer un utilisateur du groupe d’agents, dans la liste des agents, cliquez sur l’utilisateur à supprimer, puis cliquez sur **Supprimer**.
    
    - Pour modifier l’ordre dans lequel les appels sont présentés aux agents dans des groupes utilisant des fonctions de routage en série ou à tour de rôle (tourniquet), dans la liste des agents, sélectionnez un utilisateur, puis cliquez sur la flèche vers le haut ou le bas. 
    
    - Pour utiliser une liste de distribution Microsoft Exchange Server comme groupe d’agents, cliquez sur **Utiliser une liste de distribution de courrier électronique existante**, puis tapez l’adresse de messagerie de la liste de distribution (par exemple, NetworkSupport@contoso.com) dans **Adresse de la liste de distribution**.
    
      Si vous utilisez une liste de distribution de courrier électronique, vous êtes soumis aux contraintes suivantes :
    
      - Vous ne pouvez pas sélectionner plusieurs listes de distribution pour le groupe d’agents. Chaque groupe prend en charge une seule liste de distribution.
    
      - Si la liste de distribution contient une ou plusieurs listes de distribution, les membres des listes de distribution imbriquées ne sont pas ajoutés à la liste d’agents.
    
      - Si le routage série ou le routage à tour de rôle (tourniquet) est sélectionné, le serveur présente un appel entrant à l’agent approprié selon la méthode de routage sélectionnée et dans l’ordre d’affichage des agents dans la liste de distribution.
    
      - Si la liste de distribution contient des utilisateurs pour lesquels Lync Server 2010 est activé mais pas Voix Entreprise, ces utilisateurs sont ajoutés au groupe d’agent comme agents dysfonctionnels. Assurez-vous que Voix Entreprise est activé pour le compte d’utilisateurs de tous les membres de la liste de distribution.
    
    > [!IMPORTANT]
    > Si vous utilisez une liste de distribution de courrier électronique, il est possible que les appartenances ou les listes masquées soient visibles pour l’administrateur du groupe de réponse ou les utilisateurs. 
  
    Les appartenances au groupe d’agents masquées ou les listes masquées peuvent devenir visibles, comme suit :
    
     - Si une liste de distribution a été configurée de telle sorte que l’appartenance est masquée et que l’administrateur du groupe de réponse affecte la liste de distribution à la liste des agents, les utilisateurs peuvent appeler le groupe pour savoir qui en est les membres. 
    
     - Si une liste de distribution a été configurée de façon à être cachée dans la liste d’adresses globale Exchange, l’administrateur du groupe de réponse peut voir la liste de distribution et l’affecter à la liste des agents si le processus de groupe de réponse dispose des droits d’utilisateur appropriés et les autorisations, même si l’administrateur ne possède pas les droits d’utilisateur et les autorisations appropriés.
    
11. Cliquez sur **Valider**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a>Pour utiliser Skype entreprise Server Management Shell pour créer ou modifier un groupe d’agents

1. Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre de l’un des rôles d’administration prédéfinis prenant en charge Response Group.
    
2. Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
3. Utilisez **New-CsRgsAgentGroup** pour créer un groupe d’agents. Utilisez **Set-CsRgsAgentGroup** pour modifier un groupe d’agents existant. Dans la ligne de commande, exécutez la commande suivante :
    
   ```
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    Exemple :
    
   ```
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > Le paramètre de temps d’alerte d’agent ne peut pas dépasser 180 secondes. S’il dépasse 180 secondes, l’application cliente refusera l’appel, car la durée d’attente de la transaction SIP (Session Initiation Protocol) sera dépassée. 
  
4. Confirmez la création du groupe d’agents. Exécutez :
    
   ```
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a>Voir aussi

[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
  
[Nouveau-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[Set-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)
