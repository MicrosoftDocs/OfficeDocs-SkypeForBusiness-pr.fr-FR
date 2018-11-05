---
title: Supprimer une file d’attente Response Group
TOCTitle: Supprimer une file d’attente Response Group
ms:assetid: 67c7a489-8c5f-4c6b-9387-9d4c11d43695
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg521008(v=OCS.15)
ms:contentKeyID: 49297464
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Supprimer une file d’attente Response Group

 

_**Dernière rubrique modifiée :** 2012-11-01_

Utilisez l’une des procédures suivantes pour supprimer une file d’attente.

## Pour utiliser le Panneau de configuration Lync Server pour supprimer une file d’attente

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administrateur prédéfinis qui prennent en charge Response Group.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Groupes Response Group**, puis sur **File d’attente**.

4.  Dans le champ de recherche, tapez entièrement ou partiellement le nom de la file d’attente que vous souhaitez supprimer.

5.  Dans la liste des files d’attente, cliquez sur la file d’attente souhaitée, sur **Modifier**, puis sur **Supprimer**.

6.  Cliquez sur **OK**.

## Pour utiliser des applets de commande pour supprimer une file d’attente

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administrateur prédéfinis qui prennent en charge Response Group.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  À partir de la ligne de commande, exécutez la commande suivante :
    
        Get-CsRgsQueue -Identity <Application Server service> -Name "<name of queue>" | Remove-CsRgsQueue
    
    Par exemple :
    
        Get-CsRgsQueue -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsQueue

