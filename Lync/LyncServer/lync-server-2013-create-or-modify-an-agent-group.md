---
title: 'Lync Server 2013 : Création ou modification d’un groupe d’agents'
TOCTitle: Création ou modification d’un groupe d’agents
ms:assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205370(v=OCS.15)
ms:contentKeyID: 49299294
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création ou modification d’un groupe d’agents dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-02-07_

Utilisez l’une des procédures suivantes pour créer ou modifier un groupe d’agents.

> [!NOTE]  
> Un administrateur (par exemple, CsVoiceAdministrator) doit activer les utilisateurs de Voix Entreprise et Lync Server pour qu’ils puissent être affectés aux groupes d’agents. Si vous faites partie des responsables de groupes de réponse délégués pour un flux de travail géré, vous pouvez créer des groupes d’agents et les utiliser dans les flux de travail que vous gérez.

> [!IMPORTANT]  
> Lorsque vous affectez des utilisateurs en tant qu’agents de groupe de réponse, informez-les que, si leur mode de confidentialité est activé, ils doivent rechercher des contacts « RGS Presence Watcher » et les rajouter à leur liste de contacts. Les agents dont le mode de confidentialité est activé, mais qui n’ont aucun contact « RGS Presence Watcher » dans leur liste de contacts, ne peuvent pas recevoir d’appels vers le groupe de réponse. Les agents dont le mode de confidentialité n’est pas activé ne seront pas affectés.

## Pour utiliser Panneau de configuration Lync Server pour créer ou modifier un groupe d’agents

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administrateur prédéfinis qui prennent en charge Response Group.
    
    > [!NOTE]  
    > Si vous faites partie des responsables de groupes Response Group délégués pour un flux de travail géré, vous pouvez créer des groupes et les utiliser dans les flux de travail que vous gérez.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Groupes Response Group**, puis cliquez sur **Groupe**.

4.  Dans la page **Groupe**, effectuez l’une des opérations suivantes :
    
      - Pour créer un nouveau groupe d’agents, cliquez sur **Nouveau**. Dans le champ de recherche **Sélectionner un service**, tapez entièrement ou partiellement le nom du service **ApplicationServer** que vous souhaitez ajouter au groupe. Dans la liste des services obtenus, cliquez sur le service de votre choix, puis sur **OK**.
    
      - Pour modifier un groupe d’agents existant, tapez entièrement ou partiellement le nom du groupe d’agents dans le champ de recherche. Dans la liste obtenue, cliquez sur le groupe de votre choix, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

5.  Dans **Nom**, tapez un nom d’identification pour le groupe d’agents.

6.  Dans **Description**, tapez la description du groupe.

7.  Dans **Stratégie de participation**, sélectionnez l’une des options suivantes pour définir le comportement de connexion pour le groupe :
    
      - Sélectionnez **Informel** pour spécifier que les agents du groupe n’ont pas besoin de se connecter ou se déconnecter du groupe. Les agents sont connectés automatiquement dans le groupe lorsqu’ils se connectent à Lync Server 2013.
    
      - Sélectionnez **Formel** pour spécifier que les agents du groupe doivent se connecter et se déconnecter du groupe. Lorsque vous sélectionnez cette option, les agents doivent cliquer sur un élément de menu dans Lync pour ouvrir Internet Explorer et afficher une console web pour se connecter/déconnecter du groupe.

8.  Dans **Temps d’alerte (secondes)**, spécifiez combien de temps (en secondes) un appel doit sonner pour qu’il soit transmis à un agent disponible si l’agent auquel l’appel était initialement destiné ne peut pas y répondre (la durée par défaut est 20 secondes).
    
    > [!IMPORTANT]  
    > Le paramètre de temps d’alerte d’agent ne peut pas dépasser 180 secondes. S’il dépasse 180 secondes, l’application cliente refusera l’appel, car la durée d’attente de la transaction SIP sera dépassée.

9.  Dans **Méthode de routage**, sélectionnez la méthode pour transmettre les appels aux agents dans le groupe comme suit :
    
      - Pour présenter d’abord un nouvel appel l’agent resté le plus longtemps inactif (c’est-à-dire celui qui est resté le plus longtemps avec l’état de présence **Disponible** ou **Inactif** dans Lync Server), cliquez sur **Le plus longuement inactif**.
    
      - Pour qu’un nouvel appel soit présenté à tous les agents disponibles simultanément, cliquez sur **Parallèle**. L’appel est envoyé au premier agent qui l’accepte.
    
      - Pour qu’un nouvel appel soit présenté à chaque agent, à tour de rôle, cliquez sur **Tourniquet (round robin)**.
    
      - Pour qu’un nouvel appel soit toujours présenté aux agents dans l’ordre dans lequel ils s’affichent dans la liste **Agents**, cliquez sur **Série**.
    
      - Pour présenter un nouvel appel à tous les agents connectés simultanément à Lync Server 2013 et à l’application Response Group, indépendamment de leur présence actuelle, cliquez sur **Standard**. Les utilisateurs de Intendant Lync 2010 configurés en tant qu’agents peuvent voir tous les appels en attente et y répondre, dans l’ordre qui leur convient. L’appel est envoyé au premier agent qui l’accepte, après quoi les autres utilisateurs de Intendant Lync 2010 ne peuvent plus voir l’appel.

