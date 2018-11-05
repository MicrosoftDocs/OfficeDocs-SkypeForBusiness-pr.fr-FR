---
title: Supprimer une stratégie de code confidentiel
TOCTitle: Supprimer une stratégie de code confidentiel
ms:assetid: 7c378927-2e41-418e-9721-327021bd2e45
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg521020(v=OCS.15)
ms:contentKeyID: 49297847
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Supprimer une stratégie de code confidentiel

 

_**Dernière rubrique modifiée :** 2013-02-23_

Suivez cette procédure pour supprimer une stratégie de code confidentiel (PIN).

> [!NOTE]  
> Vous ne pouvez pas supprimer la stratégie de code confidentiel globale.

## Pour supprimer une stratégie de code confidentiel dans le Panneau de configuration Lync Server 2013

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Stratégie de code confidentiel**.

4.  Dans la page **Stratégie de code confidentiel**, dans le champ de recherche, tapez entièrement ou partiellement le nom de la stratégie à supprimer.

5.  Dans la liste des stratégies, cliquez sur la stratégie que vous souhaitez supprimer, cliquez sur **Modifier**, puis sur **Supprimer**.

6.  Cliquez sur **OK**.

## Suppression de stratégies de code confidentiel avec Lync Server Management Shell et les applets de commande

Vous pouvez supprimer des stratégies de code confidentiel avec Windows PowerShell et l’applet de commande Remove-CsPinPolicy. Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Suppression d’une stratégie de code confidentiel spécifique

  - Cette commande supprime la stratégie de code confidentiel avec l’identité RedmondPinPolicy :
    
        Remove-CsPinPolicy -Identity "RedmondPinPolicy"

## Suppression de toutes les stratégies de code confidentiel appliquées au niveau du site

  - Cette commande supprime toutes les stratégies de code confidentiel configurées au niveau du site :
    
        Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy

## Suppression de toutes les stratégies de code confidentiel qui autorisent l’utilisation de critères communs

  - Cette commande supprime toutes les stratégies de code confidentiel qui autorisent l’utilisation de critères communs : G
    
        et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Remove-CsPinPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsPinPolicy).

