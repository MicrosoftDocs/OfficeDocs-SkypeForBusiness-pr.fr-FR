---
title: "Lync Server 2013 : aff. des param. de conf. de la mise à jour des dispositifs"
TOCTitle: Affichage des paramètres de configuration de la mise à jour des dispositifs
ms:assetid: aa6a70a9-bd77-4606-b797-ea6a3bab9cf2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994059(v=OCS.15)
ms:contentKeyID: 53095491
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affichage des paramètres de configuration de la mise à jour des dispositifs dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Vous pouvez afficher les paramètres de configuration du service de mise à jour des périphériques en utilisant Lync Server Management Shell et l’applet de commande **Get-CsDeviceUpdateConfiguration**, que vous pouvez exécuter à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell

> [!NOTE]  
> Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>.



  - 
    
    Pour afficher des informations sur tous les itinéraires des communications vocales, tapez la commande ci-dessous dans Lync Server Management Shell et appuyez sur Entrée :
    
        Get-CsDeviceUpdateConfiguration
    
    Cette commande renvoie le type d’information suivant :
    
        Identity               : Global
        ValidLogFileTypes      : {Watson, Config, Diaglog, CELog}
        ValidLogFileExtensions : {.dmp, .clg, .clg1, .clg2...}
        MaxLogFileSize         : 1024000
        MaxLogCacheLimit       : 512000
        LogCleanUpInterval     : 10.00:00:00
        LogFlushInterval       : 00:05:00
        LogCleanUpTimeOfDay    :

Pour plus d’informations sur cette applet de commande, reportez-vous à la rubrique d’aide sous [Get-CsDeviceUpdateConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsDeviceUpdateConfiguration).

