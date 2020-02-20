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
ms.openlocfilehash: c8dd855edfcef9d9503d433426492f0cc1517b61
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a>Création ou modification d’un groupe d’agents dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-07_

Utilisez l’une des procédures suivantes pour créer ou modifier un groupe d’agents.

<div>


> [!NOTE]  
> Un administrateur, par exemple CsVoiceAdministrator, doit activer les utilisateurs pour voix entreprise et Lync Server pour que les utilisateurs puissent être attribués à des groupes d’agents. Si vous êtes l’un des responsables des groupes Response Group délégués pour un flux de travail géré, vous pouvez créer des groupes d’agents et utiliser les groupes d’agents dans les flux de travail que vous gérez.



</div>

<div>


> [!IMPORTANT]  
> Lorsque vous affectez des utilisateurs en tant qu’agents au groupe de réponses, informez-les que, s’ils ont activé le mode de confidentialité, ils doivent rechercher des contacts « RGS Presence Watcher » et les ajouter à leur liste de contacts. Les agents dont le mode de confidentialité est activé, mais qui n’ont pas « RGS presence Watcher » dans leur liste de contacts, ne peuvent pas recevoir d’appels vers le groupe Response Group. Cela ne concerne pas les agents qui n’ont pas activé le mode de confidentialité.



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a>Pour créer ou modifier un groupe d’agents à l’aide du panneau de configuration Lync Server

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.
    
    <div>
    

    > [!NOTE]  
    > Si vous êtes l’un des responsables des groupes Response Group délégués pour un flux de travail géré, vous pouvez créer des groupes et les utiliser dans les flux de travail que vous gérez.

    
    </div>

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Groupes Response Group**, puis sur **Groupe**.

4.  Sur la page **groupe** , effectuez l’une des opérations suivantes :
    
      - Pour créer un groupe d’agents, cliquez sur **nouveau**. Dans le champ de recherche **Sélectionner un service** , tapez entièrement ou partiellement le nom du service **ApplicationServer** auquel vous souhaitez ajouter le groupe. Dans la liste des services obtenue, cliquez sur le service de votre choix, puis sur **OK**.
    
      - Pour modifier un groupe d’agents existant, tapez entièrement ou partiellement le nom du groupe d’agents dans le champ de recherche. Dans la liste obtenue, cliquez sur le groupe de votre choix, cliquez sur **modifier**, puis sur **afficher les détails**.

5.  Dans **nom**, tapez un nom d’identification pour le groupe d’agents.

6.  Dans **Description**, tapez la description du groupe.

7.  Dans **Stratégie de participation**, sélectionnez l’une des options suivantes pour définir le comportement de connexion pour le groupe :
    
      - Sélectionnez **Informel** pour spécifier que les agents dans le groupe n’ont pas besoin de se connecter au groupe pour y accéder et de se déconnecter pour le quitter. Les agents sont automatiquement connectés au groupe lorsqu’ils se connectent à Lync Server 2013.
    
      - Sélectionnez **Formel** pour spécifier que les agents sont obligés de se connecter au groupe pour y accéder et de se déconnecter pour le quitter. Lorsque vous sélectionnez cette option, les agents cliquent sur un élément de menu dans Lync pour ouvrir Internet Explorer et afficher une console de page Web pour la connexion et la déconnexion du groupe.

8.  Dans **Temps d’alerte (secondes)**, spécifiez combien de temps (en secondes) un appel doit sonner pour qu’il soit transmis à un agent disponible si l’agent auquel l’appel était initialement destiné ne peut pas y répondre (la durée par défaut est 20 secondes).
    
    <div>
    

    > [!IMPORTANT]  
    > Le paramètre de durée d’alerte de l’agent ne peut pas dépasser 180 secondes. Si la durée d’alerte de l’agent dépasse 180 secondes, l’application cliente rejette l’appel car le minuteur de la transaction SIP atteint le temps d’attente maximal.

    
    </div>

9.  Dans **Méthode de routage**, sélectionnez la méthode pour transmettre les appels aux agents dans le groupe comme suit :
    
      - Pour proposer un nouvel appel à l’agent qui a été inactif le plus longtemps (dont la présence est **disponible** ou **inactive** dans Lync Server le plus longtemps), cliquez sur le plus longtemps **inactif**.
    
      - Pour qu’un nouvel appel soit présenté à tous les agents disponibles simultanément, cliquez sur **Parallèle**. L’appel est envoyé au premier agent qui l’accepte.
    
      - Pour qu’un nouvel appel soit présenté à chaque agent, à tour de rôle, cliquez sur **Tourniquet (round robin)**.
    
      - Pour qu’un nouvel appel soit toujours présenté aux agents dans l’ordre dans lequel ils apparaissent dans la liste **Agents**, cliquez sur **Série**.
    
      - Pour proposer un nouvel appel à tous les agents connectés à Lync Server 2013 et à l’application Response Group en même temps, quelle que soit leur présence actuelle, cliquez sur **surveillance**. Les utilisateurs de la surveillance de Lync 2010 configurés comme agents peuvent voir tous les appels en attente et répondre aux appels en attente dans n’importe quel ordre. L’appel est envoyé au premier agent qui l’accepte, après quoi les autres utilisateurs de la surveillance de Lync 2010 ne voient plus l’appel.

