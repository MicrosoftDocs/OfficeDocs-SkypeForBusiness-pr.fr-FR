---
title: Supprimer une règle de mise à jour des périphériques
TOCTitle: Supprimer une règle de mise à jour des périphériques
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994066(v=OCS.15)
ms:contentKeyID: 53095499
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Supprimer une règle de mise à jour des périphériques

 

_**Dernière rubrique modifiée :** 2013-02-23_

La suppression d’une règle de mise à jour des périphériques entraîne son effacement définitif de la file d’attente de mise à jour des périphériques.

La suppression d’une règle diffère de la désinstallation d’une mise à jour des périphériques de votre déploiement ou de vos périphériques tests. Pour désinstaller une règle approuvée de votre déploiement, vous devez *restaurer* la règle de mise à jour des périphériques. Pour plus d’informations, voir [Restaurer une règle de mise à jour des périphériques](lync-server-2013-restore-a-device-update-rule.md). Pour désinstaller une mise à jour non approuvée de vos périphériques, vous devez la *réinitialiser*. Pour plus d’informations, voir [Réinitialiser une règle de mise à jour des périphériques](lync-server-2013-reset-a-device-update-rule.md).

Vous pouvez supprimer une règle de mise à jour des périphériques à l’aide du Panneau de configuration Lync Server ou de Windows PowerShell.

## Pour supprimer une règle de mise à jour des périphériques à l’aide du Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Mise à jour du périphérique**.

4.  Dans la page **Mise à jour du périphérique**, effectuez l’une des opérations suivantes :
    
      - Pour supprimer une règle, sélectionnez-la.
    
      - Pour supprimer toutes les règles, cliquez sur le menu **Modifier**, puis sur **Sélectionner tout**.

5.  Cliquez sur **Modifier**, puis sur **Supprimer**.

## Suppression de règles de mise à jour des périphériques à l’aide d’applets de commande Windows PowerShell

Les règles de mise à jour des périphériques peuvent également être supprimées à l’aide de Windows PowerShell et de l’applet de commande **Remove-CsDeviceUpdateRule**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour supprimer une seule règle de mise à jour des périphériques d’un serveur

  - La commande suivante supprime la règle de mise à jour des périphériques d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 détectée du serveur web sur atl-cs-001.litwareinc.com.
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

## Pour supprimer toutes les règles de mise à jour des périphériques d’un serveur

  - La commande suivante supprime toutes les règles de mise à jour des périphériques du serveur web server sur atl-cs-001.litwareinc.com.
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsDeviceUpdateRule).

## Voir aussi

#### Tâches

[Approuver une règle de mise à jour des périphériques](lync-server-2013-approve-a-device-update-rule.md)