10. Dans **Agents**, spécifiez la méthode de création de votre liste d’agents :
    
      - Pour utiliser une liste d’agents personnalisée, cliquez sur **Définir un groupe personnalisé d’agents**, puis effectuez l’une des opérations suivantes :
        
          - Pour ajouter un utilisateur au groupe d’agents, cliquez sur **Sélectionner**, puis dans le champ de recherche **Sélectionner des agents**, tapez l’intégralité ou le début du nom de l’utilisateur que vous souhaitez ajouter à ce groupe, puis cliquez sur **Rechercher**. Dans la liste des agents obtenus, cliquez sur l’utilisateur, puis cliquez sur **OK**.
        
          - Pour supprimer un utilisateur du groupe d’agents, dans la liste des agents, cliquez sur l’utilisateur que vous souhaitez supprimer, puis cliquez sur **Supprimer**.
        
          - Pour changer l’ordre dans lequel les appels sont présentés aux agents dans des groupes à utilisant des fonctions de routage en série ou à tour de rôle (tourniquet), dans la liste des agents, cliquez sur un utilisateur, puis cliquez sur la flèche vers le haut ou le bas.
    
      - Pour utiliser une liste de distribution Microsoft Exchange Server en tant que groupe d’agents, cliquez sur **Utiliser une liste de distribution de courrier électronique existante**, puis tapez l’adresse de messagerie de la liste de distribution (par exemple, NetworkSupport@contoso.com) dans **Adresse de la liste de distribution**.
        
        Si vous utilisez une liste de distribution de courrier électronique, vous êtes soumis aux contraintes suivantes :
        
          - Vous ne pouvez pas sélectionner plusieurs listes de distribution pour le groupe d’agents. Chaque groupe prend en charge une seule liste de distribution.
        
          - Si la liste de distribution contient une ou plusieurs listes de distribution, les membres des listes de distribution imbriquées ne sont pas ajoutés à la liste d’agents.
        
          - Si le routage série ou le routage à tour de rôle (tourniquet) est sélectionné, le serveur présente un appel entrant à l’agent approprié selon la méthode de routage sélectionnée et selon l’ordre dans lequel les agents s’affichent dans la liste de distribution.
        
          - Si la liste de distribution contient des utilisateurs pour lesquels Lync Server 2010 est activé mais pas Voix Entreprise, ces utilisateurs sont ajoutés au groupe d’agent en tant qu’agents dysfonctionnels. Assurez-vous que tous les membres de la liste de distribution ont Voix Entreprise activée pour leurs comptes d’utilisateurs.
        
        > [!IMPORTANT]  
        > Si vous utilisez une liste de distribution de courrier électronique, les appartenances au groupe d’agents masquées ou les listes masquées peuvent devenir visible pour l’administrateur ou les utilisateurs de l’application Response Group.        
        Les appartenances au groupe d’agents masquées ou les listes masquées peuvent devenir visibles comme suit :
        
          - Si une liste de distribution a été configurée pour que l’appartenance au groupe d’agents soit masquée et si l’administrateur de l’application Response Group affecte la liste de distribution à la liste d’agents, les utilisateurs peuvent appeler le groupe pour en connaître les membres.
        
          - Si une liste de distribution a été configurée pour être masquée dans la liste d’adresses globales Exchange, l’administrateur de l’application Response Group pourra consulter la liste de distribution et l’affecter à la liste d’agents, à condition que le processus de l’application Response Group dispose des droits et des autorisations d’utilisateur appropriés, même si l’administrateur ne dispose pas de ces droits et autorisations.

11. Cliquez sur **Valider**.

## Pour utiliser Windows PowerShell pour créer ou modifier un groupe d’agents

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administrateur prédéfinis qui prennent en charge Response Group.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Utilisez **New-CsRgsAgentGroup** pour créer un nouveau groupe d’agents. Utilisez **Set-CsRgsAgentGroup** pour modifier un groupe d’agents existant. À partir de la ligne de commande, exécutez la commande suivante :
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    Exemple :
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    > [!IMPORTANT]  
    > Le paramètre de temps d’alerte d’agent ne peut pas dépasser 180 secondes. S’il dépasse 180 secondes, l’application cliente refusera l’appel, car la durée d’attente de la transaction SIP sera dépassée.

4.  Confirmez la création du groupe d’agents. Exécutez :
    
        Get-CsRgsAgentGroup -Name "Help Desk"

## Voir aussi

#### Tâches

[Supprimer un groupe d’agents](lync-server-2013-delete-an-agent-group.md)  

#### Autres ressources

[Gestion des groupes d’agents Response Group](lync-server-2013-managing-response-group-agent-groups.md)  
[Get-CsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsService)  
[New-CsRgsAgentGroup](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsAgentGroup)  
[Set-CsRgsAgentGroup](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsRgsAgentGroup)  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsRgsAgentGroup)

