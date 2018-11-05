---
title: Suppression d’une stratégie de version du client existante
TOCTitle: Suppression d’une stratégie de version du client existante
ms:assetid: b88aaa25-97ff-4eb6-bd34-b97332cd6890
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ923064(v=OCS.15)
ms:contentKeyID: 53095506
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression d’une stratégie de version du client existante

 

_**Dernière rubrique modifiée :** 2013-02-23_

Si vous souhaitez supprimer une stratégie de version du client configurée précédemment, vous pouvez la supprimer à partir du Panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.

## Pour supprimer des stratégies de version du client à l’aide du Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Stratégie de version du client**.

4.  Dans la page **Stratégie de version du client**, sélectionnez la ou les stratégies de version du client à supprimer, cliquez sur **Modifier**, puis sur **Supprimer**.

## Suppression de stratégies de version du client à l’aide d’applets de commande Windows PowerShell

Vous pouvez supprimer des stratégies de version du client à l’aide de l’applet de commande **Remove-CsClientVersionPolicy**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour supprimer une stratégie de version du client spécifique

  - Cette commande permet de supprimer la stratégie de version du client appliquée au site Redmond :
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

## Pour supprimer toutes les stratégies de version du client appliquées au niveau du site

  - Cette commande supprime toutes les stratégies de version du client configurées au niveau du site :
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

## Pour supprimer des stratégies de version du client qui n’incluent pas un agent utilisateur spécifique

  - Cette commande supprime toute stratégie de version du client qui n’inclut pas de règle pour l’agent utilisateur Windows Phone Lync (WPLync) :
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Remove-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClientVersionPolicy).

