---
title: Restaurer une règle de mise à jour des périphériques
TOCTitle: Restaurer une règle de mise à jour des périphériques
ms:assetid: ac490baf-c7a0-48d9-8fd0-ba5729489341
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994061(v=OCS.15)
ms:contentKeyID: 53095495
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restaurer une règle de mise à jour des périphériques

 

_**Dernière rubrique modifiée :** 2013-02-23_

Pour désinstaller une règle de mise à jour des périphériques applicable aux périphériques de votre déploiement, restaurez-la. La restauration d’une règle de mise à jour des périphériques entraîne à la fois sa désinstallation et la réinstallation de sa version précédente.

Vous pouvez désinstaller une règle de mise à jour des périphériques à l’aide du Panneau de configuration Lync Server ou de Windows PowerShell.

## Pour restaurer une règle de mise à jour des périphériques à l’aide du Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Mise à jour du périphérique**.

4.  Dans la page **Mise à jour du périphérique**, effectuez l’une des opérations suivantes :
    
      - Pour restaurer une règle, sélectionnez-la.
    
      - Pour restaurer toutes les règles, cliquez sur **Modifier**, puis sur **Sélectionner tout**.

5.  Cliquez sur le menu **Action**, puis sur **Restaurer**.

## Restauration de règles de mise à jour des périphériques à l’aide d’applets de commande Windows PowerShell

Les règles de mise à jour des périphériques peuvent également être désinstallées à l’aide de Windows PowerShell et de l’applet de commande **Restore-CsDeviceUpdateRule**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell.

> [!NOTE]  
> Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>.

## Pour restaurer une seule règle de mise à jour des périphériques sur un serveur

  - La commande suivante restaure la règle de mise à jour des périphériques d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 sur le serveur web atl-cs-001.litwareinc.com :
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

## Pour restaurer toutes les règles de mise à jour des périphériques sur un serveur

  - La commande suivante restaure toutes les règles de mise à jour des périphériques sur le serveur web server atl-cs-001.litwareinc.com :
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Restore-CsDeviceUpdateRule).

