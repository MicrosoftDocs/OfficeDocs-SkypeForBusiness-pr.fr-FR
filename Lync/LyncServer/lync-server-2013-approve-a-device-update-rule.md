---
title: Approuver une règle de mise à jour des périphériques
TOCTitle: Approuver une règle de mise à jour des périphériques
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994053(v=OCS.15)
ms:contentKeyID: 53095482
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Approuver une règle de mise à jour des périphériques

 

_**Dernière rubrique modifiée :** 2013-02-23_

Une fois qu’une règle de mise à jour des périphériques a été importée, elle est installée sur vos périphériques tests. Si les tests sont concluants et que vous souhaitez déployer la mise à jour dans votre organisation, approuvez-la à l’aide du Panneau de configuration Lync Server ou de Windows PowerShell.

## Pour approuver une règle de mise à jour des périphériques à l’aide du Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la page **Mise à jour du périphérique**, effectuez l’une des opérations suivantes :
    
      - Pour approuver une règle, sélectionnez-la.
    
      - Pour approuver toutes les règles, cliquez sur **Modifier**, puis sur **Sélectionner tout**.

4.  Cliquez sur **Action**, puis sur **Approuver**.

## Approbation d’une règle de mise à jour des périphériques à l’aide d’applets de commande Windows PowerShell

Les règles de mise à jour des périphériques peuvent également être approuvées à l’aide de Windows PowerShell et de l’applet de commande **Approve-CsDeviceUpdateRule**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell.

> [!NOTE]  
> Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>.

## Pour approuver une seule règle de mise à jour des périphériques

  - La commande suivante approuve la règle de mise à jour des périphériques d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 détectée sur le serveur web atl-cs-001.litwareinc.com :
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

## Pour approuver plusieurs règles de mise à jour des périphériques

  - Cette commande approuve toutes les règles de mise à jour des périphériques pour les périphériques de marque Microsoft :
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Approve-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Approve-CsDeviceUpdateRule).

## Voir aussi

#### Tâches

[Importer des règles de mise à jour des périphériques](lync-server-2013-import-device-update-rules.md)  
[Restaurer une règle de mise à jour des périphériques](lync-server-2013-restore-a-device-update-rule.md)

