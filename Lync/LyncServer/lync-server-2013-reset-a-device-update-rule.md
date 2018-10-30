---
title: Réinitialiser une règle de mise à jour des périphériques
TOCTitle: Réinitialiser une règle de mise à jour des périphériques
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994069(v=OCS.15)
ms:contentKeyID: 53095533
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Réinitialiser une règle de mise à jour des périphériques

 

_**Dernière rubrique modifiée :** 2013-02-23_

Si vous n’appréciez pas le fonctionnement d’une mise à jour sur vos périphériques de test, vous pouvez réinitialiser la règle de mise à jour des périphériques, ce qui supprime l’état en attente de la règle et désinstalle la mise à jour des périphériques de test.

Vous pouvez supprimer une règle de mise à jour des périphériques à l’aide du Panneau de configuration Lync Server ou de Windows PowerShell.

> [!NOTE]  
> Pour désinstaller une règle que vous avez déjà approuvée (autrement dit, déployée), restaurez-la. Pour plus d’informations, voir <a href="lync-server-2013-restore-a-device-update-rule.md">Restaurer une règle de mise à jour des périphériques</a>.

## Pour réinitialiser une règle de mise à jour des périphériques à l’aide du Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Mise à jour du périphérique**.

4.  Dans la page **Mise à jour du périphérique**, effectuez l’une des opérations suivantes :
    
      - Pour réinitialiser une règle, sélectionnez-la.
    
      - Pour réinitialiser toutes les règles, dans le menu **Modifier**, cliquez sur **Sélectionner tout**.
    
      - Pour réinitialiser toutes les règles pour une marque, utilisez le menu de la colonne **Marque**.

5.  Cliquez sur **Action**, puis sur **Annuler les mises à jour en attente**.
    
    > [!TIP]  
    > Si vous êtes certain que vous ne souhaiterez jamais déployer les mises à jour que vous avez annulées, vous pouvez les supprimer. Pour plus d’informations, voir <a href="lync-server-2013-remove-a-device-update-rule.md">Supprimer une règle de mise à jour des périphériques</a>.

## Réinitialisation d’une règle de mise à jour des périphériques à l’aide d’applets de commande Windows PowerShell

Les règles de mise à jour des périphériques peuvent également être réinitialisées à l’aide de Windows PowerShell et de l’applet de commande **Reset-CsDeviceUpdateRule**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell.

> [!NOTE]  
> Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>.

## Pour réinitialiser une règle de mise à jour des périphériques spécifique sur un serveur

  - La commande suivante réinitialise la règle de mise à jour des périphériques d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 sur le serveur web atl-cs-001.litwareinc.com :
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

## Pour réinitialiser toutes les règles de mise à jour des périphériques sur un serveur

  - La commande suivante réinitialise toutes les règles de mise à jour des périphériques sur le serveur web server atl-cs-001.litwareinc.com :
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

## Pour réinitialiser toutes les règles de mise à jour des périphériques de marque spécifique

  - Dans cet exemple, toutes les mises à jour des périphériques dans l’organisation ayant une Marque égale à Microsoft sont réinitialisées :
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Reset-CsDeviceUpdateRule).

## Voir aussi

#### Tâches

[Approuver une règle de mise à jour des périphériques](lync-server-2013-approve-a-device-update-rule.md)

