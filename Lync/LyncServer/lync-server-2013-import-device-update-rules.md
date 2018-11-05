---
title: Importer des règles de mise à jour des périphériques
TOCTitle: Importer des règles de mise à jour des périphériques
ms:assetid: 919e9c87-912b-4bc9-92e7-5998fc2e0bf0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994056(v=OCS.15)
ms:contentKeyID: 53095466
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Importer des règles de mise à jour des périphériques

 

_**Dernière rubrique modifiée :** 2013-02-23_

L’importation des règles de mise à jour s’effectue uniquement à l’aide de Windows PowerShell et de l’applet de commande **Import-CsDeviceUpdate**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell.

> [!NOTE]  
> Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>.


## Pour importer des règles de mise à jour des périphériques sur un seul serveur web

  - La commande suivante permet d’importer des règles de mise à jour des périphériques sur le serveur web server atl-cs-001.litwareinc.com :
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

## Pour importer des règles de mise à jour des périphériques sur tous vos serveurs web

  - Dans cet exemple, les règles de mise à jour des périphériques sont importées sur tous les serveurs web déployés dans votre organisation. Pour que cette commande fonctionne, il faut que le dossier \\\\atl-fs-001.litwareinc.com\\Updates soit partagé et accessible à tous les serveurs web.
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Import-CsDeviceUpdate](https://docs.microsoft.com/en-us/powershell/module/skype/Import-CsDeviceUpdate).

## Voir aussi

#### Tâches

[Afficher des informations sur les règles de mise à jour des périphériques](lync-server-2013-view-information-about-device-update-rules.md)  
[Approuver une règle de mise à jour des périphériques](lync-server-2013-approve-a-device-update-rule.md)