10. Dans **Agents**, spécifiez comment vous voulez créer votre liste d’agents :
    
      - Pour utiliser une liste d’agents personnalisée, cliquez sur **définir un groupe personnalisé d’agents**, puis effectuez l’une des opérations suivantes :
        
          - Pour ajouter un utilisateur au groupe d’agents, cliquez sur **Sélectionner**, puis dans le champ de recherche **Sélectionner des agents** , tapez entièrement ou partiellement le nom de l’utilisateur que vous souhaitez ajouter à ce groupe, puis cliquez sur **Rechercher**. Dans la liste des agents obtenue, cliquez sur l’utilisateur, puis cliquez sur **OK**.
        
          - Pour supprimer un utilisateur du groupe d’agents, dans la liste des agents, cliquez sur l’utilisateur que vous souhaitez supprimer, puis cliquez sur **supprimer**.
        
          - Pour modifier l’ordre dans lequel les appels sont proposés aux agents dans des groupes qui utilisent le routage à répétition alternée ou le routage en série, dans la liste des agents, cliquez sur un utilisateur, puis sur la flèche vers le haut ou la flèche vers le bas.
    
      - Pour utiliser une liste de distribution Microsoft Exchange Server en tant que groupe d’agents, cliquez sur **utiliser une liste de distribution de courrier électronique existante**, puis, dans adresse de la **liste de distribution**, tapez l’adresse de messagerie de la liste de distribution (par exemple, NetworkSupport@contoso.com).
        
        Si vous utilisez une liste de distribution de courrier électronique, vous êtes soumis aux contraintes suivantes :
        
          - Vous ne pouvez pas sélectionner plusieurs listes de distribution pour le groupe d’agents. Chaque groupe prend en charge une seule liste de distribution.
        
          - Si la liste de distribution contient une ou plusieurs listes de distribution, les membres des listes de distribution imbriquées ne sont pas ajoutés à la liste d’agents.
        
          - Si le routage série ou tourniquet est sélectionné, le serveur offre un appel entrant à l’agent approprié en fonction de la méthode de routage et en fonction de l’ordre dans lequel les agents sont répertoriés dans la liste de distribution.
        
          - Si la liste de distribution contient des utilisateurs pour lesquels Lync Server 2010 est activé mais que voix entreprise n’est pas activé, ils seront ajoutés au groupe d’agents en tant qu’agents incorrects. Assurez-vous que voix entreprise est activé pour les comptes d’utilisateur de tous les membres de la liste de distribution.
        
        <div>
        

        > [!IMPORTANT]  
        > Si vous utilisez une liste de distribution de courrier électronique, les appartenances masquées ou les listes masquées peuvent devenir visibles par l’administrateur ou les utilisateurs du groupe Response Group.

        
        </div>
        
        Les appartenances au groupe d’agents masquées ou les listes masquées peuvent devenir visibles comme suit :
        
          - Si une liste de distribution a été configurée de sorte que l’appartenance est masquée et que l’administrateur du groupe réponse affecte la liste de distribution à la liste des agents, les utilisateurs peuvent appeler le groupe pour connaître l’identité des membres.
        
          - Si une liste de distribution a été configurée de sorte qu’elle soit masquée dans la liste d’adresses globale d’Exchange, l’administrateur de Response Group peut voir la liste de distribution et l’affecter à la liste des agents si le processus Response Group dispose des droits d’utilisateur appropriés et autorisations, même si l’administrateur ne dispose pas des droits d’utilisateur et des autorisations appropriés.

11. Cliquez sur **Valider**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a>Pour utiliser Windows PowerShell afin de créer ou de modifier un groupe d’agents

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Utilisez **New-CsRgsAgentGroup** pour créer un groupe d’agents. Utilisez **Set-CsRgsAgentGroup** pour modifier un groupe d’agents existant. À partir de la ligne de commande, exécutez la commande suivante :
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    Par exemple :
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > Le paramètre de durée d’alerte de l’agent ne peut pas dépasser 180 secondes. Si la durée de l’alerte de l’agent est supérieure à 180 secondes, l’application cliente rejette l’appel car le minuteur de la transaction SIP atteint le temps d’attente maximal.

    
    </div>

4.  Vérifiez que le groupe d’agents est créé. Générer
    
        Get-CsRgsAgentGroup -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Supprimer un groupe d’agents dans Lync Server 2013](lync-server-2013-delete-an-agent-group.md)  


[Gestion des groupes d’agents Response Group dans Lync Server 2013](lync-server-2013-managing-response-group-agent-groups.md)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup)  
[Set-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsAgentGroup)  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

