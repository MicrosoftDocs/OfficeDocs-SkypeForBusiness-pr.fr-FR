---
title: Suppression d’un flux de travail
TOCTitle: Suppression d’un flux de travail
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg520944(v=OCS.15)
ms:contentKeyID: 49296108
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression d’un flux de travail

 

_**Dernière rubrique modifiée :** 2012-11-01_

Pour supprimer un flux de travail, effectuez l’une des procédures suivantes.

## Supprimer un flux de travail à l’aide du Panneau de configuration Lync Server

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administrateur prédéfinis qui prennent en charge Response Group.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Groupes Response Group**, puis sur **Flux de travail**.

4.  Dans la page **Flux de travail**, cliquez sur **Créer ou modifier un flux de travail**.

5.  Dans le champ de recherche **Sélectionner un service**, tapez l’intégralité ou le début du nom du service **ApplicationServer** qui héberge le flux de travail que vous voulez supprimer.

6.  Dans la liste des services, cliquez sur le service voulu, puis sur **OK**.
    
    > [!NOTE]  
    > La page web de l’outil de configuration Response Group s’ouvre. Vous pouvez également ouvrir la page web de l’outil de configuration Response Group directement depuis un navigateur web en vous connectant à <strong>https://<em>&lt;webPoolFqdn&gt;</em>/RgsConfig</strong>.

7.  Sous **Gérer un flux de travail existant**, recherchez le flux de travail que vous souhaitez supprimer, puis sous **Action**, cliquez sur **Supprimer**.

8.  Cliquez sur **Oui**.

## Supprimer un flux de travail à l’aide d’applets de commande

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administrateur prédéfinis qui prennent en charge Response Group.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  À partir de la ligne de commande, exécutez la commande suivante :
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    Par exemple :
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

