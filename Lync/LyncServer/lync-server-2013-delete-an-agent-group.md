---
title: Supprimer un groupe d’agents
TOCTitle: Supprimer un groupe d’agents
ms:assetid: df385fd1-62f4-42b7-a349-4eb38dea50c8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182597(v=OCS.15)
ms:contentKeyID: 49299070
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Supprimer un groupe d’agents

 

_**Dernière rubrique modifiée :** 2012-11-01_

Les procédures suivantes permettent de supprimer un groupe d’agents.

## Pour utiliser Panneau de configuration Lync Server pour supprimer un groupe d’agents

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administrateur prédéfinis qui prennent en charge Response Group.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Groupes Response Group**, puis sur **Groupe**.

4.  Dans la page **Services Response Group**, tapez entièrement ou partiellement le nom du groupe d’agents que vous voulez supprimer dans le champ de recherche.

5.  Dans la liste obtenue, cliquez sur le groupe à supprimer, sur **Modifier**, puis sur **Supprimer**.

6.  Cliquez sur **OK**.

## Pour utiliser les applets de commande pour supprimer un groupe d’agents

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administrateur prédéfinis qui prennent en charge Response Group.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  À partir de la ligne de commande, exécutez la commande suivante :
    
        Get-CsRgsAgentGroup -Identity <Application Server service> -Name "<name of agent group>" | Remove-CsRgsAgentGroup
    
    Par exemple :
    
        Get-CsRgsAgentGroup -Identity service:ApplicationServer:redmond.contoso.com -Name "Human Resources" | Remove-CsRgsAgentGroup

## Voir aussi

#### Tâches

[Création ou modification d’un groupe d’agents dans Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)  

#### Autres ressources

[Remove-CsRgsAgentGroup](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsRgsAgentGroup)  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsRgsAgentGroup)

