---
title: Supprimer des fichiers journaux de mise à jour des périphériques
TOCTitle: Supprimer des fichiers journaux de mise à jour des périphériques
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994039(v=OCS.15)
ms:contentKeyID: 53095425
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Supprimer des fichiers journaux de mise à jour des périphériques

 

_**Dernière rubrique modifiée :** 2013-02-23_

Le service web de mise à jour des périphériques conserve une collection complète de fichiers journaux. Cette collection comprend des journaux d’audit effectués par le service lui-même et des fichiers journaux téléchargés depuis les périphériques clients. Pour que le serveur ne soit pas saturé de journaux de service liés au service web de mise à jour des périphériques, vous pouvez le vider des fichiers journaux présents depuis un certain nombre de jours. Définissez ce nombre de jours en fonction de l’activité de mise à jour et du nombre de périphériques clients dans votre organisation, à l’aide du Panneau de configuration Lync Server ou de Lync Server Management Shell.

## Pour nettoyer le journal de mise à jour des périphériques à l’aide du Panneau de configuration Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur **Configuration du fichier journal du périphérique**.

3.  Dans la page **Configuration du fichier journal du périphérique**, double-cliquez sur la configuration à modifier.

4.  Dans la boîte de dialogue **Modifier le paramètre du journal**, dans **Durée de conservation des fichiers journaux en jours (1 à 365)**, spécifiez un nombre de jours.

5.  Cliquez sur **Valider**. Tous les fichiers qui se trouvaient sur le serveur depuis un nombre de jours supérieur au nombre spécifié sont supprimés. Cette valeur s’appliquera à cette configuration jusqu’à ce que vous la modifiiez.

## Nettoyage du journal de mise à jour des périphériques à l’aide des applets de commande Windows PowerShell

Vous pouvez nettoyer les journaux de mise à jour des périphériques à l’aide de Windows PowerShell et de l’applet de commande **Clear-CsDeviceUpdateLog**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell.

> [!NOTE]  
> Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>.

## Pour nettoyer les journaux de mise à jour des périphériques sur un serveur

  - La commande suivante nettoie le journal de mise à jour des périphériques sur le serveur web atl-cs-001.litwareinc.com. Toutes les entrées de journal dont l’ancienneté dépasse 10 jours (valeur spécifiée par le paramètre DaysBack) sont supprimées du journal.
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

## Pour nettoyer tous les journaux de mise à jour des périphériques

  - Cette commande supprime les entrées obsolètes (dans cet exemple, les entrées dont l’ancienneté est supérieure à 10 jours) de tous les journaux de mise à jour des périphériques en cours d’utilisation dans votre organisation.
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/en-us/powershell/module/skype/Clear-CsDeviceUpdateLog).

