---
title: Suppression d’une stratégie de conférence existante
TOCTitle: Suppression d’une stratégie de conférence existante
ms:assetid: 709ed771-790f-4bf1-a4de-b37ca5168688
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688089(v=OCS.15)
ms:contentKeyID: 49891392
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression d’une stratégie de conférence existante

 

_**Dernière rubrique modifiée :** 2013-02-23_

Suivez cette procédure pour supprimer une stratégie de conférence au niveau de l’utilisateur ou du site.

> [!NOTE]  
> Vous ne pouvez pas supprimer la stratégie de conférence globale.

## Pour supprimer une stratégie de conférence au niveau de l’utilisateur ou du site

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de conférence**.

4.  Dans la liste des stratégies de conférence, cliquez sur la stratégie de site ou d’utilisateur à supprimer, cliquez sur Modifier, puis cliquez sur Supprimer.

## Suppression de stratégies de conférence à l’aide des applets de commande Lync Server Management Shell

Vous pouvez également supprimer des paramètres de configuration de jonction à l’aide de Lync Server Management Shell et de l’applet de commande **Remove-CsConferencingPolicy**. Vous pouvez exécuter cette dernière depuis Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour supprimer une stratégie de conférence spécifiée

  - La commande suivante permet de supprimer la stratégie de conférence dont le paramètre Identity a la valeur RedmondConferencingPolicy :
    
        Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"

## Pour supprimer toutes les stratégies de conférence appliquées à l’étendue par utilisateur

  - La commande suivante permet de supprimer toutes les stratégies de conférence configurées dans l’étendue par utilisateur :
    
        Get-CsConferencingPolicy -Filter "tag:*" | Remove-CsConferencingPolicy

## Pour supprimer toutes les stratégies de conférence qui autorise l’enregistrement par des utilisateurs externes

  - La commande suivante permet de supprimer toutes les stratégies de conférence qui autorisent les utilisateurs externes à enregistrer la conférence :
    
        Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy

Pour plus d’informations, voir [Remove-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsConferencingPolicy).

