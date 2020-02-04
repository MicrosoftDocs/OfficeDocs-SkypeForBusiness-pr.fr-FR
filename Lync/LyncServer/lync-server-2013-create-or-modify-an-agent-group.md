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

# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a>Créer ou modifier un groupe d’agents dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-07_

Pour créer ou modifier un groupe d’agents, utilisez l’une des procédures ci-dessous.

<div>


> [!NOTE]  
> Un administrateur (par exemple, CsVoiceAdministrator) doit permettre aux utilisateurs d’Enterprise Voice et de Lync Server d’affecter les utilisateurs à des groupes d’agents. Si vous êtes l’un des gestionnaires de groupe de réponse déléguée pour un flux de travail géré, vous pouvez créer des groupes d’agents et utiliser les groupes d’agents dans les flux de travail que vous gérez.



</div>

<div>


> [!IMPORTANT]  
> Lorsque vous affectez des utilisateurs comme agents de groupe de réponse, informez-les que, si leur mode de confidentialité est activé, ils doivent rechercher des contacts « RGS Presence Watcher » et les rajouter à leur liste de contacts. Les agents dont le mode de confidentialité est activé, mais qui n’ont aucun contact « RGS Presence Watcher » dans leur liste de contacts, ne peuvent pas recevoir d’appels vers le groupe de réponse. Les agents dont le mode de confidentialité n’est pas activé ne seront pas affectés.



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a>Pour utiliser le panneau de configuration de Lync Server pour créer ou modifier un groupe d’agents

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre de l’un des rôles d’administration prédéfinis prenant en charge Response Group.
    
    <div>
    

    > [!NOTE]  
    > Si vous faites partie des responsables de groupes Response Group délégués pour un flux de travail géré, vous pouvez créer des groupes et les utiliser dans les flux de travail que vous gérez.

    
    </div>

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Groupes Response Group**, puis cliquez sur **Groupe**.

4.  Dans la page **Groupe**, effectuez l’une des opérations suivantes :
    
      - Pour créer un groupe d’agents, cliquez sur **Nouveau**. Dans le champ de recherche **Sélectionner un service**, tapez entièrement ou partiellement le nom du service **ApplicationServer** à ajouter au groupe. Dans la liste des services obtenus, cliquez sur le service de votre choix, puis sur **OK**.
    
      - Pour modifier un groupe d’agents existant, tapez entièrement ou partiellement le nom du groupe d’agents dans le champ de recherche. Dans la liste obtenue, cliquez sur le groupe de votre choix, cliquez sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Nom**, tapez un nom d’identification pour le groupe d’agents.

6.  Dans **Description**, tapez la description du groupe.

7.  Dans **Stratégie de participation**, sélectionnez l’une des options ci-dessous pour définir le comportement de connexion du groupe :
    
      - Sélectionnez **Informel** pour spécifier que les agents du groupe n’ont pas besoin de se connecter au groupe ou de s’en déconnecter. Les agents sont automatiquement connectés au groupe lorsqu’ils se connectent à Lync Server 2013.
    
      - Sélectionnez **Formel** pour spécifier que les agents du groupe doivent se connecter au groupe et s’en déconnecter. Lorsque vous sélectionnez cette option, l’agent clique sur un élément de menu dans Lync pour ouvrir Internet Explorer et afficher une console de pages Web pour vous connecter et se déconnecter du groupe.

8.  Dans **Temps d’alerte (secondes)**, spécifiez la durée (en secondes) pendant laquelle un appel doit sonner pour qu’il soit transmis à un agent disponible si l’agent auquel l’appel était destiné initialement ne peut pas y répondre (la durée par défaut est de 20 secondes).
    
    <div>
    

    > [!IMPORTANT]  
    > Le paramètre de temps d’alerte d’agent ne peut pas dépasser 180 secondes. S’il dépasse 180 secondes, l’application cliente refusera l’appel, car la durée d’attente de la transaction SIP (Session Initiation Protocol) sera dépassée.

    
    </div>

9.  Dans **Méthode de routage**, sélectionnez la méthode de transmission des appels aux agents dans le groupe, comme suit :
    
      - Pour vous permettre d’appeler tout d’abord l’agent qui est resté inactif le plus longtemps (a été **disponible** ou **inactif** dans Lync Server le plus longtemps), cliquez sur **inactif**le plus longtemps.
    
      - Pour qu’un nouvel appel soit présenté simultanément à tous les agents disponibles, cliquez sur **Parallèle**. L’appel est envoyé au premier agent qui l’accepte.
    
      - Pour qu’un nouvel appel soit présenté à tour de rôle à chaque agent, cliquez sur **Tourniquet (round robin)**.
    
      - Pour qu’un nouvel appel soit toujours présenté aux agents dans l’ordre dans lequel ils s’affichent dans la liste **Agents**, cliquez sur **Série**.
    
      - Pour effectuer un nouvel appel vers tous les agents connectés à Lync Server 2013 et l’application de groupe de réponse en même temps, quelle que soit leur présence actuelle, cliquez sur **surveillant**. Les utilisateurs de la surveillance de Lync 2010 configurés en tant qu’agents peuvent voir tous les appels en attente et répondre aux appels en attente dans n’importe quel ordre. L’appel est envoyé au premier agent qui l’a accepté, à l’issue duquel les autres utilisateurs de Lync 2010 attendant ne verront plus l’appel.

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
        
        <div>
        

        > [!IMPORTANT]  
        > Si vous utilisez une liste de distribution de courrier électronique, il est possible que les appartenances ou les listes masquées soient visibles pour l’administrateur du groupe de réponse ou les utilisateurs.

        
        </div>
        
        Les appartenances au groupe d’agents masquées ou les listes masquées peuvent devenir visibles, comme suit :
        
          - Si une liste de distribution a été configurée de telle sorte que l’appartenance est masquée et que l’administrateur du groupe de réponse affecte la liste de distribution à la liste des agents, les utilisateurs peuvent appeler le groupe pour savoir qui en est les membres.
        
          - Si une liste de distribution a été configurée de façon à être cachée dans la liste d’adresses globale Exchange, l’administrateur du groupe de réponse peut voir la liste de distribution et l’affecter à la liste des agents si le processus de groupe de réponse dispose des droits d’utilisateur appropriés et les autorisations, même si l’administrateur ne possède pas les droits d’utilisateur et les autorisations appropriés.

11. Cliquez sur **Valider**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a>Pour utiliser Windows PowerShell pour créer ou modifier un groupe d’agents

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre de l’un des rôles d’administration prédéfinis prenant en charge Response Group.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Utilisez **New-CsRgsAgentGroup** pour créer un groupe d’agents. Utilisez **Set-CsRgsAgentGroup** pour modifier un groupe d’agents existant. Dans la ligne de commande, exécutez la commande suivante :
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    Exemple :
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > Le paramètre de temps d’alerte d’agent ne peut pas dépasser 180 secondes. S’il dépasse 180 secondes, l’application cliente refusera l’appel, car la durée d’attente de la transaction SIP (Session Initiation Protocol) sera dépassée.

    
    </div>

4.  Confirmez la création du groupe d’agents. Exécutez :
    
        Get-CsRgsAgentGroup -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Supprimer un groupe d’agents dans Lync Server 2013](lync-server-2013-delete-an-agent-group.md)  


[Gestion des groupes d’agents de Response Group dans Lync Server 2013](lync-server-2013-managing-response-group-agent-groups.md)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Nouveau-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup)  
[Set-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsAgentGroup)  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

